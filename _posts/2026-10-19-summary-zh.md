---
layout: default
title: "Horizon Summary: 2026-10-19 (ZH)"
date: 2026-10-19
lang: zh
---

> 从 35 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [vLLM v0.32.0 发布:默认启用结构化决策端点,扩展 NVFP4/FP8 KV 缓存支持](#item-tech-news-1) ⭐️ 8.0/10
2. [混合推理智能体 HybridAgent 开源：潜空间思考、文本行动](#item-tech-news-2) ⭐️ 8.0/10
3. [开源项目 RepRapMicron 力图将自复制 3D 打印推进到微米尺度](#item-tech-news-3) ⭐️ 7.0/10
4. [DeepSeek 推出搜索抓取 API：每千次成功请求 0.75 美元](#item-tech-news-4) ⭐️ 7.0/10
5. [TempoPFN:纯合成数据预训练的线性 RNN 实现零样本时间序列预测](#item-tech-news-5) ⭐️ 7.0/10
6. [Google 开源递归智能体框架 Harness²](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [外卖大战一年后：平台利润回升，商家与骑手却额外承压](#item-finance-news-1) ⭐️ 7.0/10
2. [美国 AI 基建热潮出现裂痕，巨额投资面临回报考验](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.32.0 发布:默认启用结构化决策端点,扩展 NVFP4/FP8 KV 缓存支持](https://github.com/vllm-project/vllm/releases/tag/v0.32.0) ⭐️ 8.0/10

vLLM 于 2026 年 10 月 18 日发布 v0.32.0,包含来自 363 位贡献者的 814 次提交\(其中 121 人首次参与\)。该版本默认启用新的结构化决策端点 POST /v1/systemone,可基于结构化状态回答 choice、noul、score 类问题,并已适配 Cloudflare/clef-omni、LiquidAI/d1-3B 与 DiffusionGemma;同时新增通用 hf 工具与推理解析器\(--tool-call-parser hf、--reasoning-parser hf\),直接读取检查点中的 response\_template,自带该字段的模型不再需要模型专用解析器,Python 与 Rust 前端均可用。低精度 KV 缓存覆盖面扩大:NVFP4 KV 缓存现已支持 SM8x、SM90、SM12x\(含 XQA 解码\)以及 SM100 上 MiniMax-M3 的稀疏注意力;GLM-5.x 在 SM100 上默认采用 FP8 KV 缓存,按对应 PR 的基准测试,每 rank 的 KV 内存减半、吞吐提升 2.3-5.5%,代价是 TTFT 增加 7-11%;SM90 上的 fp8\_ds\_mla 使 GLM-5.3-Flash 输出吞吐最高提升 31%,ROCm 则新增密度约为 FP8 两倍的 4 位 ultraquant\_4bit KV 缓存。升级时需留意破坏性变更:不再支持 Python 3.10,默认 CORS 策略不再放行所有来源,依赖约束收紧为 transformers&gt;=5.16.1,&lt;5.20.0 与 tokenizers&gt;=0.23.2,级联注意力\(cascade attention\)被移除,且 max\_tokens 不再从上下文窗口中预留。

github · khluu · 10月18日 06:50

**「背景」** vLLM 是一个被广泛使用的开源大语言模型推理与服务引擎，通常以 OpenAI 兼容 API 的形式对外提供服务，其版本迭代高度依赖社区贡献。在自回归推理中，KV 缓存的显存占用会随上下文长度和并发请求数增长，因此把缓存从常见的 16 位精度压缩到 FP8 或 4 位格式（如 NVIDIA 的 NVFP4），是推理引擎在显存受限时提升可容纳上下文与吞吐的常用手段；发布说明中的 SM8x、SM90 与 SM100/SM12x 分别对应 NVIDIA 的 Ampere、Hopper 和 Blackwell 架构世代。此外，从模型原始输出中提取工具调用和推理（reasoning）内容，此前通常需要针对每个模型单独实现解析器，这正是本次通用解析器改进所针对的问题。

**「升级兼容性与安全修复」** 对于在生产环境中运行 vLLM 的团队，升级到 v0.32.0 需要提前处理多项破坏性变更：Python 3.10 支持被移除，依赖被锁定为 transformers&gt;=5.16.1,&lt;5.20.0 和 tokenizers&gt;=0.23.2，cascade attention 等旧路径被删除，\`max\_tokens\` 不再从上下文窗口中预留，Responses API 的推理流事件也已改名，解析这些事件的客户端代码需要同步更新。默认 CORS 不再放行所有来源，依赖旧默认行为的部署必须显式配置允许的来源。该版本同时修复了三个已披露的安全公告（聊天模板资源耗尽、tokenizer \`max\_token\_id\`、P2P ZMQ 套接字耗尽）并将不可信图像限制为光栅格式，这为尽快升级提供了直接理由；建议升级前先核对 Python 版本、依赖锁定和 CORS 配置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aicoder.com/news/news-20261018-vllm-0-32-0-systemone-nvfp4-kv-mrv2">vLLM v0.32.0: 814 commits, built-in /v1/systemone structured ...</a></li>
<li><a href="https://e-acc.ai/items/d1ql9rmkyl5kuuhg7jmmkabck">vLLM v0.32.0 adds a structured-decision endpoint and low ...</a></li>

</ul>
</details>

**标签**: `#vllm`, `#llm-inference`, `#kv-cache`, `#quantization`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [混合推理智能体 HybridAgent 开源：潜空间思考、文本行动](https://arxiv.org/abs/2610.18861) ⭐️ 8.0/10

开源研究项目 HybridAgent 发布：一类混合推理 LLM 智能体，中间推理在模型的潜空间（连续向量）中进行，行动则通过文本完成，论文已发布于 arXiv（编号 2610.18861）。配套资源同步开放——代码位于 GitHub 的 togethercomputer/HybridAgent 仓库，模型权重与数据集发布在 Hugging Face 的 togethercomputer/hybridagent 集合，论文第 5 节附有评估结果，代码、权重与评估均已实际交付，而非仅有预告。对 AI 从业者而言，这意味着可以直接下载权重与代码进行复现和二次实验。

hackernews · allinonai · 10月18日 20:48 · [社区讨论](https://news.ycombinator.com/item?id=50145337)

**「背景：文本思维链与潜在推理的取舍」** 主流大语言模型的推理以文本思维链的形式进行：模型逐个生成可读的推理 token，过程便于人类检查，也容易接入需要文字输入的工具调用，但每个推理步骤都要解码成文字，会带来额外的生成开销。潜在推理（latent reasoning）是另一条研究路线，让模型直接在连续的隐藏状态空间中

**「对开发者的影响」** 这套开放权重已能被本地推理生态实际使用：第三方（bartowski）发布了 8-bit 量化版本，已有开发者在 llama.cpp 中运行 14B 模型。但已有公开实测提示可靠性风险——一位用户报告该模型在处理一个同类规模模型（如 Gemma 4 12B）可轻松完成的网页搜索与数据摘要请求时，在 llama.cpp 中反复循环同一段落约五分钟直至耗尽轮次预算，这位用户推测 llama.cpp 可能需要更新才能支持该模型。想在自有推理栈中试用的开发者应先小规模验证输出稳定性，并跟踪推理引擎对该架构的适配更新。

**「社区讨论」** 讨论以架构取舍为主：有用户提出，既然文本生成时已在承担潜空间模式的几乎全部算力成本，不如把 “Hybrid Link” 输出的潜向量与 token 嵌入一并传入、让潜空间推理与文本生成并行；也有人将其与同样在潜空间推理的 Astra 循环 transformer 架构比较，另有用户期待该方法用于 Qwen 3.8 27B，把其推理输出中大量的复述内容保留在潜空间。实测方面，一位用户报告在近期版本的 llama.cpp 中运行 14B 权重（bartowski 的 8-bit 量化）时，模型在一个对同规模模型（如 Gemma 4 12B）并不困难的简单网页搜索与数据汇总请求上，反复循环同一段落的变体约五分钟直至耗尽轮次预算，并推测可能是 llama.cpp 需要更新才能兼容该模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2610.18861">[2610.18861] Hybrid Reasoning Agents - arXiv.org</a></li>
<li><a href="https://arxiv.org/html/2610.18861v1">Hybrid Reasoning Agents - arXiv.org</a></li>
<li><a href="https://github.com/togethercomputer/HybridAgent">GitHub - togethercomputer/HybridAgent</a></li>

</ul>
</details>

**标签**: `#LLM agents`, `#latent reasoning`, `#machine learning research`, `#open source`, `#inference`

---

<a id="item-tech-news-3"></a>
### [开源项目 RepRapMicron 力图将自复制 3D 打印推进到微米尺度](https://github.com/VikOlliver/RepRapMicron/wiki) ⭐️ 7.0/10

RepRapMicron 是一个托管在 GitHub 上的开源项目,目标是把以自复制为理念的 RepRap 式 3D 打印从常规尺度推进到微米尺度。该项目目前仍处于早期阶段,公开资料主要是项目 wiki,尚无经过独立验证的成品或性能数据,微米级打印与自复制均属于项目愿景而非已交付的能力。这条消息在 Hacker News 上引发了较大关注,获得 329 分和 54 条评论,部分评论者将其与 18 世纪末精密制造技术起步的阶段相类比。

hackernews · RobotToaster · 10月18日 13:48 · [社区讨论](https://news.ycombinator.com/item?id=50141076)

**「从 RepRap 到微米尺度」** RepRapMicron 是 RepRap 项目的微米尺度延伸。RepRap 是一个开源自复制 3D 打印机项目，催生了桌面级 3D 打印，其在宏观尺度打印中积累的经验（如三轴定位系统）正是这一新项目所依赖的基础。RepRapMicron 采用 GPL 许可，目标是制造小至一微米或更小的结构，目前该项目已完成一个长度 0.650 毫米的微缩 3DBenchy 测试打印，打印耗时 13 小时。

**「对开发者的影响」** 对创客和硬件开发者而言，RepRapMicron 目前仅处于 wiki 与设计阶段，尚无经过验证的成品，短期内不会提供可用的微米级制造能力；部分评论者也指出其自我复制与芯片打印设想和实际成果之间仍有很大差距。现阶段确有微米级 3D 打印需求的团队仍需依赖成熟的商用双光子聚合（TPP）系统，例如基于 Nanoscribe 设备的研究已演示多种微尺度结构的制造，该技术可实现亚微米级特征，并已应用于光学、微流控等领域。开发者当前可行的做法是跟踪或参与这个 GitHub 上的早期开源项目，同时对其远期设想保持谨慎，而不应期待它很快替代现有微制造设备。

**「社区讨论」** 评论者 mikewarot 将该项目类比为 18 世纪 90 年代 Ramsden、Maudslay 和 Wilkinson 等人把刻度划分、螺纹切削等精密加工从手艺转变为可量产工艺的时期,samayashar 则期待廉价的芯片设计打印能为硬件领域带来转机。与此同时,godber 以“18 个月后就能自制内存”的调侃和 le-mark 对“打印出千分之一缩小版自身”是否可行的追问,显示出部分社区成员对项目愿景与实际成果之间的差距持保留态度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://makeprintable.com/reprap-micron-achieves-0-650mm-3dbenchy-print/">RepRap Micron Achieves 0.650mm 3DBenchy Print - makeprintable</a></li>
<li><a href="https://reprap.org/wiki/RepRapMicron">RepRapMicron - RepRap</a></li>
<li><a href="https://www.4additive.com/en/reprap-micron-3dbenchy-smallest/">RepRap Micron : the smallest 3DBenchy is 0.650 mm - 4Additive</a></li>
<li><a href="https://www.sciencedirect.com/science/article/pii/S2949822826018058">Two-photon polymerization: A versatile platform for 3D micro ...</a></li>
<li><a href="https://www.mdpi.com/2673-8023/1/2/13">Micro 3D Printing by Two-Photon Polymerization ... - MDPI</a></li>
<li><a href="https://www.nanoscribe.com/en/microfabrication-technologies/2pp-two-photon-polymerization/">Two-Photon Polymerization (2PP) 3D printing - Nanoscribe</a></li>

</ul>
</details>

**标签**: `#open-source-hardware`, `#3d-printing`, `#microfabrication`, `#self-replication`, `#hardware`

---

<a id="item-tech-news-4"></a>
### [DeepSeek 推出搜索抓取 API：每千次成功请求 0.75 美元](https://api-docs.deepseek.com/guides/search/) ⭐️ 7.0/10

DeepSeek 上线了搜索与抓取（search and fetch）API，定价为每 1000 次成功请求 0.75 美元，相关文档已发布在其官方 API 文档站点。该服务面向需要实时联网获取网页信息的 AI 智能体开发者。在 Hacker News 的讨论中，有人对比称 Brave Search API 的同类价格约为每 1000 次请求 5 美元、Kagi 约为 12 美元，DeepSeek 的报价明显更低。

hackernews · fagnerbrack · 10月18日 06:50 · [社区讨论](https://news.ycombinator.com/item?id=50138531)

**「背景：AI 代理与搜索 API」** 大语言模型无法自行获取训练截止之后的实时网页信息，因此构建 AI 代理的开发者通常需要接入 Brave、Kagi 等厂商提供的托管搜索 API，并按请求量付费。据《环球时报》报道，DeepSeek 是在发布速度更快、成本更低的新模型的同时宣布这一变化的：其 API 新增了 Search 和 Fetch 接口，以每 1000 次请求 5 元（约 0.75 美元）的价格向公众开放；官方定价文档则将两者描述为按每 1000 次成功请求 0.75 美元计费的独立 API。

**「对智能体开发者的成本影响」** 对于需要为 AI 智能体接入联网搜索的开发者，DeepSeek 每千次成功请求 0.75 美元的定价显著拉低了托管搜索的成本基准：第三方比价数据显示，Brave Search API 目前约为每千次查询 4–5 美元，Kagi Search API 约为 15–25 美元，DeepSeek 的单价仅相当于前者的约 1/5–1/7、后者的约 1/20–1/33。按此价格，1 万次成功请求的搜索开销约 7.5 美元，检索环节在智能体运行成本中的占比明显下降。正在为智能体选型搜索 API 的团队值得据此重新比价，并注意其仅对成功请求计费的口径。

**「社区讨论」** 评论者 thombles 给出的价格对比（Brave 约 5 美元、Kagi 约 12 美元每千次请求）凸显了 DeepSeek 的定价优势，而 mjmvisser 则认为这类托管搜索服务之所以存在，是因为 Google 拒绝提供付费搜索 API。另有工具作者 nikvdp 推荐自托管的 searxng-ai-kit 等免费方案，称对个人使用而言比任何付费搜索 API 都更划算。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.globaltimes.cn/page/202610/1372476.shtml">DeepSeek unveils faster, cheaper AI model, with... - Global Times</a></li>
<li><a href="https://api-docs.deepseek.com/quick_start/pricing/">Models &amp; Pricing | DeepSeek API Docs</a></li>
<li><a href="https://costbench.com/compare/brave-search-api-vs-kagi-search-api/">Brave Search API vs Kagi Search API Pricing (2026)</a></li>
<li><a href="https://costbench.com/software/ai-search-apis/brave-search-api/">Brave Search API Pricing 2026: Free-$30 per 1K queries</a></li>

</ul>
</details>

**标签**: `#deepseek`, `#search-api`, `#llm-agents`, `#pricing`, `#web-search`

---

<a id="item-tech-news-5"></a>
### [TempoPFN:纯合成数据预训练的线性 RNN 实现零样本时间序列预测](https://www.reddit.com/r/MachineLearning/comments/1x97v19/tempopfn_synthetic_pretraining_of_linear_rnns_for/) ⭐️ 7.0/10

NeurIPS 2026 接收的论文 TempoPFN 提出完全用合成数据预训练时间序列基础模型的方案:作者构建了一个合成时间序列生成器与增强库,并在其上训练基于 DeltaProduct 的线性 RNN,使模型无需真实训练数据即可进行零样本预测。代码已在 GitHub\(automl/TempoPFN\)开源,权重发布在 HuggingFace 的 AutoML-org 组织下,论文为 arXiv 编号 2510.25502,作者包括 Frank Hutter 所在 AutoML 团队的 Vladyslav Moroshan、Julien Siems、Arber Zela、Timur Carstensen 与 Frank Hutter。据发布者介绍,其合成数据生成器已被其他时间序列模型 Toto-2 和 TS-ICL 采用;不过这些复用情况与模型效果目前主要来自论文及发布方自述,属于单一研究成果,实际影响尚待第三方验证。

reddit · r/MachineLearning · /u/Yossarian\_1234 · 10月18日 16:43

**「背景」** 时间序列基础模型指在大规模序列数据上完成一次预训练后，即可对从未见过的序列直接进行零样本预测的模型，以往此类模型通常以真实世界的时间序列数据作为预训练语料。TempoPFN 所依托的合成预训练路线则完全不使用真实序列，模型仅由时间序列生成器与数据增强产生的合成数据来训练。在架构上，它基于线性 RNN：这类网络会将整段历史压缩进单个隐藏状态，因而能以恒定的开销支持流式推理。

**「实际影响」** 对从事时间序列预测的研究者和工程团队而言，这项工作表明完全基于合成数据预训练的模型（tool-3-3）在 GIFT-Eval 基准上已能达到与真实数据训练模型相当的水平（tool-3-2），且其合成数据生成方法已被 Toto 2.0 实际采用（tool-3-1）。可行的跟进方式是直接复用作者在 GitHub 和 HuggingFace 上开源的生成管线、代码与权重，将合成数据预训练整合进自己的零样本预测流程，从而省去收集和清洗真实时序数据集的工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2510.25502v3">TempoPFN : Synthetic Pre - training of Linear RNNs for Zero-shot...</a></li>
<li><a href="https://paperswithcode.co/paper/2510.25502">TempoPFN : Synthetic Pre - training of Linear ... | Papers with Code</a></li>
<li><a href="https://arxiv.org/html/2605.20119">Toto 2 .0: Time Series Forecasting Enters the Scaling Era</a></li>
<li><a href="https://openreview.net/pdf?id=Iqex1gfnvc">TempoPFN : Towards Synthetic Pre-training of Linear</a></li>
<li><a href="https://www.emergentmind.com/topics/tempopfn">TempoPFN : Univariate Zero-Shot Forecasting</a></li>

</ul>
</details>

**标签**: `#time-series-forecasting`, `#foundation-models`, `#synthetic-data`, `#linear-rnns`, `#zero-shot-learning`

---

<a id="item-tech-news-6"></a>
### [Google 开源递归智能体框架 Harness²](https://github.com/google-research/harness2) ⭐️ 7.0/10

Google Research has open-sourced Harness², an Apache-2.0 framework that boosts LLM agent performance via two-layer recursive optimization without weight tuning, reportedly gaining up to 11.5 points on agent benchmarks.

telegram · zaihuapd · 10月18日 11:24

**标签**: `#llm-agents`, `#open-source`, `#google-research`, `#agent-frameworks`, `#recursive-optimization`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [外卖大战一年后：平台利润回升，商家与骑手却额外承压](https://www.latepost.com/news/dj_detail?id=3762) ⭐️ 7.0/10

A year after China&\#x27;s food delivery subsidy war, platform profits have rebounded and combined daily orders rose ~50% to ~140 million, but the cost burden has shifted to merchants facing compressed margins and riders whose per-order pay has fallen.

telegram · zaihuapd · 10月18日 07:40

**标签**: `#food-delivery`, `#China-platform-economy`, `#Meituan`, `#Alibaba`, `#gig-economy`

---

<a id="item-finance-news-2"></a>
### [美国 AI 基建热潮出现裂痕，巨额投资面临回报考验](https://www.ft.com/content/9ea5a37d-15c9-4d5b-94d6-719048c9cd3c?syn-25a6b1a6=1) ⭐️ 7.0/10

Citing FT reporting, this item describes mounting financing costs, public opposition, and project cancellations \(47+ large data centers\) casting doubt on the multi-trillion-dollar US AI infrastructure boom, reflected in falling chip and AI-cloud stocks.

telegram · zaihuapd · 10月18日 08:52

**标签**: `#AI infrastructure`, `#data centers`, `#semiconductors`, `#capital expenditure`, `#market selloff`

---