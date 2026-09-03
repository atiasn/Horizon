---
layout: default
title: "Horizon Summary: 2026-09-03 (EN)"
date: 2026-09-03
lang: en
---

> From 42 items, 10 important content pieces were selected

---

**Technology News**
1. [Meta Releases Muse Spark 1.3 with Near-SOTA Claims and Low-Cost Pricing](#item-tech-news-1) ⭐️ 8.0/10
2. [Gemini 3.8 Flash and 3.8 Flash Cyber](#item-tech-news-2) ⭐️ 8.0/10
3. [Google defeats DOJ bid to break up its ad tech business](#item-tech-news-3) ⭐️ 8.0/10
4. [Three sites mass-produced 215,128 &quot;best software&quot; pages that Perplexity cites](#item-tech-news-4) ⭐️ 7.0/10
5. [Paint.NET author uses Claude to rewrite Direct2D, bringing the app to WINE](#item-tech-news-5) ⭐️ 7.0/10
6. [Jasper Research Releases Open Cookbook for Building Text-to-Image Models](#item-tech-news-6) ⭐️ 7.0/10
7. [Benchmark finds most open-source AI text detectors fail at 0.5% false-positive rate](#item-tech-news-7) ⭐️ 7.0/10
8. [Alibaba Releases Qwen3.8-Max-0902, Claiming Top Spot on CodeArena Coding Leaderboard](#item-tech-news-8) ⭐️ 7.0/10
9. [FBI Probes Dark Web Service Nexus Selling 153 Million Driver&\#x27;s License Scans](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [Nepal tourism faces cancellations after Himalayan flood disaster](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meta Releases Muse Spark 1.3 with Near-SOTA Claims and Low-Cost Pricing](https://developer.meta.com/ai/models/muse-spark/) ⭐️ 8.0/10

Meta has released Muse Spark 1.3, announcing the new version of its AI model in a blog post at research.meta.ai with a listing on its developer model pages. The company bills it as approaching state-of-the-art benchmark performance at a very low cost, and Hacker News commenter bertili reports a DeepSWE score of 75.4 — described as the best so far and ahead of Google&\#x27;s Gemini 3.8 Flash, which had held the top spot hours earlier — though that figure comes from a community comment rather than a verified leaderboard. Early hands-on testing by simonw measured a pelican-riding-a-bicycle SVG generation at 4.2266 cents and 38 seconds, finding version 1.3&\#x27;s output better than 1.2&\#x27;s on details like the bicycle frame and wing. Pricing follows the approach introduced with 1.2, where the model is cheapest for users who consent to letting Meta train on their data, a structure the company now states explicitly in its pricing. The release drew heavy engagement on Hacker News \(381 points, 250 comments\), with users predicting that competition between Meta and Google at the top of the leaderboards will keep driving prices down.

hackernews · bvaldivielso · Sep 2, 19:35 · [Discussion](https://news.ycombinator.com/item?id=49541256)

**「Background」** Muse Spark is Meta&\#x27;s line of API-accessible language models; its predecessor, Muse Spark 1.2, is a reasoning model aimed at complex agentic tasks, priced at $1.25 per million input tokens and $4.25 per million output tokens with a 1,048,576-token context window. The line is notable for a training-consent pricing model in which Meta charges less to users who allow their prompts and outputs to be used for training, which is why the 1.3 tiers span from effectively free \(max\) to the same $1.25/$4.25 rates as 1.2 \(xhigh\). Claims of near-state-of-the-art performance are typically judged against independent benchmark trackers such as Artificial Analysis, and community members often supplement these with informal hands-on tests, such as generating an SVG of a pelican riding a bicycle.

**「Impact」** Developers building on budget-tier models get an immediately usable upgrade from Muse Spark 1.2 to 1.3 — early hands-on testing shows better output at roughly 4.2 cents per run under the same opt-in training-data discount — and the model&\#x27;s reported leapfrog of Google&\#x27;s Gemini 3.8 Flash at the top of leaderboards keeps competitive pressure on pricing in a segment where independent cost comparisons show Spark 1.2 at $0.00337 per chat task versus Gemini 3 Flash&\#x27;s $0.002. The near-SOTA benchmark claims for 1.3 itself remain community-reported and unverified.

**「Hacker News reaction」** Reaction was broadly positive: superfrank described the predecessor as &\#x27;dirt cheap&\#x27; and well suited to development work that doesn&\#x27;t need a frontier model, saying it seemed aware of its weaknesses and didn&\#x27;t impose its own opinions. The training-data pricing drew both praise and skepticism — jmward01 called Meta&\#x27;s explicit &\#x27;we train on this and value it this much&\#x27; framing a standard every provider should adopt while noting it exposes how much providers value users&\#x27; tokens, and Lucasoato quipped that the transparency almost made him forget Meta&\#x27;s $18B lawsuit over children&\#x27;s social media addiction.

<details><summary>References</summary>
<ul>
<li><a href="https://artificialanalysis.ai/models/muse-spark-1-3">Muse Spark 1.3 (max) - Intelligence, Performance &amp; Price Analysis | Artificial Analysis</a></li>
<li><a href="https://openrouter.ai/meta/muse-spark-1.2">Muse Spark 1.2 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://artificialanalysis.ai/models/muse-spark-1-3-xhigh">Muse Spark 1.3 (xhigh) - Intelligence, Performance &amp; Price Analysis | Artificial Analysis</a></li>
<li><a href="https://benchlm.ai/compare/gemini-3-flash-vs-muse-spark-1-2">Gemini 3 Flash vs Muse Spark 1.2: Benchmarks &amp; Cost | BenchLM.ai</a></li>

</ul>
</details>

**Tags**: `#artificial-intelligence`, `#large-language-models`, `#meta`, `#model-release`, `#benchmarks`

---

<a id="item-tech-news-2"></a>
### [Gemini 3.8 Flash and 3.8 Flash Cyber](https://blog.google/innovation-and-ai/models-and-research/gemini-models/3-8-flash-and-3-8-flash-cyber/) ⭐️ 8.0/10

Google released Gemini 3.8 Flash and 3.8 Flash Cyber, a fast, low-cost model family showing surprisingly strong benchmark results that drew substantial community attention and hands-on testing.

hackernews · bratao · Sep 2, 15:12 · [Discussion](https://news.ycombinator.com/item?id=49537553)

**Tags**: `#large-language-models`, `#google-gemini`, `#model-release`, `#ai-benchmarks`, `#inference-cost`

---

<a id="item-tech-news-3"></a>
### [Google defeats DOJ bid to break up its ad tech business](https://www.nytimes.com/2026/09/02/technology/google-ad-tech-remedies.html) ⭐️ 8.0/10

Google has defeated the U.S. Department of Justice&\#x27;s attempt to force the divestiture of its ad tech business, avoiding a court-ordered breakup in a decision reported by The New York Times and Reuters on September 2, 2026. The outcome leaves the company&\#x27;s advertising technology operations intact despite the government&\#x27;s monopoly case and represents a significant setback for structural antitrust remedies against large technology platforms. Figures cited from the Times&\#x27; reporting put the ad tech unit&\#x27;s revenue at about $30 billion last year, roughly 8 percent of Alphabet&\#x27;s total revenue, though it has declined for 16 consecutive quarters and analysts estimate it accounts for less than 1 percent of Alphabet&\#x27;s profit. The relative economic weight of that business shaped the remedies fight, since the government sought a sale while Google argued the unit was no longer dominant. The decision is expected to influence how regulators weigh breakup remedies in ongoing and future technology monopoly cases.

hackernews · donohoe · Sep 2, 14:46 · [Discussion](https://news.ycombinator.com/item?id=49537131)

**「Background」** This ruling concludes the remedies phase of the U.S. government&\#x27;s antitrust case over Google&\#x27;s advertising technology, after a federal judge ruled in April 2025 that Google illegally monopolizes the servers that host publisher ads and the ad exchanges that sit between advertising buyers and sellers. It also unfolds alongside Google&\#x27;s separate search monopoly case, in which D.C. District Judge Amit Mehta previously declined to force the company to spin off products such as Chrome and Android. Together, these cases frame the current decision, in which the court required Google to change its ad tech business to address antitrust issues while stopping short of the divestiture the DOJ sought.

**「Impact」** Publishers and advertisers using Google&\#x27;s ad stack face no immediate operational change, since Judge Brinkema declined to order a divestiture of AdX or DFP even after previously finding that Google&\#x27;s conduct substantially harmed its publisher customers, the competitive process, and consumers on the open web. Her remedy-phase reasoning that disrupting AdX or DFP could negatively affect the small publishers that currently use DFP for free signals that structural breakups will remain a difficult remedy to obtain against major tech platforms.

**「Community discussion」** Commenters were largely skeptical that antitrust enforcement meaningfully constrains large tech companies, with one arguing merger law should make unmerging companies as easy as merging them and another proposing progressive taxes on monopolies so companies would break themselves up without decade-long DOJ cases. Others debated the stakes themselves, pointing to the article&\#x27;s figures that the ad tech unit earns about $30 billion a year yet contributes under 1 percent of Alphabet&\#x27;s profit, which left some readers questioning what exactly the business covers and whether a divestiture fight was worthwhile; a longer comment argued tech giants now preemptively adapt to antitrust scrutiny rather than relying on lenient judges alone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/09/02/technology/google-ad-tech-remedies.html">In a Big Win, Google Avoids a Breakup of Its Ad Tech Business</a></li>
<li><a href="https://www.politico.com/news/2026/09/02/google-advertising-business-ruling-01061874">Google dodges another court-ordered breakup - POLITICO</a></li>
<li><a href="https://www.cnbc.com/2026/09/02/google-defeats-us-bid-to-force-ad-tech-sale.html">Google defeats U.S. bid to force ad tech sale - CNBC</a></li>
<li><a href="https://www.usatoday.com/story/tech/news/2026/09/02/google-ad-tech-antitrust-breakup/91580194007/">Google avoids breakup in DOJ ad tech antitrust case</a></li>
<li><a href="https://www.adexchanger.com/antitrust/google-wont-have-to-break-up-its-ad-tech-business-judge-brinkema-rules/">Google Won’t Have To Break Up Its Ad Tech Business, Judge Brinkema Rules | AdExchanger</a></li>

</ul>
</details>

**Tags**: `#antitrust`, `#google`, `#ad-tech`, `#regulation`, `#tech-industry`

---

<a id="item-tech-news-4"></a>
### [Three sites mass-produced 215,128 &quot;best software&quot; pages that Perplexity cites](https://trellner.com/reports/manufactured-sources-behind-ai-recommendations/) ⭐️ 7.0/10

An independent blog investigation published on Trellner documents how three websites mass-produced 215,128 &quot;best software&quot; recommendation pages that Perplexity cites as sources. The report illustrates how cheaply and at what scale content can be manufactured specifically to be picked up by AI-powered answer engines rather than to serve human readers. Because Perplexity draws on such pages when recommending software, the findings point to a systemic weakness in how AI search engines evaluate source quality. The investigation drew substantial attention on Hacker News, receiving 304 points and 141 comments, where discussion extended to related problems such as LLMs favoring LLM-generated text and hallucinated recommendations.

hackernews · jakobgreenfeld · Sep 2, 13:59 · [Discussion](https://news.ycombinator.com/item?id=49536375)

**「Background」** Perplexity is an AI answer engine that generates responses grounded in web citations rather than presenting a conventional ranked list of links, so the pages it retrieves and cites directly shape the recommendations users receive. This follows a familiar pattern from traditional search: publishers have long used programmatic SEO—mass-producing thousands of templated pages to rank for commercial queries—and similar tactics are now being aimed at AI citations rather than Google rankings. The report notes that across 380 software categories, 59.8% of the sources behind grounded AI recommendations sit outside the 100,000 most-visited websites, indicating AI search can draw heavily from low-traffic sites built to be read by models rather than people.

**「Impact」** Users of Perplexity and similar AI answer engines face software recommendations that can be captured by operators mass-producing fabricated &quot;best software&quot; pages, meaning citations in AI search are no longer a reliable signal of product quality or popularity. This extends an already-documented pattern of the engine citing AI-generated spam across topics and strengthens incentives for a programmatic-SEO economy optimized for AI citations rather than human readers.

**「Skepticism toward Perplexity, and toward the report itself」** Commenters largely treated the findings as confirmation of existing skepticism toward Perplexity, with one user reporting that results degraded after the service optimized for speed over quality, while another broadened the concern to models themselves, citing research that LLMs favor LLM-generated passages over human-written ones and describing a hallucinated recommendation of a nonexistent landmark. One commenter dismissed the report itself as an obvious AI-generated artifact, a criticism aimed at its writing style rather than its data.

<details><summary>References</summary>
<ul>
<li><a href="https://trellner.com/reports/manufactured-sources-behind-ai-recommendations/">Three sites made 215,128 &quot;best software&quot; pages for AI. Perplexity cites ...</a></li>
<li><a href="https://infin8content.com/resources/blog/three-sites-generated-215128-ai-software-pages-and-perplexity-is-citing-them-c0851b6d">Three sites generated 215,128 AI software pages, and Perplexity is ...</a></li>
<li><a href="https://www.forbes.com/sites/rashishrivastava/2024/06/26/search-startup-perplexity-increasingly-cites-ai-generated-sources/">Garbage In, Garbage Out: Perplexity Spreads Misinformation ...</a></li>
<li><a href="https://growthengineer.ai/blog/programmatic-seo-ai-citations-audit">We Audited 100 Programmatic SEO Pages: What Gets Cited by ...</a></li>

</ul>
</details>

**Tags**: `#AI search`, `#Perplexity`, `#SEO spam`, `#LLM reliability`, `#content quality`

---

<a id="item-tech-news-5"></a>
### [Paint.NET author uses Claude to rewrite Direct2D, bringing the app to WINE](https://simonwillison.net/2026/Sep/2/rick-brewster/) ⭐️ 7.0/10

Rick Brewster, author of the Windows image editor Paint.NET, announced in a forum post quoted by Simon Willison that the application now runs under WINE on Linux thanks to an internal, from-scratch, clean-room reverse-engineered rewrite of Microsoft&\#x27;s Direct2D graphics API, activated with a /wine flag and shipped in the assembly PaintDotNet.Windows.Direct2D1.Managed.dll. Direct2D had been the biggest hurdle for Paint.NET on WINE, since its WINE implementation will never be completed enough for Paint.NET&\#x27;s needs and the application cannot simply disable its use of Direct2D. Brewster credits the Claude AI assistant with making the project possible, estimating the rewrite at about 180,000 lines of code, most of it &\#x27;vibe coded&\#x27; and not thoroughly reviewed — a scale he contrasts with the roughly 700,000 lines of the rest of Paint.NET, which he has worked on for over 20 years. He describes having to supervise the model closely, including fixing missing COM reference counting \(the AddRef\(\) equivalent\) for reference-counted objects and rejecting bad design and architecture decisions, while praising Claude&\#x27;s clever reverse engineering of the formulas behind Direct2D&\#x27;s built-in effects library. The result stands as a striking data point for both the reach of AI-assisted coding at unusual scale and the risks of shipping large volumes of effectively unreviewed code.

rss · Simon Willison · Sep 2, 05:50

**「Background」** Paint.NET is a free raster graphics editor for Windows built on the .NET Framework, developed by Rick Brewster for over two decades. Direct2D is Microsoft&\#x27;s hardware-accelerated 2D graphics API that Paint.NET relies on, and WINE is the compatibility layer that lets Windows applications run on Linux by reimplementing Windows APIs — but WINE&\#x27;s Direct2D support has never been complete enough for Paint.NET&\#x27;s needs. According to Brewster, Claude advanced this effort in three weeks further than the WINE project had managed in the previous twelve years, which is why Paint.NET 5.2 now ships its own managed, clean-room rewrite of Direct2D for use under WINE.

**「Linux users gain WINE access」** Linux users can now run the Windows-only .NET-based Paint.NET editor under WINE by launching it with the /wine flag, bypassing the incomplete Direct2D support that had long blocked the application from working outside Windows. Because the roughly 180,000-line AI-written Direct2D reimplementation is largely unreviewed, the feature is experimental and its long-term correctness and stability remain unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://ru.wikipedia.org/wiki/Paint.NET">Paint . NET — Википедия</a></li>
<li><a href="https://dzen.ru/b/aph517l2b0_H1PO5">Paint . NET : Claude сдвинул WINE за три недели paint . net ... | Дзен</a></li>
<li><a href="https://en.wikipedia.org/wiki/Paint.NET">Paint.NET - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#ai-assisted-coding`, `#llm`, `#wine`, `#direct2d`, `#paint.net`

---

<a id="item-tech-news-6"></a>
### [Jasper Research Releases Open Cookbook for Building Text-to-Image Models](https://www.reddit.com/r/MachineLearning/comments/1w5c9rd/detailed_explanation_of_how_to_create_a/) ⭐️ 7.0/10

Jasper Research has released an open cookbook that walks through how to build a text-to-image model from scratch, sharing the full reasoning and intermediate results along the way. The release is aimed at practitioners who want to deep-dive into text-to-image architectures or understand how such models are built at frontier labs. It bundles three components: an interactive technical report hosted on Hugging Face \(jasperai/t2i-technical-interactive-report\), a codebase called nano t2i on GitHub \(gojasper/nano-t2i\) containing a tiny model that can be trained from scratch, and a 100M-image dataset named Monet hosted on Hugging Face \(jasperai/monet\). Together, these resources let users reproduce a small-scale text-to-image training pipeline end to end. The release is educational in nature rather than a frontier-scale model announcement, and its claims currently come from a Reddit post by /u/dh7net without independent verification.

reddit · r/MachineLearning · /u/dh7net · Sep 2, 14:40

**「Background」** Building a text-to-image model typically requires pairing a large image-text dataset with a generative training approach such as flow matching, resources that are usually available only inside frontier labs and rarely documented end-to-end. The release described here consists of three parts: MONET \(Massive, Open, Non-redundant and Enriched Text-to-image dataset\), an English-language dataset of about 103.8M image-text pairs hosted on Hugging Face; nano-t2i, an Apache-2.0 licensed minimal codebase for training a text-to-image flow-matching model end-to-end on MONET, reportedly reproducible on a single H200 GPU for under $300; and an interactive technical report \(cookbook\) explaining the reasoning and intermediate results.

**「Impact」** ML practitioners and researchers gain a rare end-to-end educational resource for text-to-image development, including a 104.9M-sample open dataset \(MONET, refined from 2.9 billion images\) and the nano-t2i codebase for training small models from scratch, lowering the barrier to hands-on generative model research.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/datasets/jasperai/monet">jasperai/ monet · Datasets at Hugging Face</a></li>
<li><a href="https://github.com/gojasper/nano-t2i">gojasper/ nano - t 2 i : Minimal training code of a nano text - to - image ...</a></li>
<li><a href="https://gojasper.github.io/monet/">A Massive, Open, Non-redundant and Enriched Text - to - image dataset</a></li>
<li><a href="https://huggingface.co/blog/jasperai/monet">MONET: Lowering the Barrier to World Class Image Generation Research</a></li>

</ul>
</details>

**Tags**: `#text-to-image`, `#generative-models`, `#machine-learning`, `#open-source`, `#training-from-scratch`

---

<a id="item-tech-news-7"></a>
### [Benchmark finds most open-source AI text detectors fail at 0.5% false-positive rate](https://www.reddit.com/r/MachineLearning/comments/1w58erw/most_opensource_ai_detectors_cant_hold_a_05/) ⭐️ 7.0/10

A Reddit post on r/MachineLearning by /u/grumpyp2 reports a community benchmark of six notable open-source AI text detectors run through a single evaluation protocol, using only public data: the Jabarian &amp; Imas 2025 NBER dataset, Liang&\#x27;s 2023 TOEFL essays, a 1,060-text set of outputs from frontier models \(GPT-5.x, Claude Opus 5, Gemini 3.x\), and 5,000 pre-LLM \(2018\) FineWeb pages as the human pool. Each detector&\#x27;s threshold was calibrated on the same 6,930 human documents to a matched 0.5% false-positive rate, and recall was then measured per group. The results show that 4 of 6 models effectively cannot reach the 0.5% FPR target at any threshold — MAGE scores above 0.9999 on 26% of ordinary human web text — and the old OpenAI RoBERTa detector lands at AUC 0.31, worse than a coin flip on modern generators. Detection collapses on humanizer-paraphrased AI text, where the best model \(tropa-mini, AUC 0.968\) catches only 41.6% and the second best \(desklib/ai-text-detector-v1.01\) catches 4.0%, while all models flag non-native English writers&\#x27; essays at higher rates than native writers&\#x27; essays, which the authors call a fundamental flaw in the entire class of models. The authors disclose that one of the six tested detectors is their own \(released as Apache-2.0 open weights\), and all datasets and methodology are published in the model card on Hugging Face so results can be reproduced.

reddit · r/MachineLearning · /u/grumpyp2 · Sep 2, 12:04

**「Background」** AI text detectors are classifiers trained to distinguish machine-generated text from human writing, and their reliability is usually judged by the trade-off between the false-positive rate \(human text wrongly flagged as AI\) and recall \(AI text correctly caught\). Concerns about these tools are not new: a 2023 Stanford study found that seven GPT detectors unanimously flagged 19% of TOEFL essays by non-native English writers, and 97% were flagged by at least one detector, with the authors showing that simplifying or adjusting the vocabulary of such essays sharply reduced misclassification. The present benchmark extends this line of work by evaluating open-source detectors under a matched false-positive-rate protocol across modern frontier generators and paraphrasing-based evasion.

**「Impact」** Educators and practitioners relying on open-source AI detectors face evidence that these tools produce unacceptable false-positive rates at practical thresholds, systematically penalize non-native English writers, and can be defeated by humanizer paraphrasing — though the findings are self-reported by an author with a competing product and have not been independently verified.

<details><summary>References</summary>
<ul>
<li><a href="https://www.sciencedirect.com/science/article/pii/S2666389923001307">GPT detectors are biased against non-native English writers - ScienceDirect</a></li>
<li><a href="https://hai.stanford.edu/news/ai-detectors-biased-against-non-native-english-writers">AI-Detectors Biased Against Non-Native English Writers</a></li>

</ul>
</details>

**Tags**: `#AI text detection`, `#benchmarking`, `#false positive rate`, `#model evaluation`, `#fairness`

---

<a id="item-tech-news-8"></a>
### [Alibaba Releases Qwen3.8-Max-0902, Claiming Top Spot on CodeArena Coding Leaderboard](https://mp.weixin.qq.com/s/BfKRXMAR5ykD58LDkBftLg) ⭐️ 7.0/10

Alibaba&\#x27;s Tongyi Qianwen team has released Qwen3.8-Max-0902, a new version of its flagship model that was further post-trained for programming and professional office tasks. According to the announcement, the model took first place on the CodeArena frontend programming leaderboard with 1691 points, a 22-point improvement over the previous version. The model reportedly has 2.4 trillion parameters and supports a 1M token context length. Its API is priced at $2 per million input tokens and $6 per million output tokens, an average of roughly $5, which is lower than the $20 and $12 average prices of the models ranked second and third on the leaderboard. The new version is already available on the Qwen AI platform and has been integrated into Qwen Office, Qoder, and the Qwen app. Note that these figures come from a promotional channel announcement and have not been independently verified.

telegram · zaihuapd · Sep 2, 06:05

**「Background」** Qwen \(Tongyi Qianwen\) is Alibaba&\#x27;s flagship large language model family, and the &quot;Max&quot; variants represent its top-tier models, with version numbers like 0902 reflecting date-based iterative releases. CodeArena is a frontend programming leaderboard that ranks large language models on coding tasks, where vendors routinely compete for the top position as a public benchmark of coding capability. Post-training on programming and professional office tasks is a common technique for specializing a general-purpose model toward coding and agentic workloads without changing its underlying architecture.

**「Impact」** If the reported pricing and capabilities hold up, developers building coding-focused applications could access a top-ranked large-context model at a fraction of the cost of competing leaderboard models, though the benchmark claims remain unverified by independent sources.

<details><summary>References</summary>
<ul>
<li><a href="https://www.admin5.com/article/20260902/16701775.shtml">阿 里 Qwen 3 . 8 - Max 0902 版登顶 CodeArena ：前端 编 程 榜 1691 ...</a></li>
<li><a href="https://cn.technode.com/post/2026-09-02/qwen3-8-max-0902-codearena/">通义千问升级 Qwen 3 . 8 - Max ，前端 编 程 榜 得 分 升至 1691 - 动点科技</a></li>
<li><a href="https://www.ithome.com/0/997/270.htm">阿 里 千问 Qwen 3 . 8 - Max - 0902 ...</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#Qwen`, `#model-release`, `#coding-benchmark`, `#AI-industry`

---

<a id="item-tech-news-9"></a>
### [FBI Probes Dark Web Service Nexus Selling 153 Million Driver&\#x27;s License Scans](https://krebsonsecurity.com/2026/09/fbi-probes-service-selling-153m-drivers-licenses/) ⭐️ 7.0/10

The FBI is investigating Nexus, a dark web service that claims to hold more than 153 million digital scans of driver&\#x27;s licenses belonging to residents of the United States and Canada and has begun selling them. According to reporting by KrebsOnSecurity, the trove may originate from previously leaked scans held by auto dealerships, insurance companies, and similar organizations, though officials have not confirmed the exact source or the number of affected individuals. Because driver&\#x27;s licenses contain names, home addresses, and birth dates, the data is well suited for identity fraud, making the potential victim pool substantial if the claimed volume is accurate. The involvement of the FBI signals that law enforcement treats the case as a significant identity-theft threat, but key details — including verification of the 153 million figure and the breach origins — remain unconfirmed.

telegram · zaihuapd · Sep 2, 09:31

**「Background」** Driver&\#x27;s license scans are digital images captured when businesses such as car dealerships, insurers, and identity-verification vendors confirm a customer&\#x27;s identity, and each scan bundles a person&\#x27;s name, address, date of birth, and license number into a single record useful for identity fraud. Dark web marketplaces that resell such scans typically draw from breaches of these upstream collectors, meaning one compromised source can expose millions of consumers at once. In this incident, early reporting has linked the Nexus dataset to a suspected breach of the identity-verification firm IDScan, though the exact origin of the 153 million scans remains unconfirmed.

**「Identity Fraud Risk for US and Canadian Residents」** US and Canadian residents whose license scans are in the dataset face heightened risk of identity fraud, such as fraudulent account openings, since the data includes names, addresses, and birth dates. Until the source and scope are officially confirmed, the true number of affected individuals remains uncertain.

<details><summary>References</summary>
<ul>
<li><a href="https://www.malwarebytes.com/blog/news/2026/09/dark-web-site-puts-153-million-drivers-licenses-and-millions-more-ids-up-for-sale">Dark web site puts 153 million driver ’s licenses and... | Malwarebytes</a></li>
<li><a href="https://cyberinsider.com/153-million-drivers-licenses-exposed-in-suspected-idscan-breach/">153 million driver ’s licenses exposed in suspected IDScan breach</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#data-breach`, `#dark-web`, `#identity-theft`, `#privacy`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nepal tourism faces cancellations after Himalayan flood disaster](https://www.cnbc.com/2026/09/02/nepal-tibet-floods-adventure-tourism-economy.html) ⭐️ 8.0/10

A glacial collapse and flood along Nepal&\#x27;s border with China has killed 987 people with about 4,250 missing, and Nepal reportedly estimates reconstruction costs of $4-5 billion — roughly one-tenth of its economy. Tourist cancellations are hitting the tourism-dependent country just before its peak season \(Sept. 15-Nov. 15\), with one Kathmandu hostel owner expecting 60% occupancy versus 100% last year, prompting industry calls for climate-resilient rebuilding.

rss · CNBC Finance · Sep 2, 09:23

**「Background」** Tourism is a core pillar of Nepal&\#x27;s economy and a major source of foreign exchange, with the country of nearly 30 million renowned for trekking, mountaineering and spiritual travel. The disaster began on Aug. 26 when a massive glacial collapse in northern Nepal triggered floods along the Nepal-Tibet border, though scientists caution it was not a conventional glacial lake outburst flood, in which water bursts through the fragile natural dam holding back a meltwater lake.

**「Who is affected」** Nepal&\#x27;s tourism businesses — hostels, trekking operators and mountain guides — face cancellations just before the peak Sept. 15–Nov. 15 season, with one Kathmandu hostel owner expecting at best 60% occupancy versus 100% last year, hitting a sector that supplies a major share of the country&\#x27;s foreign exchange and contributes roughly 6.7% of GDP.

<details><summary>References</summary>
<ul>
<li><a href="https://www.news18.com/explainers/nepal-floods-raise-himalayan-glacial-lake-risks-how-exposed-are-kashmir-ladakh-and-uttarakhand-shil-ws-l-10301505.html">Nepal Floods Raise Himalayan Glacial Lake Fears. Are Kashmir ... - News18</a></li>
<li><a href="https://www.newindianexpress.com/world/2026/Aug/31/nepal-floods-disaster-exposes-blind-spot-in-himalayan-glacier-risk-assessment">Nepal floods disaster exposes blind spot in Himalayan glacier risk ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Tourism_in_Nepal">Tourism in Nepal - Wikipedia</a></li>
<li><a href="https://trishulivilla.com/tourism-industry-in-nepal-insights-for-travelers-investors/">Tourism Industry in Nepal: Insights for Travelers &amp; Investors - TRISHULI VILLA - Villa By Trishuli River Side Resort</a></li>

</ul>
</details>

**Tags**: `#Nepal economy`, `#tourism industry`, `#natural disaster`, `#climate change`, `#reconstruction costs`

---