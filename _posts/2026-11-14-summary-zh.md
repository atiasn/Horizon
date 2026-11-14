---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 39 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [美国 FAA 因空管通信网络故障下令全国停飞](#item-tech-news-1) ⭐️ 8.0/10
2. [在 384 张 GH200 上用 TorchTitan 训练约 1T 参数 MoE，单卡吞吐提升 14 倍](#item-tech-news-2) ⭐️ 8.0/10
3. [Python 早期贡献者 Tim Peters 去世，享年 74 岁](#item-tech-news-3) ⭐️ 7.0/10
4. [微软 Outlook、Teams、Copilot 全球宕机超 12 小时](#item-tech-news-4) ⭐️ 7.0/10

**财经新闻**
1. [卢特尼克因英伟达风波面临质询，其家族企业与其关系深厚](#item-finance-news-1) ⭐️ 8.0/10
2. [Chicago Fed&\#x27;s Goolsbee says central bank &\#x27;has definitely got work to do&\#x27; on inflation](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [美国 FAA 因空管通信网络故障下令全国停飞](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 8.0/10

美国联邦航空管理局（FAA）于 2026 年 11 月 13 日下令全国范围内暂停离港航班，原因是用于空中交通管制的电信网络出现故障。据《华尔街日报》报道，故障涉及由 L3Harris Technologies 运营的网络，该网络承载管制员与飞行员通信所用的关键无线电频率；尚不清楚雷达数据是否也受到影响。社区评论显示《纽约时报》已报道停飞令后来解除，但一名官员表示这可能是一次持续时间较长的故障，恢复情况仍不确定。

hackernews · zulln · 11月13日 21:05 · [社区讨论](https://news.ycombinator.com/item?id=50489641)

**「背景」** 全美范围的停飞令极为罕见，上一次发生在 2023 年 1 月，起因是向飞行员提供航行通告（NOTAM）的系统发生故障。本次事件中，FAA 于美国东部时间 2026 年 11 月 13 日下午 3:54 发布全国停飞指令，原因是影响多个空中交通管制中心的通信问题，据 WSJ 报道该问题涉及由 L3Harris 运营、承载管制员与飞行员无线电通信的网络。FAA 此前（11 月 10 日）曾宣布其 SMART AI 空管工具将在全部 22 个管制中心推广，部分社区评论者据此猜测与此次故障有关，但这一联系尚无证据支持。

**「实际影响」** 据 CNBC 报道，该全国性地面停飞令在持续约四个小时后解除，但已造成数千架次出发航班延误或取消；仅丹佛一地就有 640 次延误和 369 次取消。受影响旅客应通过航空公司渠道确认航班状态并预留后续调整时间，因为恢复运行后的积压清理可能需要更长时间。

**「社区讨论」** Hacker News 用户指出公开信息极为稀少，主要来自官员在社交媒体上的发言，并以 LAX 等机场离港数据显示大面积延误或取消作为佐证。另有用户提出故障是否与前一日宣布的 FAA 全美范围 AI 空管工具（SMART）部署有关的猜测，但这只是未经证实的猜测，官方披露的原因仍是 L3Harris 电信网络故障。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://www.faa.gov/newsroom/faa-statement-nationwide-ground-stop">FAA Statement on Nationwide Ground Stop | Federal Aviation ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.cpr.org/2026/11/13/flights-ground-stop-faa-dia/">UPDATE: National ground stop lifted after more than 4 hours ...</a></li>

</ul>
</details>

**标签**: `#air-traffic-control`, `#infrastructure`, `#outage`, `#FAA`, `#telecom`

---

<a id="item-tech-news-2"></a>
### [在 384 张 GH200 上用 TorchTitan 训练约 1T 参数 MoE，单卡吞吐提升 14 倍](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

一支工程团队与 TorchTitan 和 PyTorch 维护者合作，在 JUPITER 超算的 384 张 GH200 GPU 上训练约 1 万亿参数的混合专家（MoE）模型，达到每 GPU 约 1,300 tokens/s 的吞吐，相比起点提升 14 倍。方案采用 384 路 FSDP 加 4 路节点内专家并行（EP），刻意不用流水线并行以缩短步长、加快迭代。关键优化包括全量激活检查点（单独带来 4 倍）、向 Grace CPU 的激活卸载与预取、Muon 优化器、按注意力成本预打包数据（最慢 rank 从平均的 7.9 倍降到 1.15 倍）、梯度以 bf16 传输但按 fp32 本地累加、FP8 专家 all-gather（+18%），以及修复 PyTorch 缓存分配器在侧流上滞留约 21 GiB 内存的问题（吞吐再涨 21%）。作者把完整细节发布在 Domyn 博客，并在 PyTorch 博客发布了浓缩版。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「背景」** TorchTitan 是 PyTorch 官方推出的大规模训练框架，FSDP（全分片数据并行）会把每一份权重切成切片分散到各 GPU，并在计算时按需聚合，从而让单个 GPU 能训练远超自身显存的模型。混合专家模型（MoE）通过仅激活部分专家来扩展参数量，但专家权重仍需分片，因此通常与专家并行（EP）结合——每张 GPU 持有若干完整专家，token 通过 all-to-all 通信被路由到对应专家。这种组合之所以关键，是因为像 JUPITER 这样通过 InfiniBand（约 25 GB/s/GPU）互连的集群，跨节点带宽远低于 NVLink 或 Grace-Hopper 的片间链路，分片与通信策略的选择直接决定了 GPU 是在计算还是在等待网络。

**「实际影响」** 对在大规模集群上训练大模型的工程团队，这条经验报告给出了可直接复用的调优清单：在节点间带宽受限（此例中每 GPU 约 25 GB/s 的 InfiniBand）时，优先减少线上字节数、按通信成本设计分片（如 FlexShard 按完整专家切分使 Newton-Schulz 正交化零通信）、并用 Grace CPU 的 900 GB/s C2C 链路卸载激活。其中多项修复（GPU 上运行 Newton-Schulz、FSDP2 的 unshard\_async\_op 标志转为公开 API 的进行中工作）已回馈 TorchTitan/PyTorch 上游，采用相关技术栈的用户可直接受益；但作者也提示组限路由虽使专家负载完全均衡（+7%），早期运行显示可能损害训练质量，取舍尚无定论。

**标签**: `#distributed-training`, `#mixture-of-experts`, `#pytorch`, `#FSDP`, `#GPU-scaling`

---

<a id="item-tech-news-3"></a>
### [Python 早期贡献者 Tim Peters 去世，享年 74 岁](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Python 创造者 Guido van Rossum 宣布，Python 早期贡献者 Tim Peters 去世，享年 74 岁。Peters 是 Python 的第二位真实用户，撰写了 Timsort 排序算法（Python 的默认排序算法）和《Python 之禅》（PEP 20），并曾在 Python 软件基金会董事会任职 13 年。

telegram · zaihuapd · 11月13日 09:55

**「背景」** Tim Peters 于 1999 年在 Python 邮件列表上发表了《Python 之禅》的 19 条格言，并将第 20 条留空“给 Guido 填写”，该原则集至今仍是 Python 设计哲学的标志性文本（输入 import this 即可显示）。根据 Guido van Rossum 在 Python 官方核心开发者论坛发布的讣告，Peters 实际去世于今年 7 月 15 日，享年 74 岁，其影响力“怎么估计都不为过”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028">In Memoriam: Tim Peters 1952–2026 - Core Development...</a></li>

</ul>
</details>

**标签**: `#python`, `#tim-peters`, `#timsort`, `#open-source`, `#community-news`

---

<a id="item-tech-news-4"></a>
### [微软 Outlook、Teams、Copilot 全球宕机超 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

微软 Outlook、Teams 和 Copilot 于 11 月 13 日仍处于宕机状态，故障持续超过 12 小时，打乱全球企业与政府的日常通信。微软表示原因在于服务器问题，未发现恶意活动，并称已扩大修复范围、看到服务回稳迹象。澳大利亚、日本和美国部分政府机构受到影响，欧交所 Euronext 邮件受阻，台湾有金融机构改用传真确认交易。报道称这是微软 365 服务今年第二次中断。

telegram · zaihuapd · 11月13日 12:21

**「背景」** Microsoft 365 是微软将 Outlook 邮箱、Teams 协作通信和 Copilot 助手等办公工具托管在其云服务器上的订阅服务，大量企业和政府机构日常依赖它进行邮件与即时通信，因此其服务器一旦故障就会造成大范围通信中断。据来源报道，这是微软 365 服务今年第二次发生中断。

**「影响」** 依赖微软 365 邮件和通信服务的机构在宕机期间被迫启用备份渠道，例如台湾金融机构改用传真确认交易；相关组织可考虑为关键邮件与协作流程预先准备替代通信手段，以应对类似长时间中断。

**标签**: `#Microsoft 365`, `#cloud outage`, `#Teams`, `#Outlook`, `#service reliability`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克因英伟达风波面临质询，其家族企业与其关系深厚](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC 调查发现，商务部长霍华德·卢特尼克之子执掌的 Cantor Fitzgerald 在 2025 年 9 月至 2026 年 3 月间将所报告的英伟达持股减少 49%（从 350 万股降至 178 万股），同期卢特尼克被指抵制打击涉嫌向中国走私英伟达芯片的公司，引发利益冲突质疑；目前并无证据表明存在不当行为。

rss · CNBC Finance · 11月13日 23:42

**「背景」** Cantor 前身为卢特尼克执掌的华尔街公司，现为英伟达安排数十亿美元融资并保持密切关系；据报道，卢特尼克在收到关于英伟达 CEO 黄仁勋与一名涉嫌中国间谍关系的机密情报警告后，多次抵制将新加坡公司 Megaspeed 列入出口管制“实体清单”，而财政部长贝森特周五称财政部、国防部和国务院数月来均支持此举。

**「影响」** 此事可能影响美国 AI 芯片对华出口管制政策的推进节奏，并使英伟达及其商业伙伴的融资与合规环境面临额外审查不确定性；总统特朗普仍表示对卢特尼克“完全信任”，相关指控尚未得到证实。

**标签**: `#nvidia`, `#howard-lutnick`, `#cantor-fitzgerald`, `#export-controls`, `#ethics-conflict`

---

<a id="item-finance-news-2"></a>
### [Chicago Fed&\#x27;s Goolsbee says central bank &\#x27;has definitely got work to do&\#x27; on inflation](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

Chicago Fed President Goolsbee said the central bank &\#x27;has work to do&\#x27; on inflation after October PPI rose 6.5% annually, with markets pricing a rate hike at the December FOMC meeting.

rss · CNBC Finance · 11月13日 14:22

**标签**: `#Federal Reserve`, `#inflation`, `#PPI`, `#interest rates`, `#monetary policy`

---