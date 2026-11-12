---
layout: default
title: "Horizon Summary: 2026-11-12 (ZH)"
date: 2026-11-12
lang: zh
---

> 从 52 条内容中筛选出 17 条重要资讯。

---

**科技新闻**
1. [《Python 之禅》作者 Tim Peters 去世（1952–2026）](#item-tech-news-1) ⭐️ 8.0/10
2. [AWS 开源官方云服务模拟器，称由自主 AI 智能体构建](#item-tech-news-2) ⭐️ 8.0/10
3. [《华尔街日报》报道称英伟达正准备罢免 CEO 黄仁勋](#item-tech-news-3) ⭐️ 8.0/10
4. [用电压毛刺破解熔丝，解锁矿卡内隐藏的 A100](#item-tech-news-4) ⭐️ 8.0/10
5. [Anthropic IPO 路演视频披露多芯片算力战略细节](#item-tech-news-5) ⭐️ 8.0/10
6. [GitHub Actions 锁定：哈希固定与工作流锁文件的取舍](#item-tech-news-6) ⭐️ 7.0/10
7. [Jane Street 纽约唯一数据中心因误报烟警险遭水淹](#item-tech-news-7) ⭐️ 7.0/10
8. [Google 推出 Gemini Decisions API](#item-tech-news-8) ⭐️ 7.0/10
9. [《魔法时代的 Emacs》一文引发 GNU Emacs 是否接受 LLM 代码的争论](#item-tech-news-9) ⭐️ 7.0/10
10. [Faster Retrieval for Better, More Efficient RAG](#item-tech-news-10) ⭐️ 7.0/10
11. [线性规划能否直接编辑神经网络权重？](#item-tech-news-11) ⭐️ 7.0/10
12. [Atuin 推出 Threads：跨机器同步 AI 编程代理会话](#item-tech-news-12) ⭐️ 7.0/10
13. [The Information 调查：24 万颗英伟达被禁芯片经关系网流入中国](#item-tech-news-13) ⭐️ 7.0/10
14. [美商务部拟定稿规则，封堵中国 AI 公司境外远程用芯](#item-tech-news-14) ⭐️ 7.0/10

**财经新闻**
1. [芝加哥联储主席称 10 月通胀报告“近乎令人不安”](#item-finance-news-1) ⭐️ 8.0/10
2. [离岸信托收益征税过渡期结束，累计申报超 1600 亿元](#item-finance-news-2) ⭐️ 8.0/10
3. [阿里巴巴获准分拆芯片子公司平头哥，拟赴港上市](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [《Python 之禅》作者 Tim Peters 去世（1952–2026）](https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028) ⭐️ 8.0/10

Tim Peters（1952–2026）去世，Python 官方讨论区 discuss.python.org 已发布题为 &quot;In Memoriam: Tim Peters \(1952–2026\)&quot; 的纪念帖，开发者社区纷纷致哀。他是《The Zen of Python》（Python 之禅）的作者——这段可通过 \`import this\` 随 Python 解释器调出的设计格言广为流传；他也是垃圾邮件过滤工具 SpamBayes 的重要贡献者，并参与撰写了《Python Cookbook》第 2 版。自 1990 年代起，他长期在 comp.lang.python 新闻组等渠道与开发者深入交流，被许多人视为良师。

hackernews · ayhanfuat · 11月11日 07:03 · [社区讨论](https://news.ycombinator.com/item?id=50450488)

**「背景」** 蒂姆·彼得斯（Tim Peters）是 Python 社区最具影响力的核心开发者之一：他撰写的《Python 之禅》（The Zen of Python）以 \`import this\` 彩蛋的形式内置于 Python 中，用简练的格言概括了这门语言的设计哲学；他还在 2002 年为 Python 实现了 Timsort 排序算法，该算法通过识别数据中已有序的片段（run）并逐步合并来高效完成排序，此后成为 Python 内置的排序实现。此外，他与 Gary Robinson 等人将 Paul Graham 的《A Plan for Spam》一文变成了成功的反垃圾邮件程序 SpamBayes，并参与撰写《Python Cookbook（第 2 版）》，在书中向读者细致讲解编程的技巧与门道。

**「Timsort 仍是 Python 与 Java 的默认排序算法」** 对 Python 与 Java 开发者而言，Peters 的核心贡献仍在每日运行：他于 2002 年为 Python 编写的 Timsort 至今是 Python 中 sorted\(\) 与 list.sort\(\) 的默认排序算法，并自 Java 7 起成为 Java 中 Arrays.sort\(\) 对对象排序的默认实现，两大生态的日常排序调用仍在执行他的代码。开发者无需采取任何迁移或兼容性措施；一篇近期实测文章指出，Timsort 对一百万个已排序整数约 5.6 毫秒即可完成排序，比同样数据打乱后快 66 倍，与其面向真实世界数据设计的初衷一致。

**「社区讨论」** 评论以个人回忆为主：dalke 回忆自己 1990 年代末在 comp.lang.python 上从 Tim Peters 的帖子中学到很多，并提到社区当时亲切地称他为 &quot;Uncle Timmy&quot;；lumpa 则称赞他在《Python Cookbook》第 2 版中&quot;替读者读 Knuth&quot;式的讲解令人受益。leoc 梳理了 SpamBayes 的渊源，认为是 Tim Peters 与 Gary Robinson 将 Paul Graham 的《A Plan for Spam》一文变成了实用的过滤程序，并认为 Robert Woodhead 也应分享部分功劳；另有用户直接贴出 \`import this\` 输出的《Python 之禅》全文作为悼念。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Timsort">Timsort - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timsort">Timsort - Wikipedia</a></li>
<li><a href="https://www.geeksforgeeks.org/dsa/timsort/">TimSort - GeeksforGeeks</a></li>
<li><a href="https://dev.to/frankchu/66x-faster-on-sorted-data-timsort-24-years-on-437e">66x faster on sorted data: Timsort, 24 years on - DEV Community</a></li>

</ul>
</details>

**标签**: `#python`, `#obituary`, `#open-source`, `#programming-history`, `#community`

---

<a id="item-tech-news-2"></a>
### [AWS 开源官方云服务模拟器，称由自主 AI 智能体构建](https://github.com/aws/aws-emulator) ⭐️ 8.0/10

AWS 已在 GitHub 上开源发布其云服务的官方模拟器（aws/aws-emulator），面向需要在本地模拟 AWS 服务进行开发与测试的开发者。Amazon 宣称该项目由自主 AI 智能体构建，并配套发布了关于智能体编写代码时代工程师角色变化的文章，但这一构建方式目前是厂商自述，尚无独立验证。项目文档同时明确列出安全局限：不要用该模拟器测试 IAM 策略与权限边界、存储桶策略等基于资源的策略、KMS 密钥策略、跨账户或跨区域访问，以及其他任何安全控制；部分服务虽会评估模拟器内创建的 IAM 用户和角色的策略，但评估方式与真实 AWS 并不相同。

hackernews · super\_linear · 11月11日 18:21 · [社区讨论](https://news.ycombinator.com/item?id=50456631)

**「背景」** 本地模拟器\(local emulator\)是指在开发者本机上模拟云服务 API 行为、用于运行和测试代码的工具,可避免真实云调用带来的费用、网络延迟和凭据管理负担。在 AWS 发布官方模拟器之前,这一需求长期由 LocalStack、Floci 等第三方项目填补,它们通常与 Testcontainers 等容器化测试工具搭配使用;AWS 官方此前并未提供同类工具,第三方模拟器因此成为本地测试 AWS 依赖代码的主要途径。

**「官方模拟器不能替代安全策略验证」** 在本地测试 AWS 应用的开发者（包括使用 LocalStack、Floci 以及 Testcontainers 官方 LocalStack 模块的团队）多了一个 AWS 官方开源选项，但该模拟器明确不适用于安全验证：其安全页面要求不要用它测试 IAM 策略与权限边界、存储桶等资源策略、KMS 密钥策略以及跨账户或跨区域访问，且它对使用自身凭证签名的请求从不拒绝，IAM 评估方式也与真实 AWS 不一致。因此涉及权限和安全控制的测试仍需在真实 AWS 环境中完成；已将 Testcontainers LocalStack 模块集成到 CI/CD 流程的团队在评估是否迁移时，需要把这一限制以及该模拟器长期维护承诺尚不明确纳入考量。

**「社区讨论」** 评论区的核心分歧在于项目前景：CharlieDigital 质疑它究竟是“一次性行动”还是会持续发布和维护的真实产品，表示自己目前更依赖 Floci 和 Testcontainers（后者同时支持 GCP 和 Azure）；自称亚马逊员工的 morelandjs 则认为，这类用于模拟外部依赖的工具对“尽可能封闭系统、再模拟无法封闭的输入”的智能体开发方式价值很大。wg0 评论称，若非 AI 智能体，AWS 几乎不会愿意承担覆盖如此多服务的人力成本，LocalStack 等第三方模拟器的护城河“已经消失”——以上均为评论者个人观点，而非已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://testcontainers.com/modules/localstack/">Testcontainers LocalStack Module</a></li>
<li><a href="https://qaskills.sh/blog/testcontainers-localstack-aws-mocking-guide">Testcontainers LocalStack AWS Mocking — Complete... | QASkills.sh</a></li>

</ul>
</details>

**标签**: `#aws`, `#ai-agents`, `#developer-tools`, `#cloud-testing`, `#open-source`

---

<a id="item-tech-news-3"></a>
### [《华尔街日报》报道称英伟达正准备罢免 CEO 黄仁勋](https://www.wsj.com/business/nvidia-is-preparing-to-oust-nvidia-ceo-jensen-huang-30f421ad) ⭐️ 8.0/10

《华尔街日报》于 2026 年 11 月 11 日发布报道称,英伟达正准备罢免首席执行官黄仁勋,该报道经 Hacker News 转载后引发大量讨论\(678 分、约 946 条评论\)。由于原文位于付费墙后且本条未提供正文,现有材料无法核实报道的具体指控、信源及董事会层面的实际进展,该消息目前只是媒体披露,英伟达方面也未在可见材料中予以确认。评论区流传的多项具体说法\(涉及黄仁勋的私人关系,以及涉嫌知悉向中国违规销售等\)均出自网友转述或个人猜测,未经独立证实,应与报道本身区分看待。

hackernews · jbredeche · 11月11日 22:31 · [社区讨论](https://news.ycombinator.com/item?id=50459703)

**「背景」** 黄仁勋于 1993 年联合创立 Nvidia 并担任 CEO 至今,其任内长期推动 CUDA 平台与 GPU 通用计算,被视为深度学习浪潮的关键推手,Nvidia 也因此成为全球 AI 算力供应的核心企业。此次罢免传闻之所以超出普通人事变动,在于报道所指的婚外情对象之一被怀疑为中国间谍,而 Nvidia 的先进芯片正受美国对华出口管制约束,事件因此同时触及公司治理与出口合规两个敏感层面。

**「市场与治理影响」** 据多家媒体报道，董事会审议消息传出后，英伟达股价在盘后交易中一度下跌超过 8%。由于黄仁勋被视为公司 AI 战略与 CUDA 生态的关键推动者，投资者会关注继任安排能否保持产品路线与合作关系的连续性；若相关报道持续，股价与治理不确定性可能成为短期市场关注点。

**「社区讨论」** 讨论的焦点之一是指控的严重性排序:用户 zug\_zug 认为私人生活问题本身影响有限,真正重大的是涉嫌知悉对华违规销售的指控;Topfi 则援引英伟达此前对 Gamers Nexus GPU 走私调查的异常激烈回应,猜测其中或有隐情。另一派以 flowerlad 为代表,强调黄仁勋早年押注 CUDA 和通用 GPU 计算、支撑了 2012 年 AlexNet 的训练突破,是深度学习浪潮的关键推手,因而难以替代——以上均为基于未经证实信息的个人判断,而非已确认的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wsj.com/business/nvidia-is-preparing-to-oust-nvidia-ceo-jensen-huang-30f421ad">Exclusive | Nvidia Is Preparing to Oust CEO Jensen Huang</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-11/nvidia-ceo-had-an-affair-with-health-executive-at-firm-nyt-says">Nvidia Preparing to Oust Jensen Huang After Affairs, WSJ Says</a></li>
<li><a href="https://www.nytimes.com/2026/11/11/business/nvidia-stock-jensen-huang-ceo.html">Nvidia’s Stock Price Plummets as Board Is Said to Consider ...</a></li>
<li><a href="https://www.cbsnews.com/news/nvidia-stock-dives-report-board-prepares-oust-jensen-huang/">Nvidia&#x27;s stock dives as board weighs move to oust Jensen Huang</a></li>

</ul>
</details>

**标签**: `#nvidia`, `#jensen-huang`, `#corporate-governance`, `#ai-industry`, `#export-controls`

---

<a id="item-tech-news-4"></a>
### [用电压毛刺破解熔丝，解锁矿卡内隐藏的 A100](https://blog.kate.land/posts/using-voltage-glitching-to-unlock-the-a100/) ⭐️ 8.0/10

一位硬件黑客在博客中演示，利用电压毛刺（voltage glitching，一种故障注入技术）绕过 NVIDIA 矿卡上基于熔丝的保护，解锁了卡内被大幅禁用的 A100 GPU。这是博主实测达成的结果，而非厂商提供的功能；该手法本身并非首创，且只适用于这一小类矿卡，社区讨论指认涉事卡为 CMP 170HX 的 8GB 型号。需要注意的是，操作涉及改动熔丝、风险较高，被禁用显存中实际可用的容量也仍不确定。文章发布于 2026 年 11 月 11 日，在 Hacker News 上获得 277 分和 112 条评论。

hackernews · lae · 11月11日 10:48 · [社区讨论](https://news.ycombinator.com/item?id=50451903)

**「矿卡中的 A100 硅片与熔丝锁」** CMP 170HX 是英伟达推出的加密货币挖矿专用矿卡，其内部搭载的其实是一颗物理完整的 GA100 硅片——与数据中心 A100 相同的芯片，只是算力、显存容量等特性被 OTP 熔丝和固件寄存器锁人为限制。社区此前已确认这一点，开发了 cmpunlocker 等解锁工具，并整理出涵盖该卡硅片、固件与解锁流程的系统性技术文档。电压毛刺（voltage glitching）则是一种硬件故障注入技术：在芯片执行关键校验的瞬间短暂扰动其供电电压，诱使硬件出错，从而绕过熔丝限制。

**「影响」** 对在二手市场持有此类矿卡的用户而言，这篇博文提供了一条把矿卡变成 A100 级算力的路径，但流程需要改动熔丝、失败风险高，且解锁后有多少被禁用的显存真正可用尚无定论，尝试前需自行评估。对硬件安全而言，这一结果也表明仅靠熔丝不足以防住故障注入类的物理攻击。

**「社区讨论」** 用户 notenchange 报告称，他连续两周尝试以纯软件方式解锁 CMP 170HX 中的 80GB 显存均未成功，并认为改熔丝的做法风险更大；他还指出本文针对的是 8GB 型号，而 10GB 型号此前已被证实含 80GB 显存，只是始终无法通过 CUDA 完整调用，只能以慢得多的 CPU 内存拷贝方式访问。用户 amelius 则提出另一种可能：这些熔丝或许正是因为芯片制造缺陷过多才被降级为矿卡，因此解锁后的稳定性并无保障。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/d3dx9/cmpunlocker">GitHub - d3dx9/cmpunlocker: Unlock tool for the NVIDIA CMP ...</a></li>
<li><a href="https://news.lavx.hu/article/kate-uses-voltage-glitching-to-turn-a-cmp-170hx-mining-card-into-an-a100-class-gpu">Kate uses voltage glitching to turn a CMP 170HX mining card ...</a></li>
<li><a href="https://github.com/Consensus-Protocol/cmp170hx">GitHub - Consensus-Protocol/cmp170hx: CMP 170HX technical ...</a></li>

</ul>
</details>

**标签**: `#hardware-hacking`, `#voltage-glitching`, `#nvidia`, `#gpu`, `#security`

---

<a id="item-tech-news-5"></a>
### [Anthropic IPO 路演视频披露多芯片算力战略细节](https://simonwillison.net/2026/Nov/11/anthropic-ipo-roadshow/) ⭐️ 8.0/10

Anthropic 已启动 IPO 路演，其路演视频披露了此前未公开的算力策略：公司目前在 AWS Trainium、Google TPU、NVIDIA GPU 和 AMD GPU 四大芯片家族上训练并服务 Claude；由于官方未提供视频文字稿，Simon Willison 使用 MacWhisper 提取并发布了完整转录。联合创始人 Tom Brown 在“算力方法”部分称，多芯片战略是早期一次非常规押注，因为每种芯片都需要单独定制的软件栈和推理栈；他举例说，今年首次接入 AMD GPU 时，借助 Mythos，Claude 在三天内、几乎无人工干预地完成移植，内核几乎全部由 Claude 编写或移植，而过去接入新芯片平台需要数十名工程师数月的工作——上述数字均为公司自述，暂无独立验证。视频还提出“算力乘数”（compute multipliers）概念，称总有效算力等于物理算力乘以已发现的算力乘数，例如 4 倍乘数意味着原本需要 100 单位算力训练的模型只需 25 单位；公司同时表示，相信随着接近递归自我改进，Claude 将能完全自主发现算力乘数，这属于愿景性表述而非已实现的能力。Willison 还指出，Anthropic 此前 9 月发布的三起事故复盘曾暗示这一战略，其中描述了仅影响其 TPU 部署的故障。

rss · Simon Willison · 11月11日 15:11

**「背景」** IPO 路演是公司上市前向机构投资者进行推介的环节，这类材料有时会披露此前未公开的业务细节。Anthropic 的多芯片策略此前已有公开线索：今年 9 月，该公司在三起近期事故的复盘报告中描述了仅影响其 TPU 部署的 bug。多芯片运营的门槛在于每种芯片都需要单独定制的软件栈和推理栈，构建成本高、难度大，因此业内曾有很多人认为在不同芯片上运行 AI 模型不值得投入，Anthropic 早期的这一押注在当时被视为非常规选择。

**「影响」** Anthropic 正以最高 1.4 万亿美元估值、每股 70 至 78 美元的价格区间推进本月晚些时候的 IPO，这些多芯片效率与“计算乘数”的说法因此直接构成其面向公开市场投资者的估值叙事；准备认购的投资者应将其视为路演视频中的公司自述，而非经独立验证或审计的结果。对芯片与云厂商而言，若“新芯片平台接入从数十名工程师数月的工作缩短至三天、Claude 编写近 100% 的内核”属实，AMD 等非 NVIDIA 平台进入前沿模型训练与服务环节的门槛将明显降低，这一说法后续值得用独立证据加以检验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/anthropic-ipo-raise-much-644-billion-latest-draft-prospectus-shows-2026-11-10/">EXCLUSIVE: Anthropic eyes $1.4 trillion IPO valuation in test ...</a></li>
<li><a href="https://www.forbes.com/sites/fionariley/2026/11/10/anthropic-targets-14-trillion-valuation-in-highly-anticipated-ipo/">Anthropic Targets $1.4 Trillion Valuation In Massive IPO - Forbes</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#IPO`, `#AI infrastructure`, `#hardware`, `#Claude`

---

<a id="item-tech-news-6"></a>
### [GitHub Actions 锁定：哈希固定与工作流锁文件的取舍](https://hugovk.dev/blog/2026/lock-github-actions/) ⭐️ 7.0/10

Hugo van Kemenade 在博客文章中建议开发者锁定 GitHub Actions，例如通过哈希固定或工作流锁文件来降低 CI/CD 供应链风险。该帖在 Hacker News 获得约 \*\*170 分\*\*和 \*\*29 条评论\*\*的讨论。zizmor 维护者在评论中指出，当前的工作流锁文件只锁定普通的 action 调用；若工作流调用其他可复用工作流，仍需手动哈希固定，而 composite action 本身不被直接锁定，只能通过调用它的工作流传导锁定。这是对已确立做法（SHA 固定）的实践建议，而非新的工具或测量结果。

hackernews · gslin · 11月11日 22:16 · [社区讨论](https://news.ycombinator.com/item?id=50459485)

**「背景」** GitHub Actions 工作流通常通过标签引用第三方动作，标签可被仓库所有者移动，因此哈希固定（SHA pinning）成为限制供应链风险的常见做法。围绕这一实践的静态分析工具已经存在，例如 zizmor 可扫描工作流 YAML 中的模板注入、令牌权限过大、提交欺骗等问题（tool-1-2、tool-1-3）。与此同时，GitHub 文档描述了“不可变发布”机制：发布后的工件与关联 Git 标签不可更改，这一机制旨在阻断供应链攻击（tool-2-1、tool-2-2）。

**「影响」** 采用该建议的团队需要注意：单靠工作流锁文件无法完全覆盖可复用工作流和 composite action，仍需对前者手动进行哈希固定，并把 composite action 的安全性视为取决于调用方工作流的锁定状态。这意味着可以借助自动化工具减少人工维护，但无法完全免除对依赖关系的审计。

**「讨论」** 有评论者认为哈希固定的信任模型实际上是用“信任仓库所有者不会移动标签”换成了“信任提交哈希的合并者已确认该提交来自目标仓库而非某个 fork 的提交”——因为 GitHub 上任意 fork 的提交都可以被固定。该评论者建议 GitHub 在市场发布时强制使用不可变标签。另有评论者主张尽量避免使用 GitHub Actions，也有人质疑导入第三方 action 的必要性，倾向将脚本内容直接复制进配置以实现完全自主控制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.x-cmd.com/install/zizmor/">Zizmor : GH Actions Misconfig? Static CI/CD Scan</a></li>
<li><a href="https://dev.co/security/open-source/zizmor">Zizmor : GitHub Actions Static Security Analysis | DEV.co</a></li>
<li><a href="https://docs.github.com/en/code-security/concepts/supply-chain-security/immutable-releases">Immutable releases - GitHub Docs</a></li>
<li><a href="https://docs.github.com/api/article/body?pathname=/en/code-security/concepts/supply-chain-security/immutable-releases">GitHub Docs</a></li>

</ul>
</details>

**标签**: `#github-actions`, `#supply-chain-security`, `#ci-cd`, `#devops`, `#security`

---

<a id="item-tech-news-7"></a>
### [Jane Street 纽约唯一数据中心因误报烟警险遭水淹](https://michael.bacarella.com/2026/11/10/false-smoke-alarm-jane-street-datacenter/) ⭐️ 7.0/10

一篇第一人称的事故复盘文章描述了 Jane Street 位于纽约的唯一数据中心因一次误报的烟雾警报险些被水淹没。据社区讨论，报警触发后的事故处置暴露了消防灭火系统设计、紧急断电（EPO）保护以及单数据中心风险方面的具体问题。发帖人在 Hacker News 上获得 \*\*437 分\*\*与 \*\*223 条评论\*\*，讨论集中在对消防系统联动逻辑与应急程序的技术批评。

hackernews · mbac32768 · 11月11日 16:38 · [社区讨论](https://news.ycombinator.com/item?id=50455394)

**「背景」** 数据中心的水喷淋灭火系统通常与烟雾探测联动：一旦探测器报警，系统会假定火灾已经发生且未被控制，从而触发喷水。讨论中有人提到，作者所在机房在误报后经历的是冷却失效与断电抢救的过程。评论还指出，烟雾报警器与设备断电（EPO）是否应当联动并无统一做法，例如《国际机械规范》允许单空间空调机组在烟雾报警时不联动停机，这与喷淋逻辑属于不同层面的设计选择。

**「影响」** 对纽约地区仅有单一数据中心、且物理灭火系统不完善的运营方来说，这一事件暴露了连锁风险：灭火气体释放不当会直接威胁设备供电。评论者 rdl 指出，缺少机房门禁级别的紧急断电按钮（EPO）及烟雾报警联动是明显缺口；rainbowzootsuit 则从机械规范角度说明，对单一空间的 CRAC 不设烟雾联动停机是行业惯例，以避免误动作。因此，依赖单点基础设施的团队应复核消防与电力联锁逻辑，并明确手动干预流程。

**「社区讨论」** 评论者 rdl 指出该数据中心至少缺少两项常见设计：机房内可用于一键断电的物理紧急断电（EPO）按钮，以及烟雾报警与 EPO 的联动机制。rainbowzootsuit 则从规范角度解释，其负责的数据大厅在顺序控制（Sequence of Operations）中特意不在烟警触发时关闭 CRAC，并称《国际机械规范》（IMC）对仅服务单一空间、风量超过 2000 cfm 的空气处理机组允许此类做法，以降低误报风险。另有评论者以飓风 Sandy 期间纽约数据中心被淹、人们搬运柴油维持发电机的经历作类比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50455394">A false smoke alarm almost drowned Jane Street &#x27;s only NYC ...</a></li>
<li><a href="https://michael.bacarella.com/2026/11/10/false-smoke-alarm-jane-street-datacenter/">How a false smoke alarm almost drowned Jane Street ’s only NYC ...</a></li>

</ul>
</details>

**标签**: `#datacenter`, `#incident-postmortem`, `#fire-suppression`, `#infrastructure`, `#operational-resilience`

---

<a id="item-tech-news-8"></a>
### [Google 推出 Gemini Decisions API](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google 发布 Gemini Decisions API，将 Gemini 面向需要分类、路由或概率判断的开发者场景。公告本身未在可用材料中披露模型版本、定价、输入限制或概率输出方式等细节，因此目前只能确认为一项已宣布的开发者接口。Hacker News 讨论中，开发者一方面指出决策模型已有先例（如 Jev、respan/span-02），另一方面关注该 API 支持音频与视频输入，认为这在其特定场景下可能很有用。也有人认为其价格高于同类的其他决策模型。

hackernews · iamdelirium · 11月11日 18:32 · [社区讨论](https://news.ycombinator.com/item?id=50456791)

**「背景」** 该 API 由 Gemini Decision 1 模型驱动，官方定位为快速、经过校准的多模态决策，支持是/否、选项与评分三类输出，且声称不产生输出 token；官方文档还称单次可评估最多 1,000 个问题。评论者指出决策模型并非全新品类，已有 Jev 与 respan/span-02 等先例，并提到后者基于 Gemma 衍生模型微调，说明 Google 是在既有小型决策模型赛道中推出自家产品。

**「对开发者的影响」** 打算采用该 API 的团队需要先核对价格与输入能力：有评论者指出它比同类决策模型更贵，但支持音频和视频输入（waximabbax）。由于 Google 公布的材料未提供具体定价或规格，直接迁移前应先确认配额与实际费用。

**「社区讨论」** 评论者提出了几个实质问题：有用户询问这类模型如何给出概率，并指出仅用语法约束输出只能得到固定 JSON 结构、无法获得概率分布。waximabbax 认为 Gemini Decisions API 比同赛道其他决策模型更贵，但可接受音频和视频输入，在这些场景下可能非常有用。theanonymousone 称其用过的最好决策模型之一是基于 Gemma4 26A4 微调的 respan/span-02，并因此对本次发布持乐观态度，尽管成本较高。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/">Gemini Decisions API : Fast multimodal decisions</a></li>
<li><a href="https://aistudio.google.com/docs/models/gemini-decision-1">Gemini Decision - Gemini API | Google AI Studio</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/google-gemini-decisions-api-fast-ai-agents">Google unveils Gemini Decisions API to handle 1,000 questions at...</a></li>

</ul>
</details>

**标签**: `#google-gemini`, `#decision-models`, `#ai-apis`, `#developer-tools`, `#llm`

---

<a id="item-tech-news-9"></a>
### [《魔法时代的 Emacs》一文引发 GNU Emacs 是否接受 LLM 代码的争论](https://commandlinesystems.com/magic.txt) ⭐️ 7.0/10

一篇题为《魔法时代的 Emacs》（Emacs in the Age of Magic）的文章在 Hacker News 上引发讨论，焦点是 AI 编码工具对 Emacs 与软件自由的影响。讨论延伸到一个具体的政策问题：GNU Emacs 是否应接受 LLM 生成的贡献。作为回应，社区中出现了明确的口号与行动——human-emacs.org 宣布将使用和开发一个不受 GNU 最终政策影响的、无 LLM 贡献的 Emacs 版本。该文章获得 166 分、58 条评论。

hackernews · ggcr · 11月11日 20:26 · [社区讨论](https://news.ycombinator.com/item?id=50458208)

**「背景」** 这一争议的直接前提是 GNU Emacs 项目自身的临时政策。据 emacs-devel 邮件列表 3 月 17 日的回复，项目当时正等待 GNU 项目就 LLM 贡献作出统一决定，在此期间以预防为由不接受 LLM 生成的代码，并已有关于 ELPA 包的讨论。11 月 3 日的报道显示，部分开发者与用户已发起 Human Emacs 倡议，以伦理理由拒绝 LLM 贡献，并宣称若 GNU Emacs 解除临时禁令将进行分叉。

**「影响」** 对于 Emacs 用户和贡献者而言，这一争论已经带来了一个明确的分叉信号：human-emacs.org 表示，如果 GNU 不允许其主张，他们将自行维护一个无 LLM 贡献的 Emacs 版本，即使它不再是 GNU Emacs。

**「社区讨论」** 评论者对 AI 生成代码的后果分歧明显：spapas82 表示自己已数月不用编辑器、亲手写代码“像是昨天的事”，并称喜欢这个新时代；russfink 则引用观点称 AI 把 Stallman 的软件自由目标颠倒过来，因为使用者将不再理解代码如何运作。Animats 主张用模块化和明确 API 为 AI 生成的代码建立隔离，以维持可维护性；vhantz 则感叹“扯皮式讨论”（bikeshedding）消失是一大损失。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/emacs-devel/2026-03/msg00425.html">Re: What is the policy/attitude towards LLM contributions in ...</a></li>
<li><a href="https://freenode.net/article/emacs-group-vows-fork-if-project-accepts-llm-generated-code">Emacs group vows fork if project accepts LLM-generated code</a></li>

</ul>
</details>

**标签**: `#emacs`, `#open-source`, `#ai-generated-code`, `#gnu`, `#software-freedom`

---

<a id="item-tech-news-10"></a>
### [Faster Retrieval for Better, More Efficient RAG](https://machinelearning.apple.com/research/faster-retrieval) ⭐️ 7.0/10

Apple ML Research published work on faster retrieval for more efficient and higher-quality RAG systems, prompting Hacker News debate over learned retrieval methods and their applicability beyond hyperscale deployments.

hackernews · zerop · 11月11日 16:57 · [社区讨论](https://news.ycombinator.com/item?id=50455633)

**标签**: `#RAG`, `#information-retrieval`, `#machine-learning`, `#Apple`, `#LLM-systems`

---

<a id="item-tech-news-11"></a>
### [线性规划能否直接编辑神经网络权重？](https://nathan.rs/posts/weight-space-lp/) ⭐️ 7.0/10

一篇技术博客探讨能否用线性规划（LP）直接对神经网络权重做定向编辑，从而改变或保留特定行为，作为梯度微调之外的优化式替代方案。作者给出的思路是把“消除某种行为、保留另一种行为”表达为线性约束，交由 LP 求解器处理。目前这是探索性分析，而非经过验证的突破：该来源未提供源代码或可复现的实验结果，也未说明在何种模型规模、任务与算力条件下有效。相关内容在 Hacker News 获得 255 分、37 条评论，讨论集中在模型编辑、蒸馏与训练正则化等方向。

hackernews · emschwartz · 11月11日 12:30 · [社区讨论](https://news.ycombinator.com/item?id=50452655)

**「背景」** 该博客讨论的“权重空间编程”思路，此前已由 GPT-6 Astra 的实践引发关注：据 Hugging Face 上的 Astra-Stop 说明，Astra 通过在模型权重上自行实验定位到特定编辑，其灵感来自《Sparks of Weight-Space Programming》。另有报道称，Astra 在让 Qwen 3.5-0.8B 提升数学能力时，通过直接编辑约 \*\*0.016%\*\* 的权重修复了导致推理循环的问题。这篇新文章在此基础上提出的问题是：能否改用线性规划这类优化方法，替代梯度微调来直接完成或约束权重编辑。

**「潜在影响」** 对模型编辑实践者而言，这一思路指向一种可能更可控的替代路径：用线性约束显式表达“消除某行为、保留某行为”，而非仅依赖梯度微调的隐式偏好。社区评论也据此提出，同等方法或可用于权重空间蒸馏，通过配对样本发现行为方向并求稀疏权重编辑。不过该博文为探索性分析，尚未给出可复现的基准结果或已发布工具，因此上述能力目前仍属设想而非已验证的实践。

**「社区讨论」** 有评论者（jsw97）认为该方法的定位不是让 LP 取代某个具体权重编辑流程，而是借助约束提供引导来提升其效果；dansitu 则指出方法本身如此简单，说明类似机制本应通过正则化在训练阶段就实现。mirekrusin 建议把它用于权重空间蒸馏，通过收集成对样例、发现行为方向，再用 LP 求稀疏权重修改并反复迭代；rbnafo 和 whatever1 则更激进，认为过多依赖 LLM 与强化学习回路使人们接受了次优解，在存在多目标时奖励与惩罚难以严格满足约束，数学规划应当回归。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/jarrodwatts/Qwen3.8-27B-Astra-Stop">jarrodwatts/ Qwen 3.8-27B- Astra -Stop · Hugging Face</a></li>
<li><a href="https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/">Qwen 3.8 27B on my laptop can interpret model weights , too</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#linear-programming`, `#optimization`, `#model-editing`, `#neural-networks`

---

<a id="item-tech-news-12"></a>
### [Atuin 推出 Threads：跨机器同步 AI 编程代理会话](https://blog.atuin.sh/threads-agent-sessions/) ⭐️ 7.0/10

Atuin 发布 Threads 功能，用于在开发者所有机器之间同步 AI 编程代理（coding agent）的会话记录，把原先以 shell 历史同步为核心的工具延伸到 agent 工作流。该消息由 Atuin 官方博客发布，属于功能发布声明而非第三方评测，具体支持的代理格式、平台和同步机制在现有材料中未细述。对已使用 Atuin 同步 shell 历史的用户而言，这意味着代理会话也进入同一同步与检索范围；对于担心会话数据噪声的人，是否全部同步、如何检索仍是待确认的设计问题。

hackernews · linsomniac · 11月11日 14:10 · [社区讨论](https://news.ycombinator.com/item?id=50453637)

**「背景」** Atuin 最初是开源的 shell 历史记录工具：它用 SQLite 数据库替换传统的 shell 历史记录，记录命令的额外上下文，并能通过自建服务器或托管服务在不同机器间进行端到端加密的同步。官方资料显示，该项目已从 shell 历史同步扩展至 Atuin Desktop，并将这一同步能力延伸到 AI 编程代理会话场景。

**「影响」** 对多机开发者而言，Threads 的核心便利是无需手动迁移或整理即可在不同设备上继续同一 agent 会话；社区评论中也有自建方案者指出，完整同步原始会话会带来大量实验性、一次性会话的噪音，因此实际使用中可能需要过滤或剪枝策略。另需注意，评论中提到 Atuin 在只读文件系统（EFSRO）等异常场景下的健壮性问题长期未修复，部署前值得评估其对本地 shell 的依赖风险。

**「社区讨论」** 有用户表示 Atuin 对自身价值极高，即便不用自建服务端、仅用客户端也很好用；也有人维护同类工具 cv，强调对主流代理格式多个版本的高性能解析，并称自定义裁剪的效果优于摘要压缩。另一位开发者则质疑是否需要保存每台机器的每个会话，认为大量实验性、一次性会话会带来噪声，但也承认数据量小到可以随时用 ripgrep 或 LLM 检索。还有用户提到长期使用的顾虑：Atuin 对只读文件系统错误处理不正确，相关 issue 已开放近一年，曾在其 /home 挂载盘出现故障时影响本地 shell。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://atuin.sh/">Atuin - Making Your Terminal Magical</a></li>
<li><a href="https://atuin.sh/?featured_on=pythonbytes">Atuin - Shell History &amp; Executable Runbooks</a></li>
<li><a href="https://github.com/atuinsh/atuin">GitHub - atuinsh/ atuin : Making your shell magical · GitHub</a></li>

</ul>
</details>

**标签**: `#developer-tools`, `#ai-agents`, `#open-source`, `#cli`, `#sync`

---

<a id="item-tech-news-13"></a>
### [The Information 调查：24 万颗英伟达被禁芯片经关系网流入中国](https://www.tomshardware.com/tech-industry/policy/alice-huang-reportedly-instrumental-in-securing-over-usd7-5-billion-of-nvidia-ai-gpu-imports-during-three-year-relationship-with-jensen-huang-helped-move-240-000-banned-chips-into-china-mostly-h100-and-h200) ⭐️ 7.0/10

据 Tom&\#x27;s Hardware 转述 The Information 的调查报道，化名“Alice Huang”（黄乐）的人士被指借助与英伟达 CEO 黄仁勋的关系，协助约 \*\*24 万颗\*\*受美国出口管制的芯片进入中国，以 \*\*H100 和 H200\*\* 为主，对应 AI GPU 进口金额约 \*\*75 亿美元\*\*。报道称，相关交易牵涉上海世纪利通（Shanghai Century Liantong）与新加坡公司 \*\*Megaspeed\*\* 等主体。上述内容均为 The Information 的调查指控，而非监管机构或法院已确认的结论；摘要未披露涉案芯片的具体出货时间分布、单笔交易结构或英伟达方面的回应。

telegram · zaihuapd · 11月11日 14:41

**「背景」** 美国对华高端 AI 芯片出口管制自 2022 年起逐步收紧，H100、H200 等英伟达数据中心 GPU 属于受限产品，因此任何绕道第三国或经中间商转运的行为都可能触及出口管制合规问题。相关调查中已出现新加坡公司 Megaspeed 的身影：据《金融时报》等报道，美国方面正就该公司涉嫌违反芯片出口限制展开调查，新加坡警方也在对其进行本地立案调查，该公司唯一董事为 Tan Yong Pong，其母公司为 Swiftdata。

**「合规与执法压力」** 若报告所述成立，涉案规模将超过此前披露的同类案件：Tom&\#x27;s Hardware 另一篇报道称，有中国公司被指在三个月内走私约 10 亿美元的英伟达 AI 芯片，而本次涉及金额约 75 亿美元。这意味着新加坡等中转地的监管审查可能进一步收紧，此前新加坡已就相关走私活动逮捕三人，进口方与中介机构的合规审查也将随之加强。需要注意的是，上述指控来自 The Information 的调查报道，尚未经司法或监管机构确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/52b5f9a8-346f-4dae-8a16-14d5d9eb1244?syn-25a6b1a6=1">Nvidia spy scandal exposes Singapore ’s role in China’s AI chip trade</a></li>
<li><a href="https://www.straitstimes.com/business/the-megaspeed-mystery-whos-the-singaporean-behind-firm-at-centre-of-nvidia-chips-probe">The Megaspeed mystery: Who’s the Singaporean ... | The Straits Times</a></li>
<li><a href="https://www.businesstimes.com.sg/companies-markets/telcos-media-tech/megaspeed-singapore-firm-centre-us-nvidia-chip-probe-goes-dark">Megaspeed , Singapore firm at centre of US Nvidia chip probe, goes...</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/artificial-intelligence/chinese-companies-allegedly-smuggled-in-usd1bn-worth-of-nvidia-ai-chips-in-the-last-three-months-despite-increasing-export-controls-some-companies-are-already-flaunting-future-b300-availability">Chinese companies allegedly smuggled in $1bn worth of Nvidia AI...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#AI GPUs`, `#US-China tech policy`, `#chip smuggling`

---

<a id="item-tech-news-14"></a>
### [美商务部拟定稿规则，封堵中国 AI 公司境外远程用芯](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 7.0/10

美国商务部正敲定一项规则，阻止中国 AI 公司通过境外数据中心远程使用先进 AI 芯片，最早可能在 2026 年 11 月内公布。管制范围将从现行的半导体出口限制扩展至马来西亚、新加坡、泰国等七个国家，目标包括远程访问和芯片走私两条路径。报道称，商务部正在与其他政府机构磋商后定稿，因此该规则目前仍处于拟议阶段，尚未正式生效。白宫此前已要求国会立法，授权商务部制定这一规则；英伟达曾游说反对封堵该远程访问缺口，理由是美国的 AI 基础设施需要在全球范围内取胜。

telegram · zaihuapd · 11月12日 03:42

**「背景」** 美国现行对华半导体出口管制主要针对芯片实物的出口与再出口，中国 AI 公司因此转向在境外数据中心租用算力，以远程方式使用受控芯片。新加坡等东南亚国家是这一路径的关键节点：有报道指出，先进 AI 芯片经新加坡转手可能违反美国出口管制，而泰国目前以 42 座数据中心在东盟位列第四，仅次于新加坡、印度尼西亚和马来西亚。新规则正是要把这类远程访问纳入管制范围。

**「影响」** 若规则按报道所述定稿，在马来西亚、新加坡、泰国等七个国家数据中心运行训练或推理任务的中国 AI 公司将失去合规的远程算力通道，相关企业需要在规则生效前评估现有境外算力安排。目前规则的具体条款、生效时间和适用芯片范围均未公布，实际影响仍待商务部正式文本确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ft.com/content/52b5f9a8-346f-4dae-8a16-14d5d9eb1244?syn-25a6b1a6=1">Nvidia spy scandal exposes Singapore ’s role in China’s AI chip trade</a></li>
<li><a href="https://www.linkedin.com/posts/justinidcnova_thailand-datacenter-tiktok-activity-7457972322801487872-x1C8">Thailand &#x27;s AI Infrastructure Boom: TikTok &amp; Digital Edge... | LinkedIn</a></li>

</ul>
</details>

**标签**: `#export-controls`, `#AI-chips`, `#semiconductors`, `#US-China-policy`, `#Nvidia`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [芝加哥联储主席称 10 月通胀报告“近乎令人不安”](https://www.cnbc.com/2026/11/11/goolsbee-october-inflation-fed-rates-disturbing-distressing.html) ⭐️ 8.0/10

美国 10 月消费者价格指数（CPI）环比上涨 0.4%（经季节调整），高于经济学家预期，为连续第三个月大幅上涨。芝加哥联储主席古尔斯比称这份报告“近乎令人不安”，多位美联储官员释放鹰派信号，联邦基金期货随后完全定价 12 月加息。

rss · CNBC Finance · 11月11日 16:49

**「背景」** 美联储在 9 月将联邦基金利率上调 25 个基点至 3.75%-4%，这是自 2023 年以来的首次加息，随后在 10 月会议上按兵不动。此次 10 月 CPI 数据公布之际，美联储官员正在权衡 12 月是否再次加息。

**「影响」** 市场对 12 月加息的预期已升至 100%，并计入 15%的加息半个百分点的概率，这意味着家庭和企业的借贷成本可能进一步上升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/09/16/fed-rate-decision-september-2026.html">Fed rate decision September 2026 : Rates rise to 3 . 75 %- 4 %</a></li>
<li><a href="https://tradingeconomics.com/united-states/interest-rate">United States Fed Funds Interest Rate</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#CPI`, `#interest rates`

---

<a id="item-finance-news-2"></a>
### [离岸信托收益征税过渡期结束，累计申报超 1600 亿元](https://www.news.cn/20261111/9bcce99c779b4a6197ff45bbbc3e4c50/c.html) ⭐️ 8.0/10

国家税务总局 11 月 11 日表示，离岸信托收益征税的 90 天过渡期已结束，累计申报个人所得税超\*\*1600 亿元\*\*，其中 10 月当月入库超\*\*1200 亿元\*\*。税务总局称，这一因素带动 10 月全国个人所得税收入增长近\*\*90%\*\*（未说明对比基数）。对未主动申报或申报不实的，税务部门将督促补缴并加收滞纳金，仍不改正的将依法立案稽查。

telegram · zaihuapd · 11月11日 10:35

**「背景」** 2026 年 7 月 24 日，财政部和税务总局发布离岸信托个人所得税公告，规定对 2026 年 1 月 1 日前离岸信托存续期收益，纳税人需在公告实施起 90 天内按“利息、股息、红利所得”申报，期内缴税不加收滞纳金。

**「影响」** 税务部门表示，对未主动申报或申报不实的离岸信托收益纳税人将督促补缴并加收滞纳金，仍不改正的将依法立案稽查，这意味着取得离岸信托收益的中国税收居民若未在过渡期内申报，后续面临补税与滞纳金成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.ifeng.com/c/8xy4Zh6tZlZ">离 岸 信 托 个 税 申报超1600亿，带动全国10 月 份个 税 收 入增长 90 %_凤凰网</a></li>
<li><a href="https://hainan.chinatax.gov.cn/xxgk_6_1/24166170.html">财政部 税务总局关于离岸信托个人所得税有关事项的公告（财政部 税务...</a></li>
<li><a href="http://beijing.chinatax.gov.cn/bjswj/sszc/zxwj/202607/a28344d9de4640feb6c632d761818ada.shtml">财政部 税务总局关于离岸信托个人所得税有关事项的公告</a></li>
<li><a href="https://news.qq.com/rain/a/20261111A0DRM200">国家税务总局：全国10月份个人所得税收入增长近90%</a></li>
<li><a href="https://trrb.net/hot-headlines/voachinese-x-2120485917710258292">中国10月个人所得税收入激增近九成 离岸信托税款贡献突出</a></li>

</ul>
</details>

**标签**: `#China tax policy`, `#offshore trusts`, `#personal income tax`, `#fiscal revenue`, `#tax enforcement`

---

<a id="item-finance-news-3"></a>
### [阿里巴巴获准分拆芯片子公司平头哥，拟赴港上市](https://www.cnbc.com/2026/11/11/alibaba-pr.html) ⭐️ 7.0/10

阿里巴巴周二晚间宣布，香港交易所已同意其分拆半导体子公司平头哥（T-Head），公司计划在香港公开发行该子公司股票，交易仍需港交所和中国证监会批准，目前未披露上市时间与发行规模。此举正值美国限制中国获取先进 AI 芯片之际，阿里巴巴等中国企业正推进芯片自研。

rss · CNBC Finance · 11月11日 07:47

**「背景」** 平头哥（T-Head）是阿里巴巴旗下的半导体子公司，其处理器设计主要采用开源的 RISC-V 指令集架构。分拆上市指母公司将子公司独立出来、单独发行股票；百度此前也在筹划将旗下 AI 芯片部门昆仑芯分拆赴港上市。

**「潜在影响」** 若上市成行，投资者将获得直接投资阿里巴巴自研 AI 芯片业务的渠道，但据媒体报道，百度昆仑芯与长江存储的同类上市已被推迟，显示此类交易仍面临审批和时机上的不确定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/T-Head">T - Head - Wikipedia</a></li>
<li><a href="https://www.cnbc.com/2026/01/02/baidus-semiconductor-kunlunxin-hong-kong-ipo-ai-chips-listing-china.html">Baidu plans Hong Kong IPO of AI chip unit Kunlunxin in spin-off move</a></li>

</ul>
</details>

**标签**: `#Alibaba`, `#semiconductors`, `#Hong Kong IPO`, `#AI chips`, `#US-China tech restrictions`

---