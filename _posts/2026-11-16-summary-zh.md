---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 37 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [Sebastian Raschka 深入讲解现代大语言模型中的位置编码](#item-tech-news-1) ⭐️ 8.0/10
2. [Meta FAIR 与 NYU：MLLM 无需视觉编码器预训练，但必须有专属视觉参数](#item-tech-news-2) ⭐️ 8.0/10
3. [🦘 美团开源 LongCat-2.5 称其未使用英伟达 GPU 训练](#item-tech-news-3) ⭐️ 8.0/10
4. [阿里发布 Qwen4-Max：稀疏 MoE、2.4 万亿参数，成本降近 58%](#item-tech-news-4) ⭐️ 8.0/10
5. [微软 365 中断叠加加药系统缺陷致酒店 15 名客人氯气中毒](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [中国 10 月经济数据全面低于预期，消费与投资继续走弱](#item-finance-news-1) ⭐️ 8.0/10
2. [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](#item-finance-news-2) ⭐️ 7.0/10
3. [中美俄领导人拟于 11 月 19 日在深圳 APEC 场边举行首次三方会晤](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Sebastian Raschka 深入讲解现代大语言模型中的位置编码](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

机器学习研究者 Sebastian Raschka 发布了一篇深度文章，系统讲解现代大语言模型中位置嵌入（positional embeddings）的工作原理。文章源自 Hacker News 社区分享，获得 213 点支持和 27 条评论。这篇文章定位为面向工程师和研究者的技术详解，而非新产品或研究成果的发布。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** Transformer 中的自注意力机制本身不包含词元顺序信息，因此需要位置编码来告诉模型每个词元在序列中的位置。早期 GPT 类模型使用可学习的绝对位置嵌入，即直接为每个位置训练一个向量并加到词元嵌入上；而 Sebastian Raschka 在文中讲解的相对位置编码（尤其是 RoPE，旋转位置编码）则是后来主流 LLM 采用的方案，通过旋转向量的方式让注意力得分天然依赖词元之间的相对距离。

**「社区讨论」** 评论者 programjames 认为文章仅涵盖了位置嵌入的实现层面，要真正理解其本质需要掌握群表示理论——例如旋转位置编码（RoPE）可视为平移群的表示，群的结构性质决定了如何推导并参数化位置嵌入使其可学习。这一观点将讨论从工程实现引向了理论基础层面。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://archive.md/R5CbU">Understanding Positional Embeddings in Transformers: From...</a></li>

</ul>
</details>

**标签**: `#llms`, `#transformers`, `#positional-embeddings`, `#machine-learning`, `#deep-dive`

---

<a id="item-tech-news-2"></a>
### [Meta FAIR 与 NYU：MLLM 无需视觉编码器预训练，但必须有专属视觉参数](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR 与 NYU 的研究团队在相同数据、相同计算预算下从零训练了 200 多个多模态大语言模型，以逐一拆解标准视觉编码器所捆绑的三项设计选择。结果显示：编码器的独立预训练是可选的——在算力对齐时，用对比学习、自监督或字幕等四种目标预训练过的编码器，最多只能与从零训练的编码器打平，甚至将 MetaCLIP 预训练时间延长 6.5 倍虽提升 ImageNet 线性探测准确率（80.4%→84.4%），却不改善 VQA 表现；而视觉专属参数是必需的——无编码器模型在 0.6B 到 6.4B 各规模上均落后，需要约 3 倍算力才能追平。编码器位于 LLM 之前这一位置也是可选的：在前 8 层插入零初始化、仅供视觉 token 使用的&quot;in-fusion&quot;分支，性能与标准编码器相当，且首 token 延迟降低约 13%。主要实验基于 Qwen3-1.7B 和 4B 配置（含 0.4B 视觉参数），并在 16 个 Cambrian VQA 基准和 12 个语言基准上评测。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 目前各家实验室对多模态大模型（MLLM）是否需要视觉编码器做法不一：Gemma 4 12B 去掉了编码器，Kimi K3 从头训练编码器，而 Inkling 2 Small 又重新引入编码器。由于已发布模型在数据和算力上各不相同，且很少把编码器预训练的开销计入比较，这类发布差异无法说明哪一种设计选择真正有效。此前对编码器的讨论通常把三个选择捆绑在一起——单独预训练、仅供视觉 token 使用的参数、以及在 LLM 之前的位置——而这项研究正是将它们逐一拆开验证。

**「实际影响」** 对于多模态模型研发团队，这项受控消融实验为当前存在分歧的编码器设计路线（如 Gemma 4 12B 去掉编码器、Kimi K3 从零训练编码器、Inkling 2 Small 重新引入编码器）提供了可操作的结论：不必投入算力做编码器独立预训练，但必须为视觉 token 保留专属参数，例如可采用零初始化的 in-fusion 分支以同时降低首 token 延迟。需要注意的是，这些结论出自论文与作者博客，尚未经过独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/papers/date/2026-11-13">Daily Papers - Hugging Face</a></li>

</ul>
</details>

**标签**: `#multimodal-models`, `#vision-encoders`, `#ablation-study`, `#machine-learning-research`, `#MLLM-training`

---

<a id="item-tech-news-3"></a>
### [🦘 美团开源 LongCat-2.5 称其未使用英伟达 GPU 训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

据报道，美团以 MIT 许可证开源了 LongCat-2.5，这是一个面向智能体的大规模 MoE 模型，其声称仅使用华为升腾芯片进行训练，而不使用英伟达 GPU。

telegram · zaihuapd · 11月15日 11:08

**标签**: `#open-source-models`, `#LLM`, `#ai-hardware`, `#huawei-ascend`, `#agents`

---

<a id="item-tech-news-4"></a>
### [阿里发布 Qwen4-Max：稀疏 MoE、2.4 万亿参数，成本降近 58%](https://mp.weixin.qq.com/s/pJUt0xwD6H-WMyzd8TjZaQ) ⭐️ 8.0/10

阿里通义千问正式上线新一代旗舰模型 Qwen4-Max，采用全新稀疏 MoE 架构，总参数量达 2.4 万亿，原生支持视觉理解和百万 Token 长上下文。官方称其前端编程能力在 Code Arena 盲测中位居全球前列，但目前仅有这一项宣称，缺少独立评测数据。成本方面，单个任务平均费用从 26.58 元降至 11.16 元（降幅近 58%），Token 消耗减少近 50%，API 定价同步下调。团队透露后续将推出规模更小的 Qwen4 系列模型并公开模型权重，但开源时间表尚未公布。

telegram · zaihuapd · 11月16日 02:52

**「背景」** 通义千问（Qwen）是阿里巴巴的开源大模型系列，此前历代版本均以同时发布商用旗舰模型和开放权重的小模型为常见做法。本条新闻中的 Qwen4-Max 是该系列的最新旗舰：相比上代，其采用稀疏 MoE 架构（总参数 2.4 万亿），原生支持视觉理解和百万 Token 长上下文，并将单任务平均费用从 26.58 元降至 11.16 元。需要注意的是，公告中的性能描述（如 Code Arena 盲测排名靠前）来自官方宣传，尚无独立基准测试佐证。

**「对开发者的影响」** Qwen4-Max 已在阿里云上线 API，开发者可直接调用该旗舰模型，其百万 Token 上下文与原生视觉输入适用于长文档处理和图像/视频理解类任务。单任务平均费用从 26.58 元降至 11.16 元、Token 消耗减少近 50%，有助于降低长程任务和代理式工作流的成本。此外团队承诺开源规模更小的 Qwen4 系列并公开模型权重，有本地部署需求的开发者可等待小模型发布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://qwen.ai/blog?id=qwen4-max">Qwen4-Max: Your New Teammate Has Arrived</a></li>
<li><a href="https://aicoder.com/news/news-20261116-alibaba-qwen4-max-official-launch-api-live-qwencloud-1-5-4-5-per-m-tokens">Alibaba Officially Launches Qwen4-Max: New MoE Architecture ...</a></li>
<li><a href="https://technode.com/2026/11/11/alibaba-opens-qwen4-max-preview-with-a-million-token-context-window/">Alibaba opens Qwen4-Max preview with a million-token context ...</a></li>

</ul>
</details>

**标签**: `#large-language-models`, `#mixture-of-experts`, `#alibaba-qwen`, `#model-release`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [微软 365 中断叠加加药系统缺陷致酒店 15 名客人氯气中毒](https://www1.wdr.de/nrw/rheinland/rhein-erft-kreis/technischer-defekt-chlor-phantasialand-100.html) ⭐️ 7.0/10

据德国 WDR 报道，一家酒店发生氯气中毒事件，15 名客人受影响，其中 13 人主诉呼吸道刺激、4 人送医（1 人中度受伤），伤者大多当天出院。事故是双重故障叠加：加药系统本身存在缺陷导致投氯过量，而通过 Microsoft 365 邮件转发的氯含量监控告警恰逢微软云服务中断而未能送达。文章指出，在德语原始报道的表述中，这是一次监控与加药两个独立系统的复合失效，而非单纯由云服务中断造成。

hackernews · DeepLogin · 11月15日 18:36 · [社区讨论](https://news.ycombinator.com/item?id=50509411)

**「背景」** 此类氯气监测系统依赖于加氯 dose（加药）装置与报警通知链路的协同工作：一旦加药系统故障导致氯投放过量，监测和告警环节必须及时通知运营人员介入。评论者引述的报道细节显示，此次事件是双重故障叠加——酒店的加药装置本身存在缺陷导致投氯过量，同时经 Microsoft 365 邮件发送的监测告警在云服务中断期间未能送达，两层防护同时失效才造成 13 名（后增至 15 名）宾客呼吸道受刺激、其中 4 人送医。因此事件的核心争议在于安全关键系统是否应依赖单一云服务作为告警通道。

**「实际影响」** 对于使用联网告警的安全监测系统的运营方，这一事件表明仅依赖单一云服务（如 Microsoft 365 邮件）作为危险状况告警通道存在单点故障风险；应配置本地声光报警或独立冗余链路，并确保有人在自动化失效时兜底。

**「社区讨论」** 多数评论认为责任主要在酒店的安全设计而非微软：闭式加氯系统容易以“测得氯含量偏低”的方式失效并过量投放，因此必须有真人值守或完全独立的传感/告警设计作为兜底。也有评论者（Havoc）翻译并整理了德语原文细节，指出原标题把双重失效渲染成了单一云服务事故。

**标签**: `#cloud-outage`, `#safety-critical-systems`, `#incident-report`, `#microsoft-365`, `#failure-analysis`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中国 10 月经济数据全面低于预期，消费与投资继续走弱](https://www.cnbc.com/2026/11/16/china-retail-sales-october-industrial-output-investment.html) ⭐️ 8.0/10

中国 10 月社会消费品零售总额同比增长 0.4%，低于分析师预期的 0.8%；规模以上工业增加值增长 4.8%，也低于预期的 5.3%；前 10 个月固定资产投资同比下降 8.1%，降幅远超预期的 7%，显示经济放缓加剧。

rss · CNBC Finance · 11月16日 02:52

**「背景」** 房地产市场连续第五年下滑侵蚀居民财富，导致消费持续疲软，三季度经济增长 4.5%仍处于低位，分析机构高盛预计今年全年增速将从 2025 年的 5%放缓至 4.6%。

**「影响」** 由于内需疲弱，增长日益依赖 AI 相关设备出口推动的贸易顺差（10 月已突破 1 万亿美元，创同期最快纪录），分析师警告若全球 AI 资本开支回落或欧盟加码贸易限制，中国出口及整体增长将面临下行风险。

**标签**: `#China economy`, `#industrial output`, `#retail sales`, `#fixed-asset investment`, `#trade surplus`

---

<a id="item-finance-news-2"></a>
### [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Cantor Fitzgerald, led by Commerce Secretary Howard Lutnick&\#x27;s sons, sharply reduced its Nvidia stake and maintained financing ties to the chipmaker while Lutnick resisted a crackdown on firms suspected of smuggling Nvidia chips to China, raising ethics questions.

rss · CNBC Finance · 11月15日 19:58

**标签**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#conflict of interest`

---

<a id="item-finance-news-3"></a>
### [中美俄领导人拟于 11 月 19 日在深圳 APEC 场边举行首次三方会晤](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 7.0/10

据中国外交部发言人和美联社报道，中美俄三国领导人计划于 11 月 19 日在深圳 APEC 峰会场边举行三方会晤，媒体称这将是三国领导人首次专门举行此类会晤。

telegram · zaihuapd · 11月16日 01:38

**「背景」** 亚太经合组织（APEC）领导人非正式会议于 11 月 18 日至 19 日在中国深圳举行，这是了解本次会晤的场合背景；据《华尔街日报》报道，三方会晤的形式由普京在 10 月 9 日与特朗普通话时提出。

**「影响」** 三方会晤若成行，可能成为观察中美俄在贸易与地缘政治议题上互动的重要信号，但目前仅为计划，具体议程和成果尚未公布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bbc.com/zhongwen/articles/cwe85djzkkv5o/simp">APEC ... - BBC News 中 文</a></li>
<li><a href="https://www.dw.com/zh/%E6%B7%B1%E5%9C%B3apec%E5%89%8D%E5%A4%95-%E7%BE%8E%E5%9B%BD%E5%82%AC%E4%B8%AD%E5%9B%BD%E5%85%91%E7%8E%B0%E7%A8%80%E5%9C%9F%E6%89%BF%E8%AF%BA/a-79884476">美 促 中 国落实釜山协议 中 美 俄 三 方 会 晤 各怀心思</a></li>

</ul>
</details>

**标签**: `#中美关系`, `#APEC峰会`, `#地缘政治`, `#外交政策`

---