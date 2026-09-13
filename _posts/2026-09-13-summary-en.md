---
layout: default
title: "Horizon Summary: 2026-09-13 (EN)"
date: 2026-09-13
lang: en
---

> From 26 items, 6 important content pieces were selected

---

**Technology News**
1. [We must pace the frontier](#item-tech-news-1) ⭐️ 8.0/10
2. [Reverse-Engineering Apple&\#x27;s Undocumented Neural Engine](#item-tech-news-2) ⭐️ 8.0/10
3. [The Economist: Nvidia Acts as the Central Bank of the AI Economy](#item-tech-news-3) ⭐️ 7.0/10
4. [Google Rewrites Search Result URLs Through goto Redirect Links](#item-tech-news-4) ⭐️ 7.0/10
5. [25 Fields Medalists Warn of Severe AI Misalignment in Mathematics](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [Inflation outpaces wage growth again, squeezing U.S. paychecks](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [We must pace the frontier](https://darioamodei.com/post/we-must-pace-the-frontier) ⭐️ 8.0/10

Dario Amodei&\#x27;s essay calling to &\#x27;pace the frontier&\#x27; of AI development sparked extensive debate on Hacker News about alignment, safety motivations, and whether such proposals reflect genuine caution or anti-competitive strategy.

hackernews · apsec112 · Sep 12, 14:10 · [Discussion](https://news.ycombinator.com/item?id=49672510)

**Tags**: `#AI policy`, `#AI safety`, `#Anthropic`, `#frontier models`, `#industry debate`

---

<a id="item-tech-news-2"></a>
### [Reverse-Engineering Apple&\#x27;s Undocumented Neural Engine](https://eiln.github.io/posts/ane.html) ⭐️ 8.0/10

A detailed technical write-up on eiln.github.io presents a retrospective reverse-engineering of Apple&\#x27;s Neural Engine \(ANE\), a hardware accelerator that Apple has never publicly documented in depth. The analysis dissects the ANE&\#x27;s architecture and its surrounding data pipeline, and the author even discovered and documented a DMA-related bug in the hardware during the process. A key finding highlighted by readers is that the ANE and its data pipeline were designed around convolutional neural networks \(CNNs\) rather than transformers, which helps explain why the accelerator has been less broadly impactful than its specifications might suggest. The work drew substantial attention on Hacker News \(223 points, 31 comments\), with commenters connecting it to separate reverse-engineering efforts on newer ANE generations such as the M4, and noting that Apple continues to develop the ANE in upcoming chips. The analysis is valuable primarily because it fills a documentation gap in an area where Apple provides almost no architectural detail, though it covers prior-generation hardware rather than introducing new tooling.

hackernews · zdw · Sep 12, 07:54 · [Discussion](https://news.ycombinator.com/item?id=49670032)

**「Background」** Apple&\#x27;s Neural Engine \(ANE\) is a dedicated on-chip accelerator for neural network inference that Apple first added to its A-series chips in 2017, predating the recent surge of mainstream AI interest. Unlike the CPU and GPU, the ANE has almost no official public documentation, and Apple&\#x27;s decade-old Core ML framework has historically been the main supported path for using it. Because of this opacity, independent researchers have had to reverse-engineer the hardware and its kernel interface, producing artifacts such as a reverse-engineered Linux driver for the ANE developed as part of the Asahi Linux project and subsequent analyses of newer generations like the M4&\#x27;s ANE.

**「Impact」** Developers and researchers working on on-device machine learning gain a rare architectural understanding of the ANE, clarifying why workloads like transformers may underperform there relative to CNNs and informing decisions about which Apple accelerators to target. Apple&\#x27;s forthcoming Core AI framework, which spans CPU, GPU, and Neural Engine beyond the decade-old Core ML&\#x27;s PyTorch and TensorFlow workloads, may change how developers leverage these findings in practice.

**「Community Discussion」** Commenters praised the analysis as genuinely high-quality work, with one noting the author even found a hardware bug in the ANE&\#x27;s DMA behavior. Discussion centered on how the findings relate to newer silicon: one commenter asked whether the M4-generation ANE exposes new capabilities or is merely a faster iteration, and cautioned that the article&\#x27;s introduction appears to conflate the ANE with the Neural Accelerators \(NAX\) in M5-and-later GPUs, which are described as very different things. Others contextualized the work, pointing out that Apple added the Neural Engine to A-series chips in 2017, well before the current AI boom, and one reader said the CNN-versus-transformer design insight resolved a long-standing question about why the ANE has been less impactful than expected.

<details><summary>References</summary>
<ul>
<li><a href="https://archive.is/MmAGT">Retrospectively Reverse-Engineering Apple&#x27;s Neural Engine | Eileen Yo…</a></li>
<li><a href="https://maderix.substack.com/p/inside-the-m4-apple-neural-engine">Inside the M4 Apple Neural Engine, Part 1: Reverse Engineering</a></li>
<li><a href="https://pith.science/paper/2606.22283">Apple Neural Engine: Architecture, Programming, and Performance · Pith Review</a></li>

</ul>
</details>

**Tags**: `#apple-silicon`, `#neural-engine`, `#hardware-reverse-engineering`, `#accelerators`, `#machine-learning`

---

<a id="item-tech-news-3"></a>
### [The Economist: Nvidia Acts as the Central Bank of the AI Economy](https://www.economist.com/interactive/briefing/2026/09/03/nvidia-is-the-central-bank-of-ai) ⭐️ 7.0/10

The Economist has published an interactive briefing arguing that Nvidia now functions like a central bank for the AI economy, with the company&\#x27;s capital allocation and equity value shaping investment flows across the entire industry. The piece highlights Nvidia&\#x27;s more than $500 billion in investments and commitments, a scale of capital deployment the article frames as comparable in monetary influence to central bank easing, alongside the company&\#x27;s roughly $5.4 trillion market capitalization. The argument matters because it positions a single private company as a systemic node: its spending decisions, customer financing, and stock valuation effectively set the pace and funding conditions for AI development industry-wide. The analysis also raises questions about systemic risk and the sustainability of current AI market dynamics, since so much of the ecosystem&\#x27;s capital circulation depends on Nvidia&\#x27;s continued growth and generosity. The framing is analytical commentary on industry economics rather than a report of a specific technical or product development.

hackernews · tolugenius · Sep 12, 15:08 · [Discussion](https://news.ycombinator.com/item?id=49673098)

**「Background」** The Economist&\#x27;s &\#x27;central bank of AI&\#x27; framing borrows from monetary policy: just as a central bank influences an economy by expanding its balance sheet and directing credit, Nvidia now shapes the AI economy through its market value \(around $5.4 trillion\) and its more than $500 billion in investments and commitments to AI infrastructure, customers, and partners. This has drawn comparisons to &\#x27;circular financing&\#x27; concerns — the worry that Nvidia effectively funds the customers who buy its chips, propping up demand for its own products — though Morgan Stanley has argued the scale of Nvidia&\#x27;s investment may ease rather than worsen those concerns. Understanding the piece requires knowing that Nvidia&\#x27;s GPUs are the dominant compute platform for training and running AI models, giving the company pricing power and a pivotal position in capital flows across the AI industry.

**「Why It Matters」** If Nvidia&\#x27;s $500+ billion in investments and commitments function like monetary easing for the AI economy, a slowdown in its spending or equity value could transmit shocks across AI startups, hyperscalers, and suppliers that depend on that capital flow. This systemic role amplifies concerns already raised about credit-driven AI capex, with hyperscaler 2026 guidance reaching roughly $750 billion and analysts warning of bubble and systemic risks if AI compute financing structures proliferate.

**「Community Discussion」** On Hacker News, commenters engaged substantively with the monetary analogy: one noted that Nvidia&\#x27;s $500+ billion in investments and commitments exceeds any Federal Reserve easing over a comparable period, calling Nvidia a major source of money creation, while also observing there is no evidence Nvidia has borrowed against its stock to back those commitments. Others debated the broader implications, with one commenter reflecting on corporations taking on roles traditionally reserved for public institutions, and another arguing that cracks are appearing in the AI market, interpreting public calls from OpenAI and Anthropic for slower AI research as attempts to coordinate a slowdown and manage burn rates. A separate concern raised was Nvidia&\#x27;s apparent deprioritization of the gaming market, noting the company removed standalone gaming revenue reporting from its financial reports, and skepticism that AMD or Intel could step in if Nvidia exited that segment.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/jensen-huang-mocks-nvidia-circular-141958748.html">Jensen Huang Mocks Nvidia ‘ Circular Financing’ Fears: ‘If That Is...</a></li>
<li><a href="https://www.bbc.com/business">BBC Business | Economy , Tech, AI , Work, Personal Finance, Market...</a></li>
<li><a href="https://seekingalpha.com/article/4937644-macro-insights-unstoppable-1t-ai-capex-meets-nvidia-compute-abs-defense-amid-surging-bond-yields">Macro Insights: Navigating AI Capex Boom, Growing Bubble Risks, And Rising Yield Pressures | Seeking Alpha</a></li>

</ul>
</details>

**Tags**: `#nvidia`, `#ai-industry`, `#economics`, `#semiconductors`, `#market-analysis`

---

<a id="item-tech-news-4"></a>
### [Google Rewrites Search Result URLs Through goto Redirect Links](https://www.autom.dev/blog/google-search-goto-links) ⭐️ 7.0/10

Google has replaced direct destination URLs in its search results with redirect links of the form www.google.com/goto?url=&lt;opaque base64 string&gt;, according to an analysis published on autom.dev. The author of the analysis found that the base64 payload appears to encode a simple protobuf structure, with a long byte string in field 2 that presumably identifies the target URL. The change is framed as an anti-scraping measure, since the opaque redirect URLs make it harder for automated tools to extract destination links directly from search result pages. The redirects also appear to introduce a perceivable delay when loading, which affects ordinary users clicking through results. The development has drawn significant attention, with community discussion focusing on how such URL obfuscation increases click tracking through Google&\#x27;s servers, degrades transparency for a no-JavaScript web, and raises the cost of programmatic access to search results.

hackernews · 1e1a · Sep 12, 03:14 · [Discussion](https://news.ycombinator.com/item?id=49668386)

**「Background」** Historically, Google search result pages exposed the destination site&\#x27;s own URL directly in each link&\#x27;s href, so browsers, rank trackers, and automated agents could extract a clean list of destinations without rendering JavaScript. Google has progressively moved away from this transparency: it previously introduced URL obfuscation in its own browser and on search result pages, and roughly a year before this change it stopped serving search results without JavaScript. The new goto redirect mechanism replaces direct links with URLs of the form www.google.com/goto?url=&lt;opaque base64 string&gt;, where the base64 data appears to be a basic protobuf structure, and reportedly uses a Tink-encrypted protobuf blob that correlates with the destination URL&\#x27;s length but cannot be decrypted without Google&\#x27;s private key.

**「Impact」** Developers and services that rely on scraping or programmatically parsing Google search results face additional obstacles, as destination URLs can no longer be read directly from result pages and must be resolved through Google&\#x27;s redirect endpoint. Users and privacy-conscious tooling also lose direct link transparency, since every click now passes through Google&\#x27;s servers.

**「Community Discussion」** Commenters were largely critical, viewing the change as a continuation of a long trend away from a link-transparent, no-JavaScript web; one user noted Google search had already stopped working without JavaScript about a year earlier and argued that well-resourced scrapers can still bypass these obstacles while smaller users are locked out. Another commenter recalled a Google interview from roughly 20 years ago in which URL rewriting through Google&\#x27;s servers was posed as a click-tracking challenge, suggesting the technique has long been on the company&\#x27;s roadmap, while others expressed general distrust of Google search and mentioned alternatives such as Yandex.

<details><summary>References</summary>
<ul>
<li><a href="https://www.autom.dev/blog/google-search-goto-links">google.com/goto: Google&#x27;s anti-scraping update</a></li>
<li><a href="https://elysiancrest.com/insights/ai-development/google-search-scraping-crackdown-2026">Google&#x27;s Scraping Crackdown: goto Redirects &amp; What Breaks</a></li>
<li><a href="https://byteiota.com/google-com-goto-googles-anti-scraping-move-explained/">google.com/goto: Google’s Anti-Scraping Move Explained</a></li>

</ul>
</details>

**Tags**: `#google-search`, `#web-scraping`, `#anti-scraping`, `#url-rewriting`, `#open-web`

---

<a id="item-tech-news-5"></a>
### [25 Fields Medalists Warn of Severe AI Misalignment in Mathematics](https://www.reddit.com/r/MachineLearning/comments/1wea1t7/a_severe_misalignment_of_ai_in_mathematics/) ⭐️ 7.0/10

A joint declaration reportedly signed by 25 Fields Medalists, including Terence Tao and Yu Deng, warns that the rapid use of AI to solve mathematical problems could lead to a &\#x27;severe misalignment&\#x27; between AI development goals and the goals of mathematical research. The statement acknowledges that large language models&\#x27; ability to tackle significant mathematical problems has improved substantially in recent years, but argues that using mathematical problem-solving as an AI capability benchmark may damage mathematical research and the academic ecosystem. According to the declaration, the core of mathematical research lies in forming conceptual understanding and new insights rather than merely obtaining answers, and AI&\#x27;s mass production of results could compress the time available for verification, communication, and citing prior work, while raising issues around attribution and plagiarism. The signatories note that AI could also improve research efficiency, with its ultimate impact depending on how the technology is used. The declaration was drafted by mathematicians and is primarily addressed to the mathematical community, though a Reddit discussion on r/MachineLearning raises the question of whether its concerns also apply to the AI/ML community itself.

reddit · r/MachineLearning · /u/hihey54 · Sep 12, 11:23

**「Background」** The Fields Medal is widely regarded as the highest honor in mathematics, awarded to a small number of mathematicians, so a joint statement signed by 25 of its recipients—including Terence Tao—represents an unusually broad cross-section of the field&\#x27;s most decorated living researchers. The declaration, titled &quot;A Severe Misalignment of AI in Mathematics&quot; and published on mathandai.org, responds to the recent surge in large language models being used to solve famous mathematical problems, a trend reportedly accelerated by high-profile announcements such as OpenAI&\#x27;s claimed work on the Navier–Stokes problem. The core concern is that treating problem-solving as an AI benchmark conflicts with how mathematical research actually values conceptual understanding and new insight, rather than answers alone.

**「Impact」** Mathematicians and research institutions may need to establish clearer norms around AI-assisted proofs, verification, attribution, and citation before AI-generated results reshape publication and credit practices in the field. The extent of any concrete policy changes remains uncertain, as the declaration&\#x27;s specific recommendations are not detailed in the available source.

<details><summary>References</summary>
<ul>
<li><a href="https://officechai.com/ai/25-fields-medal-winners-including-terence-tao-sign-declaration-saying-rapid-ai-proofs-are-harming-math-in-severe-misalignment/">25 Fields Medal Winners Including Terence Tao Sign ...</a></li>
<li><a href="https://www.explainx.ai/blog/fields-medalists-ai-math-declaration-openai-2026">Fields Medalists vs OpenAI: The Math AI Declaration (2026 ...</a></li>
<li><a href="https://sigmawire.net/fields-medalists-ai-declaration-mathematics">Fields Medalists AI Declaration: 25 Top Mathematicians Warn</a></li>

</ul>
</details>

**Tags**: `#AI alignment`, `#mathematics`, `#AI in research`, `#research integrity`, `#community discussion`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Inflation outpaces wage growth again, squeezing U.S. paychecks](https://www.cnbc.com/2026/09/12/inflation-is-outpacing-wage-growth-again-squeezing-americans-paychecks.html) ⭐️ 7.0/10

New Bureau of Labor Statistics data released Friday show U.S. consumer prices rose 3.4% in August from a year earlier while average hourly earnings grew just 3.1%, meaning real hourly earnings fell 0.3% year over year and workers&\#x27; purchasing power is shrinking again.

rss · CNBC Finance · Sep 12, 12:49

**「Why it matters now」** From May 2023 to about April of this year, wage growth had generally outpaced inflation, but that progress reversed this spring as energy costs jumped, with gasoline prices up 3.9% in August alone amid fuel supply disruptions tied to the wars in Iran and Ukraine.

**「The ripple effects」** Because consumer spending drives roughly two-thirds of U.S. economic activity, households are already shifting toward discount and warehouse stores like Costco, Aldi, and Walmart across much of the income spectrum, according to YouGov polling and Navy Federal Credit Union&\#x27;s internal data covering about 15 million members.

**Tags**: `#inflation`, `#wage growth`, `#consumer spending`, `#BLS data`, `#energy prices`

---