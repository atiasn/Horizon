---
layout: default
title: "Horizon Summary: 2026-09-16 (EN)"
date: 2026-09-16
lang: en
---

> From 36 items, 7 important content pieces were selected

---

**Technology News**
1. [Google Releases Gemini 3.8 Live and 3.8 Live Extended Thinking](#item-tech-news-1) ⭐️ 8.0/10
2. [AI Pentest Agent Found Admin GitHub Access to Baseten in 25 Minutes](#item-tech-news-2) ⭐️ 8.0/10
3. [Wayback Machine Deploys Protections Against Waves of High-Volume Automated Traffic](#item-tech-news-3) ⭐️ 7.0/10
4. [Suspected sabotage causes major Netherlands rail disruption](#item-tech-news-4) ⭐️ 7.0/10
5. [Everyone Says Datacenter Moratoriums Are Killing the US Buildout. We disagree](#item-tech-news-5) ⭐️ 7.0/10
6. [Prior Labs Releases TabPFN-3.5 Tabular Foundation Model](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s August retail sales miss forecasts as investment slump deepens](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Releases Gemini 3.8 Live and 3.8 Live Extended Thinking](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-live-gemini-3-8-live-extended-thinking/) ⭐️ 8.0/10

Google announced Gemini 3.8 Live and Gemini 3.8 Live Extended Thinking, an incremental iteration on its real-time voice and multimodal model line rather than a new paradigm. The release drew substantial attention on Hacker News, with 189 comments discussing first-hand experiences with latency, accent handling, and multilingual performance. Early user reports describe low latency, pleasant voices, and strong handling of thick accents, with one commenter noting it worked on Workspace accounts that had previously been excluded from recent releases. Multilingual capability emerged as a standout: users report impressive spoken Afrikaans conversation and grammar tutoring, and creative writing that captures local nuance and humor in non-English languages. However, commenters also flagged persistent reliability problems, including frequent hallucination on supporting concepts and unreliable deep research output, so the release appears to trade some trustworthiness for strong real-time conversational performance.

hackernews · leumon · Sep 15, 17:38 · [Discussion](https://news.ycombinator.com/item?id=49715947)

**「Background」** Gemini Live is Google&\#x27;s line of real-time, voice-first dialogue models designed for natural spoken conversation, and the newly announced Gemini 3.8 Live and Gemini 3.8 Live Extended Thinking are described as its most advanced live dialogue models yet. The release, announced on September 15, 2026, splits the voice product line into two variants: a standard live conversation model and an Extended Thinking version, reflecting Google&\#x27;s broader shift from a text-first chatbot competitor toward a multimodal, real-time voice platform. This matters for context because Gemini Live competes in a space with other real-time voice AI offerings, and prior Google releases have faced criticism over availability gaps, such as Workspace accounts being excluded from recent launches.

**「Why It Matters」** For developers and users of real-time voice AI, Gemini 3.8 Live appears to offer competitive low-latency, multilingual conversation — including on Workspace accounts — though reported hallucination issues mean it may not yet be dependable for research or fact-sensitive work.

**「Community Reaction」** Commenters broadly praised the voice experience — accent tolerance, voice quality, latency, and Workspace account availability — and highlighted exceptional multilingual ability, with one Afrikaans speaker calling live conversation practice the most enjoyable LLM use case they have found. Criticism centered on reliability: users report frequent hallucination on supporting details, inconsistent reasoning beyond main concepts, and unreliable deep research results, while others questioned whether Google is still behind competitors despite its data, TPU hardware, and advertising resources.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-live-gemini-3-8-live-extended-thinking/">Gemini 3 . 8 Live &amp; Gemini 3 . 8 Live Extended Thinking</a></li>
<li><a href="https://shattered.io/gemini-3-8-live-extended-thinking-launch-2026/">Gemini 3 . 8 Live &amp; Extended Thinking : Google Voice AI [2026]</a></li>
<li><a href="https://www.orcarouter.ai/blog/gemini-3-8-live-release">Gemini 3 . 8 Live : Google Splits Its Voice Line in Two</a></li>

</ul>
</details>

**Tags**: `#google-gemini`, `#large-language-models`, `#voice-ai`, `#multimodal`, `#model-release`

---

<a id="item-tech-news-2"></a>
### [AI Pentest Agent Found Admin GitHub Access to Baseten in 25 Minutes](https://www.strix.ai/blog/baseten-harbor-github-pat-takeover) ⭐️ 8.0/10

An AI-driven penetration testing agent from Strix reportedly gained admin access to Baseten&\#x27;s production GitHub organization within 25 minutes by discovering an active GitHub personal access token belonging to the &\#x27;basetenbot&\#x27; account. The agent located the token in Docker build history after finding a publicly accessible Baseten image repository in a Harbor registry; the token had admin and push access to Baseten&\#x27;s main product repo, the GitOps repo driving their clusters, and their Homebrew tap, plus read/write access to other private repositories including customer-specific ones. The researcher reported the live token, the public Harbor project, and the repository permissions on July 13 at 11:10 PM; Baseten made the Harbor project private the next morning, and after the researcher flagged that the token still worked, Baseten Security confirmed the issue as critical on July 14 at 4:34 PM, having rotated the token and asked the researchers to securely delete the pulled images. The disclosure underscores two lessons: secrets embedded in container image build layers remain a common and high-impact leak vector, and agentic security tooling is dramatically lowering the time and effort required to find such exposures.

hackernews · bearsyankees · Sep 15, 18:11 · [Discussion](https://news.ycombinator.com/item?id=49716476)

**「Background」** A GitHub personal access token \(PAT\) is a credential that can grant programmatic access to repositories, and one with admin rights effectively gives full control over an organization&\#x27;s source code and CI/CD pipelines. Such tokens frequently leak through artifacts like Docker image layers and build history, which can remain readable in container registries such as Harbor — an open-source cloud-native registry for storing and scanning container images. In this case, Strix, a vendor of an open-source autonomous AI penetration-testing agent, discovered the exposure while evaluating Baseten, a model inference platform valued at $13 billion that the Strix team was assessing as a potential inference provider.

**「Impact」** Engineering and security teams face a shrinking window of risk, since exposures that humans might never bother to hunt down can now be found in minutes by automated agents, making rigorous secrets hygiene—purging tokens from build history, scoping PATs narrowly, and locking down container registries—effectively mandatory.

**「Community Discussion」** Commenters largely agreed the incident says more about the speed of AI agents than novel attack techniques, with one noting the agent found something &\#x27;a human could find if they were interested&\#x27; but far faster, and questioning what Strix&\#x27;s agent did that general-purpose tools like Claude or Codex could not. Others observed the disclosure doubles as highly effective marketing for Strix while being embarrassing for Baseten, though the responsible disclosure timeline was praised. One commenter raised the legal question of whether probing systems without permission is permissible, comparing it to breaking a neighbor&\#x27;s lock even without intent to steal.

<details><summary>References</summary>
<ul>
<li><a href="https://www.strix.ai/blog/baseten-harbor-github-pat-takeover">We wanted to use Baseten for inference. We ended up with... - Strix</a></li>
<li><a href="https://github.com/usestrix/strix">GitHub - usestrix/ strix : Open-source AI penetration testing tool to find...</a></li>

</ul>
</details>

**Tags**: `#security`, `#ai-agents`, `#github`, `#supply-chain`, `#penetration-testing`

---

<a id="item-tech-news-3"></a>
### [Wayback Machine Deploys Protections Against Waves of High-Volume Automated Traffic](https://blog.archive.org/2026/09/15/an-update-on-wayback-machine-access/) ⭐️ 7.0/10

The Internet Archive has published an update explaining that the Wayback Machine has been hit by waves of high-volume automated traffic and that it has deployed protections to keep the service running. The announcement matters because the Wayback Machine is a vital non-profit archive of the open web, and sustained scraping load threatens availability for ordinary users. Commenters on Hacker News observed that much of this traffic likely comes from scrapers attempting to work around blocks on original sites by fetching archived copies instead, a pattern that also risks pushing more site owners to opt out of archiving altogether. The Archive is under pressure from multiple directions at once, yet users report that anonymous access, including via Tor and without centralized gatekeepers like Cloudflare, has so far been maintained, though service consistency has suffered, with some users reporting recurring 429 rate-limit errors from certain networks. The episode highlights the broader sustainability challenge facing open internet infrastructure as automated and AI-driven crawling intensifies.

hackernews · ChrisArchitect · Sep 15, 17:52 · [Discussion](https://news.ycombinator.com/item?id=49716176)

**「Background」** The Wayback Machine, run by the non-profit Internet Archive, is a free service that stores historical snapshots of web pages so users can view content that has changed or disappeared. It has long served as critical open internet infrastructure, but as more original sites deploy anti-bot measures and paywalls, automated scrapers increasingly turn to archived copies instead, placing heavy load on the Archive. The service has also faced other pressures in recent years, including legal challenges and funding constraints, which makes operational disruptions like the current high-volume automated traffic especially consequential for its sustainability.

**「Impact」** Wayback Machine users are likely to encounter rate limits, 429 errors, and inconsistent access as the Internet Archive&\#x27;s anti-bot protections filter traffic, while the strain accelerates a trend of publishers and major organizations—including The New York Times, The Guardian, and Reddit—blocking the archive over AI-scraping concerns, shrinking the coverage of a repository holding over one trillion webpage snapshots. This means both everyday readers and legitimate researchers face a less complete and less reliably accessible historical web record.

**「Community Discussion」** Commenters largely sympathized with the Archive, with one asserting that the traffic is scrapers circumventing blocks on original sites and calling the behavior appalling, while noting some sites have already opted out of archiving. Others praised the Archive for keeping open access even via Tor despite inconsistent service, urged donations, and one user suggested AI companies should pay the Wayback Machine billions for access. Some users shared practical anomalies, such as persistent 429 errors from a work computer while a phone accessed the site fine, and one reflected on the personal value of the Archive after recovering their own early-2000s website content.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.archive.org/2026/09/15/an-update-on-wayback-machine-access/">An Update on Wayback Machine Access | Internet Archive Blogs</a></li>
<li><a href="https://www.pcmag.com/news/why-is-the-internet-archive-blocking-users-blame-the-bots">Why Is the Internet Archive Blocking Users? Blame the Bots</a></li>
<li><a href="https://blog.archive.org/2026/02/18/wayback-machine-director-pushes-back/">Wayback Machine Director Pushes Back on AI Scraping Fears ...</a></li>
<li><a href="https://www.niemanlab.org/2026/01/news-publishers-limit-internet-archive-access-due-to-ai-scraping-concerns/">News publishers limit Internet Archive access due to AI ...</a></li>
<li><a href="https://help.archive.org/help/faq-publishers-blocking-the-wayback-machine/">FAQ: Publishers Blocking the Wayback Machine – Internet ...</a></li>

</ul>
</details>

**Tags**: `#internet-archive`, `#wayback-machine`, `#web-scraping`, `#infrastructure`, `#open-web`

---

<a id="item-tech-news-4"></a>
### [Suspected sabotage causes major Netherlands rail disruption](https://www.bbc.com/news/articles/c8ly49w9g1edo) ⭐️ 7.0/10

Suspected sabotage disrupted major Netherlands rail service, sparking a well-informed Hacker News discussion on how fail-safe rail signaling systems can be exploited at scale to halt trains without causing collisions.

hackernews · choult · Sep 15, 10:22 · [Discussion](https://news.ycombinator.com/item?id=49710253)

**Tags**: `#critical-infrastructure`, `#rail-systems`, `#security`, `#fail-safe-design`, `#physical-sabotage`

---

<a id="item-tech-news-5"></a>
### [Everyone Says Datacenter Moratoriums Are Killing the US Buildout. We disagree](https://newsletter.semianalysis.com/p/everyone-says-datacenter-moratoriums) ⭐️ 7.0/10

SemiAnalysis argues that datacenter moratoriums have far less impact on the US buildout than commonly claimed, quantifying only ~2.3GW of actual slippage nationwide despite 20GW sitting inside restricted local boundaries.

rss · Semianalysis · Sep 15, 20:54

**Tags**: `#datacenters`, `#AI infrastructure`, `#energy policy`, `#power grid`, `#industry analysis`

---

<a id="item-tech-news-6"></a>
### [Prior Labs Releases TabPFN-3.5 Tabular Foundation Model](https://www.reddit.com/r/MachineLearning/comments/1wh4xhy/tabpfn35_is_released_as_the_next_sota_tabular/) ⭐️ 7.0/10

Prior Labs released TabPFN-3.5, the latest entry in its TabPFN family of tabular foundation models, announcing that it tops both the TabArena and BeyondArena benchmarks and achieves state-of-the-art results on datasets of up to 1 million rows and 20,000 features. The release ships in multiple variants: TabPFN-3.5-Fast \(in alpha\), which runs 6x faster than the base model; TabPFN-3.5-Thinking, an API-only option that trades additional compute for higher accuracy; and TabPFN-3.5-Plus. On BeyondArena, which covers text-rich, high-cardinality, and high-dimensional data, the company reports TabPFN-3.5 leads the strongest previous baseline by +250 Elo points and the previous overall leader by +150 Elo points, while TabPFN-3.5-Thinking adds +20 Elo over the base model on BeyondArena and +44 Elo on TabArena. If these self-reported results hold up under independent evaluation, the model could become a strong default choice for tabular machine learning tasks, though the figures come from the vendor via a Reddit announcement and have not yet been independently verified.

reddit · r/MachineLearning · /u/tuanacelik · Sep 15, 16:18

**「Background」** TabPFN is a family of tabular foundation models developed by Prior Labs that applies transformer-based, pretraining-driven approaches to structured data prediction, a domain traditionally dominated by gradient-boosted decision trees. The code and earlier model weights, such as TabPFN-2, have been released openly under the Prior Labs License, an Apache 2.0 variant with an additional attribution requirement. TabArena and BeyondArena are external benchmarks designed to evaluate prediction models on real-world tabular data, and they serve as the reference points for the new release&\#x27;s performance claims.

**「Impact」** If the reported results hold up under independent evaluation, practitioners working with tabular data could replace tuned gradient-boosting pipelines with a zero-shot foundation model that scales to 1M rows and 20k features, with faster or higher-accuracy variants to trade off latency and accuracy. However, the benchmark numbers are self-reported by Prior Labs, so adoption decisions should await third-party verification.

<details><summary>References</summary>
<ul>
<li><a href="https://priorlabs.ai/technical-reports/tabpfn-3-5">Prior Labs</a></li>
<li><a href="https://github.com/PriorLabs/TabPFN">GitHub - PriorLabs/ TabPFN : TabPFN : Foundation Model for Tabular ...</a></li>
<li><a href="https://priorlabs.ai/technical-reports/tabpfn-3-5">TabPFN-3.5: Technical Report - Prior Labs</a></li>
<li><a href="https://storage.googleapis.com/prior-labs-tabpfn-public/reports/tabpfn-v3.5-report.pdf">TabPFN-3.5: Technical Report - storage.googleapis.com</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#tabular-data`, `#foundation-models`, `#benchmarks`, `#model-release`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s August retail sales miss forecasts as investment slump deepens](https://www.cnbc.com/2026/09/15/china-august-retail-sales-industrial-output-investment-exports-.html) ⭐️ 7.0/10

China&\#x27;s retail sales grew just 0.4% in August from a year earlier, missing the 0.8% forecast in a Reuters poll, while fixed-asset investment fell 7.2% in January-August, a steeper decline than the 6.7% drop in the first seven months. The National Bureau of Statistics warned of an &quot;acute&quot; imbalance between strong supply and weak demand and called for stronger macro-policy support.

rss · CNBC Finance · Sep 15, 09:46

**「Background」** The world&\#x27;s second-largest economy grew 4.3% in the second quarter, its weakest pace in over three years and below Beijing&\#x27;s 4.5%-5% annual target, and August&\#x27;s new bank loans of 60 billion yuan \($8.95 billion\) came in far below the roughly 400 billion yuan expected, pushing outstanding loan growth to a record-low 4.9%.

**「Impact」** Analysts at Pinpoint Asset Management and ANZ say the data raises pressure on Beijing for more fiscal stimulus, with September seen as a key policy window, though economists expect meaningful new measures only if export growth weakens enough to threaten the annual target.

**Tags**: `#China economy`, `#retail sales`, `#fixed-asset investment`, `#monetary and fiscal policy`, `#economic data`

---