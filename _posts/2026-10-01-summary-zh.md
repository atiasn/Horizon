---
layout: default
title: "Horizon Summary: 2026-10-01 (ZH)"
date: 2026-10-01
lang: zh
---

> 从 41 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [谷歌公布 Gemini 4 Argon：主打智能体能力，暂限早期测试者](#item-tech-news-1) ⭐️ 9.0/10
2. [EDG C++ 编译器前端开源上线 GitHub](#item-tech-news-2) ⭐️ 8.0/10
3. [32 位研究者发布现代 NLP 分词技术综述](#item-tech-news-3) ⭐️ 7.0/10
4. [CO₂Jump:免训练自校正采样器改善文图并行生成一致性](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek 开源华为升腾版核心 AI 基础组件](#item-tech-news-5) ⭐️ 7.0/10
6. [Cloudflare 宣布进军公共证书颁发机构，已申请四大根证书计划](#item-tech-news-6) ⭐️ 7.0/10
7. [Kimi K3 经 Baseten 接入 OpenAI Codex 企业结算通道](#item-tech-news-7) ⭐️ 7.0/10
8. [Reddit 将停用 RSS 订阅并逐步关闭公开 API](#item-tech-news-8) ⭐️ 7.0/10
9. [OpenAI 瓦解模型蒸馏攻击活动并归因于月之暗面相关人员](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [Kalshi 与 Polymarket 部分产品交易量遭“洗售交易”质疑](#item-finance-news-1) ⭐️ 7.0/10
2. [中国商务部警告：欧盟若限制中企，中方将坚决回应](#item-finance-news-2) ⭐️ 7.0/10
3. [中国据报为人形机器人企业 IPO 设三项新门槛 鲜有企业达标](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [谷歌公布 Gemini 4 Argon：主打智能体能力，暂限早期测试者](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/) ⭐️ 9.0/10

谷歌于 2026 年 9 月 30 日在官方博客公布新一代模型 Gemini 4 Argon。据公告描述，该模型的智能体可执行底层系统调试和大规模代码迁移等任务，官方并称 Argon 智能体正在 Google 内部将 C/C++ 代码库迁移到 Rust——这些均为厂商说法，目前尚无独立技术验证。Argon 现阶段仅向早期测试者开放，公告称将继续收集反馈并迭代防护机制（guardrails），之后才&quot;尽快&quot;向开发者、企业和消费者推出，未给出正式发布时间。该消息在 Hacker News 上引发大范围讨论（1021 分、683 条评论），社区另有一个标题为&quot;Gemini 4 Argon \(High\)：智能、性能与价格分析&quot;的讨论帖，但其具体测试数据未包含在本次提供的材料中。

hackernews · bradleyg223 · 9月30日 20:04 · [社区讨论](https://news.ycombinator.com/item?id=49913571)

**「背景」** Gemini 4 Argon 是 Alphabet 旗下 Gemini 系列前沿模型的最新一代，于 2026 年 9 月 30 日公布，定位为面向复杂软件工程、法律与金融专业工作及网络防御的前沿模型，支持 100 万 token 上下文以处理深度多步问题。此前 Gemini 系列已迭代多个版本并被开发者广泛用于编程等场景，而 Argon 本身目前仅向早期测试者开放，Google 表示将在根据反馈完善防护措施后尽快向开发者、企业和消费者推出。

**「开发者暂无法调用，可先按已公布规格评估」** 对开发者和企业用户而言，最直接的影响是现阶段无法实际使用该模型：谷歌在公告中表示，Argon 目前仅面向早期测试者开放，团队将根据反馈完善护栏后，再尽快向开发者、企业和消费者推出。已公布的定价与规格可作为正式开放前的评估依据：据 DataCamp 汇总，该模型发布定价为每百万 token 2/10 美元，输出上限提升至 100 万 token，并在 Vals Index 和 DeepSWE v1.1 基准上处于领先；有采用意向的团队可据此预先规划成本与上下文预算，但基准成绩仍需在自行接入后验证，不宜直接作为选型结论。

**「社区讨论」** 评论区的核心分歧在于竞争格局：一位评论者认为今年各实验室反复&quot;交替领先&quot;的现象反驳了 Dario Amodei 此前&quot;AI 领先者将持续集中、赢家通吃&quot;的论断，另一位则建议开发者保持模型与供应商可替换。也有人对 Argon 仅限早期测试者不满，讽刺谷歌&quot;坐实了发不出模型的名声&quot;；另有用户讲述了在较早的 Gemini 3.8 Flash 上观察到智能体自行调试 GPU 驱动并编写 C 兼容层的经历，但该说法属个人见闻，且涉及的是另一版本而非 Argon。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/">Introducing Gemini 4 Argon</a></li>
<li><a href="https://www.gptunnel.ru/en/blog/gemini-4-argon">Gemini 4 Argon : what Google &#x27;s new model changes · GPTunneL</a></li>
<li><a href="https://www.cnbc.com/2026/09/30/google-gemini-4-argon-ai.html">Google rolls out Gemini 4 Argon , its most advanced model</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/">Introducing Gemini 4 Argon - The Keyword</a></li>
<li><a href="https://www.datacamp.com/blog/gemini-4-argon">Gemini 4 Argon: Benchmarks, Pricing, and Access | DataCamp</a></li>

</ul>
</details>

**标签**: `#AI`, `#large-language-models`, `#Google Gemini`, `#machine learning`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [EDG C++ 编译器前端开源上线 GitHub](https://edgcpp.org/#transition) ⭐️ 8.0/10

Edison Design Group\(EDG\)长期授权给各编译器与工具厂商的 C++ 编译器前端已在 GitHub 上公开发布,仓库为 github.com/edgcpp/compiler,公告与文档位于 edgcpp.org。评论者列出的许可证为 Apache-2.0\(带 LLVM 例外\)。评论者 jabl 指出,公告未明说的是 EDG 公司正在逐步停业,并引用维基百科条目和 Herb Sutter 2025 年 11 月的 ISO C++ 会议行程报告作为依据,这可能是此次开源的原因,也意味着项目未来的维护存在不确定性。另有评论者观察到仓库保留了自 1990 年起的提交历史,完整记录了数十年的开发过程。

hackernews · iandinwoodie · 9月30日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=49913192)

**「背景」** Edison Design Group（EDG）是一家美国公司，专门开发编译器前端，产品覆盖 C++ 以及早期的 Java 和 Fortran，其前端长期被众多商业编译器与代码分析工具授权使用。该 C++ 前端在商业领域以支持广泛的编译器方言和其他特性著称；据社区评论，Visual C++ 的 IntelliSense 补全功能便采用了它。2026 年，这家约六人规模的公司宣布将逐步停业，本次在 GitHub 上以 Apache 2.0 许可证公开源码正是在这一背景下发生。

**「影响」** 对依赖该前端的工具链开发者和商业被授权方而言,代码公开意味着他们现在可以直接审查、复用其实现;但由于 EDG 公司据称正在停业,官方支持和商业授权渠道的存续存疑,相关依赖方\(如有评论称采用 EDG 前端做代码补全的产品\)需要评估是接手维护该代码库,还是为长远考虑迁移到其他前端方案。

**「社区讨论」** 评论中最受关注的观点来自 jabl,他认为公告回避了 EDG 公司正在停业这一背景,而这很可能是开源的直接原因\(属个人判断,公告本身未提及\)。此外,有评论者设想利用其源到源编译能力把 C++ 库转译为其他语言\(例如将 FLTK 转为 Free Pascal 供 Lazarus 的 LCL 使用\),也有人惊叹仓库中自 1990 年起的完整提交历史;这些均为个人设想或观察。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Edison_Design_Group">Edison Design Group - Wikipedia</a></li>
<li><a href="https://wpnews.pro/news/edg-c-front-end-open-source-what-breaks-what-doesnt">EDG C++ Front End Open Source : What Breaks, What...</a></li>
<li><a href="https://www.phoronix.com/news/EDG-CPP-Open-Sourced">EDG C/ C++ Front - End Open -Sourced - Phoronix</a></li>

</ul>
</details>

**标签**: `#C++`, `#compilers`, `#open-source`, `#language-tooling`, `#Edison-Design-Group`

---

<a id="item-tech-news-3"></a>
### [32 位研究者发布现代 NLP 分词技术综述](https://www.reddit.com/r/MachineLearning/comments/1wuccjf/tokenization_a_survey_for_modern_nlp_r/) ⭐️ 7.0/10

一个由 32 位分词研究者组成的团队在 r/MachineLearning 社区发布了一篇自称迄今最全面的现代 NLP 分词综述，称历时约 8 个月完成。该综述声称覆盖分词算法、评估方法、多语言性、编码方式与理论，并讨论可能的替代方案（如潜空间分词与视觉分词），以及受限生成、token 修复（token healing）和分词器安全等相邻主题。论文链接托管于 alphaXiv；上述覆盖范围、作者人数和完成时长均出自发帖者自述，现有材料无法独立核实，帖子下也没有可用评论来佐证社区反馈。

reddit · r/MachineLearning · /u/mcmcmcmcmcmcmcmcmc\_ · 9月30日 18:13

**「背景：分词与语言模型」** 分词（tokenization）是把原始文本切分为语言模型实际读入和生成的离散单元（token）的步骤，是语言建模流程中的基础环节。发帖人指出，这一领域尽管影响遍及整个 NLP，却长期缺乏系统研究；与此同时，研究者也在尝试以潜在分词、视觉分词等方案替代现有分词器，并关注受限生成、token 修复（token healing）与分词器安全等相邻议题，这些正是这份综述试图一并梳理的内容。

**「影响」** 对从事语言模型开发的工程师和 NLP 研究者而言，这篇综述将分散的分词知识（包括分词器安全风险、token 修复等少见主题）整合为单一参考文献，可作为设计或评估分词策略时的查阅材料；但其实际质量和准确性仍待同行检验，目前没有独立评估。

**标签**: `#tokenization`, `#NLP`, `#survey`, `#language-models`, `#tokenizer-security`

---

<a id="item-tech-news-4"></a>
### [CO₂Jump:免训练自校正采样器改善文图并行生成一致性](https://www.reddit.com/r/MachineLearning/comments/1wtyl5m/concurrent_image_understanding_and_generation/) ⭐️ 7.0/10

来自 Google、Google DeepMind 与石溪大学的研究团队在一篇 NeurIPS 2026 论文中提出 CO₂Jump,一种无需额外训练的自校正耦合马尔可夫跳过程采样器,针对并行生成文本与图像时二者不一致的问题\(例如模型文字描述的迷宫解法与实际画出的路径不符\)。该方法利用文本置信度与跨模态注意力引导图像更新,并允许低置信度 token 被重新掩码后再生成,使早期决策可在生成过程中被修正;每个去噪步骤只需一次模型前向传播,且采样器本身不要求额外训练,实验以同一任务微调模型对比不同采样方法。作者在图像编辑、迷宫求解和数织\(nonogram\)任务上评估,并发布了三个新数据集 JEdit-1M、JMaze-200K 和 JNono-200K,其中拼图基准要求文本答案与生成图像同时正确才计入联合准确率。据作者自述,在 8 至 512 个采样步数范围内,CO₂Jump 是其对比中唯一在编辑质量与文图对齐\(grounding\)上均随步数单调提升的采样器;这些结果目前仅来自作者在 Reddit 上的第一方帖子,内容有截断、缺少量化指标和外部验证,尚无社区讨论,研究者可关注项目页 coupled-jump.github.io 与论文原文核实细节。

reddit · r/MachineLearning · /u/Upstairs\_Theme2785 · 9月30日 07:28

**「背景」** 掩码扩散模型（Masked Diffusion Models, MDM）可以通过逐步去噪同时生成文本与图像，但该论文的 arXiv 版本（2026 年 7 月 14 日上线）指出，现有采样器要么将两种模态交错解码，要么让它们彼此独立更新，因而会出现模型文字描述的是正确迷宫解法、图像却画出另一条路径这类不一致。作为回应，论文提出了自校正耦合马尔可夫跳跃过程（SC-CMJP）这一通用框架，让两种模态在每个去噪步骤内主动交叉权衡各自的确定程度，CO2Jump 正是该框架下的具体采样器。

**「对联合多模态生成研究的实际影响」** 对于在统一多模态模型上研究或部署文本-图像联合生成的开发者，CO₂Jump 无需额外训练采样器、每个去噪步骤只消耗一次模型前向传播，因此可在已有任务微调模型上直接替换采样方法进行对比。作者还发布 JEdit-1M、JMaze-200K 与 JNono-200K 三个基准数据集（JNono-200K 含 20 万个合成数织谜题，且联合准确率要求文本答案与生成图像同时正确），可复用于文本-图像一致性评估；不过相关性能结论目前仅来自作者报告，采用前宜自行复现验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2607.13188">[2607.13188] Concurrent Image Understanding and Generation ...</a></li>
<li><a href="https://arxiv.org/html/2607.13188v1">Concurrent Image Understanding and Generation: Self ...</a></li>
<li><a href="https://www.emergentmind.com/topics/jnono-200k">JNono - 200 K : Multimodal Nonogram Benchmark</a></li>
<li><a href="https://huggingface.co/papers/2607.13188">Paper page - Concurrent Image Understanding and Generation...</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#generative-models`, `#multimodal-ai`, `#markov-jump-processes`, `#research-paper`

---

<a id="item-tech-news-5"></a>
### [DeepSeek 开源华为升腾版核心 AI 基础组件](https://mp.weixin.qq.com/s/X41mKH4Ds-VXUAnK6M8Eww) ⭐️ 7.0/10

DeepSeek 于 9 月 30 日开源了面向华为升腾平台的基础组件，包括 TileLang 高级语言编译工具、DeepGEMM Ascend、DeepEP Ascend、TileKernels、FlashMLA 和 DeepSelect，与该公司此前面向英伟达平台发布的组件相对应。DeepSeek 称这些组件在多项测试中性能已接近硬件上限，并正在与华为推进升腾 950 的 128 卡超节点方案。需要注意，&quot;接近硬件上限&quot;属于 DeepSeek 的自述性能说法，具体数字尚未经独立测试验证；本次消息也来自第三方转述渠道，而非官方仓库的直接记录。

telegram · zaihuapd · 9月30日 03:09

**「背景」** FlashMLA、DeepGEMM、DeepEP 等并非新项目，而是 DeepSeek 此前面向英伟达 GPU 平台陆续开源的基础设施组件：FlashMLA 是其优化的注意力内核库，用于支撑 DeepSeek 模型的推理，DeepGEMM 则以少量核心内核函数实现了与专家调优库相当乃至更优的矩阵计算性能，常被用作 GPU 内核优化的学习与工程资源。此次发布并非全新技术，而是将这套既有英伟达版组件逐一移植适配到华为升腾平台，与原版本一一对应。

**「对升腾部署方的影响」** 对在升腾硬件上部署或训练 DeepSeek 模型的团队而言，TileLang、DeepGEMM、DeepEP、FlashMLA 等核心基础设施现在有了官方开源的升腾适配版本，与其英伟达平台组件一一对应，有望减少自行移植和维护内核的工作量。此外，双方正共同推进基于升腾 950 的 128 卡超节点方案，并对计算与卡间通信进行深度优化，华为还称其最新的升腾 950 PR/DT 芯片在 DeepSeek V4 模型发布当日即完成适配。需注意的是，“性能接近硬件上限”为 DeepSeek 自述且暂无独立验证，且方案明显围绕最新一代升腾 950 展开，使用较早型号升腾卡的团队应在自有负载上实测性能并确认兼容性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/deepseek-ai/FlashMLA">GitHub - deepseek-ai/FlashMLA: FlashMLA: Efficient Multi-head ...</a></li>
<li><a href="https://github.com/deepseek-ai/DeepGEMM">GitHub - deepseek-ai/DeepGEMM: DeepGEMM: clean and efficient ...</a></li>
<li><a href="https://www.qbitai.com/2026/09/499263.html">DeepSeek官方开源升腾基础组件，与升腾共建高效易用的AI芯片软件生态</a></li>
<li><a href="https://pasqualepillitteri.it/en/news/19580/tilelang-deepseek-huawei-ascend-cuda">DeepSeek and Huawei release TileLang for Ascend chips, taking aim...</a></li>
<li><a href="https://www.scmp.com/tech/big-tech/article/3351349/huawei-deepseek-strengthen-chinas-ai-self-reliance-collaboration-v4-model">Huawei , DeepSeek strengthen China’s AI self-reliance with...</a></li>
<li><a href="https://www.geopolitechs.org/p/deepseek-builds-for-huawei-ascend">DeepSeek Builds for Huawei Ascend - Geopolitechs</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#Huawei-Ascend`, `#open-source`, `#AI-hardware`, `#ML-systems`

---

<a id="item-tech-news-6"></a>
### [Cloudflare 宣布进军公共证书颁发机构，已申请四大根证书计划](https://blog.cloudflare.com/cloudflare-certificate-authority/) ⭐️ 7.0/10

Cloudflare 宣布计划成为公共证书颁发机构（CA），已申请加入 Chrome、Apple、Microsoft 和 Mozilla 四大根证书计划，并与 GlobalSign 签署协议收购一个受广泛信任的根证书，以加快获得浏览器和操作系统信任。新的 CA 将优先支持 ACME 协议实现证书的自动签发与续期。目前该公司尚未开始签发任何证书，本次内容仍处于宣布阶段，能否进入各大根计划尚待审核结果。Cloudflare 还计划在 2027 年第一季度签发生产级默克尔树证书（MTC），面向后量子时代的网络安全。

telegram · zaihuapd · 9月30日 06:26

**「背景：公共 CA 的信任从何而来」** 公共 CA 签发的证书之所以能被浏览器和操作系统默认信任，是因为其根证书被纳入了 Chrome、Apple、Microsoft 和 Mozilla 等主要根证书计划，而新建根证书通常需要多年的公开签发记录才能通过这些计划的审核。为跳过这一漫长的信任积累过程，Cloudflare 采取了收购路径，签署协议获得 GlobalSign 一个自 2012 年起即受信任的根证书，使计划中的 CA 能够直接继承既有信任基础，而不必等待自有新根被逐家接纳。

**「影响」** 对网站运营者和安全团队而言，一旦该 CA 通过 Chrome、Apple、Microsoft 和 Mozilla 根证书计划的审核并开始签发证书，将新增一个以 ACME 优先的公共 TLS 证书来源，可直接对接现有的自动化签发与续期流程；不过 Cloudflare 目前尚未签发任何证书，相关团队应暂缓迁移计划，待其正式纳入根计划并签发证书后再评估接入，同时可跟踪计划于 2027 年一季度落地的默克尔树证书（MTC），以便评估后量子证书选项。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.verdict.co.uk/cloudflare-public-certificate-authority/">Cloudflare plans public CA for standard and post-quantum certificates</a></li>
<li><a href="https://ppc.land/cloudflare-targets-q1-2027-for-its-first-quantum-safe-web-certificates/">Cloudflare targets Q1 2027 for its first quantum-safe web certificates</a></li>
<li><a href="https://www.cloudflare.com/press/press-releases/2026/cloudflare-announces-public-certificate-authority-for-the-post-quantum-web/">Cloudflare Announces Public Certificate Authority for the ...</a></li>
<li><a href="https://www.helpnetsecurity.com/2026/09/30/cloudflare-certificate-authority-2027/">Post-quantum website certificates from Cloudflare are ...</a></li>

</ul>
</details>

**标签**: `#cloudflare`, `#certificate-authority`, `#tls`, `#web-pki`, `#post-quantum`

---

<a id="item-tech-news-7"></a>
### [Kimi K3 经 Baseten 接入 OpenAI Codex 企业结算通道](https://36kr.com/newsflashes/4005691489112198) ⭐️ 7.0/10

据 36 氪报道，美国 AI 基础设施公司 Baseten 宣布，企业用户可在 OpenAI 编程工具 Codex 中使用中国开源模型 Kimi K3，相关调用费用直接计入企业已有的 OpenAI 采购承诺额度，无需另行启动新增供应商的采购流程。报道称，这是中国开源模型首次进入 OpenAI 企业客户的主流付费结算体系。该消息目前仅来自单一简讯来源，未附 Baseten 或 OpenAI 的原始公告链接，“首次进入”的定位系报道说法，尚无法从现有材料独立核实。

telegram · zaihuapd · 9月30日 11:23

**「背景」** Kimi K3 是月之暗面（Moonshot AI）发布的 2.8 万亿参数开源权重多模态推理模型，第三方平台 OpenRouter 显示其定价为每百万输入 token 1.03 美元、每百万输出 token 9.043 美元。OpenAI Codex 是 OpenAI 面向企业客户的编程智能体工具，企业通常通过与 OpenAI 签订采购承诺额度来付费使用。Baseten 此前已宣布与 OpenAI 达成合作，通过 Codex 和 Responses API 原生托管开源模型，其推理运行于美国境内基础设施，并对所有提示词实行零数据留存（ZDR）以满足企业治理要求，这一合作正是本次接入得以实现的通道基础。

**「企业采购与选型影响」** 对已持有 OpenAI 企业采购承诺的组织而言，这一整合意味着可以在 Codex 中直接调用 Kimi K3，相关费用计入现有承诺额度，无需启动新的供应商采购流程；据 Baseten 的合作公告，除 Codex 内的原生集成外，企业还可通过 Responses API 使用其托管的开源模型。对负责开发工具选型的团队，现在可以在既有 Codex 环境中直接实测 Kimi K3 的能力与成本表现，而无需先完成新的供应商引入与审批。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.baseten.co/blog/baseten-openai-partnership/">Announcing our partnership with OpenAI</a></li>
<li><a href="https://openrouter.ai/moonshotai/kimi-k3">Kimi K 3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://www.baseten.co/blog/baseten-openai-partnership/">Announcing our partnership with OpenAI - baseten.co</a></li>
<li><a href="https://phemex.com/news/article/kimi-k3-becomes-first-chinese-model-in-openai-enterprise-billing-via-codex-integration-98316">Kimi K3 Joins OpenAI Codex: First Chinese Model in ... - Phemex</a></li>

</ul>
</details>

**标签**: `#OpenAI Codex`, `#Kimi K3`, `#enterprise AI procurement`, `#open-source models`, `#AI industry`

---

<a id="item-tech-news-8"></a>
### [Reddit 将停用 RSS 订阅并逐步关闭公开 API](https://techcrunch.com/2026/09/30/reddit-is-killing-rss-feeds-ending-public-api-access-because-of-ai-bots/) ⭐️ 7.0/10

据报道，Reddit 宣布将于 11 月 13 日停止 RSS 订阅支持，并计划在 2027 年 3 月前关闭公开 API 访问，给出的理由是这些渠道已被用于大规模抓取与自动化滥用，尤其是 AI 机器人。该变化影响依赖 RSS 和 API 的第三方应用、机器人开发者、版主工具以及开放数据使用者。Reddit 要求第三方应用和机器人开发者在 2027 年 1 月 12 日前完成注册，否则将失去 API 访问权限，并建议版主改用名为 Discord Relay 的替代方案。此消息来自 TechCrunch 报道的中文转载，部分细节（如 Discord Relay 替代方案的具体形态）尚无法依据现有材料独立核实。

telegram · zaihuapd · 10月1日 00:27

**「背景」** RSS 订阅与公开 API 长期以来是 Reddit 内容对外的两条开放通道：前者允许用户和工具无需登录即可跟踪版块更新，后者支撑了第三方客户端、机器人与版主管理工具。这并非 Reddit 首次收紧外部访问——2023 年该公司曾对 API 引入收费政策，导致 Apollo 等流行第三方应用停运。据 TechCrunch 报道，本轮新措施于 9 月 30 日在一个面向版主的频道中宣布，把这轮收紧进一步扩展到 RSS 与剩余的公开 API 接口。

**「对用户与开发者的具体影响」** 对普通 RSS 订阅者而言，2026 年 11 月 13 日 RSS 关闭后，官方仅为版主提供了迁移到 Discord Relay Devvit 应用的提醒方案，其他 RSS 使用场景没有替代品，习惯用 RSS 阅读器跟踪特定版块的用户需自行寻找替代工具。第三方应用与机器人开发者若想保留 API 访问权限，必须在 2027 年 1 月 12 日前完成注册为经批准的应用或机器人，否则将与公开 API 一同在 2027 年 3 月前失去访问资格。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/09/30/reddit-is-killing-rss-feeds-ending-public-api-access-because-of-ai-bots/">Reddit is killing RSS feeds and ending public API access ...</a></li>
<li><a href="https://sea.mashable.com/tech/55351/reddit-is-ending-rss-feeds-with-no-replacement-you-can-blame-ai-bots">Reddit is ending RSS feeds — with no replacement. You can ...</a></li>
<li><a href="https://mangodeveloper.com/articles/reddit-kills-rss-and-public-api-access-cites-ai-scraping-as-the-culprit">Reddit kills RSS and public API access, cites AI scraping as ...</a></li>
<li><a href="https://techbeat.co/story/reddit-ends-rss-feeds-and-public-api-as-ai-data-revenue-grows">Reddit Ends RSS Feeds and Public API as AI Data Revenue Grows</a></li>
<li><a href="https://aiweekly.co/alerts/reddit-ends-rss-nov-13-closes-public-api-by-march-2027">Reddit Ends RSS Nov 13, Closes Public API by March 2027</a></li>

</ul>
</details>

**标签**: `#Reddit`, `#API`, `#RSS`, `#AI bots`, `#developer ecosystem`

---

<a id="item-tech-news-9"></a>
### [OpenAI 瓦解模型蒸馏攻击活动并归因于月之暗面相关人员](https://openai.com/index/disrupting-a-coordinated-model-distillation-campaign/) ⭐️ 7.0/10

OpenAI 宣布已瓦解一起模型蒸馏攻击活动：攻击者通过操纵交互来提取其受保护的推理内容。据 OpenAI 说明，该活动最早出现于 2026 年 7 月初，7 月 24 至 25 日达到高峰，涉及 4000 多名用户的约 1.6 万次请求，7 月 28 日前已瓦解涉及 1.5 万余名用户的相关活动。OpenAI 将其中核心活动归因于与月之暗面（Kimi 开发商）有关的人员，并称已通过 Frontier Model Forum 等渠道与业界和政府共享信息。需要强调的是，上述归因目前仅来自 OpenAI 的单方面声明，本条消息源自 Telegram 渠道摘要，尚未见独立验证，月之暗面方面的回应在现有材料中亦未出现。

telegram · zaihuapd · 10月1日 01:18

**「什么是“对抗性蒸馏”」** 模型蒸馏指利用一家模型的输出或推理内容来帮助训练、复现或改进另一家模型，OpenAI 将这种系统性、未经授权的做法称为“对抗性蒸馏”。此类活动通常不涉及直接窃取模型权重，攻击者只需操纵正常的对话交互，即可批量套取思维链等本不直接对外公开的受保护推理内容。

**「影响」** 对开发者与依赖 API 的企业而言，最直接的后果是大规模自动化提取行为面临实质性处置：OpenAI 已在 7 月 28 日前对 1.5 万余名相关用户采取措施，并通过 Frontier Model Forum 与业界和政府共享情报，同类操作今后可能同时触发账户封禁与跨机构通报。不过该归因目前仍是 OpenAI 的单方面声明，此前蒸馏类指控（如 Anthropic 曾对月之暗面、DeepSeek 和 MiniMax 提出的指控）尚未形成闭环证据，且 Kimi K3 API 平台目前仍在正常提供服务，依赖方暂无立即更换技术栈的必要，但宜将该供应商风险纳入评估并关注后续独立核查结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.unite.ai/openai-disrupts-coordinated-model-reasoning-extraction-campaign/">OpenAI Disrupts Coordinated Model -Reasoning Extraction Campaign</a></li>
<li><a href="https://www.ic.work/article/kimi-k3-fable-distillation-claims-two-week-gap">Kimi K3遭 蒸 馏 指 控 ：两周时间窗不足以证明“复制Fable” - ic.work</a></li>
<li><a href="https://platform.kimi.ai/">Kimi API Platform</a></li>

</ul>
</details>

**标签**: `#AI安全`, `#模型蒸馏`, `#OpenAI`, `#月之暗面`, `#行业动态`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Kalshi 与 Polymarket 部分产品交易量遭“洗售交易”质疑](https://www.cnbc.com/2026/09/30/kalshi-polymarket-trading-volume-scrutiny.html) ⭐️ 7.0/10

CNBC 分析发现，Kalshi 的以太币永续合约（一种无到期日的期货产品）在 9 月 20 日有近一半美元成交额来自规模在 5,495 至 5,505 美元之间的交易，而 Polymarket 国际交易所上押注小概率事件的低赔率合约成交异常活跃，外界担忧部分交易量或被“洗售交易”（即交易者串通买卖、制造虚假活跃假象）夸大，两家公司均予以否认。《华尔街日报》报道称，美国商品期货交易委员会正在审查 Kalshi 的以太币永续合约交易（CNBC 未能独立核实）；与此同时，Polymarket 正以逾 200 亿美元估值融资，Kalshi 据报在洽谈 400 亿美元估值，两家公司据报均计划最早明年上市。

rss · CNBC Finance · 9月30日 21:09

**「背景」** 预测市场指供用户对选举、体育赛事等现实结果下注的交易所，其融资估值高度依赖交易量增长数据；此前哥伦比亚大学研究人员在 2025 年 11 月发布的报告曾估计，呈现洗售特征的交易一度占 Polymarket 国际交易所 2024 年 12 月周交易量的 60%，至 2026 年 4 月已降至可忽略水平。

**「潜在影响」** 德国乌尔姆大学金融学教授 Andre Guettler 在其工作论文中警告，若永续合约交易量中有实质性部分是“制造”出来的，交易量及其增长轨迹可能高估估值所依赖的真实交易需求，而作为预测市场交易所上市时天然买家的散户投资者受此影响最大。

**标签**: `#prediction markets`, `#Kalshi`, `#Polymarket`, `#wash trading`, `#CFTC scrutiny`

---

<a id="item-finance-news-2"></a>
### [中国商务部警告：欧盟若限制中企，中方将坚决回应](https://www.cnbc.com/2026/09/30/china-warns-europe-increases-trade-pressure.html) ⭐️ 7.0/10

中国商务部周二晚间表示，若欧盟在双方贸易谈判期间对中国企业或产品施加限制，中方将&quot;坚决回应&quot;，并称此类举动将严重损害互信、扰乱谈判。此前欧盟贸易专员谢夫乔维奇要求北京在 10 月前就缩小创纪录的欧盟对华贸易逆差拿出&quot;具体成果&quot;，否则将面临&quot;更严厉措施&quot;。

rss · CNBC Finance · 9月30日 03:39

**「背景」** 欧盟与中国自今年夏天起举行贸易谈判，欧盟将 10 月设为要求北京拿出&quot;切实成果&quot;的最后期限，否则威胁采取更严厉措施，欧盟贸易专员谢夫乔维奇此前已表示将访华。所谓&quot;301&quot;式工具，指借鉴美国依据其《301 条款》单边加征关税的做法；据中国海关数据，欧盟去年对华商品贸易逆差达 3600 亿欧元，为全球最大。

**「潜在影响」** 如果欧盟对中国企业或产品设限，中方警告的“坚决回应”可能以关税或市场准入限制的形式，冲击在中欧双向贸易中经营的企业——去年双方货物与服务贸易额合计约 8800 亿欧元（近 1 万亿美元）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.biggo.com/news/ef5288b0-393d-4bd3-9b62-f62a48cfe009">China Threatens Retaliation If EU Targets Its... — BigGo Finance</a></li>
<li><a href="https://www.euronews.com/my-europe/2026/06/29/eu-sets-october-deadline-to-get-tangible-results-with-china">EU sets October deadline to get &#x27;tangible&#x27; results with China | Eurone...</a></li>
<li><a href="https://www.cnbc.com/2026/09/30/china-warns-europe-increases-trade-pressure.html">Beijing warns of retaliation if Europe imposes curbs on Chinese ...</a></li>
<li><a href="https://en.topwar.ru/290739-pekin-prigrozil-es-otvetnymi-merami-v-sluchae-vvedenija-novyh-poshlin.html">Beijing has threatened the EU with retaliatory measures if new tariffs ...</a></li>

</ul>
</details>

**标签**: `#EU-China trade`, `#trade policy`, `#tariffs`, `#trade deficit`, `#retaliation threat`

---

<a id="item-finance-news-3"></a>
### [中国据报为人形机器人企业 IPO 设三项新门槛 鲜有企业达标](https://www.cnbc.com/2026/09/29/china-criteria-humanoid-robot-ipos.html) ⭐️ 7.0/10

据 CNBC 援引三位知情人士报道，中国证监会以&quot;窗口指导&quot;方式要求人形机器人初创企业上市须满足三项标准：拥有可持续营收和商业订单、亏损持续收窄（一位消息人士称需提供三年预测）、以及掌握机器人大脑等核心技术。在逾百家国内人形机器人企业中，仅香港一地已有至少二十余家递交上市申请，但据信鲜有乃至没有企业能达到新门槛；证监会与港交所均未置评。

rss · CNBC Finance · 9月30日 02:50

**「背景」** 所谓&quot;窗口指导&quot;，指监管机构以口头、非正式方式向市场传达审批意向；按现行制度，内地企业不论在境内还是赴香港上市，都需获得中国证监会的批准。此前，行业标杆企业宇树科技于 8 月 19 日在上海上市，募资约 61 亿元人民币（9.05 亿美元），首日股价飙升逾 460%收于 845 元，但截至周一已回落至 459.65 元、几乎减半，引发市场对整个人形机器人行业估值与盈利能力的质疑。

**「对拟上市企业与投资者的影响」** 仅在港股一地已有至少二十余家人形机器人相关企业递交上市申请，且内地企业赴港上市亦需证监会放行；若新门槛属实，这些难以满足可持续营收、亏损收窄或核心技术要求的初创公司及其早期投资者，其 IPO 进程与退出计划可能被推迟或搁浅。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.sedaily.com/international/2026/08/28/two-chinese-robot-startups-plan-hong-kong-ipos-despite">Two Chinese Robot Startups Plan Hong Kong IPOs Despite Unitree ...</a></li>
<li><a href="https://www.cnbc.com/2026/09/29/china-criteria-humanoid-robot-ipos.html">China&#x27;s criteria for humanoid robot IPOs may be hard to meet</a></li>

</ul>
</details>

**标签**: `#China regulation`, `#humanoid robots`, `#IPOs`, `#embodied AI`, `#AI bubble`

---