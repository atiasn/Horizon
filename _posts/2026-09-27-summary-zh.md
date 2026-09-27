---
layout: default
title: "Horizon Summary: 2026-09-27 (ZH)"
date: 2026-09-27
lang: zh
---

> 从 30 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [SemiAnalysis 发布 Intel Panther Lake 18A 芯片免费拆解报告](#item-tech-news-1) ⭐️ 8.0/10
2. [DeepSeek 弹性计算论文 DSec 引热议：据称 160 台服务器承载 38 万并发沙箱](#item-tech-news-2) ⭐️ 7.0/10
3. [开源 XMPP 客户端 Conversations 退出 Google Play 并转为免费](#item-tech-news-3) ⭐️ 7.0/10
4. [美国上诉法院 2:1 维持五角大楼将 Anthropic 列入军事合同黑名单](#item-tech-news-4) ⭐️ 7.0/10
5. [Excel 预览版首次支持单元格存放多个值](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [美国 10 年期国债收益率升至 5.23%，创 2007 年以来新高](#item-finance-news-1) ⭐️ 7.0/10
2. [香港证监会与普华永道就恒大审计失职达成 10 亿港元和解](#item-finance-news-2) ⭐️ 7.0/10
3. [大众因转向螺栓隐患全球召回约 286 万辆车](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [SemiAnalysis 发布 Intel Panther Lake 18A 芯片免费拆解报告](https://newsletter.semianalysis.com/p/intel-panther-lake-teardown) ⭐️ 8.0/10

半导体分析机构 SemiAnalysis（作者 Adith Shankar）于 2026 年 9 月 26 日发布了一份关于英特尔 Panther Lake 芯片的免费技术拆解报告。该报告以 STEEL 拆解形式呈现，检视了这款基于 Intel 18A 工艺节点制造的芯片的裸片（die）与封装结构。报告通过 SemiAnalysis 电子报免费公开发布，读者无需付费即可访问。需要说明的是，所提供的源材料仅包含报告标题与简介，其中未给出拆解中的具体测量数据或分析结论。

rss · Semianalysis · 9月26日 13:36

**「18A 节点与 Panther Lake 的技术背景」** Panther Lake（酷睿 Ultra 300 系列）是英特尔首款采用 18A 节点的客户端处理器，其计算 tile 是最早在该公司这一最先进制程上制造的产品之一，搭载新一代 Cougar Cove P 核与 Darkmont E 核，并在 P 核与 E 核之间共享最高 18MB 的 L3 缓存。相关 CPU、GPU 与 NPU 架构细节已在英特尔 2025 年的 Tech Tour 活动上完整披露。在物理结构上，该芯片通过英特尔的 Foveros-S 先进封装，将一个计算 tile、一个 GPU tile 和一个 I/O tile 组装在无源基座 tile 之上，这种多裸片构成方式正是理解此次裸片级拆解的前提。

**「实际影响」** 对于评估 Intel Foundry 代工能力的潜在客户和硬件工程师而言，这份免费公开的拆解报告提供了独立于 Intel 官方口径的 18A 裸片与封装实物检验材料。此前有报道称，Intel 计划用 18A 节点生产 Panther Lake，而其在 18A 与 14A 之间的代工路线取舍以及与台积电的竞争定位都依赖 18A 节点的实际执行质量，因此拆解中的实测细节可能直接影响潜在代工客户对 Intel 的评估。读者可直接访问 SemiAnalysis 网站免费阅读完整报告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/intel-panther-lake-deep-dive-18a-compute-tile-cougar-cove-p-cores-darkmont-e-cores/">Intel Panther Lake Deep-Dive: 18 A Compute Tile With Cougar Cove...</a></li>
<li><a href="https://newsletter.semianalysis.com/p/intel-panther-lake-teardown">Intel Panther Lake Teardown , 18 A , BSPD, GAAFET, SemiAnalysis...</a></li>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-takes-the-wraps-off-panther-lake-first-18a-client-processor-brings-the-best-of-lunar-lake-and-arrow-lake-together-in-one-package">Intel takes the wraps off Panther Lake — first 18 A client processor...</a></li>
<li><a href="https://www.monexa.ai/blog/intel-corporation-foundry-strategy-shift-impact-on-INTC-2025-07-02">Intel Corporation Foundry Strategy Shift: Financial Impact ... | Monexa</a></li>
<li><a href="https://www.koreajoongangdaily.com/business/chasing-chip-king-tsmc-samsung-and-intel-chart-courses-nanometers-apart/12161474">Chasing chip king TSMC, Samsung and Intel chart courses...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#semiconductors`, `#chip-teardown`, `#process-nodes`, `#hardware`

---

<a id="item-tech-news-2"></a>
### [DeepSeek 弹性计算论文 DSec 引热议：据称 160 台服务器承载 38 万并发沙箱](https://arxiv.org/abs/2609.22978) ⭐️ 7.0/10

DeepSeek 的一篇题为《DeepSeek Elastic Compute（DSec）》的弹性计算论文（arXiv:2609.22978）于 2026 年 9 月 26 日登上 Hacker News，获得 158 分和 43 条评论，讨论面向 AI 基础设施与分布式系统领域的技术读者。据评论区用户 vblanco 转述，论文描述了在 160 台基于 AMD EPYC 的服务器节点上运行 38 万个并发沙箱的规模。由于本次材料未附论文正文，DSec 的具体架构与技术细节无法核实，上述数字目前仅为评论者对论文内容的转述，尚未得到独立验证。

hackernews · shenli3514 · 9月26日 18:22 · [社区讨论](https://news.ycombinator.com/item?id=49859112)

**「背景：智能体训练为何需要沙箱基础设施」** 沙箱指为代码执行提供隔离环境的基础设施，AI 智能体在训练时需要大量隔离环境来安全、并行地运行模型生成的代码和工具调用。据该论文的 arXiv 摘要，DSec 是一个已投入生产的沙箱平台，通过统一的 SDK 对外提供 FnCall、容器、microVM 和完整虚拟机（full-VM）四类沙箱后端。另有第三方报道称，该系统能以每秒超过 5,000 个的速度生成沙箱，用于支撑大规模的 AI 智能体训练。

**「影响」** 如果 Hacker News 讨论中引用的数字属实——38 万个并发沙箱运行在 160 台基于 EPYC 的服务器节点上——这一密度将超过 Modal 公开披露的 10 万+ 并发沙箱容量（其创建吞吐量实测基准约为 1,000 个/秒），对需要大规模运行 AI 代理沙箱的团队而言，可能影响其在托管沙箱平台与自建基础设施之间的成本和选型考量。不过该数字目前仅来自讨论区评论，论文原文未随本条消息提供，节点规格、负载假设与测量方法尚待核实，评估前应先查证论文细节。

**「社区讨论」** 讨论大多停留在论文外围而非技术内容本身：flowerlad 观察到该论文署名作者极多（页面未能全部显示，另有 31 人未列出），并推测列出全部员工可能是防止竞争对手精准挖走核心人才的策略；yipinwong 则好奇上百名作者如何协作完成这篇论文。将 38 万并发沙箱联想为“agent 蜂群”式攻击能力的评论属于发帖者个人臆测，评论区总体缺乏对论文技术内容的实质分析。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2609.22978">[2609.22978] DeepSeek Elastic Compute ( DSec ): A Sandbox ...</a></li>
<li><a href="https://cryptobriefing.com/deepseek-dsec-ai-agent-training/">DeepSeek reveals innovative method for training AI agents with...</a></li>
<li><a href="https://modal.com/resources/best-microvm-sandboxes-ai-code-execution">Best microVM Sandboxes for AI Code Execution in 2026 | Modal Blog</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#elastic compute`, `#sandboxing`, `#DeepSeek`, `#distributed systems`

---

<a id="item-tech-news-3"></a>
### [开源 XMPP 客户端 Conversations 退出 Google Play 并转为免费](https://gultsch.de/posts/breaking-up-with-google-play/) ⭐️ 7.0/10

开源 XMPP 客户端 Conversations 的开发者 Daniel Gultsch 于 2026 年 9 月 26 日在个人网站 gultsch.de 发文，宣布该应用将退出 Google Play 商店并转为免费应用。这篇题为《Breaking Up with Google Play》的文章说明了做出这一决定的原因。据条目分析，此事在 Hacker News 上引发大量讨论（638 分、251 条评论），讨论焦点集中在 Play 商店的分成费用、审核与开发者验证流程的摩擦，以及对单一分发平台的依赖。

hackernews · ezst · 9月26日 10:55 · [社区讨论](https://news.ycombinator.com/item?id=49855315)

**「背景」** Conversations 是开发者 Daniel Gultsch 于 2014 年推出的安卓开源即时通讯客户端，基于开放标准 XMPP。该应用长期在 Google Play 上以付费形式销售，虽然 F-Droid 的打包维护者早期征得其同意后一直提供免费安装包，但 Gultsch 并未在官方网站链接这一免费渠道，以便引导用户购买付费版本。2026 年 8 月，他已宣布该应用在 Google Play 上连续两天限时免费，建议想从其分支应用切换到官方版的用户趁机迁移，并向不了解 F-Droid 的亲友推荐这一免费获取渠道。

**「影响」** 此次调整的直接后果是，Conversations 的用户无法再通过 Google Play 安装或更新该应用，需要改用 F-Droid 或开发者直接分发 APK 等渠道。随之而来的兼容性风险是：据外部报道，Google 自 2026 年 3 月起要求认证 Android 设备上的侧载应用完成开发者验证，绕过需在开发者模式下等待 24 小时，且自 2026 年 9 月起，即便不经 Play 商店分发，所有 Android 开发者也须向 Google 注册——这意味着应用脱离 Play 商店后，开发者和最终用户面临的分发与安装门槛可能继续上升。

**「社区讨论」** 多位评论者认为问题不在于 15% 的商店抽成本身，而在于 Google 对开发者的支持与响应质量——例如有评论者称，由于公司的 IVR 支持电话号码无法通过 Google 要求的短信或人工即时接听验证，其产品尝试上架 Play 商店已超过一年仍未成功。另有评论者担心 Google 会继续收紧对 Play 商店外安装应用的限制，从目前的安装警告逐步演变为更繁琐的启用流程甚至全面禁止。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Conversations_%28software%29">Conversations (software) - Wikipedia</a></li>
<li><a href="https://gultsch.de/posts/breaking-up-with-google-play/">Daniel Gultsch | Breaking Up with Google Play: Why Conversations Is Now Free</a></li>
<li><a href="https://gultsch.social/@daniel/117109809726763499">Daniel Gultsch: &quot;#Conversations_im remains free…&quot; - Mastodon</a></li>
<li><a href="https://unstore.io/discover/best-google-play-store-alternatives/">Best alternatives to Google Play Store in 2026 — Unstore</a></li>
<li><a href="https://www.linkedin.com/posts/jeff-hall-33b7871_google-will-require-developer-verification-activity-7366450854045896705-zMsC">Google to require developer verification for Android apps | LinkedIn</a></li>

</ul>
</details>

**标签**: `#open-source`, `#android`, `#google-play`, `#app-store-policies`, `#xmpp`

---

<a id="item-tech-news-4"></a>
### [美国上诉法院 2:1 维持五角大楼将 Anthropic 列入军事合同黑名单](https://www.reuters.com/world/us-appeals-court-declines-block-pentagons-blacklisting-anthropic-2026-09-25/) ⭐️ 7.0/10

据报道，美国华盛顿特区联邦上诉法院于 9 月 25 日以 2 比 1 的投票裁定，维持五角大楼将 Anthropic 列为国家安全供应链风险、禁止其参与军事合同的决定。多数法官认为，鉴于 Anthropic 拒绝允许其产品被用于自主武器和大规模监控，五角大楼的相关担忧具有合理性。Anthropic 表示不同意该裁决，正考虑请求全体上诉法院法官复审；此前旧金山一名联邦法官曾依据另一部法律推翻该列名，并阻止政府对 Anthropic 实施更广泛禁令。

telegram · zaihuapd · 9月26日 05:19

**「争议背景」** 此次裁决源于 Anthropic 与美国国防部围绕 AI 使用限制的长期争端：Anthropic 拒绝允许其模型被用于自主武器和大规模监控，五角大楼随后以国家安全供应链风险为由，将其列入禁止参与军事合同的黑名单。此前，旧金山联邦地区法院曾依据另一部法律推翻该列名，并阻止政府对 Anthropic 实施更广泛禁令；路透社的背景报道也将本案定性为双方围绕 AI 安全保障条款不断升级的争端。

**「直接影响」** 对 Anthropic 及其潜在防务客户而言，禁止参与美国军事合同的限制在该裁决后继续生效，此前地区法院层面依据另一部法律取得的胜诉未能恢复其资格；在可能的全院复审有结果之前，其产品无法进入美国军方采购流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic%E2%80%93United_States_Department_of_Defense_dispute">Anthropic–United States Department of Defense dispute - Wikipedia</a></li>
<li><a href="https://www.reuters.com/world/how-anthropic-pentagon-dispute-over-ai-safeguards-escalated-2026-09-25/">Anthropic&#x27;s Pentagon blacklist upheld in US appeals court - Reuters</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#Anthropic`, `#military AI`, `#AI safety`, `#regulation`

---

<a id="item-tech-news-5"></a>
### [Excel 预览版首次支持单元格存放多个值](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/put-multiple-values-in-one-cell-with-lists-and-arrays-in-excel/4559395) ⭐️ 7.0/10

微软在 Microsoft 365 Insider 的 Beta 通道（Windows 版与 Mac 版 Excel）中预览「列表」与「单元格内数组」功能，这是 Excel 面世约 40 年来首次允许单个单元格存放多个值。用户可通过 Ctrl+J 快捷键或「插入 &gt; 列表」在单元格中写入以逗号或分号分隔的多个项目，并支持按单个条目进行筛选与计算；微软还同步新增 FLATTEN、HAS、HASANY、HASALL 四个函数用于处理数组。上述功能目前均为预览状态，正式发布前行为可能调整，微软建议暂勿将其用于重要工作簿。

telegram · zaihuapd · 9月26日 16:26

**「背景」** Excel 的底层数据模型自问世以来一直把每个单元格限定为单一值，微软官方博客也确认在约 40 年历史中“每个单元格只能放一个值”。受此约束，用户此前想在单元格中表达多项内容，只能保存用分隔符拼接的文本再自行拆分，或把数据摊开到多个单元格和区域里。据 Windows Forum 报道，此次 Beta 变更随新的兼容性版本 Compatibility Version 3 一同引入，微软于 2026 年 9 月 24 日公布了这一消息。

**「影响」** 需要在单元格中维护多值数据（如标签列表、逗号分隔字段）的用户，现在可以在 Windows 和 Mac 的 Beta 通道测试该功能：用 Ctrl+J 或「插入 &gt; 列表」录入内容，并配合 FLATTEN、HAS、HASANY、HASALL 对单个项目进行筛选与计算。但这仍是预览特性，微软建议暂不用于重要工作簿，且行为在正式发布前可能调整，因此关键业务流程和共享文件不应依赖这套新语法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcommunity.microsoft.com/blog/Microsoft365InsiderBlog/put-multiple-values-in-one-cell-with-lists-and-arrays-in-excel/4559395">Put multiple values in one cell with lists and arrays in Excel | Microsoft Community Hub</a></li>
<li><a href="https://windowsforum.com/news/excel-beta-adds-lists-and-nested-arrays-with-compatibility-version-3.445888/?amp=1">Excel Beta Adds Lists and Nested Arrays With Compatibility Version 3 | Windows Forum</a></li>
<li><a href="https://www.geeky-gadgets.com/multiple-values-one-excel-cell/">Excel Multiple Values in One Cell : Microsoft 365... - Geeky Gadgets</a></li>
<li><a href="https://www.xelplus.com/excel-lists-in-cells/">Excel Lists in Cells : Put Multiple Values in One Cell</a></li>

</ul>
</details>

**标签**: `#Excel`, `#Microsoft-365`, `#spreadsheets`, `#arrays`, `#data-analysis`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美国 10 年期国债收益率升至 5.23%，创 2007 年以来新高](https://www.cnbc.com/2026/09/26/10-year-treasury-yield-is-at-its-highest-in-19-years-how-we-got-here.html) ⭐️ 7.0/10

美国基准 10 年期国债收益率周五升至 5.23%，为 2007 年以来最高，而本月初还仅略低于 4.8%。麦格理集团策略师蒂埃里·维兹曼认为，政府为巨额赤字发债、企业为人工智能基建大举借债带来的债券供应激增，比顽固通胀更能解释这轮涨势，并警告收益率可能继续上行。

rss · CNBC Finance · 9月26日 13:30

**「背景」** 10 年期美国国债收益率是美国房贷利率和企业借贷成本的重要参考基准；密歇根大学 9 月调查显示，消费者预计未来一年通胀率为 4.6%，高于 8 月的 4%，而利率期货显示市场认为美联储 10 月加息的概率约为 64%（CME FedWatch 数据）。

**「影响」** 收益率上行会直接抬升美国房贷和企业借贷成本，并令债券相对股票更具吸引力，从而对股票估值构成压力。

**标签**: `#Treasury yields`, `#Federal Reserve`, `#inflation`, `#bond issuance`, `#AI capex`

---

<a id="item-finance-news-2"></a>
### [香港证监会与普华永道就恒大审计失职达成 10 亿港元和解](https://wallstreetcn.com/articles/3782573) ⭐️ 7.0/10

香港证监会就恒大审计失职与普华永道香港达成和解，普华永道不承认责任，但同意支付 10 亿港元用于补偿受影响的独立小股东。恒大清盘人已入禀法院要求撤销该和解，香港高等法院预计于 10 月底左右作出判决。

telegram · zaihuapd · 9月26日 07:18

**「背景」** 中国恒大因债务危机已进入清盘程序，普华永道是其多年审计机构。此次以和解款项直接补偿独立小股东的做法，在香港属于创新安排。

**「影响」** 恒大的独立小股东有望获得这笔 10 亿港元补偿；由于款项来自普华永道香港而非恒大财产，恒大债权人的申索优先次序不受影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wallstreetcn.com/articles/3782573">wallstreetcn.com/articles/3782573</a></li>

</ul>
</details>

**标签**: `#Evergrande`, `#PwC`, `#audit regulation`, `#SFC settlement`, `#liquidation litigation`

---

<a id="item-finance-news-3"></a>
### [大众因转向螺栓隐患全球召回约 286 万辆车](https://www.ithome.com/1/007/382.htm) ⭐️ 7.0/10

大众汽车集团证实，因转向系统固定螺栓可能腐蚀断裂、极端情况下可致转向失灵，将在全球预防性召回约 286 万辆汽车，其中德国约 96 万辆。此次召回涉及约 216 万辆大众品牌汽车和近 70 万辆奥迪 Q3，公司称这是预防性措施，目前暂无相关伤人事故报告。

telegram · zaihuapd · 9月26日 10:01

**「背景」** 转向固定螺栓的作用是将转向部件固定在车身上。德国联邦机动车管理局（KBA）指出，腐蚀可能导致该螺栓断裂并造成转向失效，此次召回涉及高尔夫、途观、途安及奥迪 Q3 等车型。

**「影响」** 全球约 286 万辆大众品牌车及奥迪 Q3 的车主（其中德国约 96 万辆）需按召回安排检修车辆，因为转向机固定螺栓可能经多年水分和道路融雪盐侵蚀而断裂，极端情况下导致转向失控。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.instagram.com/moretify/">好用的分享都在这里 Moretify Sdn. Bhd. 201701037954 (1252125-V)</a></li>
<li><a href="https://www.guancha.cn/qiche/2026_09_26_902327.shtml">转 向 螺 栓 可能 腐 蚀 断 裂 ， 大 众 、 奥 迪 全 球 召 回 约 286 万 辆 汽 车</a></li>
<li><a href="https://ground.news/article/volkswagen-to-recall-286-million-vw-audi-models-over-potential-steering-problem_258437">Volkswagen to Recall 2.86 Million VW, Audi Models over Potential Steering Problem</a></li>
<li><a href="https://www.euronews.com/2026/09/25/over-28-million-audi-and-volkswagen-vehicles-face-recall-worldwide">Over 2.8 million Audi and Volkswagen vehicles face recall worldwide | Euronews</a></li>

</ul>
</details>

**标签**: `#automotive recall`, `#Volkswagen`, `#Audi`, `#product safety`, `#consumer impact`

---