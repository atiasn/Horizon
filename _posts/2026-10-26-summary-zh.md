---
layout: default
title: "Horizon Summary: 2026-10-26 (ZH)"
date: 2026-10-26
lang: zh
---

> 从 27 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [十年前的 CNN 微调后诊断皮肤癌胜过前沿大模型](#item-tech-news-1) ⭐️ 7.0/10
2. [Brotli 解码器高危漏洞波及 Python 与 Node.js，修复版本已发布](#item-tech-news-2) ⭐️ 7.0/10
3. [苹果将于周三发布首款触屏 OLED MacBook Pro](#item-tech-news-3) ⭐️ 7.0/10

**财经新闻**
1. [2025 年全国总人口减少 339 万，逼近 14 亿关口](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [十年前的 CNN 微调后诊断皮肤癌胜过前沿大模型](https://lynchlab.net/llm-skin-cancer) ⭐️ 7.0/10

Lynch 实验室的一篇博文报告称,作者将十年前的 Inception v3 卷积神经网络\(先在普通照片上预训练\)在 ISIC 存档的 68,011 张皮肤镜和临床图像上全层微调,且仅需单张 H100 GPU,随后在 200 个测试皮损上的皮肤癌诊断表现优于两个前沿多模态大语言模型。作者称训练前已从训练集和验证集中剔除测试皮损以及同一皮损或同一患者的所有照片,测试集也未用于挑选模型或设定阈值。需要说明的是,这是博客作者自述的单一比较结果,并非同行评审研究,作者本人也表示对老网络胜出感到意外。

hackernews · sungam · 10月25日 17:15 · [社区讨论](https://news.ycombinator.com/item?id=50233779)

**「背景」** 用卷积神经网络（CNN）对皮肤病变图像做良恶性分类早有先例：2017 年 1 月发表于《自然》的研究采用的正是 Google Inception v3 架构——先在 ImageNet 的 128 万张通用图像上预训练，再在皮肤病变数据集上微调——并报告其分类准确率可与至少 21 名持证皮肤科医生相当。本次实验沿用的就是这条技术路线，只是把对比对象从人类医生换成了十年后出现的通用多模态大语言模型。

**「对诊断类 AI 选型的影响」** 对于评估或构建医学影像诊断工具的开发者和医疗机构，这一结果意味着在皮肤病变筛查这类窄任务上直接采用前沿多模态 LLM 可能以诊断准确率为代价，而微调专用模型的成本并不高——该研究仅在单张 H100 GPU 上完成了对 68,011 张 ISIC 图像的训练，因此选型时应把在病变级别 held-out 数据上微调的专用分类器作为对照基线，而非默认通用大模型更优。不过需注意评论者指出的限定：该 CNN 是在与测试集同分布的 ISIC 数据上微调的，其领先可能部分来自对基准分布的拟合；一项针对急诊场景的独立研究也指出，多模态 LLM 的影像决策支持仍缺乏与临床医生对照的前瞻性基准验证，因此在真实临床环境部署前仍需独立验证。

**「社区讨论」** 在 Hacker News 讨论中,多数评论者对结果并不意外:tasuki 以约 3000 万参数、单次演算即超人类的 KataGo 围棋网络类比,认为专用小网络在窄任务上胜过通用大模型本属常态,MitPitt 也以&quot;计算器在乘除法上同样胜过 LLM&quot;作比。分歧集中在比较的公平性上——Legend2440 批评这是&quot;benchmaxxing&quot;,在基准分布上微调过的模型必然胜过未微调的通用模型;snitty 则主张 LLM 的真正价值在于把构建专用分类器的成本降到接近零,而非直接承担所有任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nature.com/articles/nature21056">Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ... Dermatologist–level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer... : Nature Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ...</a></li>
<li><a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC8382232/">Dermatologist–level classification of skin cancer with deep ...</a></li>
<li><a href="https://link.springer.com/article/10.1186/s13049-026-01577-6">Multimodal large language model versus emergency physicians for...</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#computer-vision`, `#medical-imaging`, `#llm-evaluation`, `#fine-tuning`

---

<a id="item-tech-news-2"></a>
### [Brotli 解码器高危漏洞波及 Python 与 Node.js，修复版本已发布](https://www.aikido.dev/blog/python-packages-vulnerable-node2shell-brotli-cve-2026-111497) ⭐️ 7.0/10

据 Aikido Security 报告，谷歌 Brotli 解码器的高危漏洞 CVE-2026-111497（CVSS 4.0 评分 9.2）影响 1.0.3 至 1.2.0 版本：远程未认证攻击者可发送特制压缩流触发内存损坏，进而导致敏感数据泄露、进程崩溃或可能执行任意代码；该漏洞最初以 Node2Shell 名称披露，后改称 HTTP2Shell，Node.js 与 Python 的相关 HTTP 组件均受影响。受影响用户需升级至修复版本：Python 的 Brotli 需升至 1.2.1，brotlicffi 需升至 1.2.1.0，Node.js 需升至 22.23.4、24.22.1 或 26.12.1。OpenAI 声称其于今年 2 月发现了该问题，但这一说法及漏洞的确切影响范围目前仅见于厂商博客，尚待官方安全公告进一步核实。

telegram · zaihuapd · 10月25日 02:42

**「背景」** Brotli 是谷歌开发的无损压缩算法，常通过 HTTP 的 Content-Encoding 机制用于压缩网页响应，其 C 语言实现的解码器被 Node.js、Python 等众多 HTTP 组件直接或间接嵌入，因此解码器缺陷可被远程触达。据 NVD 描述，Google Brotli 1.0.3 至 1.2.0 版本解码器（c/dec/decode.c）存在缓冲区溢出，全平台受影响，远程未认证攻击者可借特制 Brotli 压缩流破坏相邻解码器状态内存、泄露敏感内存内容、造成拒绝服务或可能执行任意代码。该漏洞最初以 Node2Shell 之名披露、聚焦 Node.js 生态，本次报道则将其影响范围扩展至 Python 的 Brotli 与 brotlicffi 组件。

**「影响与应对」** 在服务端解压 Brotli 编码 HTTP 内容的 Node.js 与 Python 服务是主要暴露面：只要依赖 1.0.3 至 1.2.0 版本的 Brotli 解码器，未认证的远程攻击者就能用特制压缩流触发 decode.c 中的缓冲区溢出，在所有平台上破坏相邻解码器状态内存，导致敏感内存内容泄露、拒绝服务或可能执行任意代码。受影响团队应尽快将 Python 的 Brotli 升级到 1.2.1、brotlicffi 升级到 1.2.1.0，Node.js 升级到 22.23.4、24.22.1 或 26.12.1；由于该解码器以 C 实现、被多种运行时和语言绑定嵌入，通过间接依赖引入 Brotli 的项目也应核对实际链接的解码器版本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2026-111497">NVD-CVE-2026-111497</a></li>
<li><a href="https://www.oligo.security/blog/critical-node-js-rce-vulnerability-cve-2026-111497-detection-and-mitigation">Node.js Brotli Vulnerability (CVE-2026-111497): Detection &amp; Mitigation</a></li>
<li><a href="https://www.tenable.com/cve/CVE-2026-111497">CVE-2026-111497 | Tenable®</a></li>

</ul>
</details>

**标签**: `#security`, `#Brotli`, `#Node.js`, `#Python`, `#HTTP`

---

<a id="item-tech-news-3"></a>
### [苹果将于周三发布首款触屏 OLED MacBook Pro](https://www.bloomberg.com/news/newsletters/2026-10-25/apple-to-unveil-touch-screen-macbook-pro-executive-promotions-in-box-checker) ⭐️ 7.0/10

据 Bloomberg 报道，苹果将于本周三发布首款支持触控的 MacBook Pro，这也是 Mac 首次配备 OLED 屏幕并加入灵动岛，提供 14 英寸和 16 英寸两种版本，起售价高于现款的 2499 美元。报道指出，苹果高管多年来一直以人体工学为由否定触屏笔记本，此次转变更多出于营收与营销层面的考虑，触控将被定位为键盘和触控板的补充。上述信息来自发布会前的媒体报道，在周三发布会举行前，具体配置与定价尚未得到苹果官方确认。

telegram · zaihuapd · 10月25日 14:25

**「背景」** 苹果高管多年来一直以人体工学为由否定触屏笔记本，此次推出触屏 MacBook Pro 是对这一长期立场的逆转。新机预计在本周三（10 月 28 日）苹果名为「Pro and Tell」的发布会上亮相；另有报道称，受近期内存价格大幅上涨影响，其售价可能较现款 2499 美元的起售价再上调 300 至 500 美元。

**「影响」** 对考虑升级的用户而言，最直接的影响是价格门槛提高：新款起售价将高于现款的 2499 美元，建议等待周三发布会确认确切定价与配置后再做购买决定。触控被定位为键盘与触控板的补充而非替代，现有输入方式不因此改变。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://appleworld.today/2026/10/apples-oled-touchscreen-macbook-pro-may-face-a-300-to-500-price-hike-to-protect-their-profits-from-ramageddon/">Apple&#x27;s OLED touchscreen MacBook Pro may face a $300 to $500 ...</a></li>

</ul>
</details>

**标签**: `#apple`, `#macbook-pro`, `#touchscreen`, `#oled`, `#hardware`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [2025 年全国总人口减少 339 万，逼近 14 亿关口](https://weibo.com/1796087453/5357878513767954) ⭐️ 7.0/10

据微博转述的《中国统计年鉴 2026》数据（荔枝新闻发布），2025 年末全国总人口为 140489 万人（约 14.05 亿），较 2024 年末减少 339 万人，正逼近跌破 14 亿。全年出生 792 万人，出生率 5.63‰，自然增长率为-2.41‰。

telegram · zaihuapd · 10月25日 12:02

**「背景」** 数据出自国家统计局编印的《中国统计年鉴 2026》；其中“自然增长率”为出生率减去死亡率，-2.41‰ 表示 2025 年死亡人数多于出生人数。分省来看，出生率超过 7‰ 的 9 个省份和自然增长率为正的 7 个省份主要集中在西部和华南，黑龙江、吉林、辽宁三省出生率垫底。

**「潜在影响」** 人口持续负增长意味着劳动年龄人口和养老缴费基数逐步收缩，对养老金体系、劳动密集型行业及依赖人口规模的区域经济构成长期压力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://t.me/zaihuapd/44691">在花 科技圈 – Telegram</a></li>

</ul>
</details>

**标签**: `#China demographics`, `#population decline`, `#birth rate`, `#macroeconomic data`, `#regional statistics`

---