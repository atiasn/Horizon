---
layout: default
title: "Horizon Summary: 2026-10-24 (ZH)"
date: 2026-10-24
lang: zh
---

> 从 33 条内容中筛选出 5 条重要资讯。

---

**科技新闻**
1. [Today, we hacked what we&\#x27;d set out to hack: the iPhone](#item-tech-news-1) ⭐️ 8.0/10
2. [Kimi K3.1 Pro 登陆 API，承诺 11 月 4 日开放全部权重](#item-tech-news-2) ⭐️ 8.0/10
3. [SemiAnalysis：亚马逊 Trainium 开始挑战英伟达的训练主导地位](#item-tech-news-3) ⭐️ 8.0/10
4. [谷歌隐私政策更新:Gmail 与 Google Photos 数据或用于广告定向](#item-tech-news-4) ⭐️ 7.0/10

**财经新闻**
1. [国办发文：减缓 AI 应用就业替代影响](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Today, we hacked what we&\#x27;d set out to hack: the iPhone](https://blog.calif.io/p/iphone) ⭐️ 8.0/10

A security research team reports successfully hacking an iPhone, prompting wide discussion of the exploit demos, root access, defensive mitigations like Lockdown Mode, and Apple&\#x27;s ecosystem lock-in.

hackernews · pavel\_lishin · 10月23日 16:21 · [社区讨论](https://news.ycombinator.com/item?id=50211474)

**标签**: `#security`, `#ios`, `#exploits`, `#jailbreak`, `#apple`

---

<a id="item-tech-news-2"></a>
### [Kimi K3.1 Pro 登陆 API，承诺 11 月 4 日开放全部权重](https://simonwillison.net/2026/Oct/23/kimi-k31-pro/) ⭐️ 8.0/10

Moonshot AI 的 Kimi K3.1 Pro 已在 Kimi API 上线，美元定价为输入每百万 token 2 美元、输出每百万 token 10 美元，与 GPT-6.1 Sol 持平、约为 Claude Opus 5.5 的一半；另提供速度快 2-3 倍、价格翻倍的 Highspeed 版本（输入缓存命中部分定价不变）。第三方评测机构 Artificial Analysis 给其打出 55 分，领先 Claude Fable 5.1、GPT-6 Astra 和 Gemini 4 Argon（均为 53 分），仅次于 Claude Opus 5.5 的 58 分；Moonshot 自家基准则显示其与 Opus 5.5 和 GPT-6 Astra 大致相当，博主 Simon Willison 称这是即将开放权重的模型首次在这一水平上逼近前沿。模型权重目前尚未开放，Moonshot 承诺将于 2026 年 11 月 4 日前发布完整权重；Willison 已通过 Moonshot 的 OpenAI 兼容接口实测，其 max 推理档在“鹈鹕骑自行车”SVG 测试中表现“相当扎实”，但把两条腿画在了车架同一侧。

rss · Simon Willison · 10月23日 19:40

**「背景」** Kimi 是中国公司月之暗面（Moonshot AI）开发的大语言模型系列，以持续发布开放权重模型著称。其直接前代 Kimi K3 于 2026 年 7 月发布并开放了完整权重：2.8 万亿参数、100 万 token 上下文，是当时规模最大的开放权重模型，权重以 Kimi K3 许可证形式托管在 GitHub 上。K3.1 Pro 承诺 11 月 4 日前放出权重的做法与该系列的开放策略一脉相承，作者也在本次评测中将其与 K3 的输出直接对比。

**「影响」** 开发者现在即可通过兼容 OpenAI 接口的 Moonshot API 调用该模型，现有 OpenAI 兼容工具链（如 Willison 使用的 llm openai endpoint 命令）可直接接入，以约 Claude Opus 5.5 一半的价格获得接近前沿的性能；若 Moonshot 兑现 11 月 4 日开放权重的承诺，需要自托管或微调的团队将多出一个前沿级别的可选模型。

**「社区讨论」** Hacker News 上有订阅用户报告，99 美元/月的套餐在单会话使用 47 分钟后即触发 5 小时配额上限，提醒他人不要对订阅方案的用量限制抱太高期待；另有用户引用 Moonshot 的声明提出质疑——该公司称 K3.1 Pro 的攻击性网络能力被有意控制在低于自身技术管线所能达到的水平，并计划逐步提高开放权重中的网络能力，评论者追问“承认能做更多却不做”是否合理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kimi_%28AI%29">Kimi (AI) - Wikipedia</a></li>
<li><a href="https://www.yottalabs.ai/post/kimi-k3-specs-benchmarks-how-to-access-2026">Kimi K3 Model Size, Open Weights, and Hardware Requirements ...</a></li>
<li><a href="https://github.com/MoonshotAI/Kimi-K3">GitHub - MoonshotAI/Kimi-K3: Open Frontier Intelligence</a></li>

</ul>
</details>

**标签**: `#LLMs`, `#model releases`, `#Moonshot AI`, `#open weights`, `#AI benchmarks`

---

<a id="item-tech-news-3"></a>
### [SemiAnalysis：亚马逊 Trainium 开始挑战英伟达的训练主导地位](https://newsletter.semianalysis.com/p/amazons-trainium-takes-a-strike-at) ⭐️ 8.0/10

SemiAnalysis 于 10 月 23 日发布深度分析，认为亚马逊自研加速器 Trainium 正从“最适合推理”扩展到大规模训练场景，对英伟达在 AI 训练硬件上的主导地位构成挑战。文章列出的依据包括 Trainium 的原生 PyTorch 支持、高质量的持续集成（CI）体系、与 TorchTitan 训练框架的集成，以及一款新的性能分析工具（原文称 &quot;GPU Impossible Profiler&quot;）。对需要为大规模模型训练做硬件选型的 ML 基础设施团队而言，这意味着在英伟达 GPU 之外出现了一个值得评估的 PyTorch 兼容选项。不过，本次仅提供该文的标题与导语，SemiAnalysis 所依据的具体基准测试、训练规模与性能对比数据未包含在所供材料中，其“训练竞争力”结论的强度尚无法据此独立核实。

rss · Semianalysis · 10月23日 19:06

**「背景：TorchNeuron 原生 PyTorch 后端」** Trainium 是亚马逊 AWS 自研的 AI 加速器芯片，此前主要定位推理工作负载，而大规模模型训练市场长期由 NVIDIA GPU 主导。近日 AWS 推出开源的 TorchNeuron，为 Trainium2 和 Trainium3 提供原生 PyTorch 后端，它基于 PyTorch 社区的 PrivateUse1 设备后端等加速器无关扩展接口构建，使现有模型代码、库和工具可以直接在 Trainium 上运行。TorchNeuron 还集成了 PyTorch 原生分布式训练框架 TorchTitan，开发者可沿用与 GPU 相同的 FSDP（全分片数据并行）模式在 Trainium 实例间扩展训练。

**「影响」** 对于运行大规模、重复性训练任务的 ML 团队，Trainium 提供了一条具体的降本路径：第三方成本对比认为，在 Neuron SDK 支持的模型上 Trainium 实例通常训练成本更低，Trainium 3 更宣称较 NVIDIA H200 可节省 30–50% 成本。兼容性是主要顾虑：迁移到 Neuron 软件栈存在实际成本，前沿架构、一次性实验和需要跨平台可移植性的工作负载仍更适合留在 GPU 上。建议团队在签订长期算力承诺前，先针对自身模型实测 cost-to-train 与软件兼容性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pytorch.org/blog/introducing-torchneuron-native-pytorch-backend-for-aws-trainium/">Introducing TorchNeuron: Native PyTorch backend for AWS Trainium</a></li>
<li><a href="https://www.aboutamazon.com/news/innovation-at-amazon/torchneuron-pytorch-aws-trainium-chips-ai">Amazon&#x27;s TorchNeuron runs PyTorch on AWS Trainium chips</a></li>
<li><a href="https://cryptobriefing.com/amazon-trainium3-native-pytorch-torchneuron/">Amazon gives Trainium3 native PyTorch support to win over AI ...</a></li>
<li><a href="https://www.usage.ai/blogs/aws/ai-ml-cost/trainium-vs-gpu-instances/">AWS Trainium vs GPU: AI Training Cost Guide 2026</a></li>
<li><a href="https://www.spheron.network/blog/aws-trainium-3-vs-nvidia-h200-b200-llm-training-inference-2026/">AWS Trainium 3 vs NVIDIA H200 and B200 for LLM Training and ...</a></li>
<li><a href="https://cloudcostroom.com/blog/aws-trainium-vs-gpu-for-training-a-cost-comparison">AWS Trainium vs GPU for Training: Cost Compared</a></li>

</ul>
</details>

**标签**: `#AI hardware`, `#Amazon Trainium`, `#PyTorch`, `#ML training infrastructure`, `#NVIDIA competition`

---

<a id="item-tech-news-4"></a>
### [谷歌隐私政策更新:Gmail 与 Google Photos 数据或用于广告定向](https://www.theverge.com/tech/1017600/google-personal-intelligence-privacy-policy-ads-update) ⭐️ 7.0/10

据 The Verge 报道,谷歌表示可能会将用户 Gmail 邮件和 Google Photos 照片中的内容用于广告定向投放。这一说法来自谷歌的隐私政策更新,属于厂商声明的政策方向,且原文使用的是&quot;可能&quot;\(might\)的措辞,并非已确认全面上线的既成功能。若落实,将影响 Gmail 与 Google Photos 这两项广泛使用的服务,但目前公开材料未说明具体生效时间、适用地区或用户可控的设置细节。

hackernews · JustSkyfall · 10月23日 19:34 · [社区讨论](https://news.ycombinator.com/item?id=50214218)

**「背景」** Google 此前已推出名为 Personal Intelligence 的测试功能,通过一键授权将 Gemini 应用与用户的 Gmail、Google Photos、YouTube 历史和搜索数据连接,以提供更个性化的 AI 助手服务。此次报道的不同之处在于,这些个人数据的用途可能从 AI 个性化扩展到广告定向。在欧盟,《数字市场法》\(DMA\)第 5\(2\) 条促使 Google 提供服务关联选项,用户可自行选择是否关联搜索、YouTube、广告服务等部分服务。

**「影响与可行应对」** 对把邮件和照片长期存放在 Google 的用户而言，最直接的后果是私人内容可能成为广告定向的输入，但目前这仍是媒体报道中的“可能”变化，并非已确认生效的既成事实。想采取行动的用户有两条现成路径：欧盟用户可依据 DMA 第 5\(2\) 条在账号设置中选择不关联搜索、YouTube、广告服务等服务（该清单本身未列出 Gmail 或 Google Photos），以限制跨服务数据合并；其他用户可通过 Google Takeout 导出相册并迁移到自托管方案（如 Immich）。另需注意，Google Photos 官方页面目前仍宣称“不会将你的照片和视频用于广告”，与此次报道存在出入，应以隐私政策原文和账号实际设置为准，而非营销页面。

**「社区讨论」** 评论区的核心争议在措辞本身:有用户直言政策中的&quot;可能&quot;实际上等于&quot;一定会用&quot;,另一位用户则以未经证实的个人经历称,其 2023 年仅在 Google Docs 中记录减重表格、未改变其他上网习惯的情况下就看到了相关广告,据此怀疑谷歌早已将 Drive/Docs 数据用于广告定向。在应对方面,有用户分享了关闭广告个性化的设置入口\(google.com/search-personalization\),有人建议用 Google Takeout 导出照片并迁移到自托管的 Immich,还有用户引用谷歌页面说明称,依据 2024 年 3 月 6 日生效的欧盟《数字市场法》第 5\(2\) 条,欧盟用户可选择是否关联 Search、YouTube、广告服务等 Google 服务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/shellypalmer_google-launched-personal-intelligence-activity-7417596850314334208-eqxa">Google &#x27;s Personal Intelligence connects Gemini to Gmail , Photos ...</a></li>
<li><a href="https://www.google.com/photos/about/">Google Photos : Edit, Organize, Search , and Backup Your Photos</a></li>

</ul>
</details>

**标签**: `#google`, `#privacy`, `#ad-targeting`, `#tech-policy`, `#self-hosting`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国办发文：减缓 AI 应用就业替代影响](https://mp.weixin.qq.com/s/St8URoMYcV-voM7kLAK3Bw) ⭐️ 7.0/10

国务院办公厅印发《关于适应人工智能技术发展助力构建就业友好型发展方式的意见》，提出减缓 AI 应用对就业的替代影响，要求优先在劳动力紧缺、环境高危等岗位推广 AI，并稳慎把握其在劳动密集型行业应用的范围、力度和节奏。文件还鼓励企业探索建立失业缓冲期制度，提前告知受影响劳动者并提供转型转岗就业支持。

telegram · zaihuapd · 10月23日 12:54

**「背景」** 国务院办公厅是协助国务院处理日常政务的机构，其印发的“意见”属于面向各地各部门的指导性政策文件，通常不设强制罚则，实际效果取决于后续执行；该文件编号为国办发〔2026〕29 号，于 2026 年 10 月 23 日公开发布。

**「影响」** 劳动密集型行业的工人和计划部署 AI 的企业是直接相关方：前者有望获得提前告知与转岗支持，后者在劳动密集型领域推广 AI 的节奏可能被放慢；PwC 此前预计中国工业就业将从低价值劳动密集型生产转向更高价值岗位，这类工人正是此次政策重点关注的群体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gov.cn/zhengce/zhengceku/202610/content_7084108.htm">国务院办公厅关于适应人工智能技术发展助力构建就业友好型发展方式的...</a></li>
<li><a href="https://rst.hubei.gov.cn/bmdt/rsyw/202610/t20261023_6040324.shtml">国务院办公厅印发《关于适应人工智能技术发展助力构建就业友好型发展...</a></li>
<li><a href="https://www.pwc.com/gx/en/issues/artificial-intelligence/impact-of-ai-on-jobs-in-china.pdf">What will be the net impact of AI and related technologies on jobs in...</a></li>

</ul>
</details>

**标签**: `#China policy`, `#AI regulation`, `#labor market`, `#employment`, `#State Council`

---