---
layout: default
title: "Horizon Summary: 2026-10-23 (ZH)"
date: 2026-10-23
lang: zh
---

> 从 43 条内容中筛选出 18 条重要资讯。

---

**科技新闻**
1. [Quad9 因法院罚款宣布退出法国并地理封锁法国用户](#item-tech-news-1) ⭐️ 8.0/10
2. [Switch 2 越狱技术细节公布，AI 代理驱动硬件自动化研究](#item-tech-news-2) ⭐️ 8.0/10
3. [Earstrip 三角剖分库 489 毫秒处理 370 万地图多边形，超越 Earcut](#item-tech-news-3) ⭐️ 8.0/10
4. [研究：部分智能电视关闭内容识别后仍回传观看数据](#item-tech-news-4) ⭐️ 8.0/10
5. [禁运 Nvidia B300 服务器现身中国移动宁夏数据中心采购](#item-tech-news-5) ⭐️ 8.0/10
6. [NVIDIA 组织发布 OpenShell:面向自主 AI 代理集群的沙箱运行时](#item-tech-news-6) ⭐️ 7.0/10
7. [Getting ready to operate GNU Taler in Germany](#item-tech-news-7) ⭐️ 7.0/10
8. [eMudhra 宣布退出全球 SSL/TLS 证书业务](#item-tech-news-8) ⭐️ 7.0/10
9. [Arc 浏览器告别：社区回顾其创新 UX 并转向替代品](#item-tech-news-9) ⭐️ 7.0/10
10. [pwn.watch：实时追踪在野利用漏洞的仪表板上线](#item-tech-news-10) ⭐️ 7.0/10
11. [Anthropic 将 Agent Skills 标准捐赠给 Linux 基金会旗下 AAIF](#item-tech-news-11) ⭐️ 7.0/10
12. [Carbon-X:DNA 与文本联合训练的 148 亿参数开源模型](#item-tech-news-12) ⭐️ 7.0/10
13. [澳洲法院裁定苹果须向第三方应用商店开放 iPhone](#item-tech-news-13) ⭐️ 7.0/10
14. [米哈游联合清华大学开源 GameScaling 键鼠操作模型](#item-tech-news-14) ⭐️ 7.0/10
15. [甲骨文修复 Java SE JSSE 组件 CVSS 9.1 高危漏洞 CVE-2026-91403](#item-tech-news-15) ⭐️ 7.0/10
16. [333 个被植入 Ebury 后门的 Tor 出口节点下线](#item-tech-news-16) ⭐️ 7.0/10

**科技博客**
1. [软件慢的根源是设计，而非语言](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [沪深 300 较 6 月高点回落 20%，A 股逼近熊市](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Quad9 因法院罚款宣布退出法国并地理封锁法国用户](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 8.0/10

非营利 DNS 解析服务 Quad9 宣布将退出法国市场，并对法国用户实施地理封锁，此前该公司因拒不执行盗版相关的 DNS 屏蔽令被法国法院认定为藐视法庭并处以罚款。据 Quad9 公布的细节，原告索尼音乐娱乐德国公司（Sony Music Entertainment GmbH）曾使用 VPN 从德国绕过其地理封锁访问被屏蔽内容，法院据此认定其不合规；其 CTO 表示，针对法国用户的 geoIP 过滤很可能在 11 月 24 日之后生效。据该条目分析，Google、Cloudflare 和 Cisco 运营的解析器此前也收到过类似的法国法院屏蔽命令，此事凸显了 DNS 解析器运营商面临的法律压力。

hackernews · farrokhi · 10月22日 14:32 · [社区讨论](https://news.ycombinator.com/item?id=50195959)

**「法国的解析器屏蔽令与先例」** DNS 解析器负责把域名翻译成 IP 地址，在法国已被法院用作盗版网站屏蔽令的执行环节：版权方 Canal+ 针对体育盗版流媒体网站取得了网络屏蔽禁令，Google、Cloudflare 和 Cisco 运营的解析器此前都曾是禁令目标，三家公司反对均未成功，其中 Google 和 Cloudflare 被迫执行了屏蔽。Quad9 此前也因同类屏蔽令被 Sony Music Entertainment GmbH 起诉——据其博客自述，原告用 VPN 从德国绕过其 geoIP 屏蔽继续访问被屏蔽内容后，法院认定 Quad9 藐视法庭并处以罚款，可见仅靠 geoIP 屏蔽难以让法院认可其合规。

**「对法国用户的影响」** 自 2026 年 11 月 24 日起，Quad9 将通过 geoIP 过滤阻止法国用户使用其公共 DNS 解析服务，境内依赖该服务（如 9.9.9.9）的个人用户和机构需在此之前迁移到其他解析器，否则相关域名解析请求将被拒绝。但巴黎法院 2026 年 7 月 17 日发布的 14 项封锁令同样约束 Cloudflare、Google Public DNS 和 DNS4EU 等解析器，因此换用这些主流服务也无法绕开与 Canal+相关的域名封锁。法国用户和系统管理员在调整 DNS 配置前，应核实目标解析商是否也已执行同类法国法院命令。

**「社区讨论」** Quad9 CTO johnhtodd 在评论区亲自回应，承认地理封锁无法精确实现对特定域名的选择性解析、围绕“如何屏蔽法国用户”的追问花错了力气，并表示很可能在 11 月 24 日之后对法国用户启用 geoIP 过滤。其他评论者则质疑追责解析器的逻辑：有人指出索尼用 VPN 绕过封锁后 Quad9 仍被罚款、近乎“做了能做的一切反被惩罚”，还有人将其比作“因电话簿里出现罪犯号码而惩罚电话簿公司”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lawyerd.net/news/paris-court-blocking-orders-dns-vpn-search-engines/">French blocking order: DNS resolvers, VPNs, search engines ...</a></li>
<li><a href="https://www.heise.de/en/news/Censorship-ruling-prompts-DNS-service-Quad9-to-leave-France-11497631.html">Censorship ruling prompts DNS service Quad9 to leave France</a></li>

</ul>
</details>

**标签**: `#dns`, `#internet-infrastructure`, `#geoip-blocking`, `#legal`, `#censorship`

---

<a id="item-tech-news-2"></a>
### [Switch 2 越狱技术细节公布，AI 代理驱动硬件自动化研究](https://pepsipu.com/blog/2026-10-switch2-jailbreak-ns2jb/) ⭐️ 8.0/10

2026 年 10 月 22 日，作者 ledoge 在个人博客 pepsipu.com 发布题为《Jailbreaking the Switch 2》的技术文章，介绍任天堂 Switch 2 的越狱方法，并称其实现了对主机文件系统的解密读写访问。文章还描述了一套自动化研究装置：AI 编码代理（原文提及 Codex）通过 JetKVM 硬件向 Switch 2 发送 USB 手柄输入并接收 HDMI 视频输出，再由一个蓝牙控制的机械装置在主机死机时按下电源键重启，使实验流程可以无人值守地持续运行。这些技术声明目前仅来自博主本人，尚未得到独立验证，评论者在讨论时也对漏洞的完整影响范围有所保留。该文章在 Hacker News 上引发大量关注，获得 721 分和 252 条评论。

hackernews · ledoge · 10月22日 08:01 · [社区讨论](https://news.ycombinator.com/item?id=50192536)

**「背景」** 在 ns2jb 出现之前，Switch 2 尚无公开的纯软件越狱方案：据 GBAtemp 报道，若开发者 pepsipu 公布的细节可信，这是该主机的首个纯软件、tethered（需在每次启动时借助外部设备重新执行）的用户态越狱，据称支持最新的 23.0.1 固件。其入口据报是初代 Switch 游戏《SmileBASIC 4》中的一个漏洞——该游戏允许用户自行编写程序，为进入 Switch 2 系统提供了途径。据博客描述，ns2jb 可让任意原生代码以普通 sysmodule 身份运行，包括内置的文件系统模块（fs sysmodule），从而支持运行自制软件、逆向和修改 Switch 2 游戏以及备份存档。

**「游戏转储与重编译的连锁影响」** 若解密文件系统读写属实，社区预计 Switch 2 游戏转储可能在短时间内出现，并接入已相当成熟的重编译/反编译生态：GBAtemp 等社区维护着 N64 重编译移植列表，Switch 1 上也已有重编译作品实机运行的演示，且已有报道称任天堂对 AI 参与的 PC 移植日益担忧。这意味着主机独占游戏在任意硬件上运行——评论者所称任天堂的“最坏情形”——从设想变为可操作路径；但该结果目前仅出自个人博客，评论者对其完整范围亦有保留，在解密读写获得独立验证之前，转储与移植能否落地仍属推测。

**「社区讨论」** 评论者 hturan 推测，如果解密文件系统读写属实，Switch 2 游戏转储可能在数小时内出现，结合现有的重编译/反编译生态，主机独占游戏将能在任意硬件上运行——他称这是对任天堂而言的最坏情形，并以《塞尔达传说：王国之泪》在 iPhone 上原生以 60 帧运行为先例。评论者 rootsudo 则报告了不同体验：他尝试用 Codex 调查旧版 Android ROM 的 CVE 时被拒绝，因此不解这类安全研究为何能顺利进行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pepsipu.com/blog/2026-10-switch2-jailbreak-ns2jb/">pepsipu .com/blog/2026-10- switch 2 - jailbreak - ns 2 jb</a></li>
<li><a href="https://gbatemp.net/news/switch-2-jailbreak-ns2jb-released-software-only-exploit-tethered.685698/">Switch 2 jailbreak &quot; ns 2 jb &quot; released. Software-only exploit , tethered</a></li>
<li><a href="https://www.androidauthority.com/nintendo-switch-2-software-jailbreak-3727013/">Nintendo Switch 2 jailbreak could open the door to a world of mods</a></li>
<li><a href="https://www.youtube.com/watch?v=PHezpbUQ94E">Burnout 3: Takedown - ( Nintendo Switch 1) - Recompilation ...</a></li>
<li><a href="https://gbatemp.net/threads/full-list-of-n64-recompilation-switch-ports.681836/">Full List of N64 Recompilation Switch ports | GBAtemp.net - The...</a></li>
<li><a href="https://www.noobfeed.com/news/nintendo-concerns-pc-ports-games">Nintendo Faces Growing Concerns Over AI-Powered PC... | NoobFeed</a></li>

</ul>
</details>

**标签**: `#hardware-security`, `#reverse-engineering`, `#nintendo-switch-2`, `#homebrew`, `#ai-agents`

---

<a id="item-tech-news-3"></a>
### [Earstrip 三角剖分库 489 毫秒处理 370 万地图多边形，超越 Earcut](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 8.0/10

一款名为 Earstrip 的新多边形三角剖分库公布了基准结果：370 万个地图多边形的三角化在 489 毫秒内完成，速度快于地图渲染领域事实上的标准库 Earcut。该库提供 WASM 构建，作者还公开了测试数据集，不过这些数字目前来自作者自己的基准，尚无独立复现。Earcut 的作者在 Hacker News 上称赞这项工作，表示会研究能否把其中的优化技巧借鉴到 Earcut 的 JS 版本，同时指出 Earcut 为控制包体积（压缩后约 4.1 KB）有意拒绝了部分优化，对 Mapbox GL JS 等实际应用来说已经足够快。Delaunay32 的作者也提议用其基于分治法的约束 Delaunay 三角剖分器与 Earstrip 做对比基准。

hackernews · molind · 10月22日 09:31 · [社区讨论](https://news.ycombinator.com/item?id=50193170)

**「背景：Earcut 与地图三角剖分」** 在地图渲染中，多边形面要素需要先剖分成三角形才能交给 GPU 绘制，三角剖分因此是地图引擎渲染管线的基础环节。Mapbox 开源的 Earcut 是基于耳切法（ear clipping）的多边形三角剖分库，长期被视作该领域的事实标准，并被 Mapbox GL JS 等地图渲染方案采用。此次发布的 earstrip 正是以 Earcut 为对标对象：采用与它相同的 ISC 许可证，以单个 C++ 头文件发布并在 npm 提供 WebAssembly 构建，接口参数与 Earcut 完全一致，因而可以直接替换和对比。

**「对地图渲染开发者的影响」** 对于因多边形三角剖分而出现性能瓶颈的地图渲染与 GIS 管线，开发者现在可以用作者公开的数据集在自己的负载上实测这款新库（Earstrip），并与 Earcut、Delaunay32 等现有方案对比后择优采用。不过浏览器端替换未必划算：Earcut 作者 mourner 表示，他为了把包体积控制在 4.1 kB（min+gzip）有意拒绝了部分优化，对 Mapbox GL JS 等大多数实际应用而言 Earcut 已足够快；而 Earcut 正是 Mapbox GL JS、Three.js 等项目广泛依赖的三角剖分库，因此采用新库前需先确认其 WASM 构建体积——这一数据目前尚未公布。另有评论者质疑新库输出中大量细长三角形可能拖慢 GPU 光栅化，该问题尚无实测结论，采用前宜结合自身渲染场景评估三角形质量。

**「社区讨论」** Earcut 作者称赞该库并考虑借鉴其技巧，但强调包体积是 Earcut 的刻意取舍；Delaunay32 作者则提议用其分治法剖分器做直接基准对比。用户 stymaar 质疑结果中大量细长三角形可能不利于 GPU 光栅化，用户 mistercow 则追问为何耳切法在实践中胜过时间复杂度接近线性的 Seidel 梯形法——这些属于讨论中的观点与未解问题，而非已验证的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut : triangulating 3 . 7 M map polygons in 489 ms</a></li>
<li><a href="https://github.com/MichaCo/Earcut">MichaCo/ Earcut : Fast and robust ear -clipping polygon triangulation ...</a></li>
<li><a href="https://github.com/mapbox/earcut">GitHub - mapbox/earcut: The fastest and smallest JavaScript ...</a></li>
<li><a href="https://hysenlabs.com/projects/mapbox-earcut">earcut npm: polygon triangulation for WebGL | Hysen Labs</a></li>

</ul>
</details>

**标签**: `#computational-geometry`, `#triangulation`, `#performance-optimization`, `#gis-mapping`, `#wasm`

---

<a id="item-tech-news-4"></a>
### [研究：部分智能电视关闭内容识别后仍回传观看数据](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 8.0/10

一项名为“Watching the Watchers”的研究对美国市场上 10 家厂商的 12 台智能电视开展了 5943 次受控实验，发现部分机型即使用户在设置中关闭自动内容识别（ACR），仍会继续上传与观看内容相关的流量。其中 VIDAA OS 通过明文 MQTT 协议传输数据，包含不可重置的设备 ID 和音频指纹；Vizio 的 WatchFree+ 则把节目名写入未加密的 DNS 域名查询，且用户无法关闭这一行为。这些属于研究团队的实测结果而非厂商披露，说明在受影响机型上退出 ACR 并不能完全阻止内容相关数据的外传。

telegram · zaihuapd · 10月22日 09:50

**「什么是自动内容识别（ACR）」** 自动内容识别（ACR）是智能电视普遍采用的技术：加州大学戴维斯分校的计算机科学家解释说，这类电视会截取屏幕上的内容并共享给厂商，后者可将其用于销售广告。以三星、Vizio、Roku 等系统为例，用户可以在电视设置中退出这类追踪。据研究团队介绍，这项研究是首个针对美国八大主流智能电视操作系统（合计约占美国市场 95%）的自动化、规模化 ACR 测量，共测试了 12 台市售电视。

**「对用户的影响」** 对已在设置中关闭 ACR 的用户来说，这个开关不能被当作可靠的隐私控制：三星、Vizio 和 Roku 系统的电视在用户退出追踪后仍持续向 ACR 端点发送数据。由于 Vizio WatchFree+ 的节目名外泄无法在电视设置中关闭，VIDAA OS 又以明文 MQTT 发送不可重置的设备 ID 和音频指纹，想阻止观看数据离开电视的用户只能考虑在网络层面限制电视的联网或流量，而不是依赖设备自带的隐私菜单。此外，ACR 由各厂商自行实现，没有统一的采样频率、数据流或保留期限，一台电视的退出效果不能推广到其他机型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/gadgets/2026/10/does-opting-out-of-smart-tv-tracking-work-research-finds-suspicious-traffic/">Does opting out of smart TV tracking work? Research ... - Ars Technica</a></li>
<li><a href="https://watchingthewatchers.github.io/watchingthewatchers/index.html">Watching the Watchers : Privacy Analysis of U.S. Smart TV ...</a></li>
<li><a href="https://www.ucdavis.edu/news/your-smart-tv-watching-what-you-watch">Your Smart TV is Watching What You Watch | UC Davis</a></li>
<li><a href="https://arstechnica.com/gadgets/2026/10/does-opting-out-of-smart-tv-tracking-work-research-finds-suspicious-traffic/">Does opting out of smart TV tracking work? Research... - Ars Technica</a></li>
<li><a href="https://www.offlist.me/blog/disable-smart-tv-data-collection">Disable Smart TV ACR Data Collection (Samsung, LG, Roku 2026)</a></li>

</ul>
</details>

**标签**: `#privacy`, `#security-research`, `#smart-tv`, `#surveillance`, `#iot`

---

<a id="item-tech-news-5"></a>
### [禁运 Nvidia B300 服务器现身中国移动宁夏数据中心采购](https://theinference.org/article/china-s-state-money-bought-banned-nvidia-b300-servers-then-redacted-the-receipts) ⭐️ 8.0/10

据 The Inference 与 Quartz 报道，中国国资控股的半导租赁集团为 AI 公司荣耀视图科技融资购入 32 台搭载 Nvidia B300 芯片的华硕服务器，该采购是总额超 30 亿元人民币、共 700 余台服务器交易的一部分，计划部署于中国移动宁夏数据中心。B300 属于美国对华基本禁运的最严出口管制层级，若属实，这将构成受管制 AI 芯片经国有融资渠道进入中国运营商算力设施的一起违规事件。报道指出，相关备案受到关注后，半导租赁重新提交文件并抹去了硬件描述；Nvidia 表示正联合代工伙伴调查，华硕则称其遵守出口管制。该事件目前仍是基于采购文件的指控，相关方正在核查，尚未被证实为确定的违规。

telegram · zaihuapd · 10月22日 15:22

**「背景：B300 与对华出口管制」** B300 是 Nvidia Blackwell 系列的数据中心 AI 芯片，被列入美国对华出口管制中最严格的层级，基本禁止销往中国，因此这类芯片进入中国数据中心即涉及管制规避问题。据彭博 10 月初的报道，这批交易最早是通过中国公共信用登记系统中的融资备案文件被发现的，融资方半导租赁（Semi-Tech Leasing）由深圳和北京的市级国资实体控制。

**「对华高端芯片采购与渠道合规风险上升」** 对通过融资租赁等渠道采购美国顶级 AI 芯片的中国机构而言，此案（尚在调查中）把合规风险具体化：B300 被美国商务部工业与安全局归入 ECCN 3A090.a 最严出口管制类别，交易一旦曝光，不仅中国移动宁夏枢纽这类部署计划可能受阻，已购设备也面临调查乃至处置风险。对 Nvidia 与华硕等渠道伙伴，这是数月内第二起 B300 疑似流向中国的案件——2026 年 8 月台湾方面的一份起诉书曾指控一名 Nvidia 经理为向中国转移而解锁 B300 服务器——面向中国的高端服务器销售预计将面临更严格的最终用途与融资结构核查，Nvidia 已表示正联合制造伙伴调查。在美国立法者已在评估封堵出口管制漏洞的背景下，这类在备案中抹去硬件描述的案例，可能为针对融资与租赁渠道的更严核查规则提供直接依据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tftc.io/nvidia-blackwell-chinese-state-financing-export-controls">Nvidia Blackwell Chips Tied to Chinese State Financing · TFTC</a></li>
<li><a href="https://qz.com/chinese-state-firm-nvidia-blackwell-chip-purchases-100226">Chinese state firm financed restricted Nvidia Blackwell chip ...</a></li>
<li><a href="https://www.techtimes.com/articles/325419/20260825/nvidia-manager-unlocked-b300-server-diversion-china-taiwan-indictment-says.htm">Nvidia Manager Unlocked B300 Server Diversion To China ...</a></li>
<li><a href="https://www.cnbc.com/2026/08/19/china-ai-nvidia-chips-us-export-controls.html">China AI firms tap Nvidia power overseas as U.S ... - CNBC</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#AI hardware`, `#semiconductors`, `#China`

---

<a id="item-tech-news-6"></a>
### [NVIDIA 组织发布 OpenShell:面向自主 AI 代理集群的沙箱运行时](https://github.com/NVIDIA/OpenShell) ⭐️ 7.0/10

OpenShell 以 NVIDIA 组织名义出现在 GitHub 上,定位为面向自主 AI 代理集群的“安全、私密”运行时:按项目介绍,它让代理保留读取文件、安装软件包、调用 API 和使用凭据的能力,同时不授予对数据、机密和网络的无限访问权限。该发布于 2026 年 10 月 22 日登上 Hacker News,获约 300 分和 160 条评论,讨论集中于代理沙箱的实现方式及其安全声明是否言过其实。需要说明的是,本次可得的材料只有发布链接与社区评论,缺乏技术文档或独立评测,上述安全能力目前仅是项目方说法,实际隔离效果无法据此核实。

hackernews · niemandhier · 10月22日 17:44 · [社区讨论](https://news.ycombinator.com/item?id=50198675)

**「代理沙箱的能力与安全权衡」** 自主 AI 代理要有用，就需要能读取文件、安装软件包、调用 API 和使用凭据，而这些权限给得越多，数据、密钥和网络被滥用或外泄的风险也越大，这正是代理沙箱化要处理的核心矛盾。从此次讨论看，此前团队大多自行拼凑隔离方案：把代理放进容器里运行，再配合按域名限制网络、轮换凭据的独立工具，配置分散且缺少统一的策略层。OpenShell 由 NVIDIA 以 Apache-2.0 许可证在 GitHub 开源，把沙箱、策略和凭据代理整合为一个专用运行时，第三方介绍称其目前处于早期预览阶段并存在已知限制。

**「对代理部署团队的影响」** 对已在运行自主编码代理的团队，OpenShell 提供了一条低改造成本的管控路径：据项目页面，OpenClaw、Claude Code、Codex 等代理可原样运行，文件系统、网络与进程控制在代理工作负载之外强制执行，并记录每次允许与拒绝决策的完整审计轨迹，因此团队无需改动代理本身即可叠加访问控制。行动上，已在容器中隔离代理的团队可将其作为这些容器的管理层来评估——有开发者表示代理本就应运行在容器中，并认为该工具是管理这类容器的合适方式，也有用户称其团队已使用一段时间，并在其上叠加团队策略、安全 git 使用等能力。但采用者不应将其视为完整防线：一位评论者认为其宣传回避了“给代理的访问越多、能力越强”这一根本权衡，读起来像能兼顾一切；另有用户反馈即使把网络限制到可信域名，仍难以阻止代理对代码库等数据的外泄，网络白名单不能替代数据防泄漏措施。

**「社区讨论」** 评论区的核心分歧在于安全声明是否可信:smallnix 认为项目宣传“既给代理充分能力、又不给无限制访问”掩盖了能力与风险同步上升的矛盾,读起来像“什么都能做还很安全”,这不可能是真的;mfro 则认为不给代理套容器“简直是疯了”,OpenShell 的价值在于让这类容器的管理更方便。使用经验方面,razuba 称团队已使用 OpenShell 一段时间,并正在其上构建团队策略、安全 git 使用与 SCA/SAST 能力,同时警告其见到的代理行为轨迹显示“无边界的目标追求”真实存在;fennecbutt 介绍了用 iron proxy 做域名级网络限制和凭据替换的做法,但指出防止代码库外泄\(类似 HF 事件\)仍是未解难题;crypt1d 则报告在自建类似工具时被 Claude 的安全分类器拦下,无法实现进程执行审计功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/NVIDIA/OpenShell">GitHub - NVIDIA / OpenShell : OpenShell is the safe, private runtime ...</a></li>
<li><a href="https://www.intelligenthq.com/nvidia-ecosystem/products/openshell/">NVIDIA OpenShell : secure runtime for AI agents ... | IntelligentHQ</a></li>
<li><a href="https://nvidia-openshell.com/">OpenShell</a></li>
<li><a href="https://build.nvidia.com/openshell">NVIDIA OpenShell</a></li>

</ul>
</details>

**标签**: `#ai-agents`, `#security`, `#sandboxing`, `#containers`, `#open-source`

---

<a id="item-tech-news-7"></a>
### [Getting ready to operate GNU Taler in Germany](https://www.taler.net/en/news/2026-13.html) ⭐️ 7.0/10

GNU Taler, an open-source privacy-preserving payment system, is preparing for real-world operation in Germany, prompting community debate over e-money expiration, KYC constraints, and Europe&\#x27;s need for independent payment infrastructure.

hackernews · dewey · 10月22日 16:14 · [社区讨论](https://news.ycombinator.com/item?id=50197404)

**标签**: `#digital-payments`, `#privacy`, `#gnu-taler`, `#open-source`, `#regulation`

---

<a id="item-tech-news-8"></a>
### [eMudhra 宣布退出全球 SSL/TLS 证书业务](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

证书颁发机构 eMudhra 宣布退出全球 SSL/TLS 证书业务,公司称此事发生在一次引发浏览器和 Web 信任社区高度关注的证书误签发事件之后。eMudhra 表示其全球 SSL/TLS 基础设施与其其他业务\(如全球数字签名服务\)是分开运行的,并将此次退出定位为对整体业务影响有限的调整。目前公告原文细节有限,关于事件的完整原因和责任归属仍缺乏公开说明。

hackernews · bo0tzz · 10月22日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50195110)

**「事件背景」** 此前有研究披露，eMudhra 的 8 个中间 CA 私钥竟然是小于 256 的整数（其中一个就是数字 4），第三方研究者验证了公开签名证明并称能在毫秒级时间内暴力破解全部密钥，其中既有 TLS 密钥也有代码签名密钥。 Mozilla 曾将受影响的证书附在其通告中，并据 Mozilla Bugzilla（编号 2083449）展开了针对该事件的公开调查，Chrome 团队也在该议题下提交了大量质询。由于被泄露的 CA 密钥可被用于伪造受信任证书，该事件波及范围不止浏览器，还涉及用系统信任库校验云端配置的各类设备。

**「影响」** 使用 eMudhra SSL/TLS 证书的网站和运营方需要尽快将其证书迁移到其他受信任的证书颁发机构,因为该公司将停止这一业务,后续续期和签发将不再可用。

**「社区讨论」** 社区评论普遍对 eMudhra 持批评态度:有评论指出涉事 CA 使用了强度极低的私钥\(甚至被戏称为一位数的 RSA 密钥\),且公司未就事故原因做出充分解释,这加深了不信任感。另有评论提到 Chrome 团队曾通过 Mozilla 的缺陷跟踪系统向 eMudhra 公开提出了一整套尖锐问题,显示浏览器厂商对此次事件的审查非常严格;也有评论质疑该公司&quot;受影响的 CA 未签发过最终实体证书&quot;的说法,认为任何人都可以用受影响的 CA 签发证书,这一声明并不可靠。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/frankchu/eight-ca-private-keys-were-integers-under-256-i-recovered-all-eight-in-11-milliseconds-4o1f">Eight CA private keys were integers under 256.... - DEV Community</a></li>
<li><a href="https://scotthelme.co.uk/eight-bits-of-trust-emudhras-ca-keys-cracked-in-milliseconds/">Eight Bits of Trust; eMudhra &#x27;s CA keys cracked in milliseconds</a></li>
<li><a href="https://github.com/miilv/ya-station-root-shell">miilv/ya-station-root-shell: Full chain reproduction: eMudhra CA MITM...</a></li>

</ul>
</details>

**标签**: `#TLS/SSL`, `#PKI`, `#certificate-authorities`, `#web-security`, `#browser-trust`

---

<a id="item-tech-news-9"></a>
### [Arc 浏览器告别：社区回顾其创新 UX 并转向替代品](https://arc.net/) ⭐️ 7.0/10

Arc 浏览器的开发已终止，Hacker News 上的一场讨论（229 分、209 条评论）成为用户告别该产品的场合。开发方将资源转向了 AI 导向的 Dia 浏览器，多位长期用户表示 Dia 无法替代 Arc 的核心体验。社区成员正在迁移到 Zen 等基于 Firefox 的替代品或 Orion 等 WebKit 浏览器。

hackernews · suhdonghwi · 10月22日 16:27 · [社区讨论](https://news.ycombinator.com/item?id=50197601)

**「从 Arc 到 Dia：2025 年的转折」** Arc 浏览器由 The Browser Company of New York 开发，2025 年 9 月 Atlassian 宣布以 6.1 亿美元收购这家同时拥有 Arc 和 Dia 两款浏览器的公司。同样在 2025 年，该公司停止了 Arc 的新功能开发，将资源转向内置 AI 功能的 Dia 浏览器，并承认 Arc 独特的界面虽然受到早期用户喜爱，但其复杂性和所谓的“新奇税”（novelty tax）限制了更广泛的采用。

**「影响」** 现有 Arc 用户需要选择迁移路径：评论者推荐的替代品包括近乎即插即用的 Zen 浏览器（基于 Firefox，继承了侧边栏标签、固定标签、空间等 Arc 设计），以及 Kagi 团队开发、基于 WebKit 的 Orion（支持垂直标签和页面修改，但并非开源）。用户需注意引擎差异可能影响扩展兼容性，例如 Chrome 扩展在 Firefox 系的 Zen 上不可用。

**「社区讨论」** 评论者普遍认为 Arc 转向 Dia 后其结局已在意料之中：slantedview 认为 Dia 缺少 Arc 的空间功能及跨配置共享标签的能力，对重度用户是交易杀手；jamie\_ca 和 constantlm 则推荐 Zen 作为接近无缝的替代品。throwaway13337 赞赏 Orion 背后 Kagi 自负盈亏、不依赖风投的商业模式，但指出其不开源是一大遗憾。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/10/22/arc-browser-sunsets-december-22-as-the-browser-company-doubles-down-on-dia/">Arc browser sunsets December 22 as The Browser Company ...</a></li>
<li><a href="https://www.atlassian.com/blog/company-news/atlassian-acquires-the-browser-company">Welcoming The Browser Company to Atlassian</a></li>
<li><a href="https://www.kucoin.com/news/flash/the-browser-company-to-discontinue-arc-on-december-22-2026-shifting-focus-to-ai-powered-dia">The Browser Company to Discontinue Arc on December ... - KuCoin</a></li>

</ul>
</details>

**标签**: `#web-browsers`, `#arc-browser`, `#ai-browsers`, `#browser-alternatives`, `#tech-industry`

---

<a id="item-tech-news-10"></a>
### [pwn.watch：实时追踪在野利用漏洞的仪表板上线](https://pwn.watch/) ⭐️ 7.0/10

pwn.watch 是一个实时仪表板，用于追踪正在被主动利用的安全漏洞和事件，于 Hacker News 上引发关注（346 分、161 条评论）。它面向需要排定补丁优先级和响应威胁的工程师，定位为在野利用情况的聚合展示。不过，有用户指出其事件分类方法存在明显问题：例如 Signal 的 ringrtc 漏洞 CVE-2026-113380 补丁已发布一个多月，且并无已知利用，但该站点仍将其标注为&quot;Live&quot;和&quot;ongoing&quot;。

hackernews · mrkd · 10月22日 14:08 · [社区讨论](https://news.ycombinator.com/item?id=50195543)

**「背景」** pwn.watch 属于&quot;在野利用&quot;（actively exploited）漏洞追踪类工具：与按理论严重程度排序的 CVE 数据库不同，它汇总正在被实际利用或被披露的安全事件，帮助工程师决定补丁优先级。理解社区讨论中的一个争议案例需要具体背景：评论者 aeturnum 提到的 Signal 漏洞 CVE-2026-113380 出自 RingRTC 库（2.72.0 之前的版本），会在用户按下挂断后仍保持通话音频通道开放，该漏洞于 2026 年 10 月 20 日被披露并评为 CVSS 9.3 的严重级别。评论者质疑的正是 pwn.watch 将这一已修复一个多月的事件仍标记为&quot;进行中&quot;（ongoing）的分类方法。

**「对安全团队的影响」** 对于负责补丁管理和应急响应的安全团队，pwn.watch 提供了一个可实时查看在野利用事件的免费看板，可用于辅助确定修复优先级；这一需求的规模不小——2025 年 CISA 向 KEV 目录新增了 245 个在野利用漏洞，其中 31 个被勒索软件利用，最常受影响的厂商为 Microsoft、Apple 和 Cisco，且在野利用数量较 2024 年显著增加。但评论者指出该站点的分类方法存在缺陷：一个补丁已发布一个多月的 Signal 漏洞仍被标记为 &quot;Live&quot; 和 &quot;ongoing&quot;，且据其描述并无已知利用。因此团队在依据该看板排定修复优先级时，应与厂商公告或 CISA KEV 等一手来源核对事件状态，避免把已修复的问题误判为仍在活跃利用。

**「社区讨论」** 用户 aeturnum 质疑其分类逻辑：一个已无已知利用、补丁发布一个半月后的事件仍被标记为&quot;ongoing&quot;，不知何时才算结束。另有评论者认为漏洞被发现的速度&quot;疯狂&quot;增长，并将近期攻击激增归因于当代 LLM 能力的普及；还有用户指出 pwn.watch 与 CVE 严重性时间线工具 supplychain.fail 形成互补。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://1275.ru/vulnerability/ochered-sobytiy-vyzovov-signal-dopuskaet-proslushivanie-posle-zaversheniya-zvonka_49184">Очередь событий вызовов Signal допускает прослушивание после...</a></li>
<li><a href="https://www.securitylab.ru/news/579109.php">В Signal нашли способ слушать человека даже после попытки...</a></li>
<li><a href="https://osint.foundation/cve/year/2025">Exploited Vulnerabilities of 2025 : 245 CVEs Added to CISA KEV</a></li>
<li><a href="https://threatresearch.ext.hp.com/reviewing-zero-day-vulnerabilities-exploited-in-malware-campaigns-in-2025/">Reviewing Zero-day Vulnerabilities Exploited in Malware Campaigns...</a></li>

</ul>
</details>

**标签**: `#security`, `#threat-intelligence`, `#vulnerability-tracking`, `#cybersecurity`, `#incident-response`

---

<a id="item-tech-news-11"></a>
### [Anthropic 将 Agent Skills 标准捐赠给 Linux 基金会旗下 AAIF](https://simonwillison.net/2026/Oct/22/donating-agent-skills/) ⭐️ 7.0/10

Anthropic 宣布将 Agent Skills 标准捐赠给 Linux 基金会旗下的 Agentic AI Foundation\(AAIF\),使其成为厂商中立、社区驱动的开放标准。AAIF 由 Anthropic 与 Block、OpenAI 于 2025 年共同创立,此前已接收 Model Context Protocol\(MCP\)规范的捐赠,Agent Skills 是进入该基金会的又一项关键代理技术标准。Simon Willison 指出,他在 2025 年 12 月 Anthropic 首次将 Skills 称为&quot;开放标准&quot;时就预测到这一归属,并借助自己博客的 MCP 插件让 Claude 检索到了当年的原文;此次捐赠延续了 MCP 开创的模式,即核心代理技术规范逐步从单一厂商掌控转向中立治理。

rss · Simon Willison · 10月22日 18:09

**「背景」** Agentic AI Foundation\(AAIF\)是 Anthropic 于 2025 年与 Block、OpenAI 共同创立、隶属 Linux 基金会的厂商中立标准组织,Model Context Protocol\(MCP\)规范此前已被捐入该基金会。Agent Skills 是 Anthropic 在 2025 年 12 月首次宣称为&quot;开放标准&quot;的代理技能规范,博主 Simon Willison 当时便预测该标准最终会进入 AAIF。

**「对开发者的影响」** 对使用 Agent Skills 封装智能体专用知识与工作流的团队而言，该开放标准的治理权移交至 Linux 基金会旗下的 AAIF，意味着其后续演进不再由 Anthropic 单独决定，采用方对单一厂商路线的依赖随之降低。由于 MCP 规范此前也已捐入同一基金会，开发者可以在同一个中立机构下跟进并参与这两项智能体互操作标准的发展。就公告内容而言，此次变更仅涉及标准治理归属，未提及技术规范本身的修改。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/donating-agent-skills-to-the-agentic-ai-foundation">Donating Agent Skills to the Agentic AI Foundation \ Anthropic</a></li>
<li><a href="https://blockchain.news/news/anthropic-donates-agent-skills-standard-to-aaif">Anthropic donates Agent Skills standard to AAIF - blockchain.news</a></li>

</ul>
</details>

**标签**: `#agent-skills`, `#agentic-ai`, `#open-standards`, `#anthropic`, `#linux-foundation`

---

<a id="item-tech-news-12"></a>
### [Carbon-X:DNA 与文本联合训练的 148 亿参数开源模型](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

Carbon-X 是一个 148 亿参数、Apache 2.0 许可的 decoder-only 开源模型,让 DNA 序列和英文文本共享同一条由 6-mer token 组成的 token 流,经过 3020 亿 token 的中期训练后,可以在普通对话中直接接收原始 DNA 并用英文作答。据其 Hugging Face 模型页报告,在关闭思考模式的五个 DNA 基准上平均得分 66.7%,接近 GPT-6.1 Sol 的 67.5%,但该对比为发布方自报,尚无独立验证。权重以 bfloat16 精度可装入单张 80GB GPU,使敏感基因组数据的序列分析能够完全在本地进行,不过模型尚未经过临床验证,模型卡也注明精确的序列操作仍应交由代码处理。发布者本人提出的关键问题——基准上的提升在私有变异数据集上是否同样成立——目前还没有答案。

reddit · r/MachineLearning · /u/jatingargiitk · 10月22日 12:32

**「背景」** 要让语言模型读取 DNA,首先需要解决分词问题:Carbon-X 将 DNA 序列按每 6 个连续碱基\(6-mer\)切分为 token,并与英文文本共用同一套词表,因此一个标准的 decoder-only Transformer 可以用同一套机制同时处理 DNA 和英文。另一个背景是,据第三方模型资料页,该模型并非从零训练,而是在开源文本模型 Qwen3-14B 的基础上继续中期训练\(mid-training\)而来,这解释了这个 14.8B 参数的模型为何能用英文回答 DNA 相关问题。

**「对敏感基因组数据分析的影响」** 对于处理敏感基因组数据（如人类变异或临床样本）的实验室与开发者，Carbon-X 以 Apache-2.0 发布、bfloat16 权重可装入单张 80GB GPU，意味着 DNA 序列分析可以完全在本地运行，无需将序列上传到外部服务，直接回应了基因组数据通常不便外传的限制。采用前需注意：模型卡明确要求精确的序列操作仍应交由代码处理，且 66.7% 对 GPT-6.1 Sol 67.5% 的基准成绩为发布方自报、未经临床验证，发布者本人也在询问这些提升在私有变异数据集上是否成立；此外，现有 DNA 语言模型评测框架对分词方案敏感，例如 BEND 处理 6-mer 分词时需将每个嵌入向量重复 6 次，而 DNABERT-2、GROVER 等采用 BPE 分词，跨模型直接比较分数时需相应配置评测流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.llmreference.com/model/carbon-x">Carbon-X – 40K context, open source | LLM Reference</a></li>
<li><a href="https://tools4all.ai/trends/carbon-x-148b-dna-text-jointly-trained-model-released">Carbon-X: 14.8B DNA-Text Jointly Trained Model Released</a></li>
<li><a href="https://github.com/frederikkemarin/BEND">frederikkemarin/BEND: Benchmarking DNA Language Models on...</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#genomics`, `#DNA-language-models`, `#open-source-models`, `#model-release`

---

<a id="item-tech-news-13"></a>
### [澳洲法院裁定苹果须向第三方应用商店开放 iPhone](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

澳大利亚联邦法院裁定，苹果必须从 2027 年 3 月 1 日起允许澳区 iPhone 用户通过第三方应用商店和网站安装应用，并开放替代支付方式与外部支付链接。裁决源于 Epic Games 的反垄断诉讼，法官认定苹果在 iOS 应用分发和支付市场具有实质性市场力量，其限制竞争的行为违反澳大利亚竞争法。作为裁决的一部分，Fortnite 将立即重返澳区 App Store。苹果表示将提起上诉并申请暂缓执行，因此该裁决在 2027 年期限前能否如期落地仍存变数。

telegram · zaihuapd · 10月22日 06:54

**「案件背景」** 此案源于 Epic Games 与苹果之间持续多年的反垄断诉讼。澳大利亚联邦法院 Jonathan Beach 法官已于今年 8 月先行作出责任认定，裁定苹果在 iOS 应用分发和支付市场具有实质性市场力量、其限制竞争的做法违反澳大利亚竞争法；本次要求开放第三方应用商店与替代支付的裁决，正是在该责任认定基础上作出的救济命令。

**「对开发者的影响」** 若裁决如期生效，澳大利亚的 iOS 开发者将可以在 App Store 之外的渠道分发应用，并通过外部支付链接或替代支付方式收款，不再被限定于苹果的应用内支付体系。不过由于苹果已表明将上诉并申请暂缓执行，开发者在合规日期和最终规则明确之前，暂不宜据此重构应用分发与支付方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">Apple must open iPhone to alternative app stores in Australia ...</a></li>
<li><a href="https://smbtech.au/news/federal-court-orders-apple-to-allow-rival-app-stores-and-payments-on-iphones-in-australia/">Federal Court Orders Apple To Allow Rival App Stores And ...</a></li>

</ul>
</details>

**标签**: `#Apple`, `#antitrust`, `#app-store regulation`, `#Epic Games`, `#iOS`

---

<a id="item-tech-news-14"></a>
### [米哈游联合清华大学开源 GameScaling 键鼠操作模型](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

米哈游崩坏 AI 团队联合清华大学等开源了 GameScaling，一套基于 Qwen3.5 视觉语言模型、针对游戏键鼠操作做继续预训练的模型家族，规模覆盖 0.8B 至 27B，每次输出未来 200 毫秒的键鼠动作。配套论文已在 arXiv 发布，通过 120 组训练配置考察数据量、多样性与模型规模的影响，并报告：数据越多同源表现越好，多样性有助于迁移到相近游戏，而对差异较大的游戏世界提升有限。八个检查点与推理客户端已以 Apache-2.0 许可证开源，但发布内容不含训练代码。

telegram · zaihuapd · 10月22日 11:32

**「技术背景」** GameScaling 的基础是 Qwen3.5 视觉语言模型：研究团队在键鼠游戏操作数据上对其做继续预训练，使其能直接输出操作指令。据项目在 Hugging Face 和 GitHub 页面的说明，模型每次调用会读取当前游戏画面以及过去画面与动作的简短历史，输出未来 200 毫秒的键鼠动作，具体为 6 个 33 毫秒的步骤，外加整段一次鼠标移动和滚轮操作，并可在行动前先进行思考。理解这一「画面输入、毫秒级动作输出」的机制，是理解其 0.8B 至 27B 多规模版本与数据缩放研究的前提。

**「检查点可直接使用，但训练难以复现」** 开发者可以直接下载八个 Apache-2.0 检查点与推理客户端，用于游戏键鼠操作的推理部署或在自有数据上继续微调；但项目页明确说明训练语料不公开，发布物也不含训练代码，因此论文中 120 组配置得出的数据量、多样性与模型规模结论无法直接复现，想延续该 scaling 研究的团队需要自行采集游戏操作数据并搭建训练流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/THUSI-Lab/GameScaling">THUSI-Lab/GameScaling · Hugging Face</a></li>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/GameScaling: Scaling in Games: Continued ...</a></li>
<li><a href="https://gamescaling.github.io/">Scaling in Games : Continued Pre-Training for Embodied Agents in...</a></li>

</ul>
</details>

**标签**: `#vision-language-models`, `#game-ai-agents`, `#open-source-models`, `#scaling-study`, `#computer-use`

---

<a id="item-tech-news-15"></a>
### [甲骨文修复 Java SE JSSE 组件 CVSS 9.1 高危漏洞 CVE-2026-91403](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

甲骨文发布安全警报，披露 Java SE 的 JSSE（Java 安全套接字扩展，即 TLS/SSL 组件）存在编号 CVE-2026-91403 的严重漏洞，CVSS 评分 9.1，攻击者无需身份验证即可通过网络远程利用，可能严重破坏数据的机密性与完整性。受影响版本涵盖 Java SE 8u511、11.0.33、17.0.21、21.0.13、25.0.5、27.0.1 以及多个 GraalVM 版本。修复补丁已随警报同步发布，甲骨文呼吁用户尽快升级至受支持版本，防范潜在的网络攻击风险。

telegram · zaihuapd · 10月22日 12:30

**「背景」** JSSE（Java Secure Socket Extension，Java 安全套接字扩展）是 Java SE 内置的标准 TLS/SSL 实现库，负责处理 Java 应用的 HTTPS 及各类加密网络连接，是公网 Java 服务最常暴露的组件之一。GraalVM 则是 Oracle 基于 Java SE 构建的高性能 JDK 发行版，共享同一套 Java 类库，因此与各 Java SE 版本一同被列入受影响名单。由于 JSSE 处理的 TLS 握手发生在任何用户认证之前，攻击者无需凭据即可从网络侧直接发起利用，这类特性正是该漏洞获得 9.1 严重评分的关键背景。

**「影响与应对行动」** 由于该漏洞位于 JSSE（TLS）组件、无需身份验证即可通过网络远程利用，且 CVSS 3.1 基础评分 9.1 对数据机密性与完整性均构成影响，运行 Java SE 8u511、11.0.33、17.0.21、21.0.13、25.0.5、27.0.1 或受影响 GraalVM 版本的应用面临现实攻击风险，相关团队应尽快部署甲骨文已发布的补丁并升级至受支持版本。使用 OpenJDK 或基于其构建的 JDK 发行版的团队同样需要跟进：OpenJDK 已于 2026 年 10 月 21 日发布漏洞公告，列明本次更新修复的源代码漏洞，应确认所用构建已包含对应修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oracle.com/security-alerts/alert-cve-2026-91403.html">Oracle Security Alert Advisory - CVE - 2026 - 91403</a></li>
<li><a href="https://www.oracle.com/security-alerts/cve-2026-91403verbose.html">Text Form of Security Alert CVE - 2026 - 91403 Risk Matrices</a></li>
<li><a href="https://openjdk.org/groups/vulnerability/advisories/2026-10-21">OpenJDK Vulnerability Advisory: 2026 /10/21</a></li>

</ul>
</details>

**标签**: `#security`, `#java`, `#vulnerability`, `#oracle`, `#tls`

---

<a id="item-tech-news-16"></a>
### [333 个被植入 Ebury 后门的 Tor 出口节点下线](https://kaba.cx/posts/20261020_Tor/) ⭐️ 7.0/10

一名 Tor 运营者用脚本扫描约 3000 个出口中继，发现其中 333 个（约 10%）被植入 Ebury SSH 后门，这些节点可把 22 端口的 SSH 连接劫持到 12 台拦截服务器并窃取凭据。相关节点已于 10 月 4 日被标记为 BadExit，并在次日全部下线。调查还显示攻击者早在今年 8 月就入侵了这些服务器，并屏蔽部分端口以专门收集未加密的邮件流量，入侵途径目前尚无定论。该报告来自社区博客与 Telegram 渠道，而非 Tor 项目官方来源。

telegram · zaihuapd · 10月22日 14:52

**「背景：Ebury 是一个活跃十余年的老牌后门」** Ebury 并非新出现的威胁：它是一个 OpenSSH 后门与凭据窃取工具，ESET 在 2014 年 3 月披露的“Operation Windigo”行动中首次公开其细节，当时已有超过 1 万台 Linux 服务器被感染，每天将约 50 万访客重定向至恶意页面。ESET 后续研究显示，Ebury 一直在持续更新，累计感染约 40 万台 Linux 服务器，主要用于窃取加密货币等经济目的。换言之，此次在 Tor 出口节点上发现的是一个已活跃超过十年的老牌后门，而非针对 Tor 的新型攻击工具。

**「十月初经 Tor 的 SSH 凭据应视为已泄露」** 在 10 月 1 日至 5 日的攻击窗口内，经这 333 个出口节点转发的 22 端口 SSH 连接和未加密邮件流量可能已被劫持到 12 台拦截服务器，期间通过 Tor 登录服务器或发送明文邮件的用户应视为凭据已泄露，尽快更换密码与 SSH 密钥。据 DFIR Radar 统计，这批节点在峰值时占 Tor 出口容量的 7.46%。由于攻击者早在 8 月就已入侵这些服务器，Tor 中继运营者也应排查主机是否感染 Ebury 后门，防止节点再次被植入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2014/03/operation-windigo-linux-malware.html">Operation Windigo : Linux malware campaign that infected 500,000...</a></li>
<li><a href="https://www.welivesecurity.com/en/eset-research/ebury-alive-unseen-400k-linux-servers-compromised-cryptotheft-financial-gain/">Ebury is alive but unseen: 400k Linux servers compromised for...</a></li>
<li><a href="https://thenextweb.com/news/operation-windigo-10000-infected-linux-servers-redirecting-half-million-visitors-malware-every-day">Operation Windigo : 10,000 Linux Servers Redirecting to Malware</a></li>
<li><a href="https://x.com/DFIR_Radar/status/2112877196448542778">DFIR Radar on X: &quot;Ebury-linked actors hijacked 333+ Tor exit ...</a></li>
<li><a href="https://arstechnica.com/information-technology/2026/10/300-tor-exit-nodes-hijacked-to-intercept-ssh-traffic-and-retrieve-plaintext-email/">333 Tor exit nodes hijacked to intercept SSH traffic and ...</a></li>

</ul>
</details>

**标签**: `#security`, `#tor`, `#malware`, `#ebury`, `#privacy`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [软件慢的根源是设计，而非语言](https://seangoedecke.com/software-is-slow-because-of-bad-design-not-slow-languages/) ⭐️ 7.0/10

rss · Sean Goedecke · 10月23日 00:00

**「背景」** 面对 AI 编程浪潮，流行说法是用 C 或 Rust 重写软件就能大幅提速——毕竟 C 号称比 Python 快五十倍。作者 Sean Goedecke 认为这一直觉站不住脚：真实程序的性能瓶颈几乎不在语言本身，而在 I/O 等待与程序设计。

**「方案」** 他以典型 CRUD 网站说明：一个请求约一半时间耗在数据库查询上，重写成 C 只能加速另一半，受阿姆达尔定律限制，实际提速约 1.5 到 2 倍；curl 即使快 100 倍也无人察觉，因为它全程在等网络。至于真正的 CPU 密集部分，慢语言早已通过库委托给快语言——wiki 用 cmark-gfm 渲染 markdown，Python 的机器学习矩阵运算本就运行在优化的 C 或汇编代码上。反例确实存在：Actual Computer 用汇编重写 tiktoken，作者实测约 5 倍提速，但他认为这更可能源于避开正则依赖的重新设计，且分词只占推理时间的一小部分。Bryan Cantrill 曾把精心优化的 C 程序用朴素方式改写成 Rust，结果反而快了 30%，原因是 Rust 偏好缓存更友好的 B 树——可见即便 CPU 密集，性能仍由设计主导。作者自己的重大提速几乎都来自让程序&quot;少做事&quot;的重设计：缓存慢操作、异步化、并行化、合并 N+1 查询、优化 SQL、跳过不必要操作；高层语言反而更易看清程序在做什么、发现这些优化点。

**「启示」** 性能是设计的属性而非语言的属性；与其让 AI 代理重写程序，不如让它剖析热点、重新设计程序少做工作——换语言自有可移植性、可维护性等理由，但换不来多少原始速度。

**标签**: `#performance`, `#software-design`, `#programming-languages`, `#optimization`, `#ai-agents`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [沪深 300 较 6 月高点回落 20%，A 股逼近熊市](https://www.bloomberg.com/news/articles/2026-10-22/china-stocks-set-for-bear-market-as-ai-trade-policy-hopes-fade) ⭐️ 7.0/10

China&\#x27;s CSI 300 has dropped 20% from its June high, pushing A-shares to the brink of a bear market amid absent fiscal stimulus and earnings misses led by CATL&\#x27;s 12% plunge.

telegram · zaihuapd · 10月22日 05:05

**标签**: `#China equities`, `#bear market`, `#CSI 300`, `#CATL earnings`, `#fiscal stimulus`

---