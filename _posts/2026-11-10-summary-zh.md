---
layout: default
title: "Horizon Summary: 2026-11-10 (ZH)"
date: 2026-11-10
lang: zh
---

> 从 44 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [LingBot-Touch：JEPA 式潜变量预测提升触觉预训练](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2，社区聚焦编程表现与基准质疑](#item-tech-news-2) ⭐️ 8.0/10
3. [谷歌发布 TPU 8tx 与 8i Max，面向代理式 AI 场景](#item-tech-news-3) ⭐️ 8.0/10
4. [e-means：声称用十分之一轮数超越 k-means 的聚类算法](#item-tech-news-4) ⭐️ 7.0/10
5. [Show HN：浏览器端计算任意地点一周卫星过境并关联真实影像](#item-tech-news-5) ⭐️ 7.0/10
6. [消费版 Gemini 连接应用可将个人 Drive 文件与邮件送交人工审核](#item-tech-news-6) ⭐️ 7.0/10
7. [Claude Fable 5.2 在 Artificial Analysis 得分 65，单任务成本翻倍](#item-tech-news-7) ⭐️ 7.0/10
8. [县级停电预测模型：提前 2 小时，PR-AUC 达 NWS 预警基线 2.4 倍](#item-tech-news-8) ⭐️ 7.0/10
9. [Using latent-agent swarms for math discovery and optimization \[R\]](#item-tech-news-9) ⭐️ 7.0/10
10. [字节发布 Seedream 5.5：支持百轮连续编辑与透明通道输出](#item-tech-news-10) ⭐️ 7.0/10
11. [OPPO、vivo、小米、荣耀联合上线 ADV 开发者身份验证机制](#item-tech-news-11) ⭐️ 7.0/10
12. [欧盟《数字公平法案》草案：限制成瘾性设计并标注游戏虚拟货币真实币值](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [英伟达董事会调查黄仁勋，预测市场认为其短期离任概率低](#item-finance-news-1) ⭐️ 8.0/10
2. [2026 年前三季度中国新能源乘用车出口增 138.8%，国内零售降 12.8%](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [LingBot-Touch：JEPA 式潜变量预测提升触觉预训练](https://www.reddit.com/r/MachineLearning/comments/1xs05uo/latent_prediction_beats_reconstruction_for/) ⭐️ 9.0/10

Robbyant 发布了 LingBot-Touch，一种自监督触觉编码器，采用 JEPA 式训练，即预测被掩码接触的潜表示而非重建原始传感器信号。论文在相同数据上与同规模 MAE 和 VAE 重建模型对比：1K 小时数据下触觉到视频的 top-5 召回率为 \*\*32.1%\*\*（JEPA）、\*\*5.6%\*\*（MAE）、\*\*4.4%\*\*（VAE）；4K 小时下 JEPA 达 \*\*49.3%\*\*，MAE 低于 \*\*9%\*\*，而 VAE 反而降至 \*\*3.1%\*\*。作者解释称，触觉片段大部分是接近零的背景，重建损失可以在未学到实际接触的情况下下降。推理代码和检查点已公开。

reddit · r/MachineLearning · /u/Zealousideal-War7154 · 11月9日 18:52

**「背景」** 触觉传感器信号稀疏，接触事件只占片段的一小部分，因此以重建原始信号为目标的 MAE、VAE 等自监督方法容易被大量近零背景主导。JEPA 式方法改为在潜空间预测被掩码部分，理论上能避开这一陷阱。该工作还统一了磁性、压阻和视触觉三类传感器：通过规范化的指尖坐标与 5D RoPE（时间、手指、3D 位置）输入同一个共享 Transformer。

**「影响」** 在两个设计细节上，论文报告了具体做法：掩码比例在 300 步内从 \*\*40% 升至 80%\*\*，因为一开始就用高掩码会遮住稀疏信号中的所有接触点并导致梯度爆炸；在 26 个真实机器人任务、4 种策略的 \*\*104\*\* 个策略与任务组合中，冻结编码器特征在 \*\*89\*\* 个组合中得分最高。在预训练中从未见过的磁性手上，LingBot-VLA 的成绩从 \*\*57.21 提升到 75.04\*\*。Tiny 模型约在 4K 小时趋于饱和，而 Small 模型继续提升。

**标签**: `#Tactile Sensing`, `#Self-supervised Learning`, `#Robotics`, `#Multimodal Learning`, `#Transformer`

---

<a id="item-tech-news-2"></a>
### [Anthropic 发布 Claude Fable 5.2 与 Mythos 5.2，社区聚焦编程表现与基准质疑](https://www.anthropic.com/claude-fable-and-mythos-5-2) ⭐️ 8.0/10

Anthropic 发布了 Claude Fable 5.2 和 Mythos 5.2 两款新模型，页面地址为 anthropic.com/claude-fable-and-mythos-5-2，消息在 Hacker News 上引发约 676 条评论的密集讨论。早期用户反馈集中在编程能力上：有使用者称 Fable 5.2 在半小时内耗尽了自己的 5 小时 token 配额，但报告了 7 个严重 bug（其真实性尚未核实）；也有团队声称 Fable 5.2 在约 60 万行 Fortran 代码库上把计算材料科学任务提速 36 倍，并表示将开源相关成果。这些均为个人或团队的首批印象，尚无独立验证，基准对比方法在评论中也受到明确质疑。

hackernews · lairv · 11月9日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=50429068)

**「背景」** Anthropic 此前已有的产品线是 Opus 与 Sonnet 系列，社区用户在评论中将其与此次发布的 Fable、Mythos 并列比较，指出这是首次 Anthropic 在多个模型之间实现了较为均衡的能力分布（postalcoder 提到 Opus 5.5 已足够强，因此不再有此前 Fable 5/5.1 与 Opus 4.8 之间的 FOMO 感）。据 Anthropic 发布的系统说明，Fable 5.2 与 Mythos 5.2 是同一新大型语言模型的两个配置：Fable 5.2 面向通用场景并带有额外安全防护，限制其在生物与网络安全等高风险两用领域的部分任务执行；Mythos 5.2 则为不同用途的配置。此次发布也是自 CEO Dario Amodei 呼吁放缓 AI 发展以来，Anthropic 首次推出前沿模型。

**「实际影响」** 对已在使用 Claude 系列的开发者而言，Anthropic 的发布材料称 Fable 5.2 与 Mythos 5.2 在几乎所有测试能力上均优于自家 Opus 5.5，并提供了 Advisor（由 Haiku、Sonnet 或 Opus 咨询其解决难题）与 Orchestrator（将简单任务委派给更小模型）两种角色，这意味着可在现有工作流中作为升级或调度层接入，但具体兼容性与迁移成本仍取决于各自集成方式。评论区反馈的实际使用代价值得注意：一位用户称用 Fable 5.2 做代码审查时，半小时内耗尽 5 小时的 token 预算，并报告发现 7 个疑似严重缺陷，说明高强度任务下的用量消耗可能显著高于常规使用。

**「社区讨论」** 多位评论者质疑 Anthropic 公布的基准方法：breakwaterlabs 追问为何把 Fable 以 xHigh 努力等级对比 Carbon 的 Med 档、为何 Carbon 的努力—智能曲线与现有基准相悖、为何主要定位为网络安全模型的 Carbon 被排除在唯一的网络安全基准对比之外，以及为何在 robodojo 上改用 Argon 而非 Carbon 做对照。实践层面，postalcoder 认为 Anthropic 各模型定位终于趋于均衡，Opus 5.5 已足够好，且需大幅提高提示词的目标难度才能让 Fable 5.2 与 Opus 5.5 拉开差距；prtmnth 则推测 5.2 的编号与保留 5.5 是为应对竞品的竞争策略，属个人猜测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf">Claude Fable 5.2 &amp; Claude Mythos 5.2 System Card</a></li>
<li><a href="https://www.cnbc.com/2026/11/09/anthropic-claude-fable-5-2-mythos-5-2.html">Anthropic releases Claude Fable 5.2 and Claude Mythos 5.2 ...</a></li>
<li><a href="https://officechai.com/ai/fable-5-2-benchmarks/">Anthropic Launches Fable 5.2 &amp; Mythos 5.2, Beats Gemini 4 ...</a></li>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-2">Introducing Claude Fable 5.2 and Claude Mythos 5.2 \ Anthropic</a></li>

</ul>
</details>

**标签**: `#artificial-intelligence`, `#anthropic`, `#language-models`, `#model-release`, `#benchmarks`

---

<a id="item-tech-news-3"></a>
### [谷歌发布 TPU 8tx 与 8i Max，面向代理式 AI 场景](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/) ⭐️ 8.0/10

谷歌宣布推出两款新的张量处理单元：TPU 8tx 和 TPU 8i Max，均面向代理式 AI（agentic AI）工作负载。据社区引用的报道，TPU 8tx 主要面向政府机构及受严格监管行业、用于处理安全机密数据，并将与 AMD 芯片协同工作；TPU 8i Max 则针对超长上下文窗口的 AI 应用，将两颗 TPU 芯片集成在同一封装内，以提供更强算力和更大内存容量。谷歌此举打破了以往约每两年推出一款新处理器的节奏，在同一周期内扩展 TPU 产品线。目前尚无独立基准数据或官方详细规格得到核实，具体的能效与价格信息也未在可用材料中给出。

hackernews · \_benx\_ · 11月9日 21:56 · [社区讨论](https://news.ycombinator.com/item?id=50432831)

**「背景」** 谷歌此前维持约每两年发布一款新 TPU 的节奏，而第八代 TPU 产品线在一年内已扩充至四款系统，此次 8tx 与 8i Max 即属于这一加速发布序列（tool-2-1、tool-2-3）。据 TrendForce 报道，8i Max 将 HBM 带宽提升一倍，以应对大上下文推理中的内存瓶颈（tool-2-3）；Data Center Knowledge 则指出，8tx 面向安全 AI 负载，8i Max 面向更高容量的大上下文企业推理场景（tool-2-2）。

**「影响」** 对潜在用户而言，目前最直接的制约是获取渠道：Google 尚未公布这两款芯片的开放售卖方式或具体价格，社区中已有开发者指出 Google Colab 上可用的最强 TPU 仍为 v6e-1，规模偏小，难以支撑严肃工作负载。此外，官方材料未给出每 token 功耗或每 token 成本，也未提供与英伟达同价位产品的对比数据，因此第三方在采购或迁移评估时暂无法量化性价比。

**「社区讨论」** 评论者关注的重点集中在缺少对比数据上：有用户直接追问每款芯片的每 token 功耗或每 token 成本，以及与英伟达同价位产品的对比。另有用户希望 Google Colab 能提供新一代 TPU，指出目前 Colab 上可用的最强型号仍是 v6e-1，对严肃工作而言规模过小。也有人提出疑问，为什么谷歌不直接对外销售这些芯片。此外，一位评论者推荐了谷歌关于 TPUSync 的文章，称其与 Strata 等面向 Qwen 系列模型的开源仓库做法类似。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cloud.google.com/blog/topics/ai-infrastructure/tpu-8tx-and-tpu-8i-max">Introducing TPU 8tx and TPU 8i Max | Google Cloud Blog</a></li>
<li><a href="https://www.datacenterknowledge.com/data-center-chips/google-adds-tpu-8tx-8i-max-for-enterprise-ai">Google Adds TPU 8tx, 8i Max for Enterprise AI</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/10/news-google-marks-first-ever-4-tpu-year-with-8tx-and-8i-max-as-8i-max-doubles-hbm-bandwidth-to-tackle-memory-wall/">[News] Google Marks First 4-TPU Year with 8tx and 8i Max, as ...</a></li>
<li><a href="https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/">Introducing TPU 8 tx and TPU 8 i Max</a></li>
<li><a href="https://habr.com/ru/companies/bothub/articles/1105552/">Google представила TPU 8 i Max и 8 tx — системы для... / Хабр</a></li>

</ul>
</details>

**标签**: `#tpu`, `#ai-infrastructure`, `#google`, `#hardware`, `#custom-silicon`

---

<a id="item-tech-news-4"></a>
### [e-means：声称用十分之一轮数超越 k-means 的聚类算法](https://e-means.github.io/) ⭐️ 7.0/10

e-means 是一个新提出的聚类算法，项目页面声称其在仅相当于 k-means 十分之一的迭代轮数（epochs）下即可取得更优的聚类效果。Hacker News 讨论中，多位实践者报告了具体收益：real\_faxenoff 称将其适配到自己的 IVF 索引（code-daemon 项目）后，在 GPU 上获得 \*\*146 倍\*\*加速；kingcauchy 表示在需要完全重建索引的批量构建场景（如分片拆分）中快 \*\*2.5 倍\*\*。但这些结果均为社区成员自述，方法本身尚缺乏外部独立验证，效果明显依赖具体用例。

hackernews · porridgeraisin · 11月9日 18:45 · [社区讨论](https://news.ycombinator.com/item?id=50429734)

**「背景」** k-means 是经典聚类算法，通过迭代地把每个数据点分配给最近的中心、再重新计算中心均值来划分数据，Lloyd 算法是其最常用的实现形式，但每次迭代都要完整遍历数据集。e-means 由 Meta FAIR 开发并开源，定位为 k-means 的现代稳健替代方案，主张在十分之一的 epoch 数下达到相当或更好的效果。

**「实际影响」** 对向量索引和聚类流水线而言，e-means 的收益集中在需要多次遍历大规模数据的批量重建场景——kingcauchy 指出，增量插入时的聚类只占 CPU 时间的一小部分，因此整体插入耗时变化不大，收益主要体现在重索引。jlhawn 尝试用类似方法替换 Lloyd 算法来优化球面上的等面积二十面体网格，结果明确表示在该用例中并不更好，说明采用前需先验证自身工作负载。

**「社区讨论」** 讨论中既有实测反馈也有理论追问：shiandow 认为这类算法通常可以等价地描述为期望最大化或模拟退火，并猜测该更新规则类似于带摩擦项的 EM，同时指出其将质心保持在凸包内的特性很重要。jdonaldson 表示自己会在密度感知的局部敏感哈希工作中试用该方法。总体来看，社区报告的支持效果集中于大规模批处理场景，而非通用替代方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://e-means.github.io/">Modern optimization and scaling laws for k - means clustering</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#clustering`, `#algorithms`, `#vector-search`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [Show HN：浏览器端计算任意地点一周卫星过境并关联真实影像](https://www.watched.earth/) ⭐️ 7.0/10

开发者 a585gupt 发布 Show HN 项目 watched.earth，用户输入任意地点后，可在浏览器中用 SGP4 对 CelesTrak 目录做轨道推演，约半秒内找出过去 7 天内所有过境卫星，并调取这些过境对应的真实 Sentinel-2、Landsat 与 NASA 影像。开发者表示，过境搜索在极点、对经线和极小扫幅等场景下与暴力算法比对未漏掉任何一次过境，约 1.7 万颗在轨目标全部由 GPU 绘制并逐帧求解开普勒方程。工具仅在存在真实影像时标记“watched”，且不存储用户位置，代码已在 GitHub 开源。

hackernews · a585gupt · 11月9日 17:51 · [社区讨论](https://news.ycombinator.com/item?id=50428907)

**「背景」** watched.earth 沿用的核心技术基础是 SGP4 轨道传播模型：它接收 CelesTrak 提供的两行元素（TLE）目录，据此计算卫星在任意时刻的位置。作者称所有约 1.7 万个在轨目标均在浏览器端实时求解开普勒方程并绘制，无需服务器参与。该工具把轨道计算与 Sentinel-2、Landsat 和 NASA 的实际成像记录关联起来，且仅在确实存在影像时才标记该地点「被拍摄过」。

**「实际影响」** 对需要查询特定地点卫星影像的用户来说，该工具把原本分散在 Copernicus 等平台的数据源整合成一次地点查询，但有评论者指出开发者提到的 Sentinel-2 时间戳与实际过境时刻常有 5 至 10 分钟偏差，因此影像与过境窗口的对应关系需要用户自行留意。

**「社区讨论」** 评论区反响热烈，多位用户称赞其视觉呈现与多数据源整合，一位从事地理空间工作的用户（sixtyj）认为能直接看到卫星拍摄的对应影像的站点很少见，另一位用户（wnissen）表示该工具比 Copernicus 更易用，适合规划背包旅行。也有用户（adonovan）在肯定完成度的同时提到，即便代码由 AI 生成，知道该提出什么需求本身也是不小的成就。

**标签**: `#satellite-imagery`, `#geospatial`, `#orbital-mechanics`, `#webgl-gpu-rendering`, `#open-source`

---

<a id="item-tech-news-6"></a>
### [消费版 Gemini 连接应用可将个人 Drive 文件与邮件送交人工审核](https://github.com/thisisme6598/gemini_files/) ⭐️ 7.0/10

一则发布在 GitHub 上的爆料指出，消费版 Gemini 的 Connected Apps（连接应用）功能可能将用户个人的 Google Drive 文件和 Gmail 邮件内容发送给人工审核人员查看。评论者强调，这一做法与 Workspace 版 Gemini 存在明确区别：Workspace Gemini 及面向企业/Workspace 的 Workspace Intelligence（RAG 功能）仍声明其数据不受人工审核约束。换言之，只有用户在使用消费版 Gemini 并主动授权 Gmail 等应用后，Gemini 才可能调用相应工具加载邮件或文件，而这些被加载的数据可能进入人工审阅流程。该说法来自社区披露和用户对 Google 政策的解读，Google 官方尚未在本条信息中给出回应。

hackernews · gf74918 · 11月9日 18:24 · [社区讨论](https://news.ycombinator.com/item?id=50429426)

**「背景」** Gemini 的 Connected Apps 功能允许用户授权 Gemini 访问 Gmail、Drive 等个人 Google 应用数据，以便 Gemini 代为读取和处理这些内容。Google 的 Gemini Apps 隐私中心说明，连接 Google 应用后数据会按相关政策保存和使用，
而 Workspace 版 Gemini 则在文档中强调用户和组织对数据拥有控制权。本次讨论的核心区别在于消费级 Gemini 与 Workspace 版 Gemini 对人工审核的不同政策。

**「影响」** 使用消费版 Gemini 并授权 Gmail 或 Drive 连接应用的用户，其邮件和文件内容可能进入人工审核流程。有报道称，Google 在 2026 年 10 月的政策修订改变了其 2023 年关于个人 Drive 和 Gmail 内容不会由人工审核的承诺，相关数据保留期最长可达三年，且即使用户删除数据也可能继续保留。对于在个人账号与工作账号间混用 Gemini 的用户，这意味着需要重新评估哪些连接应用应被授权，或改用明确声明不进行人工审核的 Workspace Gemini。

**「社区讨论」** 评论者 bri3d 指出问题范围仅限消费版 Gemini 加 Connected Apps，Workspace 产品线仍声称免于人工审核。多位用户报告了疑似印证的经历：rustyhancock 称 Gemini 的回答异常贴合其刚收到的邮件内容，却未说明读取了邮件；EMM\_386 与 hek2sch 则担忧 Google Photos 画像及含有 Gemini、NotebookLM 的数据同样可能被标记后用于模型改进或遭泄露。这些均为用户个人陈述与推测，未获官方证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.google.com/gemini/answer/13594961?hl=en">Gemini Apps Privacy Hub - Gemini Apps Help</a></li>
<li><a href="https://workspace.google.com/">Google Workspace : Secure Online Productivity &amp; Collaboration Tools</a></li>
<li><a href="https://aiweekly.co/alerts/google-gemini-routes-personal-drive-gmail-to-human-reviewers">Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>

</ul>
</details>

**标签**: `#privacy`, `#google-gemini`, `#data-governance`, `#human-annotation`, `#consumer-ai`

---

<a id="item-tech-news-7"></a>
### [Claude Fable 5.2 在 Artificial Analysis 得分 65，单任务成本翻倍](https://artificialanalysis.ai/models/claude-fable-5-2) ⭐️ 7.0/10

人工智能模型评测聚合站点 Artificial Analysis 显示，Claude Fable 5.2 在该平台评测中取得 \*\*65\*\* 分，为该平台迄今最高分。据 HN 讨论引用的数据，同一次评测中该模型的单任务成本较 Fable 5.1 翻倍：即使厂商已下调价格，单任务输出 token 量仍从 5.1 的 \*\*118k\*\*（46k 答案 / 71k 推理）增至 5.2 的 \*\*274k\*\*（81k 答案 / 192k 推理），推理 token 的激增是主要来源。上述分数与成本均来自 Artificial Analysis 单一汇总方，尚无其他独立评测或完整方法说明予以印证。

hackernews · theanonymousone · 11月9日 20:04 · [社区讨论](https://news.ycombinator.com/item?id=50431144)

**「背景」** Artificial Analysis 是一个聚合多个大语言模型评测结果并发布综合评分的第三方平台，本次引发讨论的 65 分即来自该平台对 Claude Fable 5.2 的打分。社区评论指出该平台接受 AI 实验室的资助，且未公开完整评测方法，因此这一数值的权威性存在争议。

**「影响」** 对于已按任务量付费调用该模型的团队，成本上升可能最直接：社区评论称任务成本在 Fable 5.1 基础上翻倍，单任务输出 token 从 118k 增至 274k，其中推理 token 从 71k 增至 192k，即使计入降价这一增量仍然存在。同时，评论指出 Artificial Analysis 由 AI 实验室付费且不公开完整方法，因此该 65 分能否转化为真实任务表现仍需其他基准验证。

**「社区讨论」** 评论者的关注点从分数转向成本与评测可信度。rgbrenner 与 schnitzelstoat 指出，在价格已下调的前提下单任务成本仍翻倍，相对有限的智能提升代价过高；oliwary 则认为该模型在“任务耗时—智能”的帕累托前沿上表现更好，响应速度上有实际改善。rodorgas 质疑 Artificial Analysis 由 AI 实验室付费支持且未公开完整方法，认为在等待其他基准之前该分数意义有限；brachkow 则对比称 DeepSeek-Flash 能力尚可，而 Anthropic 为小幅领先付出了约百倍价格。

**标签**: `#large-language-models`, `#benchmarks`, `#model-pricing`, `#AI-industry`, `#cost-analysis`

---

<a id="item-tech-news-8"></a>
### [县级停电预测模型：提前 2 小时，PR-AUC 达 NWS 预警基线 2.4 倍](https://www.reddit.com/r/MachineLearning/comments/1xs4hq8/forecasting_new_power_outages_per_county_hourly_2/) ⭐️ 7.0/10

一位 Reddit 用户发布了针对美国密苏里州和伊利诺伊州 216 个县的逐小时停电预测模型，预测目标为“从 2 小时后开始的 6 小时内，某县新出现停电的客户比例达到或超过 5%”的概率。模型使用 XGBoost，输入 HRRR 风暴相关数据（阵风、切变、CAPE、结冰等）、县级特征、当前停电情况及邻近县数据，以 2020–2024 年数据训练、2025 年数据测试。在 2025 年测试集上，模型 PR-AUC 为 0.094，而基于 NWS 预警与 SPC 第一日展望的基线为 0.039，比值约 2.4 倍（95% 区间 2.0–3.3 倍）；在相同预警量下捕获 30% 的新增停电，基线为 17%，精确率分别为 15% 与 11%。作者强调这是单作者案例研究，仅覆盖 216 个县，基线事件发生率仅 0.5% 的县-小时，因此精确率虽真实但偏低。

reddit · r/MachineLearning · /u/CarRepresentative843 · 11月9日 21:34

**「背景」** 该模型使用的高分辨率快速更新（HRRR）模式是一种细网格、频繁更新的中尺度数值预报，能比常规全球模式更精细地刻画对流风暴的演变。其对比基线则由两类业务产品构成：NWS 发布的灾害天气预警，以及 NOAA 风暴预测中心（SPC）的 Day 1 强对流展望，后者按龙卷、风和冰雹分别给出概率。这两类产品是当前停电风险沟通中使用最广的官方依据。

**「影响」** 该模型只预测“新增”停电，不把已在进行的停电计入命中，作者认为这比预测当前停电更有实际价值，但也使任务更难。早期迁移测试显示，仅在密苏里州和伊利诺伊州训练后，模型在爱荷华州、印第安纳州和密歇根州的合并数据上捕获 31% 对基线的 19%。模型自 11 月 1 日起上线，所有预测均被保存以供盲测，作者同时提供了代码与泄漏审计，便于他人复现和核验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://courses.ems.psu.edu/meteo361/l1_p5.html">The Rapid Refresh Model | METEO 361: Fundamentals of Mesoscale...</a></li>
<li><a href="https://theweatherguy.net/blog/strong-storms-tonight/">STRONG STORMS TONIGHT - Philadelphia Weekend Weather...</a></li>
<li><a href="https://daculaweather.com/4_spc_day1_outlook.php">Storm Prediction Center Day 1 Severe Weather Outlook</a></li>
<li><a href="https://spankthestorm.app/storm-tracker">Live Storm Tracker | Real-Time Hail &amp; Tornado... | Spank The Storm</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#weather-forecasting`, `#xgboost`, `#power-outages`, `#applied-ml`

---

<a id="item-tech-news-9"></a>
### [Using latent-agent swarms for math discovery and optimization \[R\]](https://www.reddit.com/r/MachineLearning/comments/1xrunu7/using_latentagent_swarms_for_math_discovery_and/) ⭐️ 7.0/10

A Reddit post describes SwarmEvolve, an open-source framework using swarms of latent-reasoning LLM agents to accelerate math discovery and optimization compared with existing AlphaEvolve-style implementations.

reddit · r/MachineLearning · /u/QileHQ · 11月9日 15:30

**标签**: `#LLM agents`, `#evolutionary optimization`, `#math discovery`, `#latent reasoning`, `#open source`

---

<a id="item-tech-news-10"></a>
### [字节发布 Seedream 5.5：支持百轮连续编辑与透明通道输出](https://seed.bytedance.com/zh/blog/%E7%94%9F%E6%88%90%E6%9B%B4%E7%9C%9F%E5%AE%9E-%E7%99%BE%E8%BD%AE%E7%BC%96%E8%BE%91%E6%9B%B4%E7%A8%B3%E5%AE%9A-seedream-5-5-%E5%8F%91%E5%B8%83) ⭐️ 7.0/10

字节跳动发布图像创作模型 Seedream 5.5，支持对同一作品进行最多 \*\*100 轮\*\*连续编辑，并可原生生成带透明通道的素材，同时提升了图像真实感与文字渲染能力。字节跳动称，在影视和办公场景的评测中，该模型的可用率达到上一版本的 \*\*两倍以上\*\*，但该数据为公司自行评测，尚无独立验证。模型正陆续上线即梦、豆包、豆包工作和火山方舟。

telegram · zaihuapd · 11月9日 08:34

**「背景」** Seedream 是字节跳动 Seed 团队的图像创作模型系列。上一代 Seedream 4.0 将图像生成与图像编辑整合进统一架构，可处理知识型生成与复杂推理等任务；而面向编辑的 Seedream v5.0 Pro（I2I）此前最多支持 10 张参考图。此次 5.5 版本将连续编辑轮次上限提升至 100 轮，并新增原生透明通道输出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.atlascloud.ai/models/bytedance/seedream-v5.0-pro/edit">Seedream v5.0 Pro Edit (I2I) API Image by BYTEDANCE ...</a></li>
<li><a href="https://seed.bytedance.com/en/seedream4_0">Seedream 4.0</a></li>

</ul>
</details>

**标签**: `#image-generation`, `#multimodal-ai`, `#bytedance`, `#model-release`, `#generative-ai`

---

<a id="item-tech-news-11"></a>
### [OPPO、vivo、小米、荣耀联合上线 ADV 开发者身份验证机制](https://mp.weixin.qq.com/s/ZiKBASSLzvsZ6WR2AUmFeg) ⭐️ 7.0/10

OPPO、vivo、小米、荣耀四家厂商在中国大陆上线 Android 侧载应用开发者身份验证机制（ADV），并支持各方验证结果互认，目的是在开发者与其应用之间建立可信关联，帮助用户识别应用来源。已在四家开放平台注册上架的 APP 会自动提交验证，开发者无需单独申请；未完成验证的应用在侧载安装时会弹出「未验证」提示，用户手动确认后方可继续安装。目前公开信息较为简短，尚未披露具体的推行时间表与执行细则。

telegram · zaihuapd · 11月9日 11:44

**「背景」** 谷歌此前已在全球范围推动 Android 开发者验证（Android Developer Verification），计划要求开发者通过注册后方可在认证设备上安装应用，并在部分市场先行试点。中国大陆因缺少 Google Play 与谷歌移动服务，应用分发主要依赖各厂商应用商店与侧载，因此 OPPO、vivo、小米、荣耀选择另行建立本地化的 ADV 机制，并通过验证结果互认避免开发者重复提交。

**「影响」** 对已在这四家开放平台注册上架的开发者而言，验证会自动完成，无需额外提交材料；但仅在官网或其他渠道分发、未在开放平台备案的应用，其侧载安装将触发「未验证」提示，用户须手动确认才能继续，可能增加安装摩擦与转化流失风险。开发者也需留意：目前互认范围限于 OPPO、vivo、小米、荣耀四家，其余厂商设备是否沿用同一提示机制在现有信息中尚不明确。

**标签**: `#Android`, `#Sideloading`, `#Developer Verification`, `#Mobile Security`, `#China Tech`

---

<a id="item-tech-news-12"></a>
### [欧盟《数字公平法案》草案：限制成瘾性设计并标注游戏虚拟货币真实币值](https://www.mlex.com/mlex/articles/2546584/digital-businesses-face-addictive-design-controls-under-draft-eu-consumer-law) ⭐️ 7.0/10

一份泄露的草案显示，欧盟《数字公平法案》拟限制数字产品的成瘾性设计与订阅陷阱，并强制游戏虚拟货币标明真实币值。草案要求企业允许用户关闭自动播放、连续使用奖励等诱导强迫或过度使用的功能；在线订阅须提供取消按钮、续费提醒和人工客服，且在免费试用转为付费订阅前取得用户明确同意；同时禁止面向未成年人的游戏付费抽奖、“付费获胜”机制和画像广告。欧盟委员会定于 11 月 11 日提交该法案，并同步改革消费者保护合作框架，违规企业最高可被处以全球营业额 6% 的罚款。两项提案仍需欧洲议会与欧盟各国政府同意才能生效。

telegram · zaihuapd · 11月9日 16:42

**「背景」** 欧盟现行的《不公平商业行为指令》（UCPD）等消费者保护规则制定于互联网早期，未对成瘾性交互设计、订阅陷阱和游戏内虚拟货币作出专门规定，因此欧盟委员会近年来推动对消费者保护框架进行针对性更新。此次泄露的《数字公平法案》草案与消费者保护合作框架改革同步推进，两项提案须经欧洲议会与欧盟各国政府同意方能生效。

**「影响」** 若草案按现有内容通过，面向欧盟用户的游戏与订阅类应用将需要调整变现与界面设计：虚拟货币须标注真实货币价值，面向未成年人的付费抽奖与「付费获胜」机制被禁，订阅流程须提供取消入口、续费提醒并事先取得明确同意。违规最高可罚全球营业额的 6%，这一比例高于许多企业现有的合规风险敞口，因此产品与合规团队可能需要在新规生效前重做付费点与用户留存机制。需注意该法案仍属泄露草案，须经欧洲议会与各成员国同意方能生效，具体条款与时间表存在变动可能。

**标签**: `#EU regulation`, `#consumer protection`, `#digital policy`, `#game monetization`, `#dark patterns`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达董事会调查黄仁勋，预测市场认为其短期离任概率低](https://www.cnbc.com/2026/11/09/jensen-huang-nvidia-exit-prediction-markets.html) ⭐️ 8.0/10

英伟达董事会正在调查首席执行官黄仁勋，起因是有关他遭“外国情报行动”针对的报道。据 CNBC 报道，预测市场 Kalshi 的交易者认为黄仁勋在 2027 年前离任的概率仅为\*\*17%\*\*，而英伟达股价在消息公布后的周一（11 月 9 日）下跌超过\*\*5%\*\*。

rss · CNBC Finance · 11月9日 18:46

**「背景」** 据《纽约时报》报道，美国情报官员称与黄仁勋有婚外情的女性为中国国家安全部间谍，黄仁勋已于周日承认这段婚外情。Kalshi 合约依据彭博社的信息进行结算，Polymarket 合约则依据公司或黄仁勋本人的官方声明结算。

**标签**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#national security`, `#prediction markets`

---

<a id="item-finance-news-2"></a>
### [2026 年前三季度中国新能源乘用车出口增 138.8%，国内零售降 12.8%](https://finance.sina.com.cn/tech/roll/2026-10-26/doc-iniwpfnc2438186.shtml) ⭐️ 7.0/10

2026 年前三季度，中国新能源乘用车出口 388.7 万辆，同比增长 138.8%；同期国内零售 775.8 万辆，同比下降 12.8%。

telegram · zaihuapd · 11月10日 02:56

**「背景」** 报道将国内需求走弱与购车补贴、购置税优惠调整以及去年同期销量基数较高等因素联系起来。

**「影响」** 出口增长成为车企销量增长的重要支撑，而国内市场方面，9 月新能源乘用车零售同比下降 16.7%，燃油车下降 43%。

**标签**: `#New Energy Vehicles`, `#China Auto Exports`, `#Automotive Industry`, `#Domestic Demand`, `#Economic Data`

---