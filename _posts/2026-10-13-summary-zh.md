---
layout: default
title: "Horizon Summary: 2026-10-13 (ZH)"
date: 2026-10-13
lang: zh
---

> 从 41 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [黑客远程触发欧洲超市冷柜除霜，法国多家超市被迫停业](#item-tech-news-1) ⭐️ 8.0/10
2. [WiFi 7 路由器被改造成 320 Msps 软件定义无线电接收器](#item-tech-news-2) ⭐️ 8.0/10
3. [Codex CLI installs a persistent, self-updating background daemon by default](#item-tech-news-3) ⭐️ 7.0/10
4. [Meta 发布 Muse Wonder 模型，实测表现与跑分引争议](#item-tech-news-4) ⭐️ 7.0/10
5. [Python 3.15 发布：显式延迟导入与采样分析器，3.10 退出支持窗口](#item-tech-news-5) ⭐️ 7.0/10
6. [循环扩散 Transformer：同一组块在去噪步骤内多次运行，循环深度可在采样时调整](#item-tech-news-6) ⭐️ 7.0/10
7. [learnc：用数据拟合 C 代码中的常量，JPEG 体积再省 9.1%](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic：新反蒸馏防护使提取数据初步减少 90% 至 99%](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [中欧就混动、电动汽车贸易达成共识，中方配额不低于其他来源](#item-finance-news-1) ⭐️ 7.0/10
2. [新能源汽车出口退税率由 13% 下调至 9%](#item-finance-news-2) ⭐️ 7.0/10
3. [税务处罚新裁量基准 11 月施行，社保欠缴最高罚 3 倍](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [黑客远程触发欧洲超市冷柜除霜，法国多家超市被迫停业](https://www.tomshardware.com/tech-industry/cyber-security/unprecedented-cyberattack-cripples-supermarket-fridges-across-europe-as-hackers-activate-automatic-defrosting-delivery-and-store-prices-also-impacted-by-incident) ⭐️ 8.0/10

2026 年 10 月 12 日，据路透社、BBC 和《世界报》报道，黑客通过联网制冷控制器远程触发了欧洲超市冷柜的自动除霜程序，法国连锁超市 Intermarché 约有 150 家门店成为攻击目标，部分门店被迫关闭。除制冷系统外，配送和门店定价也受到影响。此次事件暴露了长期部署的 OT/IoT 制冷控制设备的网络安全弱点，相关讨论指向存在已知漏洞、已停止支持的老旧控制器型号。

hackernews · Zeekaas · 10月12日 12:16 · [社区讨论](https://news.ycombinator.com/item?id=50055304)

**「背景」** 安全研究团队 Claroty Team 82 此前对 Danfoss AK-SM 800A 冷藏控制器平台进行了研究，发现其嵌入式网页管理接口存在多个漏洞，其中包括一个被称为“每日口令”的隐藏认证机制，可被滥用绕过登录控制并实现远程代码执行，尤其影响 SM800、SC355 等已停止支持多年的老旧控制器。Danfoss 随后为 AK-SM 8xxA 系列中的两个漏洞提供了修复补丁，但大量门店可能尚未部署更新，这次攻击正是通过此类联网制冷控制器远程触发除霜循环造成的。

**「实际影响与应对」** 受影响超市被迫关闭门店并处置融化变质的冷藏食品，Intermarché 方面还披露约 30 万名客户的数据在此次攻击中被窃取。对零售和设施运营商而言，这类联网制冷控制器往往服役 15-20 年（社区讨论中提到的 Danfoss SM800 和 SC355 已分别于 2021 年和 2016 年停止支持），难以靠更换设备解决；可行的缓解措施是核查在用控制器的已知 CVE、限制其互联网可达性，并对远程管理功能做网络隔离。

**「社区讨论」** 有评论者（9x39）指出，受影响的可能是 Danfoss SM800 和 SC355 等 15-20 年前的老旧控制器（分别于 2021 年和 2016 年停止支持），并认为一线运维人员缺乏安全审查和设备更新预算是根本原因。另有评论者（bronco21016）注意到，此次事件与 2026 年 8 月底美国军事基地出现的类似冷柜故障疑似同源，均怀疑与已公开的 Danfoss 漏洞有关，但两者是否为同一攻击者尚无法确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.claroty.com/team82/research/freeze-the-controller-defrost-the-food-uncovering-vulnerabilities-in-danfoss-refrigeration-controllers">Freeze the Controller , Defrost the Food: Uncovering Vulnerabilities ...</a></li>
<li><a href="https://www.linkedin.com/posts/claroty_team82-activity-7371876691859746816-y04c"># team 82 | Claroty</a></li>
<li><a href="https://infrastructurenews.com.au/story/refrigeration-controller-flaws-threaten-cold-chains">Refrigeration controller flaws threaten cold chains</a></li>
<li><a href="https://www.connexionfrance.com/news/intermarche-cyberattack-affects-nearly-300000-customers/806317">Intermarché cyberattack 2026 : Nearly 300,000 customers&#x27; data stolen...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#IoT`, `#OT-security`, `#embedded-systems`, `#critical-infrastructure`

---

<a id="item-tech-news-2"></a>
### [WiFi 7 路由器被改造成 320 Msps 软件定义无线电接收器](https://github.com/h0m3us3r/w1700k-sdr) ⭐️ 8.0/10

一位开发者开源了名为 w1700k-sdr 的项目，将一台 WiFi 7 路由器改造成采样率达 320 Msps 的软件定义无线电（SDR）接收器，代码发布在 GitHub 上。该项目利用路由器现有的 WiFi 7 射频芯片实现接收功能，无需额外购置专用 SDR 硬件。需要注意的是，来源未提供原始文章内容，具体支持的频段、芯片型号和运行条件等细节无法从现有材料中确认。该项目属于硬件改装玩法，尚非正式产品或厂商支持的能力。

hackernews · djfergus · 10月12日 12:41 · [社区讨论](https://news.ycombinator.com/item?id=50055593)

**「背景」** 软件定义无线电（SDR）是一种用软件处理射频信号的接收技术，传统上依赖专用接收硬件，低成本的常见选择是 RTL-SDR 加上 SDR++ 这类开源接收软件（本次项目也可与此类软件配合使用）。此前同一开发者已在 ESP32 Wi-Fi 微控制器上实现过类似思路的 SDR（eSpDR 项目），espargos 团队也做过基于 ESP32 的方案；而 WiFi 7 路由器本身使用高采样率的射频芯片，这使其芯片可被重新利用来获得远超廉价 SDR 的 320 Msps 接收能力。

**「实际影响」** 对于射频和硬件爱好者而言，这提供了目前已知价格最低的 320 Msps 级 5 GHz 接收方案之一，社区评论者 aftbit 也表示不知道有更便宜的等效方案。有评论指出，由于使用相同芯片组，搭载 PCIe 接口的 Banana Pi R4 开发板可能同样可以运行此方案，有兴趣的用户可以关注该开源项目以获取支持的硬件清单。

**「社区讨论」** 评论者指出，同一开发者此前曾基于 ESP32 WiFi 微控制器制作过类似的 SDR（eSpDR 项目），espargos 团队也有类似的 ESP32 方案，因此希望这类技术未来能扩展到普通 WiFi 网卡，让笔记本电脑低成本变身 SDR。另有评论者猜测，手机厂商对 FM 收音机接口施加限制，是否与越来越多手机射频硬件由软件定义有关，但这只是个人推测，并无证据支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.sdrpp.org/">SDR ++ The bloat-free SDR receiver</a></li>

</ul>
</details>

**标签**: `#SDR`, `#WiFi 7`, `#RF/hardware hacking`, `#open source`

---

<a id="item-tech-news-3"></a>
### [Codex CLI installs a persistent, self-updating background daemon by default](https://github.com/openai/codex/issues/48195) ⭐️ 7.0/10

OpenAI&\#x27;s Codex CLI reportedly installs an undocumented, self-updating background daemon by default, prompting substantial community criticism and workarounds.

hackernews · whimblepop · 10月12日 18:29 · [社区讨论](https://news.ycombinator.com/item?id=50060694)

**标签**: `#ai-coding-tools`, `#developer-tools`, `#openai-codex`, `#security-privacy`, `#cli`

---

<a id="item-tech-news-4"></a>
### [Meta 发布 Muse Wonder 模型，实测表现与跑分引争议](https://research.meta.ai/blog/muse-wonder) ⭐️ 7.0/10

Meta 发布了新的 Muse Wonder AI 模型（提供 high 等配置档），并在 dev.meta.ai 上线了 Muse Code 等配套开发者入口。该发布在 Hacker News 上引发约 300 条评论的热烈讨论。不过社区实测结果与基准分数存在落差：一位开发者用“图片转 HTML”任务对比后认为，Muse Wonder 的表现明显弱于 Anthropic 的 Opus 5.5，更接近 Sonnet 或 Haiku 的水平，并怀疑其视觉模型可能是短板。另有用户报告在登录 Muse Code 时疑似看到陌生人的账户资料，且无法进入账户设置停用账号——该安全指控来自单一用户，尚未得到证实。由于原始博客内容未随本条目提供，官方声称的具体能力与指标无法核对。

hackernews · meetpateltech · 10月12日 16:48 · [社区讨论](https://news.ycombinator.com/item?id=50059115)

**「背景」** Muse Wonder 并非 Meta 首款 Muse 系列模型:2026 年 9 月,Meta 曾发布定位为个人 AI 智能体的 Muse,强调不仅能回答问题、还能直接执行任务并将长期目标转化为行动计划。此前该系列已有多代迭代,例如 8 月的 Muse Spark 1.2 和 9 月的 Muse Spark 1.3——后者是一个面向长时程智能体与编程工作流的多模态推理模型,提供约 100 万 token 的上下文窗口,定价为每百万输入 token 1.25 美元、输出 token 4.25 美元。这些前代版本为本次发布提供了直接的产品线延续和对比基准。

**「影响」** 对考虑评估该模型的开发者而言，基准数字不足以作为选型依据，建议在自身真实任务上做对比测试；同时，在 pmuse 报告的账号资料串扰与账户设置无法访问问题被证实或修复之前，用现有 Meta 账号登录 Muse Code 存在隐私风险，宜谨慎操作。

**「社区讨论」** 评论中最有分量的内容是上述 hands-on 对比与疑似账号泄露报告，均属个人实测或指控而非已证实结论。另一派讨论聚焦行业格局：有评论者认为，靠近前沿的公司越多越好，3-4 家实验室的竞争格局可以避免单家公司垄断“递归自我改进”带来的极端权力集中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/">Introducing Muse : The World’s First Personal AI Agent Built for Everyone</a></li>
<li><a href="https://openrouter.ai/meta/muse-spark-1.3">Muse Spark 1.3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**标签**: `#artificial-intelligence`, `#meta`, `#large-language-models`, `#model-evaluation`, `#industry-news`

---

<a id="item-tech-news-5"></a>
### [Python 3.15 发布：显式延迟导入与采样分析器，3.10 退出支持窗口](https://simonwillison.net/2026/Oct/12/python-3-15/) ⭐️ 7.0/10

Python 3.15 正式发布，主要特性包括 PEP 810 显式延迟导入（如 \`lazy import json\`，模块在首次使用时才真正加载）、PEP 798 推导式中的解包语法，以及标准库新增的采样分析器 Tachyon（profiling.sampling），原 cProfile 则更名为 profiling.tracing。对维护多版本支持的开源维护者来说，Python 3.10 已到生命周期末端，可以放弃对其支持并开始使用 3.11 的特性。性能方面，Miguel Grinberg 对 3.15.0rc3 的测试显示整体速度与 3.14 基本持平，但实验性 JIT 在其斐波那契测试中带来了 1.2 倍提升，这是他首次观察到 JIT 的显著性能收益。

rss · Simon Willison · 10月12日 18:15

**「背景」** Python 采用年度发布节奏，每个新版本发布后，支持全部受支持版本的开源维护者通常会将最低支持版本向前推进一个版本，因此 Python 3.15 的发布意味着 3.10（2021 年发布的版本）退出维护者的支持范围，3.11 的新特性可以开始使用。PEP 810 提出的显式延迟导入于 2025 年 10 月提交，允许开发者用 &quot;lazy import&quot; 语法标记个别导入，以降低命令行工具、测试套件及依赖庞大项目的启动时间和内存占用，现已作为 3.15 的核心语言特性落地，官方文档将其与 frozendict、UTF-8 默认编码、推导式解包和自由线程稳定 ABI 一并列为本次最大变更。

**「影响」** 维护跨版本支持的项目现在可以在兼容矩阵中移除 Python 3.10，并采用 3.11 的语言特性；而依赖重型库（如 sentence\_transformers）的插件类工具可直接使用 3.15 的 lazy import 语法降低启动耗时，无需再手写延迟加载。使用 uv 的开发者升级 uv 后即可在本地获取 Python 3.15 环境。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.python.org/3/whatsnew/3.15.html">What’s new in Python 3.15 — Python 3.15.0 documentation</a></li>
<li><a href="https://peps.python.org/pep-0810/">PEP 810 – Explicit lazy imports | peps.python.org</a></li>

</ul>
</details>

**标签**: `#python`, `#release-notes`, `#lazy-imports`, `#open-source`, `#programming-languages`

---

<a id="item-tech-news-6"></a>
### [循环扩散 Transformer：同一组块在去噪步骤内多次运行，循环深度可在采样时调整](https://www.reddit.com/r/MachineLearning/comments/1x49d61/looped_diffusion_transformer_the_same_blocks_run/) ⭐️ 7.0/10

Looped Diffusion Transformer 论文（arXiv 2609.40305，9 月 30 日）不再把文本到图像的 DiT 做大，而是在每个去噪步骤内让一组共享的 transformer 块反复运行多次。作者称朴素循环并不能稳定带来提升，需配合每个循环的深监督和自调制注意力；论文声称 260M 参数的循环模型在多个基准上胜过大 6.5 倍的模型，且推理计算量少 4.9 倍。B/16 代码与权重以 MIT 许可开源（权重托管在 Hugging Face 的 sensenova 账号下），发布者 /u/Fit-Ant2238 在 M5 Pro 上实测：模型以深度 4 训练，README 称其他深度无需重训练即可使用；实测中大部分质量变化发生在深度 3 之前，深度 3 和 4 输出非常接近，单张图像耗时从深度 1 的约 23–24 秒增加到深度 4 的 43–47 秒。

reddit · r/MachineLearning · /u/Fit-Ant2238 · 10月12日 18:13

**「背景」** Looped Diffusion Transformer（arXiv 2609.40305）的思路是在每个去噪步骤内多次复用同一组共享的 transformer 块，而不是单纯堆大模型。论文指出朴素循环并不可靠，因此引入两项技术来稳定循环中的特征更新：Deep Supervision 在每次循环后都对同一干净图像目标进行解码和训练，Self-Modulating Attention（互斥自注意力 XSA，即按头部的注意力门控）则调节循环内部的注意力更新。

**「影响」** 对使用者而言，循环深度在采样时选择（类似循环/递归深度语言模型的迭代次数），因此可以在同一套权重下逐图权衡计算量与精炼程度——例如在消费级设备上用深度 1 换取约一半的生成时间。不过上述性能优势目前仍是论文声明，独立验证有限；发布者的实测只表明深度 3 与 4 差异很小，且这些基准结果尚未被广泛复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2609.40305">[2609.40305] Looped Diffusion Transformer - arXiv.org</a></li>
<li><a href="https://github.com/OpenSenseNova/Looped-DiT">GitHub - OpenSenseNova/Looped-DiT: PyTorch implementation of ...</a></li>

</ul>
</details>

**标签**: `#diffusion-models`, `#transformers`, `#efficient-inference`, `#text-to-image`, `#machine-learning-research`

---

<a id="item-tech-news-7"></a>
### [learnc：用数据拟合 C 代码中的常量，JPEG 体积再省 9.1%](https://www.reddit.com/r/MachineLearning/comments/1x4dlbm/learnc_fit_the_constants_in_existing_c_code_to/) ⭐️ 7.0/10

learnc 是一款 MIT 许可的开源工具，可以针对现有 C 代码中已命名的常量，按用户用 C 编写的评分函数进行自动调优，并把新值写回原文件。作者给出的两个留出集验证结果：对 stb\_image\_write.h 的 128 个 JPEG 量化表条目（在 12 张 Kodak 图上调优、在另外 12 张上测试），在相同 SSIM 下实现 9.1% 的 BD-rate 提升，且在 libjpeg 中用 scikit-image 独立复核；mozjpeg 自带表为 2.7%。对 Google WebRTC VAD（vad\_core.c 中全部常量，在 LibriParty dev 上调优），F1 从 0.810 提升到 0.859。已声明的限制：码率低于 1 bpp 时 JPEG 无增益，工具适合几十到几百个常量，不适用于大型权重集合。

reddit · r/MachineLearning · /u/keep\_up\_sharma · 10月12日 20:51

**「背景」** 传统上，C 代码中的命名常量（如 JPEG 的量化表或语音活动检测器的阈值）通常由开发者手工调整或沿用历史经验值，调整过程费时且依赖直觉。BD-rate 是图像压缩领域常用的客观指标，表示在相同质量（如 SSIM）下码率的相对变化，数值为负或降低意味着同质量下文件更小。

**「实际影响」** C/C++ 开发者无需修改或重写现有代码结构，即可用自定义评分函数直接优化代码中的具名常量：作者给出的实测包括 stb\_image\_write.h 的 128 个 JPEG 量化表条目在留出测试集上获得 9.1% 的 BD-rate 改进（经 libjpeg 与 scikit-image 独立验证），Google WebRTC VAD 的 F1 从 0.810 提升至 0.859。但该方法仅在数十到数百个常量的规模上效果最佳，不适合大型权重集合，且 JPEG 在低于 1 bpp 时无收益——采用前应先在自己的目标数据与码率范围内验证调优结果是否可迁移。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismix.dev/news/dd5fee40b9ef">learnc: fit the constants in existing C code to data (9.1% ...</a></li>

</ul>
</details>

**标签**: `#C`, `#machine-learning`, `#parameter-tuning`, `#image-compression`, `#open-source`

---

<a id="item-tech-news-8"></a>
### [Anthropic：新反蒸馏防护使提取数据初步减少 90% 至 99%](https://www.anthropic.com/research/distillation-defenses) ⭐️ 7.0/10

Anthropic 于 10 月 12 日表示，初步证据显示其针对模型蒸馏攻击的新防护措施已使从 Claude 被提取的数据减少约 90% 至 99%。措施包括限制推理内容跨会话及跨模型、账号流转，部署双阶段分类器并持续修补绕过手法，同时封禁了数万个相关账号，部分账号在发起攻击后不到两小时即被封禁。这些数据为 Anthropic 自行报告的初步结果，尚无独立验证。

telegram · zaihuapd · 10月13日 01:25

**「背景」** 模型蒸馏攻击指攻击者向模型发送请求、再用其响应训练自己的模型，从而以低成本复制其能力。据 Anthropic 的研究文章，其早期工作以阻止“被动蒸馏”为主，即拦截以普通用户身份批量调用模型并训练于其响应的行为（tool-2-2）；新防护则进一步聚焦于让攻击者更难获取 Claude 的推理内容，报道称部分推理令牌提取量下降 10 到 100 倍以上，个别日子甚至低到无法测量（tool-2-1）。

**「对开发者的影响」** 依赖 Claude 输出构建服务的开发者需要检查并更新自己的集成方式：Anthropic 的跨会话限制和双阶段分类器可能拦截部分请求，且被拦截的请求仍可能产生费用。以蒸馏为目的大量提取模型输出的账号面临快速封禁——官方称部分账号在发起攻击后不到两小时即被封禁——误报率据称低于 0.1%，但这些数字均为 Anthropic 自行报告，尚无独立验证。

**「社区讨论」** 无可用社区评论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.explainx.ai/blog/anthropic-distillation-defenses-preserved-thinking-classifier-90-99-percent-2026">Anthropic Distillation Defenses: 90-99% Less Data Stolen ...</a></li>
<li><a href="https://www.anthropic.com/research/distillation-defenses">Strengthening our defenses against distillation attacks</a></li>
<li><a href="https://www.anthropic.com/research/distillation-defenses">Strengthening our defenses against distillation attacks</a></li>
<li><a href="https://www.explainx.ai/blog/anthropic-distillation-defenses-preserved-thinking-classifier-90-99-percent-2026">Anthropic Distillation Defenses: 90-99% Less Data Stolen ...</a></li>

</ul>
</details>

**标签**: `#AI security`, `#model distillation`, `#Anthropic`, `#model protection`, `#abuse detection`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中欧就混动、电动汽车贸易达成共识，中方配额不低于其他来源](https://www.mofcom.gov.cn/xwfb/sjfzrfb/art/2026/art_4d502e1d49fd4480b39a6cfd0d752038.html) ⭐️ 7.0/10

China&\#x27;s Commerce Ministry says China and the EU reached consensus under their trade consultation mechanism on hybrid and EV trade, with Chinese quotas no less favorable than other import sources and EU price-undertaking reviews to continue.

telegram · zaihuapd · 10月12日 06:19

**标签**: `#China-EU trade`, `#electric vehicles`, `#trade policy`, `#hybrid vehicles`, `#WTO`

---

<a id="item-finance-news-2"></a>
### [新能源汽车出口退税率由 13% 下调至 9%](https://www.news.cn/20261012/9709731f470b42f9a84825c2e4eb914b/c.html) ⭐️ 7.0/10

China&\#x27;s finance and tax ministries announced that NEV VAT export rebates will fall from 13% to 9% effective April 1, 2027.

telegram · zaihuapd · 10月12日 11:00

**标签**: `#export tax policy`, `#new energy vehicles`, `#fiscal policy`, `#China`

---

<a id="item-finance-news-3"></a>
### [税务处罚新裁量基准 11 月施行，社保欠缴最高罚 3 倍](https://fgk.chinatax.gov.cn/zcfgk/c100012/c5252754/content.html) ⭐️ 7.0/10

China&\#x27;s State Taxation Administration will implement the 2026 national tax penalty discretion benchmarks on November 1, 2026, adding employer social insurance underpayment as a punishable offense with fines up to three times the unpaid amount.

telegram · zaihuapd · 10月13日 02:45

**标签**: `#China tax policy`, `#social insurance`, `#regulatory enforcement`, `#employer compliance`, `#State Taxation Administration`

---