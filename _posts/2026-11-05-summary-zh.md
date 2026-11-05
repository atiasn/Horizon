---
layout: default
title: "Horizon Summary: 2026-11-05 (ZH)"
date: 2026-11-05
lang: zh
---

> 从 46 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [OpenAI 自主流水线单次运行生成 948 个 Linux 内核提权 exploit](#item-tech-news-1) ⭐️ 9.0/10
2. [月之暗面开放 Kimi K3.1 Pro 权重：2.8T 总参数、约百万 token 上下文](#item-tech-news-2) ⭐️ 8.0/10
3. [Go 标准库发布 encoding/json/v2,重新设计 JSON 处理 API](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic 发布可证明推理研究：用密码学证明验证模型服务商的计算](#item-tech-news-4) ⭐️ 8.0/10
5. [AI 漏洞挖掘迫使软件业偿还四十年安全技术债](#item-tech-news-5) ⭐️ 8.0/10
6. [腾讯发布开源权重模型 Hy4，主打游戏开发能力](#item-tech-news-6) ⭐️ 8.0/10
7. [AMD Q4 指引约 170 亿美元，历史上首次有望单季销售额超过 Intel](#item-tech-news-7) ⭐️ 8.0/10
8. [RunAnywhere 开源 Trainium2 推理引擎：NKI megakernel 将 GLM-5.3-Flash 解码步耗时降至 24.2 ms](#item-tech-news-8) ⭐️ 8.0/10
9. [黑客演示绕过锁定模式的持久 iPhone 越狱](#item-tech-news-9) ⭐️ 8.0/10
10. [OpenAI 宣布收购 git 基础设施公司 Pierre Computer Company](#item-tech-news-10) ⭐️ 7.0/10
11. [Do looped transformers save HBM traffic? Profiling weight reuse in Huginn on a B200 \[P\]](#item-tech-news-11) ⭐️ 7.0/10
12. [Anthropic 开源 FlashProve：用加密证明核实 AI 输出来自指定模型](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [Stocks making the biggest moves premarket: Trump Media, Tesla, CoreWeave, Novo Nordisk and more](#item-finance-news-1) ⭐️ 7.0/10
2. [民主党中期选举大胜 10 年期美债收益率与油价齐跌](#item-finance-news-2) ⭐️ 7.0/10
3. [甲骨文取消与腾讯约 70 亿美元 AI 芯片租赁协议](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 自主流水线单次运行生成 948 个 Linux 内核提权 exploit](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 9.0/10

OpenAI 宣布，其自主漏洞研究流水线在 2026 年 10 月的一次 Linux 内核扫描中动态复现了 1,724 个漏洞，并生成 948 个可用的本地提权（LPE）exploit——可让本地低权限用户获得 root 权限——同时产出 291 个信息泄露 PoC。据其公布的数据，该次运行总 API 成本为 1,213,430 美元，平均每个成功的 LPE exploit 花费 1,279 美元（实际成功开发的 exploit 成本约 359 美元）；OpenAI 按历史 Pwn2Own / TyphoonPWN 赏金水平（每个 2 万至 7 万美元）估算，这批漏洞理论价值约为成本的 16 至 55 倍。OpenAI 还称发现了至少 10 种新的利用技术，包括用于 cache spraying 的新型持久化弹性对象、新的 page grooming 技术、纯数据（data-only）提权/任意写技术以及任意类型混淆，并称其新颖性已获第三方专家确认。上述数字与结论均来自 OpenAI 的自行报告，目前没有独立复现或第三方实测数据。

telegram · zaihuapd · 11月5日 03:04

**「背景」** 本地提权（LPE）漏洞是指 Linux 内核中允许本机低权限用户获取 root（最高）权限的一类安全缺陷；在多用户服务器或共享环境中，这意味着一个普通账户就可能完全接管整台机器。过去这类内核漏洞的挖掘与利用主要依靠安全专家逐个手工完成，单个内核 LPE exploit 在 Pwn2Own、TyphoonPWN 等比赛中的历史赏金约为 2 万至 7 万美元，本次报告正是以这一赏金水平来折算自动化产出的理论价值。

**「影响」** 对 Linux 内核维护者和各发行版厂商而言，这批结果意味着一波待审核的漏洞报告与修复工作：OpenAI 称流水线在生成 948 个可用提权 exploit 的同时产出了对应的候选补丁，这些补丁需经上游审核合并后才会进入各发行版的内核更新。在此之前，运行多用户 Linux 环境（如共享主机、容器宿主机）的组织应将低权限本地代码执行视为潜在的 root 风险，限制不可信用户的本地访问面，并跟进后续内核安全公告以便及时部署修复。

**「社区讨论」** Hacker News 评论者对这一结果反应分化：有人追问内核为何会累积上千个提权漏洞、究竟源于系统过于复杂还是安全模型与语言实现的根本缺陷，也有人表示一直认为 Linux 本地提权“几乎必然可行”，但 948 的数量仍超出预期，还有评论者询问是什么缓解因素使这些漏洞未演变为现实威胁。一位自称该项目团队成员的评论者表示愿意代团队回答提问（该身份未经核实），并附上了 OpenAI 安全岗位的招聘链接。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/a-thousand-fewer-paths-to-root/">A thousand fewer paths to root - OpenAI</a></li>
<li><a href="https://explainx.ai/blog/openai-linux-kernel-948-local-privilege-escalation-exploits-1-2-million-api-cost-pipeline-patch-the-planet-2026">OpenAI Linux Kernel Pipeline: 948 Root Exploits, $1.2M ...</a></li>
<li><a href="https://phemex.com/news/article/openai-ai-pipeline-validates-948-linux-kernel-privilegeescalation-flaws-in-single-run-102431">OpenAI AI Finds 948 Linux Kernel Vulnerabilities in One Run ...</a></li>

</ul>
</details>

**标签**: `#ai-security`, `#linux-kernel`, `#vulnerability-research`, `#autonomous-exploitation`, `#privilege-escalation`

---

<a id="item-tech-news-2"></a>
### [月之暗面开放 Kimi K3.1 Pro 权重：2.8T 总参数、约百万 token 上下文](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

月之暗面（Moonshot AI）已在 Hugging Face 发布 Kimi K3.1 Pro 的模型权重。据社区转发的发布信息，这是 K3.1 系列的首个模型，定位为原生多模态的智能体模型，总参数约 2.8T、激活约 104B，上下文约 100 万 token，权重以 MXFP4 量化形式提供；官方 API（模型名 kimi-k3.1-pro）兼容 OpenAI 与 Anthropic 接口。第三方推理服务跟进迅速，OpenRouter、Together、Modal 均已上线该模型，有用户观察到 Together 在与官方端点相同价格下吞吐约为其两倍，Modal 还要更高。需要注意的是，现有材料未说明权重许可证条款，且有评论质疑“开放权重”的说法，相关限制尚待核实。

hackernews · abrarthought · 11月4日 15:30 · [社区讨论](https://news.ycombinator.com/item?id=50366999)

**「背景」** Kimi K3.1 Pro 是月之暗面在 K3 基础上后训练得到的模型：前代 Kimi K3 是基于 Kimi Delta Attention（KDA）与 Attention Residuals 构建的 2.8T 参数开放权重多模态智能体模型，具备 100 万 token 上下文窗口。K3.1 Pro 被官方称为其迄今最强的 3T 级模型，通过跨数百个下游领域的大规模联合强化学习完成后训练，是 K3.1 系列的首个模型，据第三方报道其在 Terminal-Bench 4.0 上得分 65.7%。

**「实际影响」** 对想自行部署的团队，硬件门槛是主要障碍：社区估计大约需要一台 8 卡 NVIDIA B300 节点才能运行该模型，远超常见多卡工作站配置，有用户表示只能继续在双 RTX PRO 4000 上运行更小的 Qwen 模型。更可行的路径是托管接入：开发者可通过 OpenAI 或 Anthropic 兼容接口调用官方 API，或在 OpenRouter、Together、Modal 之间按吞吐与价格择优，社区认为第三方端点的吞吐差距也说明推理成本仍有优化和下降空间。

**「社区讨论」** 模型成色存在分歧：一位评论者认为 K3.1 相比 DeepSeekV4.1-Flash 领先有限、在 Hy4 公布的内部基准上不及 Opus5.5，怀疑其“刷榜”（benchmaxxed）；另一位做过测试的用户则反驳称未观察到刷榜迹象，评价其为“略逊于前沿、但足以胜任多数场景的强开放模型”。另有评论直指“开放权重”名不副实，但未给出具体的许可证依据，暂无法核实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3.1-Pro">moonshotai/ Kimi - K 3 . 1 - Pro · Hugging Face</a></li>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3">moonshotai/ Kimi - K 3 · Hugging Face</a></li>
<li><a href="https://www.marktechpost.com/2026/10/23/moonshot-ai-kimi-k3-1-pro-open-weight-model/">Moonshot AI Releases Kimi K 3 . 1 Pro ... - MarkTechPost</a></li>

</ul>
</details>

**标签**: `#open-weights`, `#large-language-models`, `#moonshot-ai`, `#inference`, `#benchmarks`

---

<a id="item-tech-news-3"></a>
### [Go 标准库发布 encoding/json/v2,重新设计 JSON 处理 API](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

Go 团队在官方博客宣布为标准库设计全新的 JSON API encoding/json/v2,对 Go 中使用最广泛的包之一 encoding/json 进行重新设计。这是一项官方公告,现有材料未说明新 API 随哪个 Go 版本发布或如何启用,可用性细节尚待确认。公告在 Hacker News 上引发活跃讨论\(108 条评论\),开发者关注的焦点是从现有 encoding/json 迁移的成本与 JSON 解析性能。

hackernews · olexsmir · 11月4日 17:52 · [社区讨论](https://news.ycombinator.com/item?id=50369106)

**「背景」** Go 标准库的 encoding/json 包长期承担 JSON 编解码职责,其设计中积累的问题使改进和修复成为社区期待已久的需求。去年,Go 团队曾撰文介绍一个实验性的新 JSON API 并征集反馈,此次发布的 encoding/json/v2 与 encoding/json/jsontext 正是该实验 API 经过进一步打磨后的稳定版本。其中 jsontext 是面向底层控制的配套包,提供基于 token 的流式 API,可以在不将 JSON 反序列化为 Go 结构体的前提下处理数据,适合追求最大控制力与最低开销的场景。

**「影响」** 对维护大量 JSON 序列化代码的团队而言,迁移兼容性是最直接的影响:参与讨论的开发者指出 v2 中缺少 MarshalIndent 这类便捷函数,等价的格式化输出代码复杂且不直观,依赖可读 JSON 输出的项目在迁移时需要重写这部分逻辑。

**「社区讨论」** 讨论中最具实质性的反馈呈两面性:一位开发者表示总体欢迎 encoding/json/v2,但遗憾其未保留 MarshalIndent,认为等价实现复杂难懂、迁移不便;另一位开发者分享了在公司生产环境中用 jsontext 包为行为异常的客户端构建容错解析器的经验,称其在没有自省能力的情况下速度极快,并能针对每类错误给出具体报错,推荐将其用于非平凡解析场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://go.dev/blog/jsonv2">A new Go API for JSON - The Go Programming Language</a></li>
<li><a href="https://allur.co/en/blog/the-road-to-json-v2-exploring-gos-experimental-new-api">The Road to JSON V 2 : Exploring Go &#x27;s Experimental New API - Allur</a></li>

</ul>
</details>

**标签**: `#go`, `#json`, `#standard-library`, `#serialization`, `#api-design`

---

<a id="item-tech-news-4"></a>
### [Anthropic 发布可证明推理研究：用密码学证明验证模型服务商的计算](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic 发布了一项“可证明推理”（provable inference）研究，提出让客户端通过密码学证明验证模型服务商是否真的运行了所声称的权重和计算过程。据 Hacker News 讨论中引用的研究细节，服务商需先发布约 6.5 MB 的权重承诺，该承诺可覆盖约 1600 万次请求，之后需重新承诺；客户端对每个请求验证一个证明，在 24 线程上约需 17 秒（单线程约 21 秒），而证明过程据报带来约 90-100 倍于正常推理的计算开销。这些数字表明它目前仍是早期研究而非已上线的产品能力，高昂的证明开销是最主要的实用障碍。

hackernews · ltononro · 11月4日 17:17 · [社区讨论](https://news.ycombinator.com/item?id=50368626)

**「背景」** 可证明推理要解决的问题，是客户端无法直接验证模型服务商服务器上实际运行的权重与计算是否正确，而服务商对权重保密时尤其困难。Anthropic 采用一种名为 zkSNARK 的密码学证明技术来应对这一问题；其开源的 FlashProve 库专门针对混合专家（MoE）模型（具体为 Llama 4 Maverick）实现可证明推理：服务商在离线阶段对模型权重生成一个简短的隐藏承诺（约 6.5 MB，弱客户端也能存储，约可覆盖 1600 万次请求），之后客户端只需逐次验证每个请求的证明，单线程验证约需 21 秒，24 线程约 17 秒，代价是约 90-100 倍的计算开销。据第三方报道，该研究原型 FlashProve 于 2026 年 11 月 2 日发布，相应的公司研究文章也标注为该日期。

**「实际影响」** 对通过 API 或 OpenRouter 这类聚合商使用托管模型的企业，这类证明可用于发现服务商悄悄把请求路由到其他模型的情况——该使用场景由评论者提出，其所述的替换行为本身多属传闻而非已证实的事实。在约 90-100 倍计算开销下，该方案短期内难以进入生产环境；使用开放权重模型的组织无需等待它，直接重跑确定性推理即可完成验证，密码学证明的真正目标是不公开权重的闭源服务商。

**「社区讨论」** 在实用性上，评论者 nemo1618 认为开放权重模型根本不需要这类密码学方案——直接重跑确定性推理更快更便宜（他还指出 ZKP 方案本身同样依赖确定性推理）；vessenes 虽称这是相对既有零知识证明结果的显著进步，但也指出对闭源服务商，让四个独立服务商重放同一提示做概率性验证，可能比 90-100 倍的证明开销更划算。另有署名 neuwirth 的评论者自称是先行工作 VerInf 的作者，声称 Anthropic 的研究“连 400B Maverick 模型的选择都取自他们的工作”却几乎未作署名——该说法仅为单方陈述，未经独立证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models</a></li>
<li><a href="https://assets.claude.com/8e1d181a83015078581c92d896757041713f0160.pdf">FlashProve: an open-source library for provable inference</a></li>
<li><a href="https://shattered.io/anthropic-flashprove-provable-inference-72x-overhead-2026/">Anthropic FlashProve: Provable Inference at 72x [2026]</a></li>

</ul>
</details>

**标签**: `#llm-inference`, `#zero-knowledge-proofs`, `#cryptography`, `#verifiable-computation`, `#ai-safety`

---

<a id="item-tech-news-5"></a>
### [AI 漏洞挖掘迫使软件业偿还四十年安全技术债](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 8.0/10

IEEE Spectrum 刊文指出，以 php2shell 这一 PHP 漏洞为例，AI 驱动的漏洞发现正在集中暴露遗留软件与开源项目中数十年未被处理的安全缺陷，迫使软件行业偿还约四十年积累的安全技术债。这是该刊对行业趋势的分析判断，而非某款已发布工具的能力声明或经独立测量的结果；最直接受影响的是维护遗留代码和开源组件的开发者与组织。该分析在 Hacker News 上引发 1113 分、645 条评论的大规模讨论。

hackernews · pseudolus · 11月4日 11:52 · [社区讨论](https://news.ycombinator.com/item?id=50364336)

**「背景」** PHP2Shell 是 PHP 语言中一个漏洞的名称；PHP 由 Rasmus Lerdorf 于 1994 年创建，至今仍被大量老旧网站使用，长期积累的遗留代码成为 AI 驱动的漏洞发现工具的重点挖掘对象。IEEE Spectrum 在 2026 年 11 月 2 日的报道中指出，此类 AI 工具正在以前所未有的速度找出数十年来未被修复的安全问题，迫使行业面对这些“安全技术债”。

**「对维护者与安全团队的实际影响」** 对于维护遗留系统和开源项目的开发者，AI 驱动的漏洞发现意味着漏洞披露和修复的节奏将显著加快，许多问题无法靠小幅补丁解决，而需要重构或重新设计，这会直接增加维护负担。安全团队需要把持续性的 AI 扫描和测试纳入 CI/CD 流程，以匹配 AI 发现漏洞的速度，而不是依赖周期性的人工审计。与此同时，正如社区讨论所指出的，这种审计压力也可能让开源软件&quot;总有人审计过&quot;的假设接受真正检验，项目方应主动安排或资助针对自身代码的自动化安全审查。

**「社区讨论」** 评论区的核心分歧在于这算“一次性还债”还是“永久苦役”：swatcoder 指出许多技术债并非靠窄补丁就能修掉的小错误，而需要某种程度的重构，担心 AI 会开启一场无休止的、与功能无关的修复工作；glennfiedler 和 Arbortheus 则相对乐观，认为阵痛只会持续一段时间、长期会留下更健壮的软件，后者还希望这波扫描能顺带发现被国家机构或商业间谍公司囤积的 0-day。xbmcuser 以自己此前因“开源安全只是错觉”的言论被踩的经历为例，主张 AI 审计正在让开源“总会有别人来审计代码”的假设第一次接近成真。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability">PHP2Shell Is a Wakeup Call for AI in Cybersecurity - IEEE ...</a></li>
<li><a href="https://grafy.ai/news/php2shell-ai-exposes-40-years-of-legacy-code-debt">PHP2Shell: AI Exposes 40 Years of Legacy — Grafy News</a></li>
<li><a href="https://undercodetesting.com/ai-hackers-just-broke-appsec-how-xbow-big-sleep-found-zero-days-in-hours-your-move-defender-video/">AI HACKERS JUST BROKE APPSEC: How XBOW &amp; Big Sleep Found Zero ...</a></li>

</ul>
</details>

**标签**: `#AI security`, `#vulnerability discovery`, `#technical debt`, `#open source`, `#cybersecurity`

---

<a id="item-tech-news-6"></a>
### [腾讯发布开源权重模型 Hy4，主打游戏开发能力](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

腾讯发布了开源权重大语言模型 Hy4，据其官方材料称是当前最强的开源权重模型之一。该模型与腾讯互娱（IEG）专业开发者合作，针对 Unreal Engine、Unity 和 Godot 等主流游戏引擎进行了专门适配，覆盖功能实现、玩法逻辑、状态跟踪、资产管线及多人游戏开发。腾讯同时开源了两个由 Hy4 与 Hyra 2.0 共同开发的基础模型：用于单细胞表示的 HyCell 和用于物理场建模的 HyPDE。不过官方也承认，在研究级数学、长程编码、模型自我改进和高级视觉问答等内部基准上，Hy4 与顶级闭源模型之间仍有明显差距。

hackernews · Philpax · 11月4日 14:11 · [社区讨论](https://news.ycombinator.com/item?id=50365780)

**「背景」** Hy4 是腾讯 Hy 系列开源权重模型的第四代，在此次正式发布之前，腾讯已先行放出 Hy4 预览版供外界评测。据第三方报道，该预览版是一个 7700 亿参数的开放模型，曾与 Kimi 等其他开放模型进行基准对比；腾讯官方公布的数据则将上一代 Hy3 与 Hy4 预览版逐项对比，直观呈现了这一代相对前作的提升幅度。

**「实际影响」** 对游戏开发者而言，Hy4 提供了一个针对主流引擎工作流专门训练的开源权重选项，可用于本地部署或自托管。此外，Plotly 的数据 analytics 基准测试显示，Hy4 落在成本/准确率前沿上，介于 GPT-6.1 Sol 与 GPT-6.1 Terra 之间，但其工作方式非常缓慢——每个问题平均运行约 26 次查询，部分问题多达 64 次，个别查询耗时约一小时，采用者需权衡这种高消耗的使用方式。

**「社区讨论」** Hacker News 上的讨论（203 分，67 条评论）中，有用户称赞腾讯开源 HyCell 和 HyPDE 等科学工具的做法，认为这与美国初创公司限制科研用途的做法形成鲜明对比。另有用户对官方坦诚承认与顶级闭源模型仍有差距表示欣赏，认为对将 AI 作为工具使用的场景而言开源模型已经够用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.intelligentliving.co/tencent-hy4-preview-benchmarks/">Tencent Hy 4 Preview Benchmarks : 770B Open Model Takes on Kimi...</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#large language models`, `#Tencent`, `#scientific foundation models`, `#game development`

---

<a id="item-tech-news-7"></a>
### [AMD Q4 指引约 170 亿美元，历史上首次有望单季销售额超过 Intel](https://www.tomshardware.com/pc-components/cpus/amd-expects-to-outsell-intel-in-q4-for-the-first-time-in-history-usd17b-guidance-would-exceed-intels-projections) ⭐️ 8.0/10

AMD 给出的 2026 年第四季度营收指引约为 170 亿美元，按 Tom&\#x27;s Hardware 的对比将超过 Intel 的同期预期，这将是历史上第一个 AMD 单季销售额超过 Intel 的季度。AMD 将增长主要归因于 Instinct AI 加速器销售强劲。需要强调的是，这是公司前瞻性指引而非已确认的最终业绩，实际结果仍待季度财报验证。

hackernews · rbanffy · 11月4日 15:38 · [社区讨论](https://news.ycombinator.com/item?id=50367125)

**「背景」** AMD 与 Intel 是 x86 CPU 市场的两大主导厂商,但自该市场形成以来,Intel 一直是营收规模更大的一方,AMD 此前从未在任何一个季度实现营收反超,这正是本次

**「评论：这更多反映 Intel 的失策」** 评论者普遍认为这一里程碑更多体现 Intel 自身的困境而非 AMD 的突破：有用户指出 Intel 放弃 Optane、Arc 加速器几乎无人购买，还有人因 13/14 代酷睿电压问题及 Intel DCI 调试接口被取证读取内存的经历而转投 AMD。也有声音（如 dlcarrier）提醒，AMD Instinct 的销量与 Nvidia 相比仍很小，其超越 Intel 可能主要源于 Intel 在 AI 硬件上的缺席；另有人则强调两家竞争加剧对消费者是好事。

**标签**: `#semiconductors`, `#AMD`, `#Intel`, `#CPUs`, `#AI hardware`

---

<a id="item-tech-news-8"></a>
### [RunAnywhere 开源 Trainium2 推理引擎：NKI megakernel 将 GLM-5.3-Flash 解码步耗时降至 24.2 ms](https://www.reddit.com/r/MachineLearning/comments/1xo0yuq/p_nki_layer_megakernels_for_glm53flash_on_aws/) ⭐️ 8.0/10

RunAnywhere 工程师（帖子作者自述供职于该公司，代码归其所有）开源了面向 AWS Trainium2 的推理引擎 trnrt，可在单台 trn2.48xlarge 上服务 320B 参数、100 万 token 上下文的 MoE 模型 GLM-5.3-Flash。核心改动是用 NKI 把每层半（稀疏注意力层则为整层）改写为单个 megakernel：早期剖析显示模型本身的计算只占解码一小部分（某 KDA 线性注意力层中递推仅占注意力部分的 2%，其余为 mHC 预投影 36%、XLA 胶水 33% 等），瓶颈是每个小型向量引擎指令约 153 ns 的固定成本、每次内核边界的 HBM 回写以及每步 125 次跨芯片集合通信。按相同布局，batch-8 解码一步从 10 月 17 日版本的 32.2 ms 降至 11 月 1 日的 24.2 ms（内存下限为 6.1 ms），其中融合稀疏注意力层与 KDA、MoE 内核各贡献约 3.2 ms；剩余耗时中 10.0 ms 为向量引擎指令链占用、4.6 ms 为内核内等待、2.8 ms 为暴露的集合通信。这些结果均为作者自测自报：在 SemiAnalysis AgentX 基准（自行运行，非官方 InferenceX）上测得单机最高每分钟 28.9 个 agent 请求、16 agent 时中位请求解码 35.9 token/s，未与 GPU 对比，也没有可用的 AWS 官方基线（vLLM Neuron 插件未注册 GLM 模型，NxD Inference 处于维护模式）；此外稀疏注意力 prefill 保留了一处影响 1.2% 选择的近似（下一 token 对数概率平均偏移 0.012–0.021 nats，448 个位置中 3 个 top token 改变），该版本尚未运行任务级评测。

reddit · r/MachineLearning · /u/WildCard727 · 11月4日 21:47

**「背景：GLM-5.3-Flash 与 Trainium2」** GLM-5.3-Flash 是 Z.ai 于 2026 年 8 月发布的 GLM-5 系列首个原生多模态模型：采用混合专家（MoE）架构，总参数 320B、每 token 激活 18B，上下文窗口约 100 万 token，权重以 MIT 许可证开放在 Hugging Face 上。在 AWS Trainium2 的 Neuron 软件栈中，模型推理默认由 XLA 编译成由大量小算子组成的执行图，而 NKI 是面向 NeuronCore 的内核编程接口，可以绕过这层调度、把整层计算写进单个融合内核。发帖作者说明，这一设计借鉴了 AMD 在 vLLM 中的逐层解码内核，以及 Hazy Research 和 Mirage 的 megakernel 工作。

**「对 Trainium2 部署者的影响」** 对于希望在 AWS Trainium2 上部署 GLM-5.3-Flash 的团队，官方工具链目前没有现成支持：vLLM Neuron 插件虽被列为 AWS Trainium 上大模型推理的推荐方案，但据作者称其最新版本未注册任何 GLM 模型，NxD Inference 也已进入维护模式。因此这次开源的 trnrt 引擎为该模型提供了少数可直接使用的路径之一，仓库 docs/RESULTS.md 附有复现全部数字的命令，可在单台 trn2.48xlarge 上尝试。采用前需注意：所有性能数字均由作者所在公司 RunAnywhere 自测，无 GPU 对比也无官方基线；稀疏注意力 prefill 中保留了一处近似（影响 1.2% 的选择，下一 token 对数概率平均偏移 0.012–0.021 nats），且该版本尚未运行任务级评测，生产使用前应自行验证精度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/zai-org/GLM-5.3-Flash">zai-org/GLM-5.3-Flash · Hugging Face</a></li>
<li><a href="https://www.marktechpost.com/2026/08/26/z-ai-releases-glm-5-3-flash-a-320b-a18b-natively-multimodal-moe-with-a-1m-token-context/">Z.ai Releases GLM-5.3-Flash: A 320B-A18B Natively Multimodal ...</a></li>
<li><a href="https://github.com/vllm-project/vllm-neuron">GitHub - vllm-project/vllm-neuron: Community maintained ...</a></li>

</ul>
</details>

**标签**: `#AWS Trainium`, `#LLM inference optimization`, `#MoE models`, `#kernels`, `#LLM serving`

---

<a id="item-tech-news-9"></a>
### [黑客演示绕过锁定模式的持久 iPhone 越狱](https://appleinsider.com/articles/26/11/04/apples-lockdown-mode-thwarted-by-a-new-persistent-iphone-jailbreak) ⭐️ 8.0/10

黑客组织 Calif 在 X 上发布视频，展示一台已开启锁定模式的 iPhone 18 Pro 被成功越狱，且越狱在设备升级到 iOS 27.2 后依然存活。视频显示攻击从通过 AirDrop 接收一份 PDF 开始，随后在设置应用中完成系统更新，越狱状态全程未被清除。Calif 未公开任何技术细节，称正在向苹果披露该漏洞，且不会发布越狱工具。苹果曾在 2026 年 3 月宣称锁定模式自 2022 年推出以来防护成功率达 100%，但本次演示目前仅来自单一来源的视频，尚无独立验证或技术分析支持。

telegram · zaihuapd · 11月4日 14:38

**「什么是锁定模式」** 锁定模式（Lockdown Mode）是苹果 2022 年推出的可选极端安全功能，面向记者、活动人士等可能遭遇雇佣间谍软件定向攻击的高风险用户，通过禁用消息附件解析、链接预览等易被利用的功能来收窄攻击面。苹果曾在 2026 年 3 月宣称该模式自推出以来的防护成功率达 100%，此次演示因此被视为该模式首次被公开绕过。

**「对高风险用户的影响」** 受影响最直接的是锁定模式的目标用户——面临雇佣间谍软件威胁的记者、活动人士、异见者等高风险人群：在苹果修复该漏洞之前，他们不能再将锁定模式视为百分之百可靠的最后防线。由于 Calif 未公开技术细节且不发布越狱工具，普通用户面临的即时被利用风险较低；高风险用户应保持锁定模式开启（该模式仍会限制消息附件、陌生来电的 FaceTime 等攻击面），并在苹果发布安全更新后尽快安装。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://andro-news.com/en/iphone-18-pro-in-lockdown-mode-jailbroken-via-a-single-airdrop-pdf-file-surviving-ios-27-2-update/">iPhone 18 Pro in Lockdown Mode Jailbroken via a Single ...</a></li>
<li><a href="https://tech.yahoo.com/cybersecurity/articles/apple-lockdown-mode-supposed-protect-185240625.html">Apple’s Lockdown Mode Was Supposed to Protect iPhones ...</a></li>
<li><a href="https://www.zdnet.com/article/apple-warns-targetted-spyware-attacks-what-to-do/">Apple is warning users of new spyware attacks - what to do if ...</a></li>

</ul>
</details>

**标签**: `#security`, `#ios`, `#jailbreak`, `#apple`, `#vulnerability-disclosure`

---

<a id="item-tech-news-10"></a>
### [OpenAI 宣布收购 git 基础设施公司 Pierre Computer Company](https://openai.com/index/openai-to-acquire-pierre/) ⭐️ 7.0/10

OpenAI 在官方博客宣布已达成收购 Pierre Computer Company 的协议，消息于 11 月 4 日在 Hacker News 上引发大量讨论。Pierre 是一家 git 代码基础设施初创公司，其 Code.Storage 服务基于 git 为代码及机器生成的产物提供大规模存储；据讨论中引用的公告内容，Lovable、Bolt、Amp、Parahelp 等智能体编程（agentic coding）服务依靠它存放生成的代码、记忆文件、设计产物等随时间演变的文件。Hacker News 用户指认该公司由 Bootstrap 原始开发者 Jacob Thornton 与 Mark Otto 创立。目前公开材料未披露交易金额与完成时间，这仍是一项已宣布的协议而非已完成的交易。

hackernews · itunpredictable · 11月4日 15:21 · [社区讨论](https://news.ycombinator.com/item?id=50366863)

**「Pierre Computer Company 是什么」** 皮埃尔计算机公司（Pierre Computer Company）是一家总部位于旧金山、约 10 名员工的开发者基础设施初创公司，2023 年由 Ian Ownbey 与以联合创建 Bootstrap 框架闻名的 Jacob Thornton 创立，是 Y Combinator 2023 年冬季批次成员。其主打产品 Code.Storage 提供面向 AI 应用的现成 Git 基础设施，通过 SDK 或原生 Git 协议大规模存储代码和机器生成的产物，公司同时维护开源的 Diffs 与 Trees 库。这些库已被用于 OpenAI 的编程代理 Codex，而 OpenAI 近期也推出了自己的 Git 后端 Pando，本次收购正是在这一背景下对其面向 AI 代理的代码基础设施的扩展。

**「对 Code.Storage 客户的影响」** 对依赖 Code.Storage 承载代理式编程工作负载的团队来说，这项尚未交割的收购意味着其基于 git 的代码与机器生成产物存储将被并入 OpenAI 的 Codex 平台——OpenAI 表示，此次收购旨在为 Codex 补充分布式存储以及构建、理解和审查代码的能力。社区评论援引 Pierre 的产品介绍称 Lovable、Bolt、Amp 等平台使用 Code.Storage 存储生成的代码和记忆文件，这些现有客户需要关注服务路线图并入 OpenAI 后的连续性与供应商依赖风险，并在必要时评估迁移或备选方案。

**「社区讨论」** 用户 tiffanyh 猜测这起收购与 OpenAI 此前发布的《Scaling Git at OpenAI》一文相关，并称开发者 mitchellh 一直是 Pierre 的公开支持者、据其所知还是投资人；用户 paxy 则调侃这是“与其付订阅费不如直接把公司买下来”式的收购。上述关联与动机均属评论者个人看法，尚无 OpenAI 方面的证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ycombinator.com/companies/pierre">Pierre: Pierre is a new, opinionated, git platform. | Y ...</a></li>
<li><a href="https://code.storage/">Code Storage — Git Infrastructure at Scale by The Pierre ...</a></li>
<li><a href="https://www.linkedin.com/in/jacob-thornton-13a6a5162">Jacob Thornton - Pierre Computer Company, Inc. | LinkedIn OpenAI to Buy Pierre, the Startup Behind Code Tools Already ... OpenAI acquires Pierre Computer Company to make Git keep up ... OpenAI to Acquire Pierre: Codex, Git and Code Review Pierre: Headless Git Infrastructure for AI Agents</a></li>
<li><a href="https://openai.com/index/openai-to-acquire-pierre/">OpenAI to acquire Pierre Computer Company, Inc.</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/openai-acquire-pierre-expand-codex-170249678.html?fr=sycsrp_catchall">OpenAI to acquire Pierre to expand Codex developer infrastructure</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/openai-acquire-pierre-computer-bring-192927037.html?fr=sycsrp_catchall">OpenAI to Acquire Pierre Computer, Bring Code Storage ...</a></li>

</ul>
</details>

**标签**: `#openai`, `#acquisitions`, `#developer-tools`, `#git`, `#ai-agents`

---

<a id="item-tech-news-11"></a>
### [Do looped transformers save HBM traffic? Profiling weight reuse in Huginn on a B200 \[P\]](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

An empirical profiling study on a B200 finds that looped transformers like Huginn save weight storage but still re-read shared weights from HBM each iteration, with on-chip reuse benefits only when weights fit in L2 cache.

reddit · r/MachineLearning · /u/2dayyy6 · 11月4日 16:26

**标签**: `#GPU profiling`, `#looped transformers`, `#HBM memory traffic`, `#recurrent depth`, `#ML systems`

---

<a id="item-tech-news-12"></a>
### [Anthropic 开源 FlashProve：用加密证明核实 AI 输出来自指定模型](https://assets.claude.com/8e1d181a83015078581c92d896757041713f0160.pdf) ⭐️ 7.0/10

Anthropic 开源了 FlashProve，一套通过加密证明来验证某段 AI 输出是否确实由指定模型生成的系统，并同时发布了技术规范和代码。按其设计，模型发布方需为公开的模型发布可供后续匹配的指纹，指纹不会披露模型权重，验证也可以在本地设备上完成。研究人员称，该系统可帮助用户识别模型替换，也能核实第三方关于模型执行任务的说法。该项目仍处于研究阶段，Anthropic 目前没有部署计划。

telegram · zaihuapd · 11月4日 10:16

**「模型保密与零知识证明」** 模型权重历来是 AI 实验室的核心商业机密，用户此前没有任何加密手段核实一段回复是否真的出自所声称的模型，服务商暗中替换模型或第三方虚报模型能力都难以被识破。FlashProve 依托的零知识证明思路为这一矛盾提供了技术出路：Anthropic 与零知识证明研究人员合作，使“输出由指定模型生成”这一命题可以在不泄露权重本身的前提下得到验证。

**「影响」** 开发者和研究者现在即可获取 FlashProve 的技术规范与开源代码，在本地设备上评估或实现输出验证流程，且验证过程不会接触模型专有权重。但在 Anthropic 明确表示尚无部署计划、且该机制要求实验室为已发布模型公开指纹的前提下，用户目前无法用它验证真实的 Claude 输出——这套系统的实际价值取决于各实验室是否愿意发布指纹并接入验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-flashprove-cryptographic-model-verification">Anthropic unveils cryptographic tool to verify model outputs</a></li>
<li><a href="https://news.aibase.com/news/32073">Claude Issues Itself an ID Card: Anthropic Uses Zero-Knowledge...</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-flashprove-cryptographic-model-verification">Anthropic unveils cryptographic tool to verify model outputs</a></li>
<li><a href="https://techcrunch.com/2026/11/03/anthropic-is-working-on-a-system-to-prove-ai-models-identity/">Anthropic is working on a system to prove AI models ... | TechCrunch</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#model provenance`, `#cryptography`, `#open source`, `#Anthropic`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Stocks making the biggest moves premarket: Trump Media, Tesla, CoreWeave, Novo Nordisk and more](https://www.cnbc.com/2026/11/04/stocks-making-the-biggest-moves-premarket-djt-tsla-crwv-nvo.html) ⭐️ 7.0/10

CNBC&\#x27;s premarket movers report election-driven declines in Trump Media, Tesla, and neocloud stocks after Democratic midterm wins, alongside CVS&\#x27;s announced two-company split, Novo Nordisk&\#x27;s earnings beat with raised guidance, and other notable earnings reactions.

rss · CNBC Finance · 11月4日 13:32

**标签**: `#premarket-movers`, `#midterm-elections`, `#earnings`, `#corporate-restructuring`, `#AI-data-centers`

---

<a id="item-finance-news-2"></a>
### [民主党中期选举大胜 10 年期美债收益率与油价齐跌](https://www.cnbc.com/2026/11/03/treasury-yields-fall-as-democrats-win-big-in-us-midterm-elections.html) ⭐️ 7.0/10

民主党在美国中期选举中赢得参众两院多数席位，10 年期美债收益率周三下跌逾 6 个基点至 4.884%，WTI 原油期货同日收跌 8.29%至每桶 88.12 美元。摩根大通交易员表示，华尔街此后关注的焦点是分裂国会下的&quot;削减赤字支出&quot;前景。

rss · CNBC Finance · 11月4日 21:18

**「背景」** 民主党在 11 月 3 日的中期选举中赢得参众两院多数席位，将在共和党籍总统特朗普的剩余任期内控制国会，形成白宫与国会分属两党、政府支出计划更难获得通过的

**「潜在影响」** BondBloxx 策略师 JoAnne Bianco 认为，更分裂的政策环境&quot;应使赤字增长更困难，并可能改善财政前景&quot;，这一前瞻判断若兑现将支撑美国国债市场。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bbc.com/news/election/2026/us/results">US midterm elections results 2026 - BBC News</a></li>
<li><a href="https://en.wikipedia.org/wiki/Economic_impact_of_the_2026_Iran_war">Economic impact of the 2026 Iran war - Wikipedia</a></li>
<li><a href="https://www.dallasfed.org/~/media/documents/research/papers/2026/wp2615.pdf">How Times Have Changed: The Impact of the 2026 Iran War on ...</a></li>
<li><a href="https://www.jpmorgan.com/insights/global-research/commodities/iran-us-tensions-market-effect">Economic Impact of Iran Conflict on Oil, Gold and More Iran war is driving up US gas and oil prices. Here&#x27;s how. The Impact of the 2026 Iran War on U.S. Inflation: A Scenario ... Economic impact of the 2026 Iran war - Wikipedia When war moves oil: Energy dependence and global equity ... US-Iran War Oil Price Impact 2026: Energy Markets Face ...</a></li>

</ul>
</details>

**标签**: `#Treasury yields`, `#midterm elections`, `#oil prices`, `#fiscal policy`, `#bond market`

---

<a id="item-finance-news-3"></a>
### [甲骨文取消与腾讯约 70 亿美元 AI 芯片租赁协议](https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/) ⭐️ 7.0/10

据英国《金融时报》报道，在美国官员对交易表达担忧后，甲骨文取消了与腾讯价值约 70 亿美元的 AI 芯片租赁协议。这项今年签署的五年期协议原计划让腾讯通过甲骨文在东南亚的数据中心，租用约 10 万枚在中国境内无法获取的先进 AI 芯片。

telegram · zaihuapd · 11月4日 11:01

**「背景」** 根据美国出口管制，腾讯等中国企业通常无法直接获取先进 AI 芯片，这促使腾讯今年与甲骨文签下为期五年的租赁协议，拟通过甲骨文在东南亚的数据中心使用这些芯片。随着中国 AI 企业转向东南亚市场，当地此类租赁的价格、租期和首付款要求均被推高。

**「影响」** 协议取消使腾讯失去了一条在中国境外获取先进 AI 算力的渠道，也显示中国企业在海外数据中心租用美国先进芯片的安排正面临美国官方的审查。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/entrepreneur-news-network_oracle-tencent-ai-activity-7511636631246987264-phQX"># oracle # tencent # ai # datacenters #artificialintelligence #nvidia...</a></li>
<li><a href="https://nypost.com/2026/11/04/business/oracle-nixes-7b-chip-leasing-deal-with-chinas-tencent-after-trump-admin-pushback-report/">Oracle nixes $7B chip leasing deal with China &#x27;s Tencent after Trump...</a></li>
<li><a href="https://www.zerohedge.com/ai/oracle-kills-7bn-tencent-ai-chip-deal-under-trump-pressure">Oracle Kills $7BN Tencent AI Chip Deal Under Trump... | ZeroHedge</a></li>

</ul>
</details>

**标签**: `#US-China tech tensions`, `#AI chips`, `#Oracle`, `#Tencent`, `#export controls`

---