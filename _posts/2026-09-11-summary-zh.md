---
layout: default
title: "Horizon Summary: 2026-09-11 (ZH)"
date: 2026-09-11
lang: zh
---

> 从 40 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Rust is tier-1 language at Microsoft](#item-tech-news-1) ⭐️ 9.0/10
2. [Shopify 弃用 React Native，回归 Swift 与 Kotlin 原生开发](#item-tech-news-2) ⭐️ 8.0/10
3. [Forgejo 16.0.4 修复模板仓库相关的严重远程代码执行漏洞](#item-tech-news-3) ⭐️ 8.0/10
4. [More questions about whether researchers can trust OpenAI with unpublished math](#item-tech-news-4) ⭐️ 7.0/10
5. [Cognition 发布 SWE-2 编程模型，社区质疑基准过拟合](#item-tech-news-5) ⭐️ 7.0/10
6. [PlanetScale 发布闭源分片 Postgres 产品 Neki，引发社区争议](#item-tech-news-6) ⭐️ 7.0/10
7. [trynix.dev：在浏览器中直接运行任意 Nix 软件包](#item-tech-news-7) ⭐️ 7.0/10
8. [SemiAnalysis 深度解析：数据中心表后供电的技术与经济难题（第一部分）](#item-tech-news-8) ⭐️ 7.0/10
9. [I tried to make a real fly connectome learn to play Pong. It didn&\#x27;t — and auditing why turned out to be way more interesting than if it had worked \[p\]](#item-tech-news-9) ⭐️ 7.0/10
10. [DeepSeek 发布 V4.1 Flash：552B 参数新架构模型上线 API 并调价](#item-tech-news-10) ⭐️ 7.0/10
11. [HBM 短缺推高中国 AI 芯片价格，华为寒武纪相继涨价](#item-tech-news-11) ⭐️ 7.0/10
12. [腾讯混元开源音频编辑模型 AuK，同步推出更快的 AuK-Flash](#item-tech-news-12) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Rust is tier-1 language at Microsoft](https://rustfoundation.org/media/guest-post-rust-is-tier-1-language-at-microsoft/) ⭐️ 9.0/10

The Rust Foundation confirms Microsoft has elevated Rust to a tier-1 language, marking a major endorsement of Rust for systems programming alongside C and C++.

hackernews · mmastrac · 9月10日 13:39 · [社区讨论](https://news.ycombinator.com/item?id=49643546)

**标签**: `#rust`, `#microsoft`, `#systems-programming`, `#memory-safety`, `#language-adoption`

---

<a id="item-tech-news-2"></a>
### [Shopify 弃用 React Native，回归 Swift 与 Kotlin 原生开发](https://shopify.engineering/back-to-native) ⭐️ 8.0/10

Shopify 在其官方工程博客上宣布，将把移动应用从 React Native 迁回 Swift 和 Kotlin 原生开发。作为 React Native 最具代表性的大型采用者之一，Shopify 的这一转向被广泛视为跨平台移动开发路线的重要行业信号。该消息在 Hacker News 上引发约 515 条评论的热烈讨论，核心争议在于 AI 辅助编码工具是否正在改变原生开发与跨平台框架之间的成本权衡。由于公开信息主要来自公告本身，此次迁移的具体技术细节、时间表和实施方式尚不完整，需等待 Shopify 后续披露。

hackernews · fnthawar2 · 9月10日 14:09 · [社区讨论](https://news.ycombinator.com/item?id=49643982)

**「背景」** React Native 是 Meta 推出的跨平台移动开发框架，允许开发者用 JavaScript 和 React 同时构建 iOS 与 Android 应用，长期以来被视为降低双端开发成本的主流方案，Shopify 曾是其知名的大型采用者之一。2026 年 9 月，Shopify 宣布其移动应用将从 React Native 迁回 Swift 和 Kotlin 原生开发，其中 Shop 应用已在 AI 编码工具的辅助下于 12 周内完成了从概念验证到发布的迁移，公司称编码代理改变了构建移动应用的成本结构，使分别构建两套原生代码比维护一套共享代码库更为划算。

**「影响」** Shopify 作为曾公开推广 React Native 的知名企业回归 Swift 和 Kotlin 原生开发，这对跨平台移动开发生态是一个显著的行业信号，可能促使其他仍在权衡共享代码库方案的企业重新评估 React Native 的成本收益。社区讨论显示，AI 辅助编码大幅降低了编写原生代码的成本，使原本过于昂贵的原生迁移变得可行，但也有开发者指出迁移成本并非主要因 AI 而下降，且代码阅读与手动测试等成本并未同比例减少，实际长期效果仍有待观察。

**「社区讨论」** 评论区的普遍共识是 AI 大幅降低了编写代码的成本，使原生方案更具吸引力：有开发者分享用 LLM 从零生成代码后应用更轻量、运行速度快 1.5 到 3 倍的经验，也有人称借助 AI 工具在一夜之间完成了类似的原生迁移。但存在明显分歧：一位亲历中型 React Native 应用迁移的工程师指出，其大部分迁移工作在 LLM 普及之前已完成，质疑&quot;AI 使迁移变得可行&quot;的叙事；另有评论者提醒，阅读代码和手动测试的成本并不会随 AI 同等下降，且 iOS 工程师群体普遍对放弃共享代码库的决定表示认同。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://shopify.engineering/back-to-native">Native is now the future of mobile at Shopify (2026) - Shopify</a></li>
<li><a href="https://shopify.engineering/shop-app-migration">Migrating Shop app from React Native to native (2026) - Shopify</a></li>
<li><a href="https://dev.to/jamilxt/shopify-is-moving-its-mobile-apps-back-to-native-coding-agents-made-it-cheaper-to-build-twice-than-4bf9">Shopify Is Moving Its Mobile Apps Back to Native. Coding Agents Made It Cheaper to Build Twice Than to Share One Codebase. - DEV Community</a></li>
<li><a href="https://vultrade.com/saas-devsecops/shopify-moves-back-to-native-from-react-native/">Shopify Moves Back To Native From React Native - Vultrade</a></li>

</ul>
</details>

**标签**: `#react-native`, `#mobile-development`, `#swift`, `#kotlin`, `#shopify`

---

<a id="item-tech-news-3"></a>
### [Forgejo 16.0.4 修复模板仓库相关的严重远程代码执行漏洞](https://codeberg.org/forgejo/forgejo/src/branch/forgejo/release-notes-published/16.0.4.md) ⭐️ 8.0/10

Forgejo 发布了 16.0.4 版本，修复了一个影响 16.0.3 及更早版本的严重（Critical）远程代码执行漏洞。该漏洞出现在从模板仓库生成新仓库的流程中：Forgejo 会克隆模板仓库、删除 .git 文件夹、对列在 .forgejo/template 文件中的文件执行变量模板展开，然后初始化新的 git 仓库，而在此过程中模板展开可能干扰 git 仓库的初始化，从而被利用实现远程代码执行。此次发布共包含两项安全修复，其中模板展开干扰仓库初始化的修复被标记为严重级别。任何运行受影响版本的 Forgejo 实例都应尽快升级到 16.0.4 以消除该风险。

hackernews · weierstass · 9月10日 15:57 · [社区讨论](https://news.ycombinator.com/item?id=49645907)

**「背景」** Forgejo 是一个开源的自托管代码托管平台（从 Gitea 分支而来），广泛用于搭建私有 Git 服务。它支持从模板仓库创建新仓库：系统会克隆模板仓库、移除 .git 文件夹，并对 .forgejo/template 目录中列出的文件执行变量模板展开，然后初始化新的 git 仓库。此次修复的漏洞正出在这一模板展开流程中，攻击者若能构造恶意模板仓库，即可在服务器上执行任意代码（CVE-2026-89094）。

**「影响」** 所有运行 Forgejo 16.0.3 及更早版本、且使用模板仓库功能的自托管实例面临远程代码执行风险，运营者应立即升级到 16.0.4。

**「社区讨论」** 评论区补充了修复 PR 的具体内容，并确认 Gitea 不受此漏洞影响（Gitea 项目领导层成员 techknowlogick 同时提醒不应因安全事件羞辱任何项目或报告者）。另有用户指出，由于 Codeberg 的速率限制导致发布说明一度无法访问，社区成员相互转发了完整的修复链接与说明，以便运维人员及时获取升级信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-89094">CVE-2026-89094 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://forgejo.org/docs/latest/admin/upgrade/">Upgrade guide | Forgejo – Beyond coding. We forge. Forgejo v15.0 is available — Forgejo Forgejo v16.0 documentation | Forgejo – Beyond coding. We forge. CVE Crowd | Crowd Intelligence on CVEs CVEs and Security Vulnerabilities - OpenCVE</a></li>

</ul>
</details>

**标签**: `#security`, `#rce`, `#forgejo`, `#open-source`, `#git`

---

<a id="item-tech-news-4"></a>
### [More questions about whether researchers can trust OpenAI with unpublished math](https://mathstodon.xyz/@andreasthom/117240535270608201) ⭐️ 7.0/10

A widely discussed Hacker News thread examines whether OpenAI can be trusted with unpublished mathematical problems after concerns arose that the company published results connected to researchers&\#x27; confidential model interactions without attribution.

hackernews · pred\_ · 9月10日 06:49 · [社区讨论](https://news.ycombinator.com/item?id=49639408)

**标签**: `#openai`, `#research-ethics`, `#machine-learning`, `#mathematics`, `#ai-industry`

---

<a id="item-tech-news-5"></a>
### [Cognition 发布 SWE-2 编程模型，社区质疑基准过拟合](https://cognition.com/blog/swe-2) ⭐️ 7.0/10

Cognition 发布了新的编程模型 SWE-2,宣称其能力可媲美 Fable 5.1 与 GPT-Astra。根据公告及社区讨论，该模型并非从零训练，而是在 Kimi K3 基础上经强化学习后训练而成。此次发布在 Hacker News 上引发活跃争论\(351 分、142 条评论\)，焦点之一是基准成绩：模型在 Terminal Bench 2.1 上取得 92.8%,但在数周前发布的 Terminal Bench 4 上仅得 27.3%,评论者认为如此大的落差暗示模型可能针对旧基准过度拟合、对新问题的泛化能力有限。此外，SWE-2 未开放模型权重，叠加 Cognition 此前产品演示曾引发的争议，社区对其性能宣称普遍持谨慎态度。

hackernews · seelos · 9月10日 15:29 · [社区讨论](https://news.ycombinator.com/item?id=49645443)

**「背景知识」** Cognition 是一家以 AI 软件工程智能体（如 Devin）闻名的公司，其 SWE 系列模型采用&quot;后训练&quot;（post-training）路线：即在 Moonshot AI 已开源权重的 2.8 万亿参数 Kimi K3 基础模型之上，通过强化学习（RL）针对智能体编码任务进行优化，官方称这一过程在多个基准上带来了 5–6 个百分点的提升，并重塑了该基座的成本–性能前沿。理解此次发布的关键概念包括：一是后训练与从零预训练的区别，它意味着模型能力部分继承自开放的基座模型；二是 Terminal Bench、SWE 等编码基准，它们被广泛用于衡量模型在真实软件工程任务中的自主表现，但新旧基准版本之间的分数差异常被用来检验模型是否只是针对旧基准过度拟合；三是开放权重与闭源权重模型的区别，后者限制了用户本地部署和自主可控性。

**「影响」** 对于正在选型 AI 编程工具的开发者而言，SWE-2 的实际效果存疑：社区指出其在 Terminal Bench 2.1 上得分 92.8%，但在几周前发布的更新基准 Terminal Bench 4 上仅得 27.3%，暗示模型可能存在针对旧基准的过拟合而非真正泛化能力。此外，由于该模型由 Kimi K3 后训练而来、闭源发布且缺乏详细模型指标，开发者需要以审慎态度对待厂商宣称的性能提升，并在采用前将其与 DeepSeek 等开源权重模型进行独立对比验证。

**「社区讨论」** 评论整体偏向怀疑：有人以 Terminal Bench 2.1\(92.8%\)与 Terminal Bench 4\(27.3%\)的巨大差距质疑模型“刷榜”，有人提醒 SWE-2 由本已很强的 Kimi K3 后训练而来、性能提升应打折扣看待，还有人因模型闭源而质疑其相对 DeepSeek Flash 4.1 等替代品的价值，并有用户批评 Cognition 旗下 Devin 产品体验糟糕。少数声音则认为，把 K3 通过强化学习提升到 Fable 5 水平本身证明了这条技术路线可行，是积极信号。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.orcarouter.ai/blog/cognition-swe-2-release">Cognition SWE - 2 : Frontier Coding at 64% Off, Plus a Trap</a></li>
<li><a href="https://cognition.com/blog/swe-2">Introducing SWE - 2 : Pushing the Pareto Frontier | Cognition</a></li>
<li><a href="https://genztech.blog/p/cognition-swe-2-coding-model-launch/">Cognition &#x27;s SWE - 2 Nearly Matches GPT-6 Astra for a Quarter</a></li>

</ul>
</details>

**标签**: `#AI models`, `#code generation`, `#benchmarks`, `#machine learning`, `#software engineering`

---

<a id="item-tech-news-6"></a>
### [PlanetScale 发布闭源分片 Postgres 产品 Neki，引发社区争议](https://planetscale.com/blog/introducing-neki) ⭐️ 7.0/10

PlanetScale 正式推出 Neki，一个分片（sharded）Postgres 服务，这是这家以 Vitess 分片 MySQL 方案闻名的公司向 Postgres 生态的扩展。Neki 旨在为需要水平扩展 Postgres 的团队提供分片能力，并在普通分片之外提供额外的运维与部署支持。然而，该产品的发布博文因未在开头清晰说明 Neki 是什么、面向什么场景而受到批评，社区读者认为文章结构反而让人更难理解产品定位。另一个核心争议点在于 Neki 完全闭源：评论者指出 PlanetScale 的原有业务建立在 Google 开源的 Vitess 之上，如今却推出了一个专有的、类似 Vitess 之于 MySQL 的 Postgres 分片方案。此外，评论中还有开发者追问 Neki 如何处理分布式 Postgres 中的一致性保证问题，即在分片场景下能否避免最终一致性对工作负载的影响，但发布内容对此缺乏明确解答。该发布在 Hacker News 上引发了 107 条评论的热烈讨论，涉及架构设计、一致性权衡、闭源策略以及与 Multigres（Supabase 孵化的开源等效项目）的对比。

hackernews · simon\_weber · 9月10日 15:43 · [社区讨论](https://news.ycombinator.com/item?id=49645686)

**「背景知识」** PlanetScale 是一家以 MySQL 数据库托管平台起家的公司，其核心技术建立在 Google 开源的分库分表中间件 Vitess 之上，而 Vitess 正是为解决 MySQL 单机在超大规模下无法水平扩展的问题而生。分片（sharding）指将数据按某种键水平拆分到多个数据库节点上，从而突破单机写入和存储容量上限，但这一直是分布式数据库工程中公认复杂、涉及一致性权衡的难题。PlanetScale 在 2025 年宣布将其平台扩展到 PostgreSQL，并于后续推出了 Neki——面向 Postgres 的水平分片解决方案，目标是把其积累的 MySQL 分片经验复刻到 Postgres 生态中 \[tool-1-2\]\[tool-1-3\]。与此同时，Supabase 等公司在开源领域也推出了类似定位的项目 Multigres，试图为 Postgres 提供开源的分片层，这使得 Neki 的闭源商业化路线与既有的开源路线形成了直接对比。

**「影响」** 需要水平扩展 Postgres 的团队多了一个商业化选项，但选择 Neki 意味着接受闭源锁定；同时，其闭源策略与开源的 Multigres 等替代方案形成直接竞争，可能推动 Postgres 分片领域在开源与商业路线之间的进一步分化。

**「社区讨论」** 社区的主要批评集中在两点：一是发布博文结构混乱，始终没有在开头说明 Neki 到底是什么、为谁服务；二是闭源策略引发反感，评论者指出 PlanetScale 曾受益于 Google 开源的 Vitess，如今却将 Postgres 等效方案专有化，且 CEO 被指在宣传中贬低开源竞品 Multigres，被认为言行不一。也有评论从技术角度提出严肃疑问，即 Neki 如何在分片架构下处理一致性保证、是否需要以可用性为代价，这反映出潜在客户对 HA 分布式 Postgres 一致性问题的普遍关切。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://planetscale.com/docs/postgres/sharding">Horizontal sharding for Postgres - PlanetScale</a></li>
<li><a href="https://planetscale.com/blog/announcing-neki">Announcing Neki — PlanetScale</a></li>
<li><a href="https://www.infoq.com/news/2025/10/planetscale-metal-postgres/">PlanetScale Extends Database Platform to PostgreSQL - InfoQ</a></li>

</ul>
</details>

**标签**: `#postgresql`, `#sharding`, `#distributed-systems`, `#planetscale`, `#databases`

---

<a id="item-tech-news-7"></a>
### [trynix.dev：在浏览器中直接运行任意 Nix 软件包](https://simonwillison.net/2026/Sep/10/trynix/) ⭐️ 7.0/10

Farid Zakaria 发布了 trynix.dev，他称之为自己 Nix 工作的“巅峰之作”（magnum opus）。该站点基于 qemu-wasm 项目，通过 WebAssembly 在浏览器中完整运行一台 x86\_64 Linux 虚拟机，并支持启动过去 13 年间的任意 Nix 软件包。所有环境均可通过 URL 直接寻址，例如访问 https://trynix.dev/?pkg=python3%403.6.2 并点击“Load”，即可获得一个运行 2017 年 Python 3.6.2 的虚拟机交互式 shell。在此基础上，Zakaria 还推出了 trynix-preview GitHub Action：它会在拉取请求下评论一个链接，让评审者直接在浏览器中启动该 PR 的构建进行验证，且“无需服务器，只用浏览器”。Simon Willison 在其博客上转发了这一项目，并认可其技术深度。

rss · Simon Willison · 9月10日 23:44

**「背景」** Nix 是一种以可复现性著称的包管理器，其软件包集合保留了多年历史版本，因此同一软件包的旧版本仍可被精确重建。qemu-wasm 则是将 QEMU 虚拟机移植到 WebAssembly 的项目，使完整的 x86\_64 系统模拟能够在浏览器中运行。两者结合后，复现历史软件包不再需要本地安装 Nix，只需一个可分享的浏览器链接。

**「影响」** 对于使用 Nix 的开发者和代码审查者而言，trynix.dev 提供了一条无需本地安装或服务器的途径：通过浏览器中基于 qemu-wasm 的 x86\_64 Linux 虚拟机直接运行过去 13 年间的任意 Nix 包，并借助可共享的 URL（如 trynix.dev/?pkg=python3@3.6.2）复现特定环境，其配套的 trynix-preview GitHub Action 还能在拉取请求上自动评论链接，让审查者直接在浏览器中启动该 PR 的构建结果。不过需要指出，qemu-wasm 的 Wasm 后端仍处于早期阶段，存在编译开销等性能局限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://patchew.org/QEMU/cover.1744032780.git.ktokunaga.mail@gmail.com/">[PATCH 00/10] Enable QEMU to run on browsers</a></li>
<li><a href="https://github.com/ktock/qemu-wasm">GitHub - ktock/qemu-wasm: QEMU on browser · GitHub</a></li>

</ul>
</details>

**标签**: `#nix`, `#webassembly`, `#virtualization`, `#developer-tools`, `#reproducible-builds`

---

<a id="item-tech-news-8"></a>
### [SemiAnalysis 深度解析：数据中心表后供电的技术与经济难题（第一部分）](https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the) ⭐️ 7.0/10

SemiAnalysis 发布了一篇题为《What is So Hard About Behind-The-Meter Power For Datacenters? Part 1》的深度分析文章，探讨在 AI 驱动的能源需求激增背景下，数据中心采用表后（behind-the-meter）供电方案所面临的技术与经济挑战。文章副标题“愚蠢的科学实验 vs. 印钞机”暗示其分析聚焦于此类自建供电方案在科学可行性与商业回报之间的权衡。该话题之所以重要，是因为电网接入已成为制约 AI 与云计算基础设施扩张的关键瓶颈，表后供电（即在电表用户侧自建发电设施、绕过部分电网环节）被视为潜在缓解路径。需要注意的是，所提供的源内容仅包含文章标题与副标题，本文对其技术细节的评估主要基于 SemiAnalysis 的分析信誉与主题相关性，具体技术论点和数据需参阅原文核实。作为系列第一部分，后续预计还有更多内容展开。

rss · Semianalysis · 9月10日 14:28

**「什么是表后电力」** 表后电力指在电表用户侧自建发电设施、不依赖电网输送的供电方式，数据中心借此可以在主电源与备用电源之间灵活安排与电网的关系，但并非所有自称&quot;微电网&quot;的方案都名副其实。随着 AI 驱动的数据中心建设潮使电网互联排队和供电容量成为瓶颈，越来越多运营商考虑自备电源以加快上线速度。不过这种速度优势有代价：据 EIA 2025 年数据，数据中心规模的表后燃气发电成本约为每兆瓦时 80–120 美元，而美国多数地区的电网电力仅为每兆瓦时 40–60 美元。

**「影响」** 受 AI 算力扩张驱动，超大规模数据中心运营商、云厂商和 AI 实验室正加速评估表后（behind-the-meter）自备电源方案，以绕开电网互联排队和输电延迟，缩短新设施投产时间。不过，该领域涉及燃气轮机、燃料电池、小型模块化反应堆（SMR）和微电网等多种技术路径，各方案在成本、部署周期和监管审批上的成熟度差异较大，实际落地节奏仍存在不确定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the">What is So Hard About Behind - The - Meter Power For Datacenters ?</a></li>
<li><a href="https://gentic.news/article/semianalysis-us-behind-the-meter">SemiAnalysis: US behind - the - meter datacenter … | gentic.news</a></li>
<li><a href="https://radiant.co/blog/what-is-behind-the-meter-power">Demystifying Behind - the - Meter : What It Actually Means... | Radiant Blog</a></li>
<li><a href="https://www.rvninc.com/post/the-future-of-behind-the-meter-power-in-the-ai-and-data-center-era">The Future of Behind - the - Meter Power in the AI and Data Center Era</a></li>

</ul>
</details>

**标签**: `#datacenters`, `#power-infrastructure`, `#ai-infrastructure`, `#energy`, `#hardware`

---

<a id="item-tech-news-9"></a>
### [I tried to make a real fly connectome learn to play Pong. It didn&\#x27;t — and auditing why turned out to be way more interesting than if it had worked \[p\]](https://www.reddit.com/r/MachineLearning/comments/1wc67ci/i_tried_to_make_a_real_fly_connectome_learn_to/) ⭐️ 7.0/10

An ML practitioner describes attempting dopamine-style plasticity learning on a real 166k-neuron fly connectome subgraph in Pong, and explains how auditing the failure—finding a neuPrint regex bug and connectivity issues—yielded more insight than success would have.

reddit · r/MachineLearning · /u/oPeraza2007 · 9月10日 02:28

**标签**: `#machine learning`, `#connectomics`, `#neuroscience`, `#negative results`, `#plasticity`

---

<a id="item-tech-news-10"></a>
### [DeepSeek 发布 V4.1 Flash：552B 参数新架构模型上线 API 并调价](https://mp.weixin.qq.com/s/qg0NU3NNUbp1co2PdkAPAg) ⭐️ 7.0/10

DeepSeek 正式发布 V4.1 Flash，这是其全新模型结构系列中尺寸最小的模型，采用 552B 参数的 Causal-Encoder-Decoder（因果编码器-解码器）结构，输入激活为 8B、输出激活为 16B，并原生支持多模态视觉理解。该模型已上线 DeepSeek API，模型名为 deepseek-flash，新价格自 2026 年 9 月 10 日 12:00 起生效。此外，自 2026 年 9 月 14 日 12:00 起，原本请求 deepseek-v4-pro 的调用将被自动路由至 V4.1 Flash，并按其价格计费，这意味着现有 pro 版用户将无缝切换到新模型且成本发生变化。此次发布同时引入了新的架构系列并调整了 API 定价，对依赖 DeepSeek API 的开发者来说需要在切换日期前确认兼容性与成本影响。需要注意的是，该消息来自频道转载而非官方原始文档，发布内容未附基准测试结果或独立验证数据。

telegram · zaihuapd · 9月10日 05:54

**「背景知识」** DeepSeek 过去的主流模型（如 V3 系列）采用仅解码器（decoder-only）的 Transformer 结构结合多头潜在注意力（MLA），而 V4.1 Flash 属于全新构建的基座模型系列，采用因果编码器-解码器（Causal-Encoder-Decoder）结构，将输入处理与输出生成分离为两个阶段，据称可带来更高的推理吞吐和更低的推理成本。该模型同时是混合专家（MoE）模型：总参数量为 552B，但每个 token 仅激活约 8B（预填充）或 16B（解码）参数，因此推理成本远低于同等总规模的稠密模型；外部平台还提到其支持最高一百万 token 的上下文窗口，并采用低精度（FP4）KV 缓存以进一步降低显存占用。理解这些概念有助于说明为什么该模型能在保持大参数规模的同时实现&quot;更快、更普惠&quot;的定位。

**「影响」** 使用 DeepSeek API 的开发者自 2026 年 9 月 14 日 12:00 起将无法继续直接调用 deepseek-v4-pro，其请求会被路由至 V4.1 Flash 并按新价格计费，需要在切换日期前评估输出质量与成本变化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepinfra.com/deepseek-ai/DeepSeek-V4.1-Flash">DeepSeek V 4 . 1 Flash API - Demo - DeepInfra</a></li>
<li><a href="https://zenmux.ai/deepseek/deepseek-v4.1-flash">deepseek / deepseek - v 4 . 1 - flash - ZenMux</a></li>
<li><a href="https://www.orcarouter.ai/blog/deepseek-v4-1-new-base-model">DeepSeek V 4 . 1 Flash : New Base Model, Not a Point Release</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#large language models`, `#model release`, `#multimodal AI`, `#API pricing`

---

<a id="item-tech-news-11"></a>
### [HBM 短缺推高中国 AI 芯片价格，华为寒武纪相继涨价](https://www.reuters.com/world/asia-pacific/chinas-ai-chipmakers-raise-prices-high-bandwidth-memory-shortage-bites-2026-09-10/) ⭐️ 7.0/10

全球高带宽存储器（HBM）供应紧张正持续冲击中国 AI 芯片产业，华为、寒武纪等厂商已开始上调产品价格。据路透社报道，华为升腾 950DT 芯片报价较两个月前上涨约 20%—50%，部分老款芯片价格上涨约 30%；寒武纪新一代思元 690 的价格也预计上涨约 20%—30%。HBM 目前主要由 SK 海力士、三星和美光三家厂商供应，而美国出口限制进一步加剧了中国市场的供应压力。随着国内 AI 算力需求持续增长，HBM 短缺正成为制约国产 AI 芯片产能与出货扩张的重要瓶颈。需要注意的是，报道中的具体涨价幅度来自消息汇总，暂无法从该条目本身独立核实。

telegram · zaihuapd · 9月10日 09:29

**「背景」** 高带宽存储器（HBM）是一种将多层 DRAM 堆叠并与 AI 处理器紧密封装的高速内存，是训练和运行大规模 AI 模型的关键组件，目前全球供应主要由 SK 海力士、三星和美光等厂商主导。由于美国的出口管制限制了中国获取先进芯片组件的渠道，中国公司被迫加速发展国产 AI 处理器，但同时仍需在受约束的市场中获取 HBM 等关键部件，供应压力因此进一步加剧。在此背景下，华为将其集成 AI 处理器与内存的升腾 950DT 加速卡的标示价格提升至 25 万元人民币（约 37,255 美元）以上。

**「影响」** 依赖华为升腾和寒武纪芯片部署 AI 算力的中国企业和数据中心将面临更高的采购成本和潜在供货延迟，HBM 供应可能成为中国 AI 算力扩张速度的实际约束条件。

**标签**: `#AI chips`, `#HBM memory`, `#semiconductor supply chain`, `#Huawei`, `#export controls`

---

<a id="item-tech-news-12"></a>
### [腾讯混元开源音频编辑模型 AuK，同步推出更快的 AuK-Flash](https://x.com/TencentHunyuan/status/2097996926876795197) ⭐️ 7.0/10

腾讯混元宣布正式发布开源音频编辑模型 AuK，该模型可通过自然语言指令和参考音频统一完成语音生成与编辑，支持零样本文本转语音、音色/风格/情绪编辑、去口音以及多人语音分离等功能。除主模型外，混元还同步发布了推理更快的 AuK-Flash 变体，其采用 4 步推理，在匹配条件下速度约提升 4.5 倍。目前代码、模型权重和在线演示均已上线，开发者可直接获取并部署使用。作为来自大型 AI 实验室的开源发布，AuK 将语音生成与编辑整合到统一框架中，对语音与音频 AI 社区具有较高参考价值；不过该公告本身未提供深入的技术细节和详细基准测试数据，实际性能仍有待第三方验证。

telegram · zaihuapd · 9月10日 11:56

**「背景」** 语音生成与编辑此前通常由不同的专用模型分别完成，例如零样本文本转语音（TTS）模型只需几秒参考音频即可克隆陌生音色，而音色、风格、情绪修改或多人语音分离则依赖各自的工具链。AuK 属于试图用单一基础模型统一这些任务的新一代方案，用户通过自然语言指令加参考音频即可完成生成与编辑。AuK-Flash 则是经过蒸馏的版本，将推理压缩为 4 步以换取约 4.5 倍的速度提升，这种蒸馏加速在开源语音模型中已成为常见的部署优化手段。模型代码与权重发布在 GitHub 和 Hugging Face 上，便于开发者本地部署与二次开发。

**「影响」** 开发者与语音 AI 社区现在可以免费获取并本地部署一个约 1.5B 参数、采用 MIT 许可证的统一语音生成与编辑模型，用于零样本 TTS、音色/情绪编辑、去口音和多人语音分离等任务，而 AuK-Flash 的 4 步蒸馏推理（约 4.5 倍提速）也降低了实际应用中的延迟成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Tencent-Hunyuan/AuK">Tencent - Hunyuan / AuK : AuK : An Open - Source Foundational Model ...</a></li>
<li><a href="https://huggingface.co/tencent/AuK-Flash">tencent / AuK - Flash · Hugging Face</a></li>
<li><a href="https://github.com/Tencent-Hunyuan/AuK">Tencent - Hunyuan / AuK : AuK : An Open - Source Foundational Model ...</a></li>
<li><a href="https://auk-project.github.io/">AuK — An Open - Source Foundational Model for Speech Generation ...</a></li>
<li><a href="https://www.orcarouter.ai/blog/auk-open-weights-speech-explained">AuK : Tencent &#x27;s Quiet Open -Weight 1.5B Speech Editor</a></li>

</ul>
</details>

**标签**: `#open source`, `#audio editing`, `#text-to-speech`, `#Tencent Hunyuan`, `#speech AI`

---