---
layout: default
title: "Horizon Summary: 2026-09-16 (ZH)"
date: 2026-09-16
lang: zh
---

> 从 36 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Google 发布 Gemini 3.8 Live 与 3.8 Live Extended Thinking](#item-tech-news-1) ⭐️ 8.0/10
2. [AI 渗透测试代理 25 分钟内获取 Baseten 生产环境 GitHub 管理员权限](#item-tech-news-2) ⭐️ 8.0/10
3. [互联网档案馆回应 Wayback Machine 遭大规模自动化流量冲击](#item-tech-news-3) ⭐️ 7.0/10
4. [Suspected sabotage causes major Netherlands rail disruption](#item-tech-news-4) ⭐️ 7.0/10
5. [Everyone Says Datacenter Moratoriums Are Killing the US Buildout. We disagree](#item-tech-news-5) ⭐️ 7.0/10
6. [Prior Labs 发布 TabPFN-3.5：自称表格基础模型新 SOTA](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [中国 8 月零售疲弱、投资降幅扩大，政策加码压力上升](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Google 发布 Gemini 3.8 Live 与 3.8 Live Extended Thinking](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-live-gemini-3-8-live-extended-thinking/) ⭐️ 8.0/10

Google 发布了 Gemini 3.8 Live 和 Gemini 3.8 Live Extended Thinking 两个模型版本，重点聚焦实时语音与多模态交互能力，并引入扩展思考模式。此次发布在 Hacker News 上引发了大量讨论（189 条评论），用户的第一手反馈集中在低延迟、对浓重口音的良好识别、以及多语言对话表现等方面。有用户特别提到该模型在小语种（如南非语）口语对话和语法教学中的出色表现，也有用户指出其在创意写作中能捕捉本地化语言细节。不过，社区同时指出该模型仍存在幻觉频发、深度研究功能不可靠等一致性问题。总体来看，这是 Gemini 现有产品线的渐进式迭代，而非范式级突破。

hackernews · leumon · 9月15日 17:38 · [社区讨论](https://news.ycombinator.com/item?id=49715947)

**「背景」** Gemini Live 是 Google Gemini 系列中面向实时语音对话的模型线，此次发布的 Gemini 3.8 Live 与 Gemini 3.8 Live Extended Thinking 被官方称为迄今最先进的实时对话模型，专为自然对话而设计。Google 的 Gemini 产品线在较短时间内从以文本为主的聊天机器人竞争对手演变为多模态实时语音平台，而此次发布将语音产品线一分为二：标准版 Live 与带扩展推理能力的 Extended Thinking 版本，两者于 2026 年 9 月 15 日在同一篇公告中一同推出。理解这一背景有助于把握社区讨论的焦点，即实时语音延迟、口音与多语言表现，以及扩展推理带来的可靠性权衡。

**「影响」** 对于依赖实时语音交互和多语言场景的开发者与用户，Gemini 3.8 Live 提供了在低延迟语音对话和小语种支持方面更具实用价值的选择，但幻觉和可靠性问题仍限制其在严肃工作流中的使用。

**「社区讨论」** 社区反馈总体积极但存在分歧：有用户称赞其口音处理、低延迟和 Workspace 账号可用性，也有母语用户惊叹其小语种口语能力；但长期使用者反映模型在核心概念之外经常幻觉、深度研究结果不可靠。还有用户质疑 Google 拥有数据、TPU 和资金优势却仍未在语音领域超越竞争对手，并询问 Gemini 4 的发布时间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-live-gemini-3-8-live-extended-thinking/">Gemini 3 . 8 Live &amp; Gemini 3 . 8 Live Extended Thinking</a></li>
<li><a href="https://shattered.io/gemini-3-8-live-extended-thinking-launch-2026/">Gemini 3 . 8 Live &amp; Extended Thinking : Google Voice AI [2026]</a></li>
<li><a href="https://www.orcarouter.ai/blog/gemini-3-8-live-release">Gemini 3 . 8 Live : Google Splits Its Voice Line in Two</a></li>

</ul>
</details>

**标签**: `#google-gemini`, `#large-language-models`, `#voice-ai`, `#multimodal`, `#model-release`

---

<a id="item-tech-news-2"></a>
### [AI 渗透测试代理 25 分钟内获取 Baseten 生产环境 GitHub 管理员权限](https://www.strix.ai/blog/baseten-harbor-github-pat-takeover) ⭐️ 8.0/10

安全公司 Strix 报告称，其 AI 驱动的渗透测试代理在约 25 分钟内发现了一个暴露的 GitHub 个人访问令牌（PAT），该令牌属于 Baseten 的 basetenbot 账户，拥有对 Baseten 主要产品仓库、驱动其集群的 GitOps 仓库以及 Homebrew tap 的管理员和推送权限，并对其他私有仓库（包括按客户划分的特定仓库）具有读写权限。据社区评论描述，该令牌是在代理发现 Baseten 的镜像仓库后，从 Docker 构建历史中提取出来的，同时还有一个公开可见的 Harbor 镜像仓库项目。Strix 于 7 月 13 日晚 11:10 向 Baseten 报告了仍在生效的令牌、公开的 Harbor 项目以及仓库权限问题；Baseten 于 7 月 14 日上午将 Harbor 项目设为私有，但令牌本身仍然有效；当天下午 4:34，Baseten 安全团队的 Anton 确认该问题为严重级别，并表示已将 Harbor 项目设为私有并轮换了令牌，同时要求报告方安全删除已拉取的镜像。这一事件既暴露了 Baseten 在密钥管理上的失误，也展示了 AI 代理工具如何大幅降低发现此类漏洞的时间成本。

hackernews · bearsyankees · 9月15日 18:11 · [社区讨论](https://news.ycombinator.com/item?id=49716476)

**「背景知识」** Baseten 是一家为 AI 应用提供模型推理服务的基础设施公司，估值约 130 亿美元，被众多企业客户依赖，因此其生产环境的安全性备受关注。Strix 是一款开源的自主渗透测试 AI 代理，能够自动发现并修复应用程序漏洞，此次事件正是其团队在评估 Baseten 作为推理服务时发现的。事件涉及的关键技术点包括：GitHub 个人访问令牌（PAT）是一种可直接操作仓库的凭证，一旦泄露即可绕过账号密码控制；Docker 镜像的构建历史层可能残留构建时使用的机密信息；而 Harbor 是常用的容器镜像仓库，若项目被设置为公开，任何人都能拉取镜像并检查其构建历史。理解这些概念有助于明白为何一个公开镜像中的残留令牌会导致整个生产代码仓库被接管。

**「影响」** 对于工程和安全团队而言，这一事件表明泄露在 Docker 构建历史和公开镜像仓库中的密钥可被自动化工具在数分钟内发现并利用，因此需要在 CI/CD 流程中系统性地清除构建历史中的敏感信息、收紧镜像仓库的访问控制，并对 GitHub PAT 实施最小权限和定期轮换。

**「社区讨论」** 社区普遍认可 Baseten 的响应处理，认为其披露时间线体现了负责任的处理方式。有评论者指出，AI 代理的价值不在于发现人类无法找到的问题，而在于以远超人类耐心和速度的方式批量排查此类漏洞，同时质疑 Strix 相比直接使用 Claude 或 Codex 等通用工具有何独特之处。也有评论直言这是 Strix 极佳的营销案例而对 Baseten 形象不利，还有人质疑在未获授权的目标上进行此类测试的合法性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.strix.ai/blog/baseten-harbor-github-pat-takeover">We wanted to use Baseten for inference. We ended up with... - Strix</a></li>
<li><a href="https://github.com/usestrix/strix">GitHub - usestrix/ strix : Open-source AI penetration testing tool to find...</a></li>

</ul>
</details>

**标签**: `#security`, `#ai-agents`, `#github`, `#supply-chain`, `#penetration-testing`

---

<a id="item-tech-news-3"></a>
### [互联网档案馆回应 Wayback Machine 遭大规模自动化流量冲击](https://blog.archive.org/2026/09/15/an-update-on-wayback-machine-access/) ⭐️ 7.0/10

互联网档案馆（Internet Archive）发布公告称，其 Wayback Machine 近期持续遭受多波次高流量自动化访问的冲击，为维持服务正常运行，官方已部署相应的防护措施。作为非营利性的关键互联网基础设施，Wayback Machine 长期为公众提供网页历史存档的免费访问服务，此次异常流量直接威胁到其可用性与运营稳定性。社区讨论中普遍推测，这些自动化流量很可能来自试图绕过原网站访问限制的爬虫程序，它们转而抓取 Wayback Machine 中的存档副本。这种做法不仅给这一重要的非营利基础设施带来了沉重负载，还已导致部分网站选择退出存档，可能削弱未来网页历史的完整性。该事件也引发了关于开放网络访问、反爬虫防护措施以及开放互联网基础设施可持续性的更广泛讨论。

hackernews · ChrisArchitect · 9月15日 17:52 · [社区讨论](https://news.ycombinator.com/item?id=49716176)

**「背景」** Wayback Machine（时光机）是互联网档案馆（Internet Archive）运营的非营利性网页存档服务，长期保存网页历史快照供公众免费访问，是开放互联网的重要基础设施。近年来，该服务面临多重压力：除高流量带来的运营负担外，还曾遭遇数据泄露和安全事件，同时卷入出版商的版权诉讼。此次官方公告称，Wayback Machine 遭受了多波高容量自动化流量的冲击，因此部署了防护措施以维持服务运行，但这些反机器人防护也误伤了部分真实用户，导致一些正常访问者遇到访问受阻的情况。

**「影响」** 受影响最直接的是依赖 Wayback Machine 的普通用户、研究者和开发者：高流量自动化访问已迫使 Internet Archive 部署防护措施，部分用户开始遭遇 429 限流错误，服务可用性变得不稳定。更严重的后果是，一些主要媒体机构（包括《纽约时报》《卫报》和 Reddit）出于对 AI 抓取的担忧，已开始限制或屏蔽 Wayback Machine 对其网站的存档，这意味着这些站点的内容可能无法再被完整保存和回溯。

**「社区讨论」** 社区观点呈现明显分歧：有评论者认为抓取存档副本以绕过原站封锁的行为“令人不齿”，并担忧由此引发的网站退出存档会损害公共记录；也有评论者对档案馆在多重压力下仍坚持无门槛访问（包括通过 Tor 匿名访问）表示支持，并呼吁捐款。部分用户报告了疑似误伤的情况，例如在工作电脑上持续遇到 429 错误而在家庭网络中访问正常，引发对防护机制准确性的疑问；还有声音认为 AI 公司应当为获取存档数据向档案馆支付费用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.archive.org/2026/09/15/an-update-on-wayback-machine-access/">An Update on Wayback Machine Access | Internet Archive Blogs</a></li>
<li><a href="https://www.pcmag.com/news/why-is-the-internet-archive-blocking-users-blame-the-bots">Why Is the Internet Archive Blocking Users? Blame the Bots</a></li>
<li><a href="https://x.com/internetarchive/status/2099879742350540885">Internet Archive on X: &quot;“Fix the Wayback Machine!” We’ve ...</a></li>
<li><a href="https://blog.archive.org/2026/02/18/wayback-machine-director-pushes-back/">Wayback Machine Director Pushes Back on AI Scraping Fears ...</a></li>
<li><a href="https://www.niemanlab.org/2026/01/news-publishers-limit-internet-archive-access-due-to-ai-scraping-concerns/">News publishers limit Internet Archive access due to AI ...</a></li>
<li><a href="https://help.archive.org/help/faq-publishers-blocking-the-wayback-machine/">FAQ: Publishers Blocking the Wayback Machine – Internet ...</a></li>

</ul>
</details>

**标签**: `#internet-archive`, `#wayback-machine`, `#web-scraping`, `#infrastructure`, `#open-web`

---

<a id="item-tech-news-4"></a>
### [Suspected sabotage causes major Netherlands rail disruption](https://www.bbc.com/news/articles/c8ly49w9g1edo) ⭐️ 7.0/10

Suspected sabotage disrupted major Netherlands rail service, sparking a well-informed Hacker News discussion on how fail-safe rail signaling systems can be exploited at scale to halt trains without causing collisions.

hackernews · choult · 9月15日 10:22 · [社区讨论](https://news.ycombinator.com/item?id=49710253)

**标签**: `#critical-infrastructure`, `#rail-systems`, `#security`, `#fail-safe-design`, `#physical-sabotage`

---

<a id="item-tech-news-5"></a>
### [Everyone Says Datacenter Moratoriums Are Killing the US Buildout. We disagree](https://newsletter.semianalysis.com/p/everyone-says-datacenter-moratoriums) ⭐️ 7.0/10

SemiAnalysis argues that datacenter moratoriums have far less impact on the US buildout than commonly claimed, quantifying only ~2.3GW of actual slippage nationwide despite 20GW sitting inside restricted local boundaries.

rss · Semianalysis · 9月15日 20:54

**标签**: `#datacenters`, `#AI infrastructure`, `#energy policy`, `#power grid`, `#industry analysis`

---

<a id="item-tech-news-6"></a>
### [Prior Labs 发布 TabPFN-3.5：自称表格基础模型新 SOTA](https://www.reddit.com/r/MachineLearning/comments/1wh4xhy/tabpfn35_is_released_as_the_next_sota_tabular/) ⭐️ 7.0/10

Prior Labs 于今日发布了其最新一代表格基础模型 TabPFN-3.5，据称在 TabArena 和 BeyondArena 两个基准上均排名第一，并支持最多 100 万行数据和最高 2 万个特征的表格任务。该版本提供多个变体：TabPFN-3.5-Fast（alpha 阶段）速度比基础模型快 6 倍；TabPFN-3.5-Thinking 通过增加计算换取更高精度，仅通过 API 提供；另有 TabPFN-3.5-Plus 变体。在 BeyondArena 上，TabPFN-3.5 在文本丰富、高基数和高维数据上领先，比此前最强基线高出 250 Elo 分，比此前综合领先者高出 150 Elo 分；TabPFN-3.5-Thinking 相比基础模型在 BeyondArena 上提升 20 Elo 分，在 TabArena 上提升 44 Elo 分。需要注意的是，这些基准数据由厂商自行报告，且消息来源为 Reddit 发布帖，尚缺乏独立验证，因此实际表现仍待第三方复现确认。

reddit · r/MachineLearning · /u/tuanacelik · 9月15日 16:18

**「背景」** TabPFN 是由 Prior Labs 开发的表格数据基础模型系列，其思路类似于将预训练大模型应用于结构化数据，让模型在无需针对每个数据集从头训练的情况下完成表格预测任务。此前的 TabPFN-2 版本以 Apache 2.0 为基础并附加署名要求的 Prior Labs License 开源发布，代码和模型权重可在 GitHub 获取。TabArena 和 BeyondArena 是用于在真实世界数据上评估表格预测模型的外部基准，常被用来比较不同表格机器学习方法的相对表现。

**「影响」** 如果这些基准结果得到独立验证，处理表格数据的从业者和数据科学家将获得一个在 TabArena、BeyondArena、MulTaBench、RelArena 等多个基准上自称达到 SOTA 的零样本推理选项，可支持最多 100 万行、2 万特征的数据集，从而可能减少对耗时调参的传统模型的需求。不过，这些性能数据目前主要来自 Prior Labs 自行发布的技术报告，实际效果仍需第三方复现确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://twm.com.sg/tabpfn-3-5-plus-now-available-in-sap-ai-core-for-instant-business-predictions/">TabPFN - 3 . 5 Plus Now Available in SAP AI Core for Instant Business...</a></li>
<li><a href="https://github.com/PriorLabs/TabPFN">GitHub - PriorLabs/ TabPFN : TabPFN : Foundation Model for Tabular ...</a></li>
<li><a href="https://priorlabs.ai/technical-reports/tabpfn-3-5">TabPFN-3.5: Technical Report - Prior Labs</a></li>
<li><a href="https://storage.googleapis.com/prior-labs-tabpfn-public/reports/tabpfn-v3.5-report.pdf">TabPFN-3.5: Technical Report - storage.googleapis.com</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#tabular-data`, `#foundation-models`, `#benchmarks`, `#model-release`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中国 8 月零售疲弱、投资降幅扩大，政策加码压力上升](https://www.cnbc.com/2026/09/15/china-august-retail-sales-industrial-output-investment-exports-.html) ⭐️ 7.0/10

中国国家统计局 9 月 15 日公布，8 月社会消费品零售总额同比仅增长 0.4%，低于市场预期的 0.8%，前 8 个月城镇固定资产投资同比下降 7.2%、降幅较前 7 个月的 6.7%进一步扩大，同时 8 月城镇调查失业率升至 5.3%，加大了市场对北京出台更强刺激政策的期待。

rss · CNBC Finance · 9月15日 09:46

**「背景」** 中国经济第二季度同比增长 4.3%，为三年多来最弱，官方已承认国内存在“供给偏强、需求偏弱”的失衡，但迄今仅采取增发政府债券、扩大贷款贴息等渐进措施，未推出大规模刺激。

**「影响」** 8 月新增银行贷款仅 600 亿元人民币、远低于约 4000 亿元的预期，贷款余额增速降至创纪录低点 4.9%，显示企业和家庭借贷意愿疲弱，牛津经济研究院据此预计三季度增长 4.3%，令全年 4.5%至 5%的官方目标面临下行风险。

**标签**: `#China economy`, `#retail sales`, `#fixed-asset investment`, `#monetary and fiscal policy`, `#economic data`

---