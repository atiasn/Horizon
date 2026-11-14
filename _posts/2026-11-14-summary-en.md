---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 39 items, 6 important content pieces were selected

---

**Technology News**
1. [FAA orders nationwide ground stop amid ATC telecom outage](#item-tech-news-1) ⭐️ 8.0/10
2. [Training a ~1T-Parameter MoE on TorchTitan at 1,300 tokens/s per GH200 GPU](#item-tech-news-2) ⭐️ 8.0/10
3. [Python 早期贡献者 Tim Peters 去世，享年 74 岁](#item-tech-news-3) ⭐️ 7.0/10
4. [Microsoft Outlook, Teams Suffer Global Outage Lasting Over 12 Hours](#item-tech-news-4) ⭐️ 7.0/10

**Financial News**
1. [Questions raised over Lutnick ties to Nvidia as his family&\#x27;s firm cut its stake](#item-finance-news-1) ⭐️ 8.0/10
2. [Chicago Fed&\#x27;s Goolsbee says central bank &\#x27;has definitely got work to do&\#x27; on inflation](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [FAA orders nationwide ground stop amid ATC telecom outage](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 8.0/10

The FAA issued a nationwide ground stop for departing flights on November 13, 2026, amid a reported outage of an air-traffic-control telecommunications network. According to reporting cited in the discussion, the outage affects a network overseen by L3Harris Technologies that handles the radio frequencies controllers use to communicate with pilots; it was not immediately clear whether radar feeds were also affected. Commenters noted visible effects at airports such as LAX, with no departures since mid-morning PST and later flights showing delayed or canceled, and reported the ground stop was later lifted. Officials cautioned the underlying outage may not be resolved quickly.

hackernews · zulln · Nov 13, 21:05 · [Discussion](https://news.ycombinator.com/item?id=50489641)

**「Background」** According to the FAA&\#x27;s own statement, the ground stop was triggered by communication issues affecting multiple Air Route Traffic Control Centers, and community-cited reporting indicates the affected network is an L3Harris-run telecom system carrying the radio frequencies controllers use to talk to pilots. Nationwide ground stops are extremely rare; the last one occurred in January 2023 after a failure of the pilot NOTAM notice system, which is why this event drew immediate attention. The stop originated at Chicago&\#x27;s O&\#x27;Hare and Midway airports before being extended nationwide.

**「Impact on travelers」** Travelers should expect continued disruption even after the ground stop was lifted after more than four hours, as delays and cancellations ripple through the system. Denver alone recorded 640 delays and 369 cancellations, and passengers should check airline status directly before heading to airports.

**「Community discussion」** Commenters found official information sparse, with much of the early reporting traced to a Cabinet secretary&\#x27;s social media post, and one user speculated the outage might be connected to the FAA&\#x27;s just-announced nationwide rollout of its SMART AI air-traffic tool — an unverified link. Others tracked real-time effects, noting overloaded airport status pages and a report that the ground stop had been lifted while an official warned of a possibly extended outage.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://www.faa.gov/newsroom/faa-statement-nationwide-ground-stop">FAA Statement on Nationwide Ground Stop | Federal Aviation ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.cpr.org/2026/11/13/flights-ground-stop-faa-dia/">UPDATE: National ground stop lifted after more than 4 hours ...</a></li>

</ul>
</details>

**Tags**: `#air-traffic-control`, `#infrastructure`, `#outage`, `#FAA`, `#telecom`

---

<a id="item-tech-news-2"></a>
### [Training a ~1T-Parameter MoE on TorchTitan at 1,300 tokens/s per GH200 GPU](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

An engineering team, working with the TorchTitan and PyTorch maintainers, scaled TorchTitan to train a roughly 1-trillion-parameter mixture-of-experts model on 384 NVIDIA GH200 GPUs in the JUPITER supercomputer, reaching about 1,300 tokens/s per GPU — a 14X improvement over their starting point. The setup uses 384-way FSDP plus 4-way expert parallelism kept within a node, deliberately avoiding pipeline parallelism because its long step times slow failure diagnosis at scale. Key gains came from full activation checkpointing, offloading activations and optimizer state to the Grace CPU over the 900 GB/s C2C link, switching from Adam to Muon, sharding experts by whole expert with FlexShard so Newton-Schulz runs locally, cost-based sequence packing, bf16 gradient transport with local fp32 accumulation, and FP8 expert all-gather. A PyTorch caching allocator issue that caused OOM-like retries at ~70% HBM utilization was fixed via FSDP2&\#x27;s unshard\_async\_op flag, cutting peak reserved memory by 13.5 GiB and adding 21% throughput.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「Background」** TorchTitan is PyTorch&\#x27;s reference large-scale training framework, and training a model that does not fit on a single GPU requires choosing a sharding strategy: Pipeline Parallelism splits layers across GPUs, FSDP \(Fully Sharded Data Parallelism\) gives each GPU a slice of every weight and gathers what it needs just in time, and Expert Parallelism gives each GPU ownership of a subset of a mixture-of-experts model&\#x27;s experts. The setup here runs on GH200 GPUs in the JUPITER supercomputer, where the Grace CPU sits alongside the GPU on a fast 900 GB/s link but nodes are connected by InfiniBand at roughly 25 GB/s per GPU, making inter-node communication the dominant constraint that the authors&\#x27; optimizations target.

**「Why It Matters」** The writeup demonstrates that a shared, publicly funded Hopper-generation machine with user-level access and no root privileges can host frontier-scale training, provided inter-node bandwidth constraints are respected — relevant to practitioners planning large MoE runs on constrained clusters. The authors&\#x27; contributions, including the GPU-side Newton-Schulz fix and the unshard\_async\_op flag that is on its way to becoming a public PyTorch API, are landing in TorchTitan. One open question remains: group-limited routing balances expert load \(+7%\) but early runs suggest it may hurt training quality.

**Tags**: `#distributed-training`, `#mixture-of-experts`, `#pytorch`, `#FSDP`, `#GPU-scaling`

---

<a id="item-tech-news-3"></a>
### [Python 早期贡献者 Tim Peters 去世，享年 74 岁](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Python 的创造者 Guido van Rossum 宣布，早期贡献者 Tim Peters 去世，享年 74 岁。Peters 是 Python 的第二位真实用户，编写了 Timsort 排序算法——自 Python 2.3 起成为内置列表排序的标准算法——以及《Python 之禅》（PEP 20）。他还曾在 Python 软件基金会董事会任职 13 年。

telegram · zaihuapd · Nov 13, 09:55

**「Who Tim Peters Was」** Tim Peters was one of Python&\#x27;s earliest and most influential contributors: he wrote the 19 aphorisms of the Zen of Python and posted them to the Python mailing list in 1999, leaving the 20th principle open &quot;for Guido to fill in,&quot; and he created Timsort, the sorting algorithm behind Python&\#x27;s built-in sorted\(\) and list.sort\(\). According to Guido van Rossum&\#x27;s memorial post on the Python core development forum, Peters died on July 15, 2026, and van Rossum described his influence on the language as hard to overestimate.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028">In Memoriam: Tim Peters 1952–2026 - Core Development...</a></li>

</ul>
</details>

**Tags**: `#python`, `#tim-peters`, `#timsort`, `#open-source`, `#community-news`

---

<a id="item-tech-news-4"></a>
### [Microsoft Outlook, Teams Suffer Global Outage Lasting Over 12 Hours](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

Microsoft&\#x27;s Outlook, Teams, and Copilot remained down for more than 12 hours on November 13, disrupting communications for businesses and governments worldwide, according to Reuters. The company attributed the outage to server problems, said it found no evidence of malicious activity, and reported that it had expanded remediation efforts and was seeing signs of recovery. Affected organizations included government agencies in Australia, Japan, and the United States, Euronext&\#x27;s email service, and a Taiwanese financial institution that reverted to fax to confirm trades. Microsoft said this was the second Microsoft 365 service disruption this year.

telegram · zaihuapd · Nov 13, 12:21

**「Background」** Outlook, Teams, and Copilot are core Microsoft 365 cloud services that many companies and government agencies rely on for email, messaging, and AI-assisted work, so a failure in Microsoft&\#x27;s server infrastructure cascades directly into those organizations&\#x27; daily operations. The source notes this is the second Microsoft 365 outage this year, underlining the recurring single-vendor dependency risk in cloud-based communication.

**「Contingency Plans for Critical Workflows」** Organizations relying on Microsoft 365 for time-critical operations should note the reported fallback behavior: the affected Taiwanese financial institution switched to fax for trade confirmation when email went down, a concrete example of why outage contingency channels matter. The root cause had not been fully detailed beyond server issues as of the report, so the risk of recurrence remains unresolved.

**Tags**: `#Microsoft 365`, `#cloud outage`, `#Teams`, `#Outlook`, `#service reliability`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Questions raised over Lutnick ties to Nvidia as his family&\#x27;s firm cut its stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC reports that Commerce Secretary Howard Lutnick&\#x27;s family firm Cantor Fitzgerald, now run by his sons, cut its reported Nvidia holdings by 49% — from 3.5 million shares worth $652 million in September 2025 to 1.78 million shares worth $310 million by March 2026 — even as Lutnick resisted a crackdown on a company suspected of smuggling Nvidia chips to China, per Axios. CNBC found no evidence of wrongdoing, and Cantor says the filings reflect routine client swap transactions rather than material proprietary bets.

rss · CNBC Finance · Nov 13, 23:42

**「Background」** Lutnick formerly led Cantor Fitzgerald before becoming commerce secretary in February 2025; the Commerce Department controls the &\#x27;entity list&\#x27; of restricted companies, and Axios reported Nov. 11 that Lutnick repeatedly resisted adding Singapore-based Megaspeed to it despite intelligence concerns. Cantor also continued arranging billions in financing for Nvidia business partners and hosted CEO Jensen Huang for investor meetings in late September.

**「Impact」** The scrutiny could complicate U.S. export-control policy toward Nvidia&\#x27;s AI chips and China, with Treasury Secretary Scott Bessent saying other agencies backed the Megaspeed restriction for months while President Trump says he retains &\#x27;complete confidence&\#x27; in Lutnick.

**Tags**: `#nvidia`, `#howard-lutnick`, `#cantor-fitzgerald`, `#export-controls`, `#ethics-conflict`

---

<a id="item-finance-news-2"></a>
### [Chicago Fed&\#x27;s Goolsbee says central bank &\#x27;has definitely got work to do&\#x27; on inflation](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

Chicago Fed President Goolsbee said the central bank &\#x27;has work to do&\#x27; on inflation after October PPI rose 6.5% annually, with markets pricing a rate hike at the December FOMC meeting.

rss · CNBC Finance · Nov 13, 14:22

**Tags**: `#Federal Reserve`, `#inflation`, `#PPI`, `#interest rates`, `#monetary policy`

---