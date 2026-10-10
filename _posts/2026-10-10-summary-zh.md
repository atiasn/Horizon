---
layout: default
title: "Horizon Summary: 2026-10-10 (ZH)"
date: 2026-10-10
lang: zh
---

> 从 44 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [Cloudflare 收购 Deno，运行时仅获一年维护期](#item-tech-news-1) ⭐️ 9.0/10
2. [Telegram Desktop 7.2.9 修复 tg:// 链接任意文件窃取漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [Oxide Computer 宣布完成 4.45 亿美元 D 轮融资](#item-tech-news-3) ⭐️ 7.0/10
4. [JetBrains 发布开源编程模型 Mellum 2.1：12B MoE 架构、Apache 2.0 许可](#item-tech-news-4) ⭐️ 7.0/10

**科技博客**
1. [软件的“半人马时代”或将持续数十年](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [星链竞争引发电信股盘中暴跌，T-Mobile 单日跌 13%](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Cloudflare 收购 Deno，运行时仅获一年维护期](https://deno.com/blog/cloudflare) ⭐️ 9.0/10

Deno 团队在官方博客宣布公司已被 Cloudflare 收购。根据公告，Deno 运行时将再获得一年维护，以每月发布的节奏提供缺陷修复和安全更新，之后 Cloudflare 将结束对 Deno 运行时的开发；Deno 仍保持开源，并欢迎其他愿意继续开发的人接手。公告发布前，Deno 团队已于 2026 年 8 月发布了 celld 的首个版本，即 Cloudflare Workers 中 Durable Objects 模式的开源实现。公告未提及任何已确定的接手开发方。

hackernews · ilreb · 10月9日 13:03 · [社区讨论](https://news.ycombinator.com/item?id=50019911)

**「Deno 与 Cloudflare 的渊源」** Deno 是由 Node.js 原作者 Ryan Dahl 创立的 JavaScript/TypeScript 运行时，以默认沙箱化的权限模型著称，其生态还延伸出 Deno Deploy 托管平台和 JSR 包注册表。据 The New Stack 报道，在此次交易中，Deno Deploy 将在六个月内关闭并向付费客户提供迁移协助，JSR 包注册表则将继续由 Cloudflare 运营。这次收购早有铺垫：Deno 团队已于今年 8 月发布了 celld 的首个版本，对 Cloudflare Workers 的 Durable Objects 模式进行了开源实现。

**「影响」** 在生产环境使用 Deno 的团队约有一年时间规划迁移：维护期内的月度更新只包含缺陷修复和安全更新，之后除非有第三方接手，运行时将不再获得官方支持。由于 Deno 保持开源，社区分支或接手在技术上可行，但目前尚无已宣布的接手方。

**「社区讨论」** 有评论者将这笔交易称为&quot;变相收购团队&quot;（acquihire），认为其效果等同于关停 Deno 开发；另一些人则肯定 Deno 的历史作用——促使 Node 在 TypeScript 支持和标准跟进上现代化——并希望 Cloudflare 的 workerd 能吸收 Deno 的安全沙箱机制。也有长期用户把 Deno 转向 npm 兼容视为偏离最初&quot;从第一性原理重建 Node&quot;愿景的转折点，这些均属个人观点而非公告内容。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thenewstack.io/cloudflare-acquires-deno-ryan-dahl/">Cloudflare acquires Node.js creator’s startup that... - The New Stack</a></li>

</ul>
</details>

**标签**: `#javascript`, `#deno`, `#cloudflare`, `#acquisition`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Telegram Desktop 7.2.9 修复 tg:// 链接任意文件窃取漏洞](https://telegram.me/zaihuapd/44307) ⭐️ 8.0/10

据 OpenNET 报道，Telegram Desktop 7.2.9 以下版本存在编号 CVE-2026-107181 的漏洞：用户点击恶意 tg:// 链接后，本地文件可在无任何确认提示的情况下被悄悄窃取。漏洞根源在于链接中的分号未做转义、被解析为独立的 IPC 命令，攻击者可借助 interpret: 处理器盗取文档、浏览器会话、SSH 密钥、加密钱包等任意文件。官方已在 7.2.9 版本中修复该问题，建议用户尽快升级、警惕来源不明的 tg:// 链接，并启用本地密码保护。需注意该消息来自 Telegram 频道对 OpenNET 报道的转述，而非官方公告原文。

telegram · zaihuapd · 10月9日 09:51

**「tg:// 协议链接与 IPC 解析」** tg:// 是 Telegram 桌面客户端注册的专有协议链接，用户点击后，链接内容会交由客户端通过其内部 IPC（进程间通信）接口解析执行，而这类接口通常依赖分隔符把一次传入的数据拆分为逐条命令。独立漏洞数据库 Rapid7 与 SecurityVulnerability.io 均将 CVE-2026-107181 归类为 Core::Sandbox 组件中的 IPC 记录分隔符注入，与该频道转述的“分号未转义、被当作独立 IPC 命令”成因一致；dbugs 数据库还将其标记为已在野利用。

**「立即升级至 7.2.9 并采取缓解措施」** 对仍在运行 7.2.9 之前版本的用户，这是已被在野利用的现实威胁：CVE-2026-107181 被标记为在野利用，一次点击恶意 tg:// 链接即可让攻击者静默读取磁盘上的任意文件并外传，tdata 登录会话、SSH 密钥、浏览器会话和加密钱包均在波及范围；OpenNET 的复现示例还显示，受害者仅加入一个群组就可能触发会话文件被写入预设目录。最直接的应对是立即升级到 7.2.9；暂无法升级的用户可启用“每次下载前询问保存位置”设置、限制谁能将账号拉入群组，并避免点击来源不明的 tg:// 链接。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dbu.gs/vulnerability/PT-2026-107506">CVE - 2026 - 107181 — Telegram Telegram Desktop | dbugs</a></li>
<li><a href="https://securityvulnerability.io/vulnerability/CVE-2026-107181">CVE - 2026 - 107181 : IPC Record-Separation Injection Vulnerability in...</a></li>
<li><a href="https://www.rapid7.com/db/vulnerabilities/cve-2026-107181/">CVE - 2026 - 107181 : Telegram ... | Rapid7 Vulnerability Database</a></li>
<li><a href="https://beaksec.github.io/posts/telegram-desktop-one-click-account-takeover/">Telegram Desktop : one - click account takeover via IPC... | beaksec</a></li>
<li><a href="https://dbu.gs/vulnerability/CVE-2026-107181">CVE-2026-107181 — Telegram Telegram Desktop | dbugs</a></li>
<li><a href="https://www.opennet.ru/opennews/art.shtml?num=66431">Уязвимость в Telegram Desktop , позволяющая отправить...</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerability-disclosure`, `#telegram`, `#desktop-applications`, `#ipc`

---

<a id="item-tech-news-3"></a>
### [Oxide Computer 宣布完成 4.45 亿美元 D 轮融资](https://oxide.computer/blog/our-445m-series-d) ⭐️ 7.0/10

Oxide Computer 于 2026 年 10 月 9 日在官方博客宣布完成 4.45 亿美元的 D 轮融资。该公司主营面向本地部署（on-premises）场景的机架级服务器硬件，这笔大额融资被视为对本地部署机架级计算方向的强市场验证信号。公告在 Hacker News 上引发大量关注（603 分、270 条评论），社区反响总体积极。目前公开信息未披露投资方名单、公司估值或资金的具体用途。

hackernews · ahlCVA · 10月9日 13:12 · [社区讨论](https://news.ycombinator.com/item?id=50020014)

**「背景」** Oxide Computer 是一家销售本地部署（on-premises）整机柜式计算机的硬件公司，成立至今约七年，投资方 Eclipse 在此期间已多次领投其融资轮次。据 FundedIQ 记录，Oxide 累计融资已达 7.42 亿美元、共四轮，本轮规模远超其追踪的硬件公司过去两年约 1000 万美元的中位数轮次。

**「影响」** 对正在评估本地部署机架级服务器的企业而言，一家获得大额资本支持的供应商降低了从初创公司采购硬件的财务风险。不过公告本身未说明资金用途，产能扩张或产品路线上的实际变化仍需后续观察。

**「社区讨论」** 评论总体正面，多位用户称赞 Oxide 的产品与对外沟通风格；用户 arpinum 则质疑公司为何选择股权融资而非可覆盖客户订单的贸易融资等债务方式，并猜测这笔资金或许与锁定 AMD 等供应商的长期订单有关——此为个人推测，公告并未证实。另有用户 activexray 反映其应聘流程耗时极长且数月未收到任何反馈。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fundediq.co/oxide-computer-company-oxide-computer-funding/">Oxide Computer Company: Funding , Investors &amp; Team... | FundedIQ</a></li>
<li><a href="https://oxide.computer/blog/our-445m-series-d">Our $ 445 M Series D | Oxide Computer Company</a></li>

</ul>
</details>

**标签**: `#hardware`, `#funding`, `#infrastructure`, `#datacenter`, `#startups`

---

<a id="item-tech-news-4"></a>
### [JetBrains 发布开源编程模型 Mellum 2.1：12B MoE 架构、Apache 2.0 许可](https://blog.jetbrains.com/ai/2026/10/mellum2-1-gets-to-work-a-fast-open-model-for-coding-agents/) ⭐️ 7.0/10

JetBrains 发布开源编程模型 Mellum 2.1，采用 12B 总参数的混合专家（MoE）架构，每次推理仅激活 2.5B 参数，并以 Apache 2.0 许可开放权重。据官方博客介绍，该模型通过真实环境中的强化学习训练，能够探索代码库、编辑文件并检查修改结果，面向在本地运行编程代理（coding agent）的场景。模型权重已在 Hugging Face 上提供下载。需要说明的是，此次公告未附带基准测试数据，上述能力均为官方陈述，尚无独立评测佐证。

telegram · zaihuapd · 10月9日 07:30

**「背景」** 混合专家（MoE）是一种稀疏激活架构：模型保有较大的总参数量，但推理时每个 token 只调用其中一小部分参数，因此能在保持模型能力的同时大幅降低单步计算开销，这也是 Mellum 2.1 被定位为可在本地快速运行的编程代理模型的技术基础。代理式（agentic）编码与单次代码补全不同，要求模型在多步流程中自主探索代码库、编辑文件并验证修改，通常还需在执行前进行显式推理；有第三方报道将 Mellum 2.1 描述为这类具备推理能力的“thinking”模型。

**「实际影响」** 对希望在本地或自有基础设施上运行编程代理的开发者和团队而言，Apache 2.0 许可允许商用、修改与再分发，权重可直接从 Hugging Face 获取并接入现有代理工作流，无需依赖专有模型 API。由于官方未公布基准测试结果，建议在自身代码库和实际任务上先行验证效果，再决定是否投入生产使用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://theopenweights.com/news/mellum2-1-12b-a2-5b-thinking-e9kt">JetBrains ships Mellum 2 . 1 , a reasoning MoE for code</a></li>
<li><a href="https://www.marktechpost.com/2026/10/08/jetbrains-releases-mellum2-1-a-12b-moe-open-model-for-coding-agents/">JetBrains Releases Mellum 2 . 1 : A 12 B MoE Open Model for Coding ...</a></li>

</ul>
</details>

**标签**: `#open-source-models`, `#coding-agents`, `#JetBrains`, `#mixture-of-experts`, `#code-generation`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [软件的“半人马时代”或将持续数十年](https://seangoedecke.com/softwares-centaur-age-may-last-decades/) ⭐️ 6.0/10

rss · Sean Goedecke · 10月10日 00:00

**「背景」** AI 编程工具的快速演进让许多工程师担心彻底自动化已近在眼前。作者借用国际象棋“半人马”（人机组合胜过任何单独一方）的概念，主张软件工程自 2022 年起进入了人机协作占主导的时代。

**「方案」** 这条演进线从 Copilot 的 AI 补全、与 GPT-4 对话，推进到 2024 年 Cursor 的 Agent 模式与 2025 年初的 Claude Code；2025 年 11 月 Claude Opus 4.5 发布后，在他看来智能体已可靠到可完全无人监督地运行，只是输出仍需人工审查，且错误更多是对齐问题——如过度设计、偏离组织技术价值观——而非常规 bug。他的核心判断是：单干的工程师已不可能胜过人机组合，但无人监督的智能体也尚未做到，他见过的所有令人印象深刻的 LLM 成果背后都有称职的工程师掌控。至于这个时代会持续多久，他权衡了多组正反论据：国际象棋更简单、更易用自我对弈学习，但软件更有利可图、资金投入多出多个数量级；“解决”软件工程反而会制造更多待做的工作，而通用 AI 的涟漪效应又可能冲击经济与就业。他承认自己并不真正知道答案，但认为合理的默认假设是参照国际象棋——其半人马时代持续约二十年，而织袜机与人组合胜过手工织工的时代则长达两百年。据此他建议：不要转行，要拥抱人机协作，因为 AI 不是昙花一现，泡沫破裂也不会终结它；同时想清人类还能贡献什么价值——2023 年是技术专长，如今他个人认为是对齐，也有人主张是品味，但尚无定论。

**「启示」** 作者的结论是：软件的半人马时代很可能像国际象棋那样持续数十年，工程师仍有时间完成整个职业生涯，应当拥抱人机协作并想清自身价值，而不是为一个尚未到来的全自动化末日提前恐慌。

**标签**: `#AI coding agents`, `#human-AI collaboration`, `#software engineering careers`, `#LLMs`, `#industry forecasting`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [星链竞争引发电信股盘中暴跌，T-Mobile 单日跌 13%](https://www.cnbc.com/2026/10/09/stocks-making-the-biggest-moves-midday-tmus-vz-t-cci-teva.html) ⭐️ 7.0/10

10 月 9 日美股盘中，SpaceX 宣布升级星链（Starlink）手机直连服务、加剧对传统电信商的竞争担忧，T-Mobile 股价重挫 13%，AT&amp;T 与 Verizon 各跌 10%，基站运营商 Crown Castle 则逆势上涨 12%。同日其他显著波动包括：美国医保与医疗补助服务中心（CMS）公布 2027 年 Medicare 星级评级后，Humana 因最大合同评级上调大涨 12%、Alignment Healthcare 跌近 14%；据日经亚洲报道，苹果将 iPhone 18 Pro 系列 10 月生产订单较原计划削减 15%；达美航空三季度调整后每股盈利 1.72 美元、低于分析师预期的 1.75 美元，并因燃油成本上升下调全年盈利指引。

rss · CNBC Finance · 10月9日 18:57

**「背景」** SpaceX 过去主要与传统电信商合作、用卫星填补地面网络盲区，但近期宣布收购最多 14 兆赫兹的低频段频谱，计划让 Starlink 直接成为美国主要移动运营商，这引发了市场对正面竞争的担忧。另一大波动源于政策面：美国联邦医疗保险优势计划（Medicare Advantage，由商业保险公司运营的联邦医保计划）的星级评分决定保险公司能获得多少政府奖金，Humana 最大合同评级上调，而 Alignment Healthcare 在加州的最大合同从 4 星降至 3.5 星。

**「影响」** 美国电信运营商的投资者面临 SpaceX 星链直连手机服务引发的竞争性重估，信号塔公司虽被资金视为潜在受益方而大涨，但市场分析指出星链对塔企的实际影响仍完全未知。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/tech-policy/2026/10/starlink-spectrum-deal-boosts-musk-plan-to-beat-att-t-mobile-and-verizon/">Starlink spectrum deal boosts Musk plan to beat AT &amp; T , T - Mobile , and...</a></li>
<li><a href="https://www.phonescoop.com/articles/article.php?a=23799">SpaceX Ramps up Mobile Ambitions with Radio Spectrum Purchase</a></li>
<li><a href="https://www.statnews.com/2026/10/09/medicare-advantage-insurers-star-ratings-2027-humana-alignment/">Medicare Advantage insurers get new quality ratings , and bonuses...</a></li>
<li><a href="https://www.tradingview.com/news/stocktwits:789660826094b:0-hum-stock-soars-alhc-sinks-as-cms-star-ratings-redraw-2028-bonuses/">HUM Stock Soars, ALHC Sinks As CMS Star Ratings Redraw 2028...</a></li>
<li><a href="https://seekingalpha.com/article/4924982-crown-castle-the-pivotal-unknown">Crown Castle : The Pivotal Unknown (NYSE:CCI) | Seeking Alpha</a></li>

</ul>
</details>

**标签**: `#telecom-stocks`, `#SpaceX-Starlink-competition`, `#Medicare-Advantage-Star-Ratings`, `#earnings`, `#midday-market-movers`

---