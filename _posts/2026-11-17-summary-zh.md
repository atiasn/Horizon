---
layout: default
title: "Horizon Summary: 2026-11-17 (ZH)"
date: 2026-11-17
lang: zh
---

> 从 48 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 发布:可扩展 KV 缓存默认开启,Model Runner V1 移除](#item-tech-news-1) ⭐️ 8.0/10
2. [Optimizely 遭入侵，Zoom、GitLab 等大站脚本被注入恶意代码](#item-tech-news-2) ⭐️ 8.0/10
3. [Rust 日期时间库 Jiff 发布 1.0 稳定版](#item-tech-news-3) ⭐️ 8.0/10
4. [卡内基梅隆推出 CS Learn：在 YouTube 免费开放完整学期计算机课程](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows 11 遥测被曝可识别用户运行的编码代理与开发工具](#item-tech-news-5) ⭐️ 7.0/10
6. [摩根大通技术故障致美国多家银行网上银行服务延迟](#item-tech-news-6) ⭐️ 7.0/10
7. [微软称大规模邮件故障源于 7 月修复引入的软件缺陷](#item-tech-news-7) ⭐️ 7.0/10
8. [美国与九国签署《旧金山宣言》共保超级智能供应链](#item-tech-news-8) ⭐️ 7.0/10
9. [亚马逊报告 Artex 驱动的 AI 代理窃取 API 密钥以支付模型调用](#item-tech-news-9) ⭐️ 7.0/10
10. [美国临时新规将先进 AI 芯片出口管制延伸至远程访问](#item-tech-news-10) ⭐️ 7.0/10
11. [据报道中国头部 AI 公司收紧新模型网络攻击能力，Qwen 不再开放权重](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [英伟达 CEO 黄仁勋辞职,AI 交易格局面临重塑](#item-finance-news-1) ⭐️ 8.0/10
2. [Eric Trump-backed robot soldier startup can&\#x27;t pay staff after founder borrowed $4.6 million from company to buy home](#item-finance-news-2) ⭐️ 7.0/10
3. [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](#item-finance-news-3) ⭐️ 7.0/10
4. [英特尔及 CEO 陈立武遭股东集体诉讼](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 发布:可扩展 KV 缓存默认开启,Model Runner V1 移除](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM 于 2026 年 11 月 16 日发布 v0.34.0,包含来自 412 位贡献者\(其中 120 位新人\)的 1,061 次提交。此版本默认启用可扩展 KV 缓存——缓存改为按 CUDA graph 捕获和预热后实际空闲的显存分配而非估算,例如 MiniMax-M3 在 H200 上的缓存从 43.3 万 token 增至 67.2 万;同时 Model Runner V1 被彻底移除,V2 成为唯一的 GPU 运行器,并新增 Mistral Large 4\(1T 总参数/52B 激活\)、MiniMax-M3.1-Flash 等 10 个模型。官方报告在 Blackwell 和 MI355X 上获得显著加速,最高为 4×GB200 上 Step5 NVFP4 MoE 的 1.95× 解码提升,但这些数字均为项目自测结果,未经独立验证。版本还引入基于 CRIU 的检查点/恢复与 DP+EP 故障容错缩容等运维特性,不过默认 block size 改为 64、ROCm 7.2 镜像停发、huggingface\_hub &gt;= 2.0.0 成为硬性要求等破坏性变更需要升级者处理。

github · khluu · 11月16日 23:22

**「背景」** vLLM 是目前被广泛使用的开源大语言模型推理引擎。推理过程中,模型需将已处理 token 的注意力键值缓存在 GPU 显存中\(即 KV cache\),vLLM 将其切分为固定大小的块\(block\)做分页管理,缓存容量直接决定可承载的并发请求规模与上下文长度。在 v0.34.0 之前,vLLM 依据 gpu\_memory\_utilization 参数\(旧默认值 0.9\)估算空闲显存来预先划定 KV cache 大小,默认块大小为 16;GPU 侧则同时保留 V1 与 V2 两套 Model Runner 执行路径,用户可通过环境变量 VLLM\_USE\_V2\_MODEL\_RUNNER=0 继续使用旧的 V1。

**「升级注意事项」** 升级前运维人员需审计启动参数与依赖:设置过 VLLM\_USE\_V2\_MODEL\_RUNNER=0 的部署现在会在启动时直接失败,须删除该变量并将 V1 logits 处理器迁移到 vllm.v1.worker.gpu.sample.logits\_processor;要保留旧行为需显式传 --block-size 16,并用 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache 关闭新的缓存分配方式\(gpu\_memory\_utilization 现默认 1.0\)。ROCm 用户必须改用 ROCm 10.0 的 wheel 与镜像\(-rocm72 不再发布\),Python 侧需满足 huggingface\_hub &gt;= 2.0.0、tokenizers &gt;= 0.23.3、timm &gt;= 1.0.30;fp\_quant 检查点不再能加载,Marlin W4A8 需改用 --quantization humming 配合 VLLM\_HUMMING\_INPUT\_QUANT\_CONFIG。另外,默认开启的可扩展 KV 缓存在部分 H200 模型、并发 128 下会使每 token 解码延迟\(TPOT\)上升 6–18%,对解码延迟敏感的服务应据此决定是否退出该特性。

**标签**: `#vllm`, `#llm-inference`, `#kv-cache`, `#gpu-performance`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Optimizely 遭入侵，Zoom、GitLab 等大站脚本被注入恶意代码](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 8.0/10

安全博客 Report URI 于 11 月 16 日报告，网站实验与个性化服务供应商 Optimizely 遭到入侵，其分发给客户网站的脚本被注入恶意代码，Zoom、GitLab、CNN、BBC 等大型站点的访客因此接触到恶意软件。讨论区引用的报告细节指出，这并非 CDN 缓存投毒——Optimizely 的 CDN 只是原样分发了被篡改的脚本，且 Optimizely 自己的 www.optimizely.com 与 login.optimizely.com 嵌入片段同样携带该代码。攻击者如何获得对大量互不相关客户项目的写入权限（是 Optimizely 内部系统被攻破还是跨客户凭据泄露）尚无结论，恶意代码的具体行为在现有公开材料中也未得到确认。

hackernews · kristjansson · 11月16日 23:00 · [社区讨论](https://news.ycombinator.com/item?id=50524767)

**「背景：Optimizely 与第三方脚本模式」** Optimizely Web 是一个被广泛部署的网站实验（A/B 测试）平台，客户网站在页面中嵌入一段代码后，由 Optimizely 的 CDN 直接向访客分发脚本。这种第三方 JavaScript 模式让网站无需改动自身工程代码就能运行实验和营销标签，但也意味着供应商侧一旦被植入恶意代码，同一条脚本链路会把它同时送到所有客户网站的访客浏览器中。

**「影响」** 11 月 16 日,178 家组织的网站\(包括 Zoom、BBC、CNN、Salesforce、GitLab 和 HSBC\)向访客执行了注入的恶意脚本:输入支付卡信息的用户面临卡号被窃取的风险,进行加密货币转账的用户其钱包地址可能被替换为攻击者地址,iOS 访客还会被推送漏洞利用代码。在此期间在这些站点完成过支付或转账的用户应核对账单与交易记录;使用 Optimizely Web 的企业则需排查自身项目是否被写入恶意 loader。

**「社区讨论」** 评论中的主要争论集中在问责与架构：mcoliver 认为 Optimizely 缺少分阶段发布、自动安全检查等发布制衡，CNN、BBC 这类大流量站点更没有理由不设同等防护、甚至应避免直接从供应商加载脚本，stickfigure 则批评 Google Tag Manager 让营销部门绕过工程团队随意添加标签的模式正是此类风险的根源。skybrian 另外提出一个未解疑问：CNN、BBC 这类新闻网站为何会在同一页面上涉及加密货币或信用卡信息，还是攻击依赖了浏览器漏洞，现有解释缺少这一环。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cybersecuritynews.com/optimizely-websites-hijacked/">Hackers Infect 178 Major Websites via Optimizely to Steal ...</a></li>
<li><a href="https://shiftdelete.net/en/optimizely-malware">Optimizely Malware Hit 178 Sites: What It Stole and What to Do</a></li>
<li><a href="https://windowsforum.com/news/optimizely-web-javascript-breach-admin-response-to-card-skimming-and-crypto-address-swaps.452629/">Optimizely Web JavaScript Breach: Admin Response to Card ...</a></li>
<li><a href="https://vinish.dev/optimizely-web-experimentation-supply-chain-attack-malicious-javascript">Optimizely Supply Chain Attack: Flaw Put Malicious JavaScript ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/optimizely-malware-hits-zoom-bbc-cnn-what-to-do.html">Optimizely Malware Hits Zoom, BBC, CNN: What to Do</a></li>

</ul>
</details>

**标签**: `#security`, `#supply-chain-attack`, `#web-security`, `#javascript`, `#third-party-scripts`

---

<a id="item-tech-news-3"></a>
### [Rust 日期时间库 Jiff 发布 1.0 稳定版](https://burntsushi.net/jiff/) ⭐️ 8.0/10

burntsushi 开发的 Rust 日期时间库 Jiff 发布 1.0 稳定版，作者在其博客上同步发布了详细介绍。该库面向时区、夏令时与民用时间处理这一公认困难的领域，被社区视为 chrono 之外一个可信的现代替代选择。发布在 Hacker News 上引发大量讨论（347 分、78 条评论），焦点集中在它与 chrono 的取舍以及各自的适用场景。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「背景：Jiff 的前期演进与适用范围」** 在 1.0 之前，Jiff 已经以 0.x 版本公开迭代了一段时间：0.1 就引入了用于格式化 IANA 时区标识符的 %Q 和 %:Q 格式说明符，并且在解析落入空档（gap）的民用时间时，会将所有偏移量视为无效并返回错误。按照作者的设计，Jiff 把时区处理放在 API 的核心位置，自动处理与夏令时相关的常见问题，帮助使用者避开日期时间编程中的典型陷阱。不过它的适用范围有明确边界：Jiff 仅支持 Unix 时间尺度，在 Hacker News 讨论中，需要 TAI、UT1 等其他时间尺度的用户（例如从事天体轨道模拟的开发者）得到的建议是改用 hifitime 库。

**「对 Rust 开发者的影响」** Jiff 达到 1.0 稳定版本后，Rust 开发者在 chrono 和 time 之外多了一个可用于生产的日期时间库选择，但采用存在具体的兼容性代价：Blessed.rs 精选清单指出，Jiff “目前在生态系统集成方面仍不及 time 和 chrono”，依赖这类第三方集成的现有项目迁移时可能受阻。对于新项目或集成需求较少的场景，Jiff 已通过 crate feature 提供 serde 支持以及将时区数据库嵌入二进制文件的选项，可以直接评估采用。

**「社区讨论」** 自述维护 chrono 约五年的前维护者 quodlibetor 评论称，chrono 正是因 API 稳定才被广泛采用，而任何改进尝试都遭遇阻力，他最终因看不到改进路径而倦怠退出，并对 burntsushi 的工作表示感谢——这是其个人经历与看法，并非对 Jiff 的实测结论。其他评论者立场不一：有人欣赏 Jiff 文档坦承自己并非适用于所有场景，有人希望它逐步取代 chrono，也有人认为 chrono 已足够成熟、会试用 Jiff 但保持谨慎，还有从事天体轨道模拟的开发者询问其对 TAI、UT1 等时间尺度的支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff/releases">Releases · BurntSushi / jiff · GitHub</a></li>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://news.ycombinator.com/item?id=50519744">Jiff 1 . 0 : A datetime library for Rust | Hacker News</a></li>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/ jiff : A datetime library for Rust that encourages...</a></li>
<li><a href="https://blessed.rs/">Crate List - Blessed.rs</a></li>

</ul>
</details>

**标签**: `#rust`, `#datetime`, `#libraries`, `#open-source`, `#api-design`

---

<a id="item-tech-news-4"></a>
### [卡内基梅隆推出 CS Learn：在 YouTube 免费开放完整学期计算机课程](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

卡内基梅隆大学于 11 月 16 日上线 CS Learn 项目，在 YouTube 上免费发布该校现行计算机科学课程的完整学期讲座，项目由其 Griffin 计算机科学学院（Griffin School of Computer Science）教师 Phillip Compeau 负责，本周每天首播一门课程，更多课程定于 1 月上线。首批内容包含陈天奇（Tianqi Chen）的 ML Systems（机器学习系统）课程，以及即将上线的 15-259 Probability and Computing 等课程。Compeau 介绍，几名学生开发了工具来自动化课程视频的大量制作工作；他也承认 MIT 在 25 年前已通过 OpenCourseWare 开创了免费开放课程的先例，但他更看重 CMU 在制作方式上的不同。

hackernews · pcompeau · 11月16日 20:43 · [社区讨论](https://news.ycombinator.com/item?id=50522980)

**「开放课件模式的先例」** 由大学把课程免费公开并非首创:麻省理工学院约 25 年前就推出了 OpenCourseWare 项目,CS Learn 的负责人、CMU 讲师 Phillip Compeau 在发布讨论中也坦承“MIT 25 年前就做到了”。CS Learn 隶属于卡内基梅隆大学 Kenneth C. Griffin 计算机学院,定位是把该校顶尖计算机科学课程以完整学期、逐讲播放的播放列表形式免费开放给所有人。

**「影响」** 对无法就读卡内基梅隆的工程师和机器学习从业者而言，这提供了免费、成体系接触顶尖计算机科学项目完整学期教学的途径，其中 ML Systems 课程与机器学习系统和 GPU 编程方向直接相关；观众可直接在 YouTube 观看，并关注本周每日首播的新课以及 1 月的后续上线计划。

**「社区讨论」** 用户 JSR\_FDED 提出，在 AI 时代扎实掌握基础的人能把 AI 当作强力工具，缺乏基础的人则可能被取代——这是个人观点而非已验证的结论。多位有 CMU 背景的用户对课程阵容表示欢迎：一位校友称陈天奇的 ML Systems 课程与 mlc.ai 上的 Modern GPU Programming for MLSys 教材互补，并请求增设 Larry Wasserman 的中级统计学、Dave Andersen 的分布式系统和 Dave Eckhardt 的操作系统等课程；另有用户询问是否会涵盖类型论与形式化验证内容，并表示期待 15-259 Probability and Computing 上线。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/@CMULearn">CS Learn at Carnegie Mellon - YouTube</a></li>
<li><a href="https://www.pressreleasepoint.com/cmu-opens-access-top-computer-science-classes-through-free-cs-learn-platform">CMU Opens Access to Top Computer Science Classes Through Free ...</a></li>

</ul>
</details>

**标签**: `#education`, `#open-courseware`, `#machine-learning`, `#ml-systems`, `#computer-science`

---

<a id="item-tech-news-5"></a>
### [Windows 11 遥测被曝可识别用户运行的编码代理与开发工具](https://xusheng.dev/posts/windows-coding-agent-telemetry/) ⭐️ 7.0/10

一篇发布于 2026 年 11 月 16 日的博客文章（xusheng.dev）报告称，Windows 11 的遥测数据中包含可识别用户正在运行哪些 AI 编码代理和开发工具的信息。该结论目前仅来自个人博客的分析，尚未获得独立验证或微软官方说明。此事恰逢 AI 编码代理使用激增，在 Hacker News 上引发活跃讨论（393 分、247 条评论），焦点集中在开发者隐私、Windows 缺乏代理沙箱机制，以及是否应迁移到 Linux。

hackernews · cwaffles · 11月16日 22:58 · [社区讨论](https://news.ycombinator.com/item?id=50524736)

**「背景：Windows 与开发工具的既有遥测生态」** Windows 10/11 长期内置诊断数据（遥测）收集机制，用户虽可在系统设置中调整收集级别，但社区长期依赖第三方 PowerShell 工具（如 WindowsTelemetryBlocker）来阻断收集并禁用相关服务。开发工具侧同样存在独立的遥测体系，例如 VS Code 为企业环境提供集中管理界面，可统一配置遥测级别与反馈选项，因此开发者对“哪些数据被收集、如何关闭”并不陌生。

**「对开发者的影响与可行应对」** 对在 Windows 11 上运行编码代理和开发工具的开发者来说，这一发现意味着本机的工具使用情况可能随系统遥测上报，开发环境信息存在暴露面。可行的应对包括：个人用户可通过系统设置或第三方工具关闭 Microsoft 遥测，例如 GitHub 上的 pause-windows-updates 项目支持在 Windows 10 和 11 上禁用 Microsoft 遥测；企业则可参照 VS Code 官方企业文档集中管理遥测级别与反馈选项。另有评论者指出，Intel、AMD 和 NVIDIA 的驱动在未主动退出的情况下也会收集所运行程序的可执行文件名与路径，因此仅关闭 Windows 遥测未必能完全阻止此类信息收集。由于原始报告来自个人博客，该收集行为的具体范围仍有待独立验证。

**「社区讨论」** 评论中的主要分歧在于：一些用户认为此事强化了迁移 Linux 的理由，并报告 2026 年 Linux 在单机游戏上已基本可用、切换成本约一周，但多人和联机游戏仍有问题；另一人则反驳称 Intel、AMD、NVIDIA 的显卡驱动在未选择退出的情况下同样会收集所运行程序的名称和路径。还有评论者提出不同视角：据其所述，Windows 至今缺少 AI 代理沙箱机制——微软 10 月 7 日才推出 MXC 且 Claude Code 尚不支持——因此若遥测被用于确定平台功能优先级，或许有其合理性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/N0tHorizon/WindowsTelemetryBlocker">N0tHorizon/WindowsTelemetryBlocker: A PowerShell based tool to...</a></li>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>
<li><a href="https://github.com/Aetherinox/pause-windows-updates">GitHub - Aetherinox/pause- windows -updates: Pause &amp; disable...</a></li>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>

</ul>
</details>

**标签**: `#privacy`, `#windows`, `#telemetry`, `#developer-tools`, `#ai-coding-agents`

---

<a id="item-tech-news-6"></a>
### [摩根大通技术故障致美国多家银行网上银行服务延迟](https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda) ⭐️ 7.0/10

据 11 月 16 日美联社报道，摩根大通（JPMorgan Chase）的一起技术故障在美国引发多家大型银行的网上银行服务延迟，Chase、富国银行（Wells Fargo）和 Truist 均受到影响。现有报道未披露故障的具体原因、影响范围和恢复时间，这些关键细节仍待确认。由于多家银行同时出现服务异常，此次事件是否涉及共享基础设施或某个共同故障点，尚无法从现有信息中确认。

hackernews · samk3nny · 11月16日 18:31 · [社区讨论](https://news.ycombinator.com/item?id=50521045)

**「背景:跨行互联如何放大单点故障」** 美国大型银行的在线服务并非孤立运行:跨行转账和支付需要交易对方银行的系统同时可用,因此当摩根大通\(JPMorgan Chase\)——美国最大的银行之一——出现技术故障时,其他银行客户与 Chase 之间的交易也会随之失败。据 AP 报道,周一的故障集中在 Chase 客户以及试图与 Chase 交易的其他银行客户身上,而美国银行和花旗集团自身的银行服务并未出现问题;USA Today 则报道摩根大通已确认是其技术问题导致包括富国银行和美国银行在内的多家银行出现故障。这表明此次事件是 Chase 的单点故障经由银行间交易通道外溢,而非多家银行共用平台的同步瘫痪;Chase 随后表示,故障源于一个

**「客户交易与 Zelle 转账受阻，影响范围存在差异」** 故障发生时，Chase 客户报告无法使用 ATM 卡或在网点完成交易，Capital One、PNC、U.S. Bank、Wells Fargo、Bank of America 等银行的客户以及 Zelle 转账应用用户也报告了问题。Zelle 说明称，客户发送付款遇到的障碍源于合作银行的故障而非其自身系统，即转账失败可追溯到 Chase 一侧；而 Bank of America 和 U.S. Bank 分别向 USA TODAY 声明其系统未受直接影响，表明部分银行报告的异常可能属于间接影响。在故障时段尝试过刷卡或 Zelle 付款的用户，宜核对交易是否实际完成。

**「社区讨论」** 有评论者将此次事件与上个月 Revolut 因 Google Cloud 故障、约 12 小时恢复的停机相类比，猜测本次也可能源于数据库或云服务层面的问题，另有用户称银行卡支付和线下网点服务同样受到影响——但这些均属未经证实的个人描述与推测。也有评论指出，银行核心流程大概率运行在 COBOL、CICS、IMS、DB2 等老旧但成熟的大型机技术栈上，而一位西海岸用户报告部分受影响站点在其处可正常加载，暗示实际影响范围可能并不均一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda">Technical issue at JPMorgan Chase triggers online banking delays</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase , impacted Wells Fargo and BofA</a></li>
<li><a href="https://www.thegatewaypundit.com/2026/11/major-banks-experiencing-outages-developing/">Major US Banks Experiencing Outages … Update with Statement from...</a></li>
<li><a href="https://www.nytimes.com/2026/11/16/us/bank-outages-down.html">Chase Bank Transactions Disrupted by ‘Technical Issue’ Amid Outage ...</a></li>
<li><a href="https://nypost.com/2026/11/16/business/outages-hit-chase-bank-of-america-and-wells-fargo-customers/">Big bank customers report outages ; JPMorgan Chase blames...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase , impacted Wells Fargo and BofA</a></li>

</ul>
</details>

**标签**: `#banking-outage`, `#infrastructure-reliability`, `#mainframes`, `#financial-systems`, `#incident-response`

---

<a id="item-tech-news-7"></a>
### [微软称大规模邮件故障源于 7 月修复引入的软件缺陷](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

微软表示,近期影响其企业邮件服务\(Exchange\)的一次大规模中断,根源是 7 月一次修复中引入的软件缺陷。据 The Register 2026 年 11 月 16 日报道,微软给出了这一根因解释,但受影响用户规模、中断持续时间等具体数字在现有材料中未披露。需要说明的是,这是微软单方面的归因说明,尚无独立验证,且该报道本身是新闻报道,并非完整的技术事后复盘。

hackernews · Bender · 11月16日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50517321)

**「事件背景」** 微软此次的归因说明，针对的是 2026 年 11 月 12 日发生的一场持续近 24 小时的全球性宕机：Outlook、Exchange Online、Teams 和 Copilot 等 Microsoft 365 服务同时中断，全球用户无法访问电子邮件。微软于 11 月 15 日发布初步事后报告，将故障根源定位在 Microsoft 365 的网络网关服务器中。

**「影响」** 对依赖 Exchange Online 的企业租户而言，这次缺陷的后果是接近一天量级的服务中断：部分租户停机接近一整天，故障从 Exchange Online 蔓延到依赖它的其他服务，波及至少 74 个国家，整体事件持续超过 15 小时。由于根因是微软 7 月一次修复中引入的缺陷，租户无法自行规避；管理员能做的是在服务恢复后参照针对此次故障发布的管理员指南，核查租户恢复状态以及需要复查的事项。

**「社区讨论」** 在 Hacker News 的讨论\(187 条评论\)中,有读者以电力行业&quot;黑启动&quot;类比大规模系统的恢复难度,并质疑微软为何不通过按 IP 段轮流放行连接等方式削减负载、逐步恢复服务器。另有评论认为,7 月代码在规格较低的测试环境中通过验证、未能暴露生产环境高并发下的并发缺陷,这种测试与生产环境的差异是一种代价高昂的权衡;也有人对关键网络基础设施中运行 Windows 表示意外。以上均为社区观点,微软未在所提供材料中回应这些质疑。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/microsoft/microsoft-says-months-old-bug-caused-global-microsoft-365-outage/">Microsoft says months-old bug caused global Microsoft 365 outage</a></li>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://petri.com/microsoft-explains-microsoft-365-outage/">Microsoft Explains Causes of Microsoft 365 Outage</a></li>
<li><a href="https://office365itpros.com/2026/11/16/exchange-online-outage-nov26/">The Great Exchange Online Outage of November 2026</a></li>
<li><a href="https://www.billyperalta.com/blog/microsoft-365-outlook-outage-november-12-2026/">Outlook Down Nov 12, 2026: Microsoft 365 Outage Admin Guide</a></li>
<li><a href="https://neuraltrust.ai/blog/microsoft-outage-november-2026">Microsoft Outage: What Really Happened? | NeuralTrust</a></li>

</ul>
</details>

**标签**: `#microsoft`, `#outage`, `#reliability`, `#incident-response`, `#distributed-systems`

---

<a id="item-tech-news-8"></a>
### [美国与九国签署《旧金山宣言》共保超级智能供应链](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

据美国国务院消息，11 月 15 日美国与澳大利亚、印度、以色列、日本、韩国、卡塔尔、新加坡、阿联酋、英国九国签署《旧金山宣言》，宣示经济安全是国家安全根基，各方将共同保护支撑超级智能（SI）供应链的敏感技术与关键基础设施。宣言提出设立五个工作组，分别负责创新政策框架、SI 在关键领域的应用、SI 全栈供应链协作、安全港与供应链安全枢纽，以及 SI 安全与韧性。目前公开的仅为宣言要点转述，工作组的成员构成、运作机制、时间表及对相关企业的实际约束均未公布，该安排属于刚宣布的多边政策框架，而非已落地的具体措施。

telegram · zaihuapd · 11月16日 10:40

**「背景：Pax Silica 倡议」** 《旧金山宣言》是美国 2025 年 12 月发起的“Pax Silica”倡议的新阶段，该倡议旨在为关键矿产、能源、半导体和人工智能基础设施等战略领域构建更具韧性和多元化的供应链。此次宣言将这一由美国发起的供应链安全议程，扩展为美国与九个伙伴国共同参与的多边协调框架。

**「影响：供应链安全转向多边协调」** 对在美国、日本、韩国、英国、澳大利亚、印度、以色列、新加坡、阿联酋和卡塔尔市场运营的 AI 芯片、云计算与数据中心企业而言，供应链安全正从各国单边管控转向多边协调：据美国国务院表述，宣言将共同原则固化为“共同基线”和可执行的行动路径，五个工作组将分别推进创新政策、关键领域应用、全栈供应链协作、安全枢纽以及安全与韧性（tool-3-2、tool-3-3）。相关企业应跟踪各工作组的后续产出——宣言目前只确立框架而未公布具体管制措施，但若签署国在敏感技术审查和关键基础设施安全上采用统一基线，跨境采购、出口与合规安排可能需要相应调整。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>
<li><a href="https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/">The San Francisco Declaration on the Secure Foundations of ...</a></li>
<li><a href="https://organiser.org/2026/11/17/426815/international/us-india-and-8-nations-ink-san-francisco-declaration-to-secure-ai-supply-chain-amid-chinese-linked-espionage-in-nvidia/">San Francisco Declaration: US, India and 8 sign AI pact</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#supply chain security`, `#geopolitics`, `#superintelligence`, `#international cooperation`

---

<a id="item-tech-news-9"></a>
### [亚马逊报告 Artex 驱动的 AI 代理窃取 API 密钥以支付模型调用](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

亚马逊威胁情报团队报告，攻击者利用开源渗透测试框架 Artex 驱动 AI 代理，从公网暴露的 LiteLLM 和 Dify 部署中窃取 API 密钥，验证后将密钥汇入共享池，用于支付更多大模型调用。据披露，该活动自 10 月 3 日开始，11 月 5 日被亚马逊诱饵网络 MadPot 截获阻断。亚马逊以中等信心将行动归因于与中国相关的威胁组织，并表示并非所有被列目标都已失陷，可能受影响的 AWS 客户已收到通知。上述结论来自厂商威胁情报报告，目前尚无独立验证。

telegram · zaihuapd · 11月16日 13:00

**「背景」** LiteLLM、One API 和 Dify 是常见的大模型网关与 AI 应用开发平台，这类应用一旦暴露在公网，其内部保存的 AI 提供商 API 密钥就可能被窃取，这正是本次攻击的目标所在。Artex 是一个开源的智能体式（agentic）AI 渗透测试框架，攻击者用它驱动 AI 代理自动执行攻击流程。亚马逊的 MadPot 是其全球分布的诱饵传感器（蜜罐）网络，本次正是这些传感器捕获了 AI 代理发出的请求，其中还包含攻击活动的运行内存记录。

**「影响与建议」** 对将 LiteLLM 或 Dify 部署暴露在公网的团队来说，风险直接体现为 API 密钥失窃后被汇入共享池、用于支付攻击者的模型调用，从而产生实际账单损失。建议检查实例是否缺少访问控制、轮换相关密钥并监控调用量与账单异常；被列为可能受影响的 AWS 客户已由亚马逊单独通知。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">Amazon Threat Intelligence observes threat actors running ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>

</ul>
</details>

**标签**: `#AI security`, `#cybersecurity`, `#AI agents`, `#API key theft`, `#threat intelligence`

---

<a id="item-tech-news-10"></a>
### [美国临时新规将先进 AI 芯片出口管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

美国商务部于 11 月 16 日发布一项临时最终规则，将先进 AI 芯片及服务器的出口管制延伸至远程访问场景，直接针对企业租用第三国数据中心算力以规避限制的做法。据 The Verge 报道，新规还要求向印尼、马来西亚、新加坡、泰国和巴西再出口 AI 芯片时必须事先申请许可。该简讯称规则由财政部与国家安全委员会主导起草，可能进一步收紧中国获取先进芯片的渠道；此细节出自简讯转述，简讯未附规则原文，信源为路透社、美国工业与安全局（BIS）与 The Verge 的报道。

telegram · zaihuapd · 11月16日 14:44

**「背景」** 美国此前已限制英伟达等公司的先进 AI 芯片出口到中国，但管制主要针对芯片的实物出口，租用第三国数据中心算力、远程调用美国芯片由此成为绕开限制的渠道。路透社报道称，特朗普政府选择在特朗普总统出访中国之际宣布这轮收紧，以进一步限制中国获取先进 AI 芯片。

**「影响」** 受影响最直接的是依赖跨境算力租赁的企业与云服务商：中国和澳门属于 D:5 受限组别、无法直接购买先进 AI 芯片，此前通过租用第三国数据中心算力“远程调用”芯片的绕道方式，如今被明确纳入许可管制——美国商务部称，该规则旨在确保“现有对敏感美国技术的访问限制，不会通过涉及第三国数据中心的远程计算安排而被规避”。在印尼、马来西亚、新加坡、泰国和巴西提供或租用数据中心算力的企业，需要核查现有算力合同是否触发再出口许可要求，云服务商也需对远程访问先进芯片的行为落实许可合规，否则面临违规风险。市场反应已经显现：AMD 和博通股价因新规收紧而下跌，采购芯片的 AI 云服务商股价同样走低，其中英伟达投资的 CoreWeave 盘中一度跌超 8% 后收窄跌幅（该报道同时提及英伟达 CEO 黄仁勋卸任的影响仍在波及 AI 板块）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">US to curb China&#x27;s access to AI chips as Trump heads to Asia</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/article/amd-broadcom-stocks-sink-on-tighter-us-chips-rules-coreweave-drops-143342994.html">AMD, Broadcom stocks sink on tighter US chip rules , CoreWeave and...</a></li>
<li><a href="https://www.zerohedge.com/markets/us-closes-cloud-loophole-days-after-jensens-exit-new-rule-puts-ai-chip-rentals-china-and">US Closes The &quot; Cloud Loophole&quot;: Days After Jensen&#x27;s Exit, New Rul...</a></li>
<li><a href="https://wccftech.com/the-u-s-shuts-chinas-access-to-advanced-chips-via-singapore-brazil-indonesia-malaysia-and-thailand-as-scott-bessent-gives-nvidia-10-days-to-show-it-did-not-goose-its-revenues/">The U.S. Shuts China&#x27;s Access To Advanced Chips Via Singapore ...</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#semiconductors`, `#US regulation`, `#geopolitics`

---

<a id="item-tech-news-11"></a>
### [据报道中国头部 AI 公司收紧新模型网络攻击能力，Qwen 不再开放权重](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

据 Bloomberg 报道，阿里巴巴、腾讯、月之暗面等中国头部 AI 公司在新一代模型中削弱了进攻性网络能力，同时提升防御方向的表现。报道称，阿里最新旗舰 Qwen 不再开放权重，用户无法下载并自定义完整版本；腾讯在本月发布 Hy4 之前已削减网络相关功能。报道将这些调整与商务部上月公布的出口管制草案联系起来，该草案拟禁止可攻击关键基础设施和政府网络的 AI 工具出口；若 Qwen 确实不再开放权重，依赖其进行本地部署和微调的开发者将需要改用旧版开放权重模型或转向闭源 API。需要说明的是，本条为对 Bloomberg 报道的转述，Hy4 的具体发布情况与限制范围等细节尚无法从现有材料独立核实。

telegram · zaihuapd · 11月17日 02:20

**「Qwen 此前长期开放权重」** 阿里巴巴的 Qwen 系列此前长期以开放权重发布为特色：据 CNBC 2026 年 8 月报道，阿里在推出可运行于笔记本等消费级硬件的新模型时，还公开了当时最强模型 Qwen 3.8 Max 的权重，与 Meta 在开放权重市场直接竞争。而据 The Next Web 报道，阿里于 11 月 16 日发布的新旗舰 Qwen 4-Max 基于 Qwen 4 架构，具备 2.4 万亿参数骨干、原生视觉能力与百万 token 上下文窗口，但未开放权重。由于开放权重允许用户下载并自定义完整模型，旗舰模型转向封闭与阿里此前的开放策略形成明显反差。

**「Qwen 旗舰不再开放权重，开发者自托管与微调路径受限」** 对依赖开放权重进行本地部署和微调的开发者与企业，这是最直接的影响：据报道，阿里最新旗舰 Qwen 不再提供可下载的完整权重，现有自托管与定制流程无法原样迁移到新版本，只能退回旧版开放权重模型，或接受无法本地定制完整模型的限制。对厂商而言，商务部上月公布的出口管制草案一旦最终生效，可攻击关键基础设施和政府网络的 AI 工具将被禁止出口，海外发布与合规安排需要重新评估。此类收紧并非没有现实依据：据 The Register 报道，曾有团伙利用开源中国 AI 工具 ARTEX 攻击韩国多家金融机构，表明开放获取的高能力工具已出现实际滥用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://qwen.ai/home">Qwen</a></li>
<li><a href="https://www.cnbc.com/2026/08/17/alibaba-meta-qwen-open-weight-ai-laptop-models.html">Alibaba challenges Meta with new laptop-ready AI model</a></li>
<li><a href="https://thenextweb.com/news/alibaba-launches-qwen4-max-flagship-ai-model-without-open-weights">Alibaba launches Qwen 4-Max flagship AI model without open weights</a></li>
<li><a href="https://www.theregister.com/cyber-crime/2026/10/28/123-reg-discloses-ai-cyberattack-on-customer-data-suspects-china-nexus/5305936">123 Reg discloses &#x27; AI cyberattack &#x27; on customer data, suspects China ...</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#cybersecurity`, `#open weights`, `#export controls`, `#Chinese AI industry`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达 CEO 黄仁勋辞职,AI 交易格局面临重塑](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 8.0/10

英伟达创始人兼 CEO 黄仁勋在丑闻风波中宣布辞职,公司股价录得 2012 年以来最长周线连跌,本周收于 162.85 美元,券商 Yorkville Ives 将目标价从 300 美元下调至 225 美元但维持买入评级。接受 CNBC 采访的 ETF 专家认为,大型科技公司、超大规模云厂商及 AMD 等竞争对手有望承接 AI 交易的资金轮动,而民主党在 11 月 3 日选举后掌控国会,分析师估计 10%至 20%的规划数据中心可能因此无法落地。

rss · CNBC Finance · 11月16日 12:13

**「背景」** 黄仁勋于 11 月 12 日因媒体曝光的婚外情指控辞去英伟达 CEO、总裁及董事职务，其中一名涉事者被指为中国间谍，首席财务官科莱特·克雷斯已出任临时 CEO。政策层面，民主党在 11 月 3 日中期选举中赢得国会两院控制权，胜选议员随后呼吁收紧对 AI 数据中心建设的限制，不过分裂的国会格局预计会限制联邦层面重大政策变动的空间。

**「影响」** AI 板块投资者本周已将资金转向竞争对手和云巨头——AMD 涨近 13%,博通涨幅相近,纳斯达克指数创 8 月以来最佳单周表现——受访专家认为,若数据中心建设放缓,已拥有算力的超大规模云厂商将因算力更稀缺而受益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://abcnews.com/Business/nvidia-ceo-jensen-huang-resigns-amid-alleged-affair/story?id=138076256">Nvidia CEO Jensen Huang resigns amid alleged affair with ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/jensen-huang-resigns-nvidia-ceo-163011659.html?fr=sycsrp_catchall">Jensen Huang Resigns as Nvidia CEO After Second Affair ...</a></li>
<li><a href="https://www.reuters.com/business/retail-consumer/nvidia-ceo-jensen-huang-step-down-big-blow-ai-boom-2026-11-12/">Nvidia CEO Jensen Huang resigns in blow to AI boom he helped ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>
<li><a href="https://russellinvestments.com/content/ri/us/en/insights/russell-research/2026/11/midterms-results-policy-data-centers.html">What midterm results mean for policy and data center risk</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI trade`, `#semiconductors`, `#ETFs`, `#data-center policy`

---

<a id="item-finance-news-2"></a>
### [Eric Trump-backed robot soldier startup can&\#x27;t pay staff after founder borrowed $4.6 million from company to buy home](https://www.cnbc.com/2026/11/14/foundation-payroll-ceo-loan.html) ⭐️ 7.0/10

Foundation Future Industries, an Eric Trump-backed military humanoid robot startup, missed payroll after CEO Sankaet Pathak borrowed $4.6 million from the company to buy a home, while the firm seeks funding at a $3 billion valuation amid scrutiny of its defense contract claims.

rss · CNBC Finance · 11月16日 17:14

**标签**: `#defense-tech`, `#corporate-governance`, `#Eric Trump`, `#startup-funding`, `#military-robotics`

---

<a id="item-finance-news-3"></a>
### [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Commerce Secretary Howard Lutnick faces conflict-of-interest questions because his sons&\#x27; firm Cantor Fitzgerald sharply reduced its Nvidia stake and kept deep financing ties to Nvidia&\#x27;s AI ecosystem while he resisted crackdowns on suspected chip smuggling to China.

rss · CNBC Finance · 11月16日 12:14

**标签**: `#Nvidia`, `#Howard Lutnick`, `#export controls`, `#Cantor Fitzgerald`, `#US-China`

---

<a id="item-finance-news-4"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

Intel, CEO Lip-Bu Chen and CFO Zinsner face a shareholder class action alleging they concealed weak PC demand and inventory buildup, after a disappointing Q4 forecast reportedly sent the stock down 28.6% in one day and erased about $140 billion in market value.

telegram · zaihuapd · 11月16日 11:10

**标签**: `#Intel`, `#securities class action`, `#semiconductors`, `#earnings guidance`, `#stock plunge`

---