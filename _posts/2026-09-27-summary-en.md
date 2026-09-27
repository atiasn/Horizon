---
layout: default
title: "Horizon Summary: 2026-09-27 (EN)"
date: 2026-09-27
lang: en
---

> From 30 items, 8 important content pieces were selected

---

**Technology News**
1. [SemiAnalysis Teardown Examines Intel Panther Lake on the 18A Node](#item-tech-news-1) ⭐️ 8.0/10
2. [DeepSeek&\#x27;s DSec Paper Draws Attention for 380,000-Sandbox Scale Claim](#item-tech-news-2) ⭐️ 7.0/10
3. [Conversations XMPP Client Leaves Google Play and Becomes Free](#item-tech-news-3) ⭐️ 7.0/10
4. [US Appeals Court Upholds Pentagon Blacklisting of Anthropic from Military Contracts](#item-tech-news-4) ⭐️ 7.0/10
5. [Excel previews lists and arrays to put multiple values in one cell](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [10-year Treasury yield hits 5.23%, its highest since 2007](#item-finance-news-1) ⭐️ 7.0/10
2. [Hong Kong&\#x27;s SFC Settles with PwC for HK$1 Billion Over Evergrande Audit](#item-finance-news-2) ⭐️ 7.0/10
3. [Volkswagen Recalls 2.86 Million Vehicles Worldwide Over Steering Bolt Risk](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [SemiAnalysis Teardown Examines Intel Panther Lake on the 18A Node](https://newsletter.semianalysis.com/p/intel-panther-lake-teardown) ⭐️ 8.0/10

SemiAnalysis has published a free technical teardown of Intel&\#x27;s Panther Lake processor, examining the chip&\#x27;s die and packaging as built on Intel&\#x27;s 18A process node. The piece is presented as a SemiAnalysis STEEL teardown, authored by Adith Shankar, and is available on the SemiAnalysis newsletter site. It offers hardware-focused readers a die-level look at a chip built on 18A, a node the publication characterizes as strategically significant for the semiconductor industry. The available source material describes the teardown&\#x27;s scope but does not disclose its specific measurements or findings.

rss · Semianalysis · Sep 26, 13:36

**「Background」** Panther Lake is Intel&\#x27;s first client processor built on its leading-edge 18A process node, sold under the Core Ultra 300 branding with new Cougar Cove P-cores and Darkmont E-cores that Intel detailed at its Tech Tour 2025 event. The chip assembles one compute tile, one GPU tile, and one I/O tile atop a passive base tile using Intel&\#x27;s Foveros-S advanced packaging. Intel has said the compute die carries up to 18MB of shared L3 cache across the P- and E-cores and pairs with a 4 Xe-core graphics tile.

**「Why it matters」** For hardware evaluators and prospective foundry customers, this teardown arrives at a decisive moment: Intel plans to produce Panther Lake on 18A by year-end, making the chip the first large-scale demonstration of whether the node can deliver on its promises. The free die- and packaging-level analysis gives readers an independent basis for judging 18A&\#x27;s maturity, which is timely because Intel&\#x27;s foundry emphasis has reportedly shifted toward the newer 14A node for future competitiveness.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/intel-panther-lake-deep-dive-18a-compute-tile-cougar-cove-p-cores-darkmont-e-cores/">Intel Panther Lake Deep-Dive: 18 A Compute Tile With Cougar Cove...</a></li>
<li><a href="https://newsletter.semianalysis.com/p/intel-panther-lake-teardown">Intel Panther Lake Teardown , 18 A , BSPD, GAAFET, SemiAnalysis...</a></li>
<li><a href="https://www.tomshardware.com/pc-components/cpus/intel-takes-the-wraps-off-panther-lake-first-18a-client-processor-brings-the-best-of-lunar-lake-and-arrow-lake-together-in-one-package">Intel takes the wraps off Panther Lake — first 18 A client processor...</a></li>
<li><a href="https://www.monexa.ai/blog/intel-corporation-foundry-strategy-shift-impact-on-INTC-2025-07-02">Intel Corporation Foundry Strategy Shift: Financial Impact ... | Monexa</a></li>
<li><a href="https://www.koreajoongangdaily.com/business/chasing-chip-king-tsmc-samsung-and-intel-chart-courses-nanometers-apart/12161474">Chasing chip king TSMC, Samsung and Intel chart courses...</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#semiconductors`, `#chip-teardown`, `#process-nodes`, `#hardware`

---

<a id="item-tech-news-2"></a>
### [DeepSeek&\#x27;s DSec Paper Draws Attention for 380,000-Sandbox Scale Claim](https://arxiv.org/abs/2609.22978) ⭐️ 7.0/10

DeepSeek has posted an arXiv paper describing DeepSeek Elastic Compute \(DSec\), an infrastructure system for running large numbers of isolated compute sandboxes. A Hacker News commenter summarizing the paper cites 380,000 concurrent sandboxes running on 160 EPYC-based server nodes, but the supplied item does not include the paper&\#x27;s text, so the figure and the system&\#x27;s actual design cannot be independently verified here. The discussion drew moderate engagement and consisted largely of meta-commentary rather than technical analysis of the architecture.

hackernews · shenli3514 · Sep 26, 18:22 · [Discussion](https://news.ycombinator.com/item?id=49859112)

**「Sandbox infrastructure for AI agents」** Training AI agents that write and execute code requires fleets of isolated execution environments — sandboxes — where agent actions can be run safely and at scale, which is why labs have moved toward dedicated sandbox platforms instead of ad hoc cloud setups. DSec is DeepSeek&\#x27;s production system for this: it exposes FnCall, container, microVM, and full-VM sandbox backends behind a unified SDK, and outside coverage of the paper reports it can provision more than 5,000 sandboxes per second for agent training.

**「Scale claim would top commercial sandbox capacity if verified」** If the discussion&\#x27;s claim of 380,000 concurrent sandboxes running on 160 EPYC-based nodes \(about 2,375 per server\) is confirmed by the paper, it would exceed the publicly reported capacity of leading managed providers — Modal states it supports 100k+ concurrent sandboxes with creation throughput stress-tested to 1,000 sandboxes per second. For teams building sandboxed AI code execution, that suggests a modest self-hosted server footprint could replace managed sandbox spend, but the figure currently rests on a single reader comment about a paper whose contents were not available for verification, so it should be checked against the arXiv text before making procurement or architecture decisions.

**「Community Discussion」** The headline scale figure of 380,000 concurrent sandboxes on 160 EPYC nodes came from a single commenter&\#x27;s reading of the paper rather than independent verification, and other commenters only speculated about possible uses such as large agent swarms. Much of the thread instead debated DeepSeek&\#x27;s practice of listing very large author groups, with one commenter counting 131 authors on this paper and another suggesting the long author lists may be a deliberate strategy to obscure which employees competitors should try to poach.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2609.22978">[2609.22978] DeepSeek Elastic Compute ( DSec ): A Sandbox ...</a></li>
<li><a href="https://cryptobriefing.com/deepseek-dsec-ai-agent-training/">DeepSeek reveals innovative method for training AI agents with...</a></li>
<li><a href="https://modal.com/resources/best-microvm-sandboxes-ai-code-execution">Best microVM Sandboxes for AI Code Execution in 2026 | Modal Blog</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#elastic compute`, `#sandboxing`, `#DeepSeek`, `#distributed systems`

---

<a id="item-tech-news-3"></a>
### [Conversations XMPP Client Leaves Google Play and Becomes Free](https://gultsch.de/posts/breaking-up-with-google-play/) ⭐️ 7.0/10

Daniel Gultsch, developer of the open-source XMPP client Conversations, has announced that the app is leaving Google Play and is now free of charge. In his post, he attributes the move to Play Store fees, opaque review and verification processes, and the broader risks of depending on Google&\#x27;s platform. Android users of Conversations will need to obtain the app through channels other than Google Play going forward.

hackernews · ezst · Sep 26, 10:55 · [Discussion](https://news.ycombinator.com/item?id=49855315)

**「Background」** Conversations is a free and open-source instant messaging client for Android based on XMPP, written by Daniel Gultsch in 2014. Although the app has long been installable for free from the F-Droid catalog — whose maintainers asked Gultsch&\#x27;s permission because Conversations was a paid app on Google Play — he deliberately did not link to F-Droid from the official website, wanting to steer users toward the paid version. In August 2026 he had already run a two-day promotion making the app free of charge on Google Play, encouraging users of its forks to migrate and pointing people unfamiliar with F-Droid to it.

**「Impact」** Users who installed Conversations through Google Play will stop receiving updates there and must switch to sideloading or an alternative app store to keep using the now-free client. That switch carries new friction: as of March 2026, Google requires developer verification for sideloaded apps on certified Android devices, with a mandatory 24-hour wait in developer mode to bypass it, and from September 2026 all Android developers must register with Google even when distributing outside the Play Store. Since third-party stores are increasingly squeezed under these rules, users who rely on Conversations should confirm a working alternative installation channel before their Play-sourced copy falls out of date.

**「Community Discussion」** In the comments, pi-victor argued that the 15% fee is less of a problem than Google&\#x27;s poor developer support and slow app reviews, which he attributed to the store&\#x27;s effective monopoly. Other developers described matching frustrations: one reported spending a year unable to list a product because Play&\#x27;s phone-verification step cannot validate IVR numbers, and another warned that Google is progressively restricting app installs from outside its store.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Conversations_%28software%29">Conversations (software) - Wikipedia</a></li>
<li><a href="https://gultsch.de/posts/breaking-up-with-google-play/">Daniel Gultsch | Breaking Up with Google Play: Why Conversations Is Now Free</a></li>
<li><a href="https://gultsch.social/@daniel/117109809726763499">Daniel Gultsch: &quot;#Conversations_im remains free…&quot; - Mastodon</a></li>
<li><a href="https://unstore.io/discover/best-google-play-store-alternatives/">Best alternatives to Google Play Store in 2026 — Unstore</a></li>
<li><a href="https://www.linkedin.com/posts/jeff-hall-33b7871_google-will-require-developer-verification-activity-7366450854045896705-zMsC">Google to require developer verification for Android apps | LinkedIn</a></li>

</ul>
</details>

**Tags**: `#open-source`, `#android`, `#google-play`, `#app-store-policies`, `#xmpp`

---

<a id="item-tech-news-4"></a>
### [US Appeals Court Upholds Pentagon Blacklisting of Anthropic from Military Contracts](https://www.reuters.com/world/us-appeals-court-declines-block-pentagons-blacklisting-anthropic-2026-09-25/) ⭐️ 7.0/10

On September 25, a federal appeals court in Washington, DC reportedly ruled 2-1 to uphold the Pentagon&\#x27;s blacklisting of Anthropic as a national security supply-chain risk, barring the AI company from US military contracts. According to the Reuters-sourced report, the majority held the Pentagon&\#x27;s concerns reasonable in light of Anthropic&\#x27;s refusal to allow its AI to be used for autonomous weapons and mass surveillance. Anthropic said it disagrees with the ruling and is considering asking the full appeals court to rehear the case; the report adds that a San Francisco federal judge had earlier overturned the listing under a different law and blocked broader government restrictions on the company. The item is a brief secondhand summary and does not name the case, statute, or judges involved.

telegram · zaihuapd · Sep 26, 05:19

**「Background」** The dispute stems from Anthropic&\#x27;s usage restrictions, which bar its AI from being used for autonomous weapons and mass surveillance, and it began when the Pentagon blacklisted the company as a national security supply-chain risk after Anthropic declined to permit such military applications. Before this appellate ruling, Anthropic had won the earlier round in court: a federal district judge in San Francisco had overturned the designation under a different statute and blocked the government from imposing broader restrictions on the company.

**「Why it matters」** As reported, the ruling leaves Anthropic ineligible for US military contracts unless the full appeals court grants a rehearing or a higher court intervenes, and Anthropic&\#x27;s stated next step is to seek such a full-court \(en banc\) review. The 2-1 split, combined with a conflicting district-court decision under a different statute, leaves the legal footing unsettled for AI vendors whose usage policies restrict military applications such as autonomous weapons and mass surveillance.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic%E2%80%93United_States_Department_of_Defense_dispute">Anthropic–United States Department of Defense dispute - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#Anthropic`, `#military AI`, `#AI safety`, `#regulation`

---

<a id="item-tech-news-5"></a>
### [Excel previews lists and arrays to put multiple values in one cell](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/put-multiple-values-in-one-cell-with-lists-and-arrays-in-excel/4559395) ⭐️ 7.0/10

Microsoft is previewing lists and in-cell arrays in Excel, letting a single cell hold multiple values for what the company describes as the first time in the product&\#x27;s roughly 40-year history. The features are rolling out to Beta channel Insiders on Windows and Mac: users can enter comma- or semicolon-separated items with Ctrl+J or via Insert &gt; List, then filter and calculate on the individual values inside a cell. Four companion functions — FLATTEN, HAS, HASANY, and HASALL — are being added for working with the new arrays. All of this is preview functionality whose behavior may change before general release, and Microsoft advises not using it in important workbooks for now.

telegram · zaihuapd · Sep 26, 16:26

**「Background」** Throughout its roughly 40-year history, Excel has permitted only one value per cell, which is why multi-item data traditionally had to be spread across a range of separate cells; the new lists and in-cell arrays remove that long-standing constraint. The preview is tied to a new compatibility version 3 in the Beta channel, which Microsoft announced on September 24, 2026.

**「Beta-channel testing, with a caution on real work」** Users on the Windows and Mac Beta channel can start experimenting now—entering comma- or semicolon-separated items in a single cell via Ctrl+J or Insert &gt; List, then filtering and calculating on individual items with the new FLATTEN, HAS, HASANY, and HASALL functions. Because these are preview features whose behavior may change before general availability, Microsoft explicitly advises against using them in important workbooks; any file that adopts in-cell lists should be treated as experimental until the capability ships broadly, since it may not behave the same in non-Beta versions of Excel.

<details><summary>References</summary>
<ul>
<li><a href="https://techcommunity.microsoft.com/blog/Microsoft365InsiderBlog/put-multiple-values-in-one-cell-with-lists-and-arrays-in-excel/4559395">Put multiple values in one cell with lists and arrays in Excel | Microsoft Community Hub</a></li>
<li><a href="https://windowsforum.com/news/excel-beta-adds-lists-and-nested-arrays-with-compatibility-version-3.445888/?amp=1">Excel Beta Adds Lists and Nested Arrays With Compatibility Version 3 | Windows Forum</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/microsoft365insiderblog/put-multiple-values-in-one-cell-with-lists-and-arrays-in-excel/4559395">Put multiple values in one cell with lists and arrays in Excel</a></li>
<li><a href="https://www.geeky-gadgets.com/multiple-values-one-excel-cell/">Excel Multiple Values in One Cell : Microsoft 365... - Geeky Gadgets</a></li>
<li><a href="https://www.xelplus.com/excel-lists-in-cells/">Excel Lists in Cells : Put Multiple Values in One Cell</a></li>

</ul>
</details>

**Tags**: `#Excel`, `#Microsoft-365`, `#spreadsheets`, `#arrays`, `#data-analysis`

---

## Financial News

<a id="item-finance-news-1"></a>
### [10-year Treasury yield hits 5.23%, its highest since 2007](https://www.cnbc.com/2026/09/26/10-year-treasury-yield-is-at-its-highest-in-19-years-how-we-got-here.html) ⭐️ 7.0/10

The 10-year Treasury yield — the benchmark U.S. government borrowing rate that influences mortgages — leapt to 5.23% on Friday, its highest level since 2007 and up from just below 4.8% earlier this month. Analysts point to stubborn inflation, rising expectations of a Federal Reserve rate hike, and heavy government and AI-related bond issuance as the drivers.

rss · CNBC Finance · Sep 26, 13:30

**「Background」** Bond prices and yields move in opposite directions, so a flood of new debt pushes yields upward, and the U.S. government is selling debt to cover a large deficit while companies borrow heavily to fund artificial intelligence infrastructure. Macquarie strategist Thierry Wizman argues this year&\#x27;s surge stems more from that bond supply than from inflation, and he expects issuance to stay elevated into next year, meaning yields could go higher.

**「Impact」** Higher yields raise mortgage and corporate borrowing costs and can weigh on stocks by making bonds more attractive to income-seeking investors.

**Tags**: `#Treasury yields`, `#Federal Reserve`, `#inflation`, `#bond issuance`, `#AI capex`

---

<a id="item-finance-news-2"></a>
### [Hong Kong&\#x27;s SFC Settles with PwC for HK$1 Billion Over Evergrande Audit](https://wallstreetcn.com/articles/3782573) ⭐️ 7.0/10

Hong Kong&\#x27;s Securities and Futures Commission reached a HK$1 billion settlement with PwC Hong Kong over audit failures at China Evergrande, with the firm denying liability but agreeing to pay the sum to compensate affected independent minority shareholders. Evergrande&\#x27;s liquidators have filed in court to overturn the deal, with a High Court ruling expected around late October.

telegram · zaihuapd · Sep 26, 07:18

**「Background」** China Evergrande, once China&\#x27;s largest property developer, collapsed under massive debt and is being liquidated in Hong Kong, where PwC Hong Kong had served as its auditor. The HK$1 billion payment structure is a novel approach for Hong Kong, and the liquidators filed their court challenge to the settlement on June 12, according to court documents reported by the Daily Economic News.

**「Impact」** Because the payment comes from PwC Hong Kong rather than Evergrande&\#x27;s assets, it does not change the priority of creditors&\#x27; claims, while minority shareholders would receive the compensation only if the settlement survives the court challenge.

<details><summary>References</summary>
<ul>
<li><a href="https://wallstreetcn.com/articles/3782573">wallstreetcn.com/articles/3782573</a></li>

</ul>
</details>

**Tags**: `#Evergrande`, `#PwC`, `#audit regulation`, `#SFC settlement`, `#liquidation litigation`

---

<a id="item-finance-news-3"></a>
### [Volkswagen Recalls 2.86 Million Vehicles Worldwide Over Steering Bolt Risk](https://www.ithome.com/1/007/382.htm) ⭐️ 7.0/10

Volkswagen has confirmed a global preventive recall of about 2.86 million vehicles—roughly 2.16 million VW-brand cars and nearly 700,000 Audi Q3s, including around 960,000 in Germany—because a steering fastening bolt may corrode and break, potentially causing loss of steering in extreme cases. The company describes the recall as a precautionary measure and says no related injuries have been reported so far.

telegram · zaihuapd · Sep 26, 10:01

**「Background」** Germany&\#x27;s motor transport authority \(KBA\) flagged that corrosion could cause the steering bolt to break and lead to steering failure, and the affected models include the Golf, Tiguan, Touran, and Audi Q3.

**「What it means for owners」** Owners of about 2.86 million Volkswagen-brand and Audi Q3 vehicles — roughly 960,000 of them in Germany — will need dealer inspections or steering-bolt replacements, as moisture and road-salt corrosion could in extreme cases cause loss of steering control, according to Germany&\#x27;s Federal Motor Transport Authority \(KBA\).

<details><summary>References</summary>
<ul>
<li><a href="https://www.instagram.com/moretify/">好用的分享都在這裡 Moretify Sdn. Bhd. 201701037954 (1252125-V)</a></li>
<li><a href="https://www.guancha.cn/qiche/2026_09_26_902327.shtml">转 向 螺 栓 可能 腐 蚀 断 裂 ， 大 众 、 奥 迪 全 球 召 回 约 286 万 辆 汽 车</a></li>
<li><a href="https://autos.yahoo.com/safety-and-recalls/articles/volkswagen-audi-recall-2-86-183623200.html">Volkswagen, Audi recall 2.86 million vehicles over steering screw</a></li>
<li><a href="https://ground.news/article/volkswagen-to-recall-286-million-vw-audi-models-over-potential-steering-problem_258437">Volkswagen to Recall 2.86 Million VW, Audi Models over Potential Steering Problem</a></li>
<li><a href="https://www.euronews.com/2026/09/25/over-28-million-audi-and-volkswagen-vehicles-face-recall-worldwide">Over 2.8 million Audi and Volkswagen vehicles face recall worldwide | Euronews</a></li>

</ul>
</details>

**Tags**: `#automotive recall`, `#Volkswagen`, `#Audi`, `#product safety`, `#consumer impact`

---