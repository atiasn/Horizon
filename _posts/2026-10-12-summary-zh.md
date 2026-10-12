---
layout: default
title: "Horizon Summary: 2026-10-12 (ZH)"
date: 2026-10-12
lang: zh
---

> 从 36 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [Terence Tao: Math 2.0 \[pdf\]](#item-tech-news-1) ⭐️ 8.0/10
2. [Karpathy 发文：对 LLM 能力的共识分歧正在扩大](#item-tech-news-2) ⭐️ 7.0/10
3. [评论文章称 Passkeys 是陷阱，引发社区技术辩论](#item-tech-news-3) ⭐️ 7.0/10
4. [AI 氛围编程加速反编译：经典游戏浏览器移植版扎堆出现](#item-tech-news-4) ⭐️ 7.0/10

**财经新闻**
1. [食品安全法大修公开征求意见 首次纳入直播带货监管与校园陪餐制度](#item-finance-news-1) ⭐️ 7.0/10
2. [韩国股市失宠，外资年内撤离超 8700 亿元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Terence Tao: Math 2.0 \[pdf\]](https://teorth.github.io/tao-web/slides/math-2-0-caltech-2026.pdf) ⭐️ 8.0/10

Terence Tao&\#x27;s &\#x27;Math 2.0&\#x27; presentation explores how AI tools are reshaping mathematical research, sparking significant community discussion about AI&\#x27;s impact on problem-solving and scientific fields.

hackernews · Anon84 · 10月11日 13:16 · [社区讨论](https://news.ycombinator.com/item?id=50043026)

**标签**: `#artificial intelligence`, `#mathematics`, `#Terence Tao`, `#AI-assisted research`, `#academic impact`

---

<a id="item-tech-news-2"></a>
### [Karpathy 发文：对 LLM 能力的共识分歧正在扩大](https://twitter.com/karpathy/status/2109361546505966046) ⭐️ 7.0/10

Andrej Karpathy 在 Twitter/X 上发文称，人们对大语言模型（LLM）实际能力的共同理解正在出现越来越大的差距。该推文在 Hacker News 上引发大规模讨论，累计约 436 条评论。讨论的核心分歧集中在代理式编程（agentic coding）能力的真实程度以及公众对 AI 进展的感知上。

hackernews · albertzeyer · 10月11日 20:20 · [社区讨论](https://news.ycombinator.com/item?id=50047422)

**「背景」** Andrej Karpathy 是前 Tesla AI 总监，长期以来是 AI 领域有影响力的公开评论者，他对大模型能力的判断常引发开发者社区的广泛讨论。近年来围绕“智能体编程（agentic coding）”的争论不断：一部分开发者认为智能体已能独立完成大型项目，另一部分则强调仍需人工审查代码、关注维护成本和 LLM 的常见错误。这条推文正是在这种分歧背景下，指出公众与技术圈对 LLM 实际能力的共同认知差距正在扩大。

**「社区讨论」** 评论者对推文所指的&quot;少数人已能靠提示词让代理完成原本需数周或数月的大型项目&quot;这一说法本身存疑：rico735 认为，真正的分歧不在于是否相信这种能力，而在于是否审查代码、是否担心维护成本、token 费用和 LLM 常见错误。另有评论者（nsainsbury）抱怨 AI 尚未改善普通人的生活，而 NichoPaolucci 则认为普通公众本就无需关心代理能力，正如早期互联网一样，该技术仍处于起步阶段。

**标签**: `#LLMs`, `#AI-capability-debate`, `#developer-tools`, `#AI-discourse`

---

<a id="item-tech-news-3"></a>
### [评论文章称 Passkeys 是陷阱，引发社区技术辩论](https://nonfunctional.substack.com/p/passkeys-are-a-trap-do-not-use-them) ⭐️ 7.0/10

一篇发表在 Substack 上的评论文章《Passkeys are a trap》于 2026 年 10 月 11 日通过 Hacker News 传播，作者主张 passkeys（通行密钥）会造成厂商锁定和可用性陷阱，提醒用户不要使用。文章的核心担忧集中在远程证明（attestation）机制上：网站理论上可以要求 passkey 提供设备证明，从而拒绝非特定厂商生态内的凭据，导致用户被绑定在某一平台。该文章在 Hacker News 上引发了活跃的技术辩论，多位评论者从可移植性、证明机制的实现现实以及安全性权衡等角度提出质疑和补充。

hackernews · laurex · 10月11日 21:59 · [社区讨论](https://news.ycombinator.com/item?id=50048312)

**「背景：什么是 Passkey」** Passkey（通行密钥）是基于 FIDO/WebAuthn 标准的登录凭证，用设备上的公私钥对代替传统密码，私钥保存在用户设备或平台厂商的同步服务（如 Apple、Google 账户）中，因私钥不会离开设备，天然能防御钓鱼和中间人攻击。引发争议的关键在于：凭证默认绑定在特定平台生态里，跨生态迁移尚无统一标准，因此批评者担心用户被锁定在某个厂商或某台设备上。

**「社区讨论」** 评论者对文章的核心论点提出了实质性反驳。用户 danpalmer 指出文章结尾的脚注颇具讽刺意味——作者承认 passkeys 因绑定域名而能抵御中间人攻击，而这正是 passkeys 最初的核心安全特性；用户 agwa 则质疑文章的现实基础，指出证明只能在凭据注册时要求，且浏览器会弹出权限提示，他怀疑 Netflix 和 Twitter 等公司目前并未实际在注册时强制要求证明。也有用户表达了对可移植性的担忧：bmitch3020 表示自己不愿启用 passkeys，主要因为不想把凭据绑定在可能丢失的单台设备上，并认为指纹解锁的安全性不如密码管理器中的长密码。

**标签**: `#authentication`, `#passkeys`, `#security`, `#web-standards`, `#vendor-lock-in`

---

<a id="item-tech-news-4"></a>
### [AI 氛围编程加速反编译：经典游戏浏览器移植版扎堆出现](https://kotaku.com/we-might-be-cooked-as-these-vibe-coded-web-browser-ports-of-halo-the-simpsons-hit-and-run-and-gta-vice-city-seem-to-work-perfectly-2000743300) ⭐️ 7.0/10

Kotaku 报道称，近几周出现数百款由 AI 氛围编程完成反编译的模拟器和游戏移植版，《使命召唤：黑色行动》《光环：战斗进化》《GTA：罪恶都市》等 PS2/PS3 时代游戏的浏览器移植版运行接近完美，其中一款《光环》还支持联机服务器。报道称 Claude Opus 5.5 反编译能力极强，过去需数月的源码重建现在一夜即可完成。被移植游戏普遍是 PS2/PS3 时代的作品，内存早已不是瓶颈。

telegram · zaihuapd · 10月11日 03:10

**「背景」** 反编译移植是指将主机游戏的机器码还原为可读源码，再编译到其他平台运行，这类工作过去依赖社区数月甚至数年的人工逆向工程，例如经典的 PS2/PS3 时代游戏反编译项目。如今借助 Claude Opus 5.5 等 AI 编程工具，源码重建的周期被大幅压缩，使此类浏览器移植版得以在近几周内集中大量出现。

**「潜在影响」** 这类移植做得又快又容易，即使发行商发出律师函并要求下架，也只是打地鼠式的应对，经典游戏版权保护面临实际执行困难。对玩家而言，可以在浏览器中直接体验这些老游戏，但其合法性存在争议。

**标签**: `#AI`, `#game-emulation`, `#decompilation`, `#browser-ports`, `#intellectual-property`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [食品安全法大修公开征求意见 首次纳入直播带货监管与校园陪餐制度](https://weibo.com/1642634100/Rm8MOi0jg) ⭐️ 7.0/10

市场监管总局就《食品安全法（修订草案征求意见稿）》公开征求意见，这是该法 2009 年施行以来又一次大规模系统性修订，首次将直播带货纳入监管范围，并针对学校食品安全设立校长（园长）负责制和中小学、幼儿园集中用餐陪餐制度。

telegram · zaihuapd · 10月11日 06:02

**「背景」** 《食品安全法》于 2009 年施行，此次是其实施以来又一次大规模系统性修订。此前 2026 年 3 月市场监管总局曾就幼儿园食品安全管理规定征求意见，明确园长负责制并建立“日管控、周排查、月调度”的风险防控机制，此次修法将类似的校园食品安全要求上升至法律层面。

**「影响」** 若草案通过，网络食品交易平台经营者将统一成为责任主体，其管理对象扩展至平台内经营者和直播间运营者，直接影响直播电商从业者及学校餐饮管理方。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.dzwww.com/xinwen/guoneixinwen/202603/t20260325_17575111.htm">dzwww.com/xinwen/guoneixinwen/202603/t20260325_17575111.htm</a></li>

</ul>
</details>

**标签**: `#food-safety-regulation`, `#China-policy`, `#livestream-commerce`, `#school-food-safety`

---

<a id="item-finance-news-2"></a>
### [韩国股市失宠，外资年内撤离超 8700 亿元](https://m.gelonghui.com/live/2705107) ⭐️ 7.0/10

Foreign investors have pulled roughly $131 billion out of Korean equities this year as the KOSPI fell about 22% from its strength in H1, with confidence shaken by heavy reliance on Samsung Electronics and SK Hynix.

telegram · zaihuapd · 10月11日 12:13

**标签**: `#South Korea`, `#foreign capital outflows`, `#KOSPI`, `#semiconductors`, `#market sentiment`

---