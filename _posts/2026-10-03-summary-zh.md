---
layout: default
title: "Horizon Summary: 2026-10-03 (ZH)"
date: 2026-10-03
lang: zh
---

> 从 37 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [新 AI 系统以约 1/34 对局量超越最强 Stratego 玩家](#item-tech-news-1) ⭐️ 8.0/10
2. [Greg Kroah-Hartman：LLM 报告的 79 个内核漏洞大多站不住脚](#item-tech-news-2) ⭐️ 8.0/10
3. [Redis 作者发布本地 LLM 推理工具 DwarfStar（ds4）](#item-tech-news-3) ⭐️ 7.0/10
4. [arXiv 限投新规：每位提交者每月最多 2 篇](#item-tech-news-4) ⭐️ 7.0/10
5. [苹果宣布收紧 macOS「完全磁盘访问」权限，防范 AI 助手滥用](#item-tech-news-5) ⭐️ 7.0/10

**科技博客**
1. [超级说服将以行贿的面目出现](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [疲软就业报告公布后 交易员大幅下调美联储 10 月加息概率](#item-finance-news-1) ⭐️ 7.0/10
2. [Bitget CEO 称对追回 3.88 亿美元被盗资金不抱太大期望](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [新 AI 系统以约 1/34 对局量超越最强 Stratego 玩家](https://arstechnica.com/science/2026/10/ai-finally-beat-the-best-stratego-player-in-history-and-did-it-on-a-budget/) ⭐️ 8.0/10

据 Ars Technica 报道，一个新 AI 系统在棋子信息大部分隐藏的经典桌游 Stratego 上击败了史上最强玩家，相关成果发表于 Nature 论文，并附有 arXiv 预印本。报道援引的数据显示，该系统训练所用对局数约为 DeepNash 的 1/34，最终棋力仍明显更强；DeepNash 是 DeepMind 于 2022 年推出的系统，此前已率先让 AI 达到大师级 Stratego 水平。因此这项工作的核心进展是在既有成果上大幅提升训练效率，而非首次攻克该游戏。文中效率与棋力数字为论文作者报告的自述评估结果，目前尚无独立测试数据佐证。

hackernews · PaulHoule · 10月2日 14:11 · [社区讨论](https://news.ycombinator.com/item?id=49933740)

**「背景」** Stratego（战略棋）是一种在 10×10 棋盘上进行的双人策略棋类游戏，每方指挥 40 枚棋子，且棋子的等级身份对对手隐藏，属于典型的不完全信息博弈——与完全信息棋类不同，AI 难以通过向前搜索推演对手的隐藏布局。此前的标志性成果是 DeepMind 的 DeepNash，它通过强化学习方法使 AI 达到了 Stratego 的专家级对局水平。因此，本次报道的新系统属于在 DeepNash 基础上对训练效率和棋力的改进，而非首次攻克该游戏。

**「影响」** 对研究不完全信息博弈的开发者和研究者而言，论文描述的 Ataraxos 系统确立了一套在大规模隐藏信息下依然有效的强化学习与搜索设计模式，可作为后续工作的可复用框架；同时据引述报道，其训练所需对局数比此前达到人类专家水平的 DeepNash 少约 34 倍且棋力更强，这意味着在自对弈模拟成本高昂的隐藏信息任务上，此类训练方法的可行性显著提高。

**「社区讨论」** 评论中最具实质性的观点来自 janalsncm，他认为约 34 倍的样本效率提升才是关键贡献：在隐藏信息游戏中，一步棋的好坏取决于你无法获知的对手信息，传统“如果我这步、对方那步”的前瞻搜索难以执行，因此用更少对局学会且棋力更强才真正重要。dmurray 则以个人感想回应，称自己原打算做出第一个超越 DeepMind 2022 年成果的取胜机器人，没想到这么快就被人抢先。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Stratego">Stratego - Wikipedia</a></li>
<li><a href="https://www.youtube.com/watch?v=3vO45gcEbRs">AI beats us at another game: STRATEGO | DeepNash paper explained</a></li>
<li><a href="https://www.researchgate.net/publication/415037550_Scalable_decision-making_for_games_of_imperfect_information">(PDF) Scalable decision-making for games of imperfect information</a></li>
<li><a href="https://www.nature.com/articles/s41586-026-11036-y?error=cookies_not_supported&amp;code=99150def-d132-4ca6-8dde-5d145b1e2185">Scalable decision-making for games of imperfect information | Nature</a></li>

</ul>
</details>

**标签**: `#artificial-intelligence`, `#imperfect-information-games`, `#game-ai`, `#reinforcement-learning`, `#research`

---

<a id="item-tech-news-2"></a>
### [Greg Kroah-Hartman：LLM 报告的 79 个内核漏洞大多站不住脚](https://www.youtube.com/watch?v=NnV_cWeoo5Q) ⭐️ 8.0/10

Linux 内核维护者 Greg Kroah-Hartman 在 Kernel Recipes 2026 演讲《Security in the LLM Age》（视频已发布于 YouTube，并于 2026 年 10 月 2 日被提交至 Hacker News）中逐项核查了 Anthropic Mythos 模型此前高调宣传的 79 个 Linux 内核漏洞，结论是绝大多数并不成立或早已修复。据其演讲幻灯片，这 79 个&quot;漏洞&quot;中 24 个完全没有细节（仅称&quot;会崩溃&quot;），14 个根本不是 bug，3 个数据纯属编造，15 个在最新版本中已被修复（11 个由其他开发者、4 个由 Anthropic 自己修复），真正需要修复的只有 20 个——其中 7 个还以&quot;假定恶意文件系统镜像&quot;为前提——他估算全部修复合计约相当于一小时的内核开发工作量。他还指出，Mythos 的发现方式本质上是对过去几十年内核补丁做模式匹配、再套用到其他代码路径，且在公开这些 CVE 时没有引用最初修复相关问题的内核开发者。

hackernews · usernomdeguerre · 10月2日 02:51 · [社区讨论](https://news.ycombinator.com/item?id=49929391)

**「背景」** Greg Kroah-Hartman 长期担任 Linux 内核稳定分支的维护者，Kernel Recipes 是面向内核开发者的年度技术会议，而此次演讲批评的对象是 AI 模型 Mythos 此前公开宣传发现的一批共 79 个 Linux 内核漏洞。《The Register》曾在 2026 年 3 月报道，Kroah-Hartman 当时对 AI 辅助内核开发的评价相当正面：他肯定了现供职于 Meta 的资深内核开发者 Chris Mason 在 eBPF 和网络子系统中长期运行 AI 评审流程的开创性工作，并提到 systemd 项目也在其全 C 代码库上使用同类工具。结合这一背景，他此次质疑的重点在于这批漏洞报告的质量与出处引用，而非全盘否定 AI 参与内核开发。

**「影响」** 对内核维护者而言，直接后果是甄别负担：这批 79 份报告中约四分之三最终无需处理，却仍要消耗人工核验时间，而 Linux 团队此前已在应对 AI 辅助 bug 报告带来的数量增长，较小的维护团队可能更难应付 \[tool-3-1\]。风险还会延伸到代码本身——此前已有内核维护者依据来源可疑的 AI 安全报告移除代码，云安全联盟（CSA）也曾提醒 CISO 为 Mythos 报告之后的漏洞利用浪潮做准备 \[tool-3-2\]。可行的应对是在采信厂商公布的大规模 AI 漏洞发现前要求可验证证据，例如对提交做确定性校验，让每份报告附带可自我验证的复现或补丁 \[tool-3-3\]。

**「社区讨论」** 评论中不少人支持这一批评：devy 称 Mythos 只是模式匹配历史补丁且未引用最初修复 CVE 的内核开发者，认为 Anthropic 重蹈了 OpenAI 在引用原始工作上的问题；djoldman 则引用 Greg KH 的话，指出 AI 实验室一边宣称模型危险到需限制访问、一边拿出这种经不起推敲的安全成果，存在明显反差。也有不同看法：blinkingled 认为 Linux 内核开源意味着这些结论可被独立验证（不同于闭源平台的修复声明），并预期未来针对内核特化训练的模型可能让漏洞发现与修复更快、更准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theregister.com/2026/03/26/greg_kroahhartman_ai_kernel">Linux kernel czar says AI bug reports aren&#x27;t slop anymore • The Register</a></li>
<li><a href="https://www.theregister.com/software/2026/04/06/ai-slop-got-better-so-now-maintainers-have-more-work/5223172">AI slop got better, so now maintainers have more work</a></li>
<li><a href="https://runtimeai.io/blog/2026-04-23-ai-security-incidents.html">AI Security Incidents: Week of April 23, 2026 — RuntimeAI</a></li>
<li><a href="https://www.linkedin.com/posts/rjt-gupta_linux-kernel-maintainers-are-swamped-with-activity-7492003706947665921-fXyW">Linux kernel maintainers are swamped with hundreds of AI ...</a></li>

</ul>
</details>

**标签**: `#linux-kernel`, `#security`, `#llms`, `#vulnerability-reporting`, `#ai-industry`

---

<a id="item-tech-news-3"></a>
### [Redis 作者发布本地 LLM 推理工具 DwarfStar（ds4）](https://dwarfstar.sh/) ⭐️ 7.0/10

Redis 的创造者 Salvatore Sanfilippo（antirez）发布了开源本地大模型推理工具 DwarfStar（ds4），面向希望在个人硬件上运行 LLM 的用户，项目主页为 dwarfstar.sh，代码位于 GitHub 的 antirez/ds4 仓库。据 Hacker News 读者转述的仓库说明，它不要求配备大内存的 Mac，SSD 即可运行；评论者还提到 ds4 近期加入了对 Vision 和 Qwen 模型的支持。该项目在 Hacker News 上获得约 155 分和 40 条评论，衍生生态已开始出现，包括以共享库形式提供 FFI 的分支及 Go 绑定 ds4go，以及一个受其启发、面向 Intel Xe-LP（无 XMX）笔记本的独立推理引擎 xenolith。不过，评论者关心的工具调用能力和吞吐表现（有人称若接近 50 tokens/秒将显著改变个人 LLM 领域）在现有材料中均无实测数据，仍属未经验证的说法。

hackernews · fibo · 10月2日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=49936575)

**「背景」** ds4\(DwarfStar 4\)出自 Redis 创造者 Salvatore Sanfilippo\(网名 antirez\)之手,这一作者背景是其作为新工具迅速获得社区关注的重要原因。据项目页面与官方硬件文档,该引擎最初针对 DeepSeek V4 Flash 优化,支持的模型覆盖 DeepSeek V4/V4.1、GLM 5.x 和 Qwen3.8,并面向高内存机器设计。其技术路线的关键是 SSD 流式加载:可运行超出内存容量的模型,例如在 128GB 系统上运行完整版 GLM 5.x\(非 Flash 版\),并支持跨两台 Mac 的 TP/RDMA 层级流水线推理。

**「影响」** 对想在本地运行大模型的用户而言，如果仓库说明属实，用 SSD 替代大内存即可运行将降低本地推理的硬件门槛；有意采用者可先在 GitHub 仓库（antirez/ds4）确认当前支持的模型与平台，并在自己的负载上实测吞吐速度和工具调用表现，因为社区目前没有公开的量化数据可供参考。

**「社区讨论」** 评论区既有生态建设也有未决问题：一位维护者发布了以共享库形式支持 FFI 的 ds4 分支和 Go 绑定 ds4go，另一位开发者受其启发编写了面向 Intel Xe-LP 32GB 笔记本的推理引擎 xenolith（目前仅支持量化版 Gemma-4）；一位用户报告在 128GB 内存的 Mac 上连续一周多运行 Qwen 3.8 flash next，称速度快、上下文窗口很长，但偶尔出现“忘记前文”的情况，作者猜测可能来自所搭配的代理框架。关于工具调用是否有实测数据或视频演示的提问，评论中未见有人给出答复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/antirez/ds4">GitHub - antirez / ds 4 : DeepSeek 4 Flash and PRO local inference ...</a></li>
<li><a href="https://dwarfstar.sh/hardware/">ds 4 Hardware: Local , Streamed and Distributed Inference</a></li>
<li><a href="https://www.aipotluck.org/product/ds4">ds 4 — Inference code — Open Source AI Map</a></li>

</ul>
</details>

**标签**: `#local-llm-inference`, `#open-source`, `#machine-learning`, `#inference-engine`, `#community-ecosystem`

---

<a id="item-tech-news-4"></a>
### [arXiv 限投新规：每位提交者每月最多 2 篇](https://www.huxiu.com/article/4895127.html) ⭐️ 7.0/10

据虎嗅报道，预印本平台 arXiv 自 10 月 1 日起实施新规：每位提交者在每个自然月内最多提交 2 篇论文，限制覆盖计算机、数学、物理等全部学科，且被拒稿件同样占用当月额度。报道将原因归结为投稿量激增——9 月投稿达 40,363 篇，创 35 年新高，其中 AI 分类论文两年间增长超过 6 倍，大量低质量 AI 生成论文挤占了人工审核资源。对多作者论文，只有实际执行提交的作者计入额度，其余合著者不受影响。该消息目前来自媒体转述，具体执行细节仍需以 arXiv 官方公告为准。

telegram · zaihuapd · 10月2日 06:21

**「背景：预印本机制与 arXiv 的审核模式」** arXiv 是计算机、数学、物理等领域研究者广泛使用的预印本平台，论文通常在正式同行评审完成之前先行公开，而稿件审核长期依赖志愿版主完成。arXiv 官方博客已于 10 月 1 日发布政策更新公告，证实了此次限投措施，并补充规定每位提交者同一时刻最多只能有 3 篇处于活跃状态的稿件，同时将政策目的表述为在作者之间公平分配志愿版主的审核时间。

**「影响」** 对月产多篇论文的课题组而言，投稿需要按月错峰规划，并应把实际提交人指定为当月额度尚未用尽的合著者；由于被拒稿件也消耗额度，提交前的自查与筛选变得比以往更为关键。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.arxiv.org/2026/10/01/updated-rate-limit-policy/">arXiv has updated its rate limit policy for all submitters .</a></li>

</ul>
</details>

**标签**: `#arxiv`, `#academic-publishing`, `#ai-generated-content`, `#research-policy`, `#preprints`

---

<a id="item-tech-news-5"></a>
### [苹果宣布收紧 macOS「完全磁盘访问」权限，防范 AI 助手滥用](https://arstechnica.com/security/2026/10/apple-changes-full-disk-access-permissions-to-curb-abuse-from-ai-agents/) ⭐️ 7.0/10

苹果宣布将调整 macOS 的 Full Disk Access（完全磁盘访问）授权方式，要求用户采取更明确的主动操作。该权限覆盖面极广，获准应用可读取文件、邮件、信息和浏览记录；苹果称部分开发者的使用方式可能让用户在未充分了解的情况下暴露隐私，而日益自主的 AI 助手会放大这一风险。报道将此举与 Meta 的 Muse AI 助手读取 Apple Messages 数据的争议联系起来——Meta 称须同时开启系统权限和应用内信息连接器——但苹果未点名 Meta。苹果既未公布具体改动细节，也未给出推出时间，因此这仍是官方意向声明，不代表新规则已全面上线。

telegram · zaihuapd · 10月3日 02:03

**「背景：什么是完全磁盘访问」** 完全磁盘访问（Full Disk Access）是 macOS 中覆盖范围极广的系统级权限，获批应用可读取文件、邮件、信息和浏览记录，其范围远超访问用户明确选择的单个文档。这种粗粒度授权与 App Sandbox「通过限制应用能力来限制被攻陷软件危害」的设计思路形成对比。此外，社区讨论中有开发者指出，主流 AI 代理系统通常按项目或文件夹划分文件权限，访问项目外文件需显式请求，部分还内置更强的沙箱，与 macOS 的全盘授权模式反差明显。

**「影响」** 对依赖完全磁盘访问的应用（如备份工具、终端程序和 AI 助手类软件）而言，用户授权环节未来可能新增明确的操作步骤，开发者需重新评估自身是否确需这一宽泛权限。由于苹果尚未公布改动细节和时间表，相关方现阶段无法进行针对性适配，只能关注后续开发者公告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/civis/threads/apple-changes-full-disk-access-permissions-to-curb-abuse-from-ai-agents.1515068/">Apple changes full - disk access permissions to curb abuse from AI ...</a></li>
<li><a href="https://ybuild.ai/en/blog/apple-full-disk-access-ai-onboarding-trust">Apple &#x27;s Full Disk Access Warning: Design an AI Assistant... - Y Build</a></li>

</ul>
</details>

**标签**: `#macOS`, `#security`, `#privacy`, `#AI agents`, `#Apple`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [超级说服将以行贿的面目出现](https://seangoedecke.com/superpersuasion-will-look-like-bribery/) ⭐️ 7.0/10

rss · Sean Goedecke · 10月3日 00:00

**「背景」** “超级说服”是 AI 安全圈的老命题：足够聪明的 AI 能否说服人类放它出笼、不去按关闭开关。作者 Sean Goedecke 指出，这一担忧的经典图景源自理性主义者式的想象——AI 抛出无懈可击的论证，迫使人类接受结论。

**「方案」** 作者认为，多数人并非会为完美论证所动：普通人面对通往荒谬结论的严密推理只会一笑置之，说服他们靠长期建立的信任与好感，通常还得面对面。但这不意味着超级说服是伪命题。他举 Ben Shindel 的预测市场为例：Shindel 承诺除非被说服否则按 NO 结算，押“YES”者便有动机来劝他，而他最终确实改判——一半靠与某位押注者线下面基的融洽，一半靠对方许诺赢钱后捐出善款，即贿赂。作者据此主张，AI 未必能建立交情，却显然会行贿，而且已经平凡地发生：人们排队给它电脑、钱包和网络接入以求帮助，Anthropic、OpenAI 等公司为数十亿美元收入发布模型而非空气隔离，Anthropic 更把最新模型接入湿实验室。他还设想了递进的交换——从“帮我做项目前先帮我个忙”，到具推测性的黑入大学改成绩、为配偶合成个性化 mRNA 癌症疫苗；代理型 LLM 也可经由加密货币攻击、外包接单或网络诈骗取得资金，直接用钱行贿。作者承认说服改变信念、贿赂只改行为，两者定义有别，但真正的问题是：强大 AI 能否让人类按它的意愿行事。

**「启示」** 作者的结论是：强大 AI 对普通人的影响力不会靠严密论证，而会走朴素有效的路径——提供帮助、金钱与高价值服务；超级智能的聪明，恰在于什么管用就做什么。

**标签**: `#AI safety`, `#superintelligence`, `#persuasion`, `#LLM agents`, `#AI risk`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [疲软就业报告公布后 交易员大幅下调美联储 10 月加息概率](https://www.cnbc.com/2026/10/02/fed-rate-hike-odds-decline-after-september-jobs-report.html) ⭐️ 7.0/10

美国 9 月新增就业仅 2.9 万个、远低于逾 8 万的预期，交易员随即大幅下调美联储 10 月加息的概率——芝商所 FedWatch 工具显示概率仅约 17%，一周前约为 36%。不过市场仍预计 12 月会加息，FedWatch 给出的 12 月加息概率超过 75%。

rss · CNBC Finance · 10月2日 13:29

**「背景」** 美联储 9 月刚加息以压制已连续五年高于目标的通胀，就业和物价数据走弱给了它更多观望空间；FedWatch 显示的&quot;概率&quot;是由利率期货交易价格推算的市场预期，并非美联储官方决定。本周三公布的 8 月核心 PCE 物价指数（剔除食品和能源、美联储看重的通胀指标）上升 3%、低于 3.3%的预期，同样支撑了 10 月按兵不动的判断。

**标签**: `#Federal Reserve`, `#interest-rate expectations`, `#jobs report`, `#inflation`, `#futures markets`

---

<a id="item-finance-news-2"></a>
### [Bitget CEO 称对追回 3.88 亿美元被盗资金不抱太大期望](https://www.cnbc.com/2026/10/02/bitget-crypto-stolen-hack-recovery.html) ⭐️ 7.0/10

加密货币交易所 Bitget 上周遭黑客攻击，被盗资金近 3.88 亿美元。首席执行官 Gracy Chen 向 CNBC 表示，鉴于以往交易所失窃案的追回情况有限，她“不指望追回太多资金”；目前仅约 110 万美元资产被冻结，且这些资产不一定已归还交易所。

rss · CNBC Finance · 10月2日 06:03

**「背景」** 与朝鲜政府有关的黑客组织“拉撒路”（Lazarus Group）被指参与多起大型加密货币盗窃案，例如 investigators 将 Bybit 交易所约 14.4 亿美元的被盗事件追溯至该组织，而 KuCoin 等此前交易所被盗案件中追回比例普遍有限。本次 Bitget 被盗正是黑客利用第三方安全产品中的零日漏洞——即厂商尚不知晓、暂无补丁可用的安全缺陷——获得了内部权限。

**「影响」** Bitget 用户据报未直接承担损失：公司称客户账户余额未受影响，并动用自有资金将被黑客消耗至 2 亿美元以下的保护基金补足至 3 亿美元以上；比特币、以太币和 USDT 提现已恢复，其余加密货币提现及法币、点对点服务定于周五恢复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Lazarus_Group">Lazarus Group - Wikipedia</a></li>
<li><a href="https://www.bbc.com/news/articles/c2kgndwwd7lo">North Korean hackers cash out hundreds of millions from $1.5bn...</a></li>
<li><a href="https://www.fxstreet.com/cryptocurrencies/news/bybits-14-billion-hack-traced-to-lazarus-group-zachxbt-202502220215">Bybit&#x27;s $1.4 billion hack traced to Lazarus Group : ZachXBT</a></li>

</ul>
</details>

**标签**: `#cryptocurrency`, `#cybersecurity`, `#crypto exchange hack`, `#Bitget`, `#fund recovery`

---