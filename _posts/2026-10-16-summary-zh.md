---
layout: default
title: "Horizon Summary: 2026-10-16 (ZH)"
date: 2026-10-16
lang: zh
---

> 从 46 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [AdFection: Targeted ads turned into a pipeline for zero-click mercenary spyware](#item-tech-news-1) ⭐️ 9.0/10
2. [Meta 发布开放权重模型 Muse Spark Open 816B](#item-tech-news-2) ⭐️ 8.0/10
3. [Goodfire 提出“神经网络是干净的”可解释性主张引发争议](#item-tech-news-3) ⭐️ 7.0/10
4. [Libreboot 26.10 发布：集成 UEFI 并支持 233 款 Chromebook](#item-tech-news-4) ⭐️ 7.0/10
5. [Anthropic 向投资者披露第三季度营收 168 亿美元，环比增长近 50%](#item-tech-news-5) ⭐️ 7.0/10
6. [PNAS 研究：神经元单元凭共享局部规则自组装出可与反向传播媲美的学习电路](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [中国表态：无论中美贸易休战是否延续，稀土将继续输欧](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [AdFection: Targeted ads turned into a pipeline for zero-click mercenary spyware](https://citizenlab.ca/research/how-discover-tech-turned-targeted-ads-into-a-pipeline-for-spyware/) ⭐️ 9.0/10

Citizen Lab reports that targeted advertising infrastructure was exploited as a delivery channel for zero-click mercenary spyware, raising serious concerns about ad-tech security and the commercial spyware ecosystem.

hackernews · jcomp · 10月15日 10:43 · [社区讨论](https://news.ycombinator.com/item?id=50101813)

**标签**: `#security`, `#spyware`, `#adtech`, `#surveillance`, `#mobile`

---

<a id="item-tech-news-2"></a>
### [Meta 发布开放权重模型 Muse Spark Open 816B](https://research.meta.ai/blog/muse-spark-open) ⭐️ 8.0/10

Meta 发布了开放权重的大语言模型 Muse Spark Open（Hugging Face 列名为 Muse-Spark-Open-816B-A42B，即 816B 总参数、激活约 42B 的 MoE 模型），并强调其可在 Mac Studio 上运行、兼容从 Unsloth 到 MLX 等多种推理框架。模型权重已在 Hugging Face 上提供。社区讨论指出，第三方评测显示其表现落后于 Qwen3.8 Flash Next 和 GLM 5.3 Flash 等竞品。许可方面，模型可自由使用，但限制以“模型即服务”方式向第三方提供输出、且总收入超过 2000 万美元的商用场景。

hackernews · bigwheels · 10月15日 17:47 · [社区讨论](https://news.ycombinator.com/item?id=50107379)

**「背景」** Muse Spark Open 是 Meta 以开放权重形式发布的超大参数模型，总参数量 816B、每次推理激活约 42B（命名中的 A42B 即源于此），具备 100 万 token 上下文窗口，原生支持多模态，主打编程与智能体（agentic）场景，并针对开放版本做了额外的安全后训练。模型以 Muse Model License 授权发布：一般使用免费，但若被许可方或其关联公司以“模型即服务”方式向第三方提供输出、且合计年收入超过 2000 万美元，则需另行签署协议。据第三方报道，该模型可用两台 Mac Studio 在桌面端完整运行，Meta 也投入了大量工作使其兼容从 Unsloth 到 MLX 的多种推理运行器。

**「影响」** 个人和小型团队可以直接下载权重并部署该模型，Meta 为其提供了覆盖多种主流推理工具的部署文档；但年收入超过 2000 万美元的公司若想通过 API 形式对外提供基于该模型的服务，需要先评估许可中的 MaaS 条款是否符合自身业务。此外，用户在实际采用前应参考与 Qwen3.8、GLM 5.3 等竞品的实测对比。

**「社区讨论」**  Hacker News 上有评论者援引 Artificial Analysis 的数据认为该模型不如 Qwen3.8 Flash Next 和 GLM 5.3 Flash，认为 Meta 在开放权重领域“还需要追赶”，同时抱怨评测方只在最高推理档位提供对比数据；另有评论者考证了许可证条款，指出其并非完全开放，超过 2000 万美元收入的公司不得以 API 方式向第三方出售模型能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/meta-models/Muse-Spark-Open-816B-A42B">meta-models/Muse-Spark-Open-816B-A42B · Hugging Face</a></li>
<li><a href="https://www.unite.ai/metas-816b-parameter-muse-spark-open-weights-are-now-public/">Meta’s 816B-Parameter Muse Spark Open Weights Are Now Public</a></li>

</ul>
</details>

**标签**: `#open-weights`, `#large-language-models`, `#meta`, `#model-licensing`, `#model-benchmarks`

---

<a id="item-tech-news-3"></a>
### [Goodfire 提出“神经网络是干净的”可解释性主张引发争议](https://already-clean.goodfire.com/) ⭐️ 7.0/10

Goodfire 相关的研究者（经 Nick Cammarata 在 X 上发布）提出一项机制可解释性主张：神经网络中的神经元实际上承担简单、可解释的角色，而非普遍存在的多义性（polysemanticity）——即以往被解读为同时编码“猫”和“汽车”等混杂概念的神经元，可能只是其“概念”划分方式有误，例如可以更简洁地理解为“V 形神经元”响应。该主张以一份大规模证据简报的形式呈现，重新审视了此前著名的“混乱神经元”案例，并梳理了多义性在当前工具下如何在网络中呈现。需要注意，这更接近一个被推广的、尚存争议的论证，而非已被独立验证的定论。

hackernews · themgt · 10月15日 16:04 · [社区讨论](https://news.ycombinator.com/item?id=50105647)

**「背景」** 长期以来，机制可解释性研究者普遍认为神经元具有&quot;多义性&quot;（polysemanticity）——即单个神经元会混杂多种概念——主要归因于&quot;叠加态&quot;（superposition）假说，即网络把远多于神经元数量的特征压缩编码进有限参数中。Goodfire 的研究（由联合早期 OpenAI 机制可解释性工作的 Nick Cammarata 发布）挑战了这一解释，主张早期模型中神经元显得混乱其实是若干普通且可修复的问题所致，并称 Qwen3-32B 约 90% 的神经元极点各有一个主要功能。这一主张与社区长期引用的现象（如彩票假说所体现的渐进式特征复杂化、压缩表示倾向）存在张力，因此引发了关于其是否超出实际证明范围的技术争论。

**「影响」** 对于可解释性与 AI 安全研究者而言，如果该主张成立，理解模型内部结构的难度可能显著降低，正如评论者所形容的“给 AI 测序基因组”；但在主张被独立复现之前，依赖神经元角色简单这一假设的可解释性方法仍需谨慎对待。

**「社区讨论」** Hacker News 上的讨论（501 分、195 条评论）围绕该主张是否被夸大展开：有评论者认为这是对已被证明内容的过度延伸，指出早期训练结构与渐进特征复杂度早已为人所知，且与参数过载并不互斥，并援引相关工作（如 Multimodal Gap 研究）认为网络倾向于压缩表示；另一些评论者则持更积极态度，认为这是一种重新审视既有工具失败与“混乱神经元”案例的证据汇编。这些均属社区观点，该主张本身尚未获得独立确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.explainx.ai/blog/goodfire-neural-networks-are-already-clean-cammarata-neurons-interpretable-90-percent-qwen3-32b-2026">Goodfire: Neural Networks Are Already Clean, Claim Checked ...</a></li>
<li><a href="https://www.goodfire.com/research/already-clean">Neural Networks Are Already Clean - Goodfire</a></li>

</ul>
</details>

**标签**: `#mechanistic-interpretability`, `#neural-networks`, `#AI-safety`, `#machine-learning`, `#interpretability-debate`

---

<a id="item-tech-news-4"></a>
### [Libreboot 26.10 发布：集成 UEFI 并支持 233 款 Chromebook](https://libreboot.org/news/libreboot2610.html) ⭐️ 7.0/10

开源固件项目 Libreboot 发布了 26.10 版本（代号 &quot;Ominous Olive&quot;），此次更新集成了 UEFI/EDK，并引入了 MrChromebox 的 coreboot 发行版中对 Chromebook 的支持。据发布信息，该版本导入了 MrChromebox 目前支持的全部 233 款 Chromebook 机型，使 Libreboot 的设备覆盖范围扩大了数倍，也让未来添加新设备变得更加容易。需要注意的是，Chromebook 支持目前仅提供源码，用户必须自行从源码构建固件，该版本不提供预编译的二进制文件；目前仅 Bay Trail 平台的 Kip 机型经过实测，其余机型仍需测试。

hackernews · iamnothere · 10月15日 12:52 · [社区讨论](https://news.ycombinator.com/item?id=50102923)

**「背景」** Libreboot 是 coreboot 的一个发行版，以坚持完全自由的固件（不含二进制 blob）著称，因此历史上支持的主板数量远少于 coreboot 本身。此次版本引入 UEFI/EDK 支持，并直接导入 MrChromebox 维护的 coreboot Chromebook 发行版（约 233 款机型），其中 Chromebook 部分在本版本仅提供源码、需自行构建、未提供二进制。

**「影响」** 对于希望摆脱专有固件的用户而言，大量二手 Chromebook 现在可能可以刷入 Libreboot，从而获得完全自由的开源固件；但想尝试的用户需要注意，Chromebook 支持需要从源码自行构建固件，且除 Bay Trail 的 Kip 机型外，大多数机型尚未经过实测，刷机存在变砖风险。此前使用过 MrChromebox coreboot 固件的设备是潜在的可迁移对象。

**「社区讨论」** 社区讨论中，发帖人 iamnothere 认为 UEFI/EDK 集成与 Chromebook 支持才是本次发布的重头，而非项目维护者强调的 AI 政策；有评论者指出 Libreboot 在代码库中加入了严格的 LLM 辅助贡献政策，部分用户对此表示赞赏，认为严肃开源项目限制 LLM 贡献值得肯定。另有开发者分享了将 MrChromebox 代码作为上游依赖、为 Heads 固件项目移植 ChromeOS 设备的相关工作经验。

**标签**: `#open-source firmware`, `#libreboot`, `#coreboot`, `#UEFI`, `#chromebooks`

---

<a id="item-tech-news-5"></a>
### [Anthropic 向投资者披露第三季度营收 168 亿美元，环比增长近 50%](https://simonwillison.net/2026/Oct/15/anthropic-tells-investors/) ⭐️ 7.0/10

据英国《金融时报》报道，Anthropic 在本周三举行的投资者日上披露，第三季度（7-9 月）营收达到 168 亿美元，较第二季度的 115 亿美元增长近 50%，第一季度约为 48 亿美元。公司还告诉投资者，第三季度每花费 1 美元算力可带来 1.70 美元收入，剔除股票薪酬后的调整后营业利润率为 11%。这些披露正值 Anthropic 可能进行 IPO 之前，且信息来自四位&\#x27;知情人士&\#x27;而非公司官方声明。

rss · Simon Willison · 10月15日 13:04

**「背景」** 投资者日披露的这些数据是对此前沟通方式的转变：西蒙·威利森指出，Anthropic 此前（2026 年 5 月底的 Horizon 日报曾报道）在向投资者传递信息时依赖“年化运行率营收”这一指标，而这次披露改为按季度报告实际营收和利润率。此外，“蒸馏”指竞争 AI 实验室用更先进模型（此处为 Anthropic 的模型）的输出来训练自家模型的做法，这种训练需要大量调用和支出，因而会为被蒸馏方带来收入。

**「影响」** Anthropic 透露，竞争对手通过&\#x27;蒸馏&\#x27;（用其模型输出来训练自家模型）曾贡献 5% 至 7% 的营收，且公司在第三季度已&\#x27;大幅&\#x27;削减了这部分收入。Simon Willison 估算，按第二季度营收计算，这意味着未具名的其他实验室在该季度可能花费超过 5 亿美元用于蒸馏 Anthropic 的模型。值得注意的是，Anthropic 此前常用&\#x27;年化运行率营收&\#x27;来表述业绩，本次沟通中似乎已不再强调这一口径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/11632d03-358c-454b-af95-d06d4072932b?syn-25a6b1a6=1">Anthropic tells investors quarterly revenue up nearly 50% to ...</a></li>

</ul>
</details>

**标签**: `#AI industry`, `#Anthropic`, `#business-of-AI`, `#model distillation`, `#IPO`

---

<a id="item-tech-news-6"></a>
### [PNAS 研究：神经元单元凭共享局部规则自组装出可与反向传播媲美的学习电路](https://www.reddit.com/r/MachineLearning/comments/1x6hmyg/how_artificial_neural_networks_build_their_own/) ⭐️ 7.0/10

麻省理工学院于 2026 年 10 月 13 日报道、PNAS 于 10 月 9 日发表的论文《How Biological Synapses Self-Assemble Gradient Learning》显示，由共享可塑性规则支配的随机互连神经元样单元能够自行组装出学习回路，完成模式识别和图像分类任务。报告的对比结果显示，这些自组织网络在分类性能上与经过反向传播训练的测试网络相当。研究的核心区别在于：不再是直接设计学习电路，而是只指定局部规则，让学习机制自行组织。作者明确指出，这种自组织现象并不能证明大脑实际使用该机制，研究动机是生物合理性，而非为大规模模型提供反向传播的替代方案。在不同初始连接条件下回路的稳定性以及能否推广到已演示任务之外，仍是评估该结果时需考虑的开放问题。

reddit · r/MachineLearning · /u/Dorian182 · 10月15日 10:01

**「背景」** 目前主流的人工神经网络训练依赖反向传播（backpropagation）：误差信号从输出层逐层回传，网络中远距离的单元之间需要精确的对称连接，这被广泛认为在生物大脑中难以实现。这项研究探讨的正是另一条路线——不直接设计学习电路，而是只指定每个类神经元单元共享的局部可塑性规则，让学习机制在随机初始连接中自行组织涌现。研究者强调，这一思路的动机是生物合理性，即便结果有效，也不能证明大脑确实采用该机制。

**「影响」** 对机器学习研究者而言，这项工作提供了一条不依赖全局梯度信号的生物合理学习路径的可行示例，但其在已演示的分类任务之外的泛化能力和稳定性尚未得到验证，短期内不构成对大规模模型中反向传播训练的实际替代。

**标签**: `#machine-learning`, `#neural-networks`, `#biologically-inspired-learning`, `#self-organization`, `#research`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中国表态：无论中美贸易休战是否延续，稀土将继续输欧](https://www.cnbc.com/2026/10/15/china-rare-earth-exports-europe.html) ⭐️ 7.0/10

中国商务部发言人何咏前向 CNBC 表示，无论中美贸易休战能否在明年 1 月期限后延续，中国都愿意继续审批对欧洲的稀土出口许可。此前中欧上周经贸会谈后，中方提出以&quot;绿色通道&quot;机制保障稀土输欧。

rss · CNBC Finance · 10月15日 09:02

**「背景」** 2025 年 10 月，中美两国领导人在会晤中同意将彼此的稀土出口管制与美方“实体清单”扩大措施暂停一年，该休战此后被延长两个月至明年 1 月，这是本次美方最后期限的由来。上周欧盟贸易专员谢夫乔维奇在北京与中国商务部长王文涛会谈后，中方表示愿通过“绿色通道”机制保障对欧稀土供应，同时要求欧盟支持中国部分两用物项产品的进口。

**「影响」** 依赖稀土的欧洲汽车、绿色能源及国防相关企业有望获得更稳定的供应预期，但该表态属官方意向而非正式政策调整，实际落实仍取决于中方审批节奏。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/10/15/china-rare-earth-exports-europe.html">China says rare earth exports to Europe will continue past U ...</a></li>
<li><a href="https://tradersunion.com/news/financial-news/show/3823115-china-rare-earth-exports-europe/">China rare earth exports to Europe set to continue beyond U.S ...</a></li>

</ul>
</details>

**标签**: `#China`, `#rare earths`, `#EU trade`, `#US-China trade truce`, `#export controls`

---