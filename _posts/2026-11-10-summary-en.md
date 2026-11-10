---
layout: default
title: "Horizon Summary: 2026-11-10 (EN)"
date: 2026-11-10
lang: en
---

> From 44 items, 14 important content pieces were selected

---

**Technology News**
1. [JEPA-Style Tactile Pretraining Outperforms MAE and VAE Reconstruction](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic Releases Claude Fable 5.2 and Mythos 5.2](#item-tech-news-2) ⭐️ 8.0/10
3. [Google Announces TPU 8tx and TPU 8i Max for Agentic AI Workloads](#item-tech-news-3) ⭐️ 8.0/10
4. [e-means: Clustering Algorithm Claiming k-means Gains in One-Tenth the Epochs](#item-tech-news-4) ⭐️ 7.0/10
5. [Show HN: Browser Tool Maps Satellite Passes and Real Imagery](#item-tech-news-5) ⭐️ 7.0/10
6. [Consumer Gemini Connected Apps Can Send Personal Drive and Gmail Data to Human Reviewers](#item-tech-news-6) ⭐️ 7.0/10
7. [Claude Fable 5.2 Tops Artificial Analysis at 65, Doubling Cost Per Task](#item-tech-news-7) ⭐️ 7.0/10
8. [XGBoost Outage Forecast Beats NWS Warning Baseline 2.4×](#item-tech-news-8) ⭐️ 7.0/10
9. [Using latent-agent swarms for math discovery and optimization \[R\]](#item-tech-news-9) ⭐️ 7.0/10
10. [ByteDance Releases Seedream 5.5 With 100-Round Editing](#item-tech-news-10) ⭐️ 7.0/10
11. [OPPO, vivo, Xiaomi, Honor Launch Joint ADV Developer Verification for Android Sideloading](#item-tech-news-11) ⭐️ 7.0/10
12. [EU Digital Fairness Act draft targets addictive design and in-game currency](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Nvidia Board Probes CEO Jensen Huang Over Reported Foreign Intelligence Targeting](#item-finance-news-1) ⭐️ 8.0/10
2. [China NEV Passenger Vehicle Exports Up 138.8% in First Three Quarters of 2026](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [JEPA-Style Tactile Pretraining Outperforms MAE and VAE Reconstruction](https://www.reddit.com/r/MachineLearning/comments/1xs05uo/latent_prediction_beats_reconstruction_for/) ⭐️ 9.0/10

Robbyant released LingBot-Touch, a self-supervised tactile encoder trained JEPA-style to predict latent representations of masked contact rather than reconstruct raw sensor signals, with inference code and checkpoints already public. On tactile-to-video top-5 recall at 1K hours of data, the JEPA approach reached \*\*32.1%\*\* versus \*\*5.6%\*\* for a same-size MAE and \*\*4.4%\*\* for a VAE; at 4K hours JEPA reached \*\*49.3%\*\* while MAE stayed under \*\*9%\*\* and the VAE declined to \*\*3.1%\*\*. The authors attribute the gap to tactile clips being mostly near-zero background, allowing reconstruction loss to shrink without learning contact structure. On 26 real robot tasks with 4 policies, frozen LingBot-Touch features scored highest in \*\*89 of 104\*\* policy-and-task combinations, and on a magnetic hand unseen during pretraining LingBot-VLA improved from \*\*57.21\*\* to \*\*75.04\*\*.

reddit · r/MachineLearning · /u/Zealousideal-War7154 · Nov 9, 18:52

**「Background」** Self-supervised pretraining for tactile sensing has largely followed reconstruction-based objectives such as MAE and VAE, which learn by regenerating masked or compressed sensor input. JEPA-style methods instead predict the latent representation of masked content, a distinction that matters when the input signal is sparse and mostly inactive.

**「Impact」** Practitioners can reuse the released checkpoints as frozen feature extractors, since frozen encoder features outperformed alternatives in most evaluated policy and task combinations, and the same shared Transformer handles magnetic, piezoresistive, and visuotactile sensors via canonical fingertip coordinates with 5D RoPE. Two implementation details are worth copying: the masking ratio warms up from \*\*40%\*\* to \*\*80%\*\* over \*\*300\*\* steps, because starting at high masking hid every contacting taxel in sparse signals and caused gradient explosions. The Tiny model plateaus around 4K hours while Small keeps improving, so scaling data and model size is the indicated next step rather than a settled result.

**Tags**: `#Tactile Sensing`, `#Self-supervised Learning`, `#Robotics`, `#Multimodal Learning`, `#Transformer`

---

<a id="item-tech-news-2"></a>
### [Anthropic Releases Claude Fable 5.2 and Mythos 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) ⭐️ 8.0/10

Anthropic released Claude Fable 5.2 and Mythos 5.2, a new pair of flagship models drawing substantial community discussion. Early user reports describe strong coding performance, including one claim that Fable 5.2 sped up computational materials science work on an esoteric 600,000-line Fortran codebase by 36 times in two days. However, the published benchmark comparisons are contested: commenters question why Fable xHigh was stacked against Carbon Med, why Carbon&\#x27;s effort-intelligence curve diverges from other benchmarks, why the cyber-focused Carbon was omitted from the sole cyber benchmark comparison, and why the robodojo comparison switched to Argon. Hands-on impressions remain anecdotal, and no independent verification of the performance claims is available.

hackernews · lairv · Nov 9, 18:01 · [Discussion](https://news.ycombinator.com/item?id=50429068)

**「Background」** Anthropic released Fable 5.2 and Mythos 5.2 as two configurations of the same new large language model, according to the accompanying system card. Fable 5.2 is the general-use variant, carrying additional safeguards that block certain high-risk, dual-use tasks in biology and cybersecurity, while Mythos 5.2 is the less-restricted configuration. The launch is Anthropic&\#x27;s first frontier-model release since CEO Dario Amodei publicly called for slowing down frontier AI development.

**「Practical implications」** Anthropic&\#x27;s benchmark table places Fable 5.2 ahead of OpenAI&\#x27;s GPT-6 Astra and Google&\#x27;s Gemini 4 Carbon, though community commenters questioned the methodology behind some comparisons \(e.g., why Carbon was left off a cyber benchmark\). Fable 5.2 can act as an Advisor or Orchestrator, delegating simpler tasks to smaller models, which changes how teams might structure multi-model pipelines. One commenter reported Fable 5.2 exhausted a 5-hour token budget in 30 minutes during a code review, a cost consideration for heavy users.

**「Community Discussion」** Commenters reported diverging experiences: one said a code review of an in-browser machine vision project consumed a five-hour token budget in 30 minutes while flagging seven serious bugs, and another found Fable 5.2 hard to distinguish from Opus 5.5 for ordinary coding tasks unless prompts were pushed to be more ambitious. Several users also questioned the benchmark methodology, asking why Carbon was excluded from the cyber benchmark and why comparisons switched models for robodojo, while one speculated the 5.2 rather than 5.5 numbering reflects Anthropic reserving a stronger release against a possible competing model.

<details><summary>References</summary>
<ul>
<li><a href="https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf">Claude Fable 5.2 &amp; Claude Mythos 5.2 System Card</a></li>
<li><a href="https://www.cnbc.com/2026/11/09/anthropic-claude-fable-5-2-mythos-5-2.html">Anthropic releases Claude Fable 5.2 and Claude Mythos 5.2 ...</a></li>
<li><a href="https://officechai.com/ai/fable-5-2-benchmarks/">Anthropic Launches Fable 5.2 &amp; Mythos 5.2, Beats Gemini 4 ...</a></li>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-2">Introducing Claude Fable 5.2 and Claude Mythos 5.2 \ Anthropic</a></li>

</ul>
</details>

**Tags**: `#artificial-intelligence`, `#anthropic`, `#language-models`, `#model-release`, `#benchmarks`

---

<a id="item-tech-news-3"></a>
### [Google Announces TPU 8tx and TPU 8i Max for Agentic AI Workloads](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/) ⭐️ 8.0/10

Google announced two new Tensor Processing Unit chips, the TPU 8tx and TPU 8i Max, targeting agentic AI workloads. According to a secondary relay of Bloomberg&\#x27;s reporting, the 8tx is aimed at government agencies and tightly regulated industries handling sensitive or classified data and will work alongside AMD chips, while the 8i Max targets very long context window AI applications by integrating two TPU chips in a single package for more compute and memory capacity. Google is breaking from its previous cadence of roughly one new processor every two years by expanding the TPU line with scenario-specific chips in a single year. No independent benchmark data, watt-per-token or dollar-per-token figures, pricing, or availability dates are included in the supplied material, and the technical details beyond those described are not verified.

hackernews · \_benx\_ · Nov 9, 21:56 · [Discussion](https://news.ycombinator.com/item?id=50432831)

**「Background」** TPU 8tx and 8i Max are additions to Google&\#x27;s eighth-generation Tensor Processing Unit lineup. Google Cloud says the two chips bring the company to \*\*four new TPU systems in a single year\*\*, departing from its earlier roughly every-other-year cadence for new processors. Reporting on the announcement describes TPU 8tx as aimed at secure enterprise and AI workloads, and TPU 8i Max as aimed at higher-capacity inference and large-context applications, with one report saying 8i Max doubles HBM bandwidth to address the memory wall.

**「Impact」** For teams already running on Google Cloud, the 8tx is positioned for workloads handling sensitive or classified data, while the 8i Max targets very large context windows by packaging two TPU dies in one package; both are therefore tied to Google Cloud rather than sold as standalone hardware, which a commenter explicitly asked about. No independent benchmark, watt/token, or dollar/token figures have been verified, so performance and cost comparisons to Nvidia equivalents remain unquantified in the supplied material, and prospective users cannot yet evaluate price-performance from published data.

**「Community Discussion」** Commenters pressed on missing details rather than treating the announcement as settled: one asked where the watt/token and dollar/token figures are and how each chip compares to NVIDIA&\#x27;s price equivalent, and another asked why Google does not simply sell the chips. A separate thread of discussion pointed to Google&\#x27;s TPUSync material as recommended reading, describing it as the approach behind open-source projects such as Strata for Qwen-series models, while one commenter noted that the most powerful TPU available in Google Colab remains v6e-1, which they consider too small for serious work.

<details><summary>References</summary>
<ul>
<li><a href="https://cloud.google.com/blog/topics/ai-infrastructure/tpu-8tx-and-tpu-8i-max">Introducing TPU 8tx and TPU 8i Max | Google Cloud Blog</a></li>
<li><a href="https://www.datacenterknowledge.com/data-center-chips/google-adds-tpu-8tx-8i-max-for-enterprise-ai">Google Adds TPU 8tx, 8i Max for Enterprise AI</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/10/news-google-marks-first-ever-4-tpu-year-with-8tx-and-8i-max-as-8i-max-doubles-hbm-bandwidth-to-tackle-memory-wall/">[News] Google Marks First 4-TPU Year with 8tx and 8i Max, as ...</a></li>

</ul>
</details>

**Tags**: `#tpu`, `#ai-infrastructure`, `#google`, `#hardware`, `#custom-silicon`

---

<a id="item-tech-news-4"></a>
### [e-means: Clustering Algorithm Claiming k-means Gains in One-Tenth the Epochs](https://e-means.github.io/) ⭐️ 7.0/10

A clustering algorithm called e-means is presented at e-means.github.io as outperforming k-means while requiring one-tenth the epochs. The claim is the authors&\#x27; own and has not been externally validated; no source content was available beyond the project page and the Hacker News thread. Community members report independent results: a commenter says adapting the method to an IVF index in the code-daemon project produced a 146x GPU speedup, and another says bulk reindexing in the antfly project was 2.5x faster. The same commenters note the gains are workload-dependent, with one reporting no improvement when substituting it for Lloyd&\#x27;s algorithm in a mesh-relaxation hobby project.

hackernews · porridgeraisin · Nov 9, 18:45 · [Discussion](https://news.ycombinator.com/item?id=50429734)

**「Background」** k-means clustering, long the standard for partitioning data into groups, is typically implemented via Lloyd&\#x27;s algorithm, which iteratively assigns points to centroids and recomputes means until convergence. The project page describes e-means as a modern, robust k-means algorithm developed at Meta FAIR, positioning it as an alternative to that standard approach.

**「Impact」** For teams building vector indexes, the reported gains apply to full bulk rebuilds rather than incremental insertion: the antfly commenter measured 2.5x faster reindexing but said overall insertion times changed little because incremental clustering is a small share of CPU time. The mesh-relaxation attempt that showed no improvement suggests the method&\#x27;s advantage depends on the cost of repeated passes over a large dataset; a production adoption should be benchmarked against Lloyd&\#x27;s algorithm on the specific workload before replacing it.

**「Community Discussion」** Practitioners report workload-specific results rather than a general win: one commenter cites a 146x GPU speedup on an IVF index, another a 2.5x bulk-reindex speedup, while a hobbyist who swapped it for Lloyd&\#x27;s algorithm in spherical mesh relaxation said it was &quot;definitely not better&quot; for that use case. A separate commenter suggests the update rule may be interpretable as expectation maximization with a friction term, noting the centroid is kept within the convex hull.

<details><summary>References</summary>
<ul>
<li><a href="https://e-means.github.io/">Modern optimization and scaling laws for k - means clustering</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#clustering`, `#algorithms`, `#vector-search`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [Show HN: Browser Tool Maps Satellite Passes and Real Imagery](https://www.watched.earth/) ⭐️ 7.0/10

A developer released a Show HN tool called watched.earth that computes every satellite pass over any location in the past 7 days, running SGP4 orbit propagation against the CelesTrak catalog in the browser in roughly half a second. The site draws all ~17,000 tracked objects on the GPU, solving Kepler&\#x27;s equation each frame, and links real Sentinel-2, Landsat, and NASA images from the corresponding passes; it labels a location as &quot;watched&quot; only when a real image exists and does not store the user&\#x27;s location. The author reports validating the pass search against a brute-force check at the poles, the antimeridian, and tiny swaths with zero missed passes, and notes Sentinel-2 timestamps often differ 5-10 minutes from the actual overpass time. The open-source code is on GitHub, and the author is soliciting suggestions for additional data sources.

hackernews · a585gupt · Nov 9, 17:51 · [Discussion](https://news.ycombinator.com/item?id=50428907)

**「Background」** SGP4 is the standard simplified general perturbations model used to propagate two-line element \(TLE\) sets from the CelesTrak catalog into current or past satellite positions, and it is the same algorithm behind many existing trackers. Several open projects already run SGP4 against full catalogs — for example, lumixed/orbital propagates every cataloged object from a CelesTrak and Space-Track snapshot, and azmth tracks more than 15,000 objects with data refreshed every two hours — but they focus on live positions or 3D rendering rather than pairing computed passes with the actual imagery those satellites captured.

**「Community Discussion」** Commenters were broadly positive: one praised the integrated rendering of orbits, aperture ground tracks, and pass time series, while a self-identified geospatial professional said the ability to see the exact image captured by a satellite sets it apart from other satellite overview sites. One commenter noted the tool is more extensive and easier to access than Copernicus for planning backpacking trips, and another speculated the code may have been largely generated by an AI assistant while crediting the author for knowing what to build.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/lumixed/orbital">lumixed/ orbital : Every catalogued object in Earth orbit , propagated in...</a></li>
<li><a href="https://azmth.space/?sat=43573">azmth: Real-Time Satellite Tracker | Live 3D Globe of 15,000+...</a></li>

</ul>
</details>

**Tags**: `#satellite-imagery`, `#geospatial`, `#orbital-mechanics`, `#webgl-gpu-rendering`, `#open-source`

---

<a id="item-tech-news-6"></a>
### [Consumer Gemini Connected Apps Can Send Personal Drive and Gmail Data to Human Reviewers](https://github.com/thisisme6598/gemini_files/) ⭐️ 7.0/10

Consumer Gemini&\#x27;s Connected Apps feature can route users&\#x27; personal Drive files and Gmail content to human reviewers when those apps are explicitly authorized, according to a disclosure raised on Hacker News. Commenters distinguish this from Google Workspace Gemini and Workspace Intelligence, which the linked Workspace knowledge-base page says are not subject to human review. The practical condition is the user grant: once the Gmail or Drive tool is connected, query-triggered data loads fall under consumer terms that permit human annotation, unlike Workspace terms. No source content was supplied beyond the discussion, so the specific scope, retention, and review procedures are not independently confirmed here.

hackernews · gf74918 · Nov 9, 18:24 · [Discussion](https://news.ycombinator.com/item?id=50429426)

**「Background」** Gemini&\#x27;s privacy terms have long distinguished the consumer Gemini apps from Gemini in Workspace. Google&\#x27;s Gemini Apps Privacy Hub states that data from connected Google apps is saved and used under the applicable app and Google privacy policies, including to provide and improve services, while Google&\#x27;s Workspace materials emphasize that organizations retain control over their data. The current report concerns consumer Gemini&\#x27;s connected-app data flows rather than Workspace deployments.

**「Impact」** Users who authorize Connected Apps in consumer Gemini should assume that personal Gmail and Drive content may be retained for up to three years and can survive account deletion, according to reporting on Google&\#x27;s October 2026 policy edit. The clearest action for privacy-sensitive users is to review or revoke Connected Apps authorizations; Workspace accounts remain governed by a separate no-human-review policy, so the risk applies specifically to consumer accounts. Organizations whose employees mix personal Google accounts with corporate devices should treat this as a data-governance concern rather than a Workspace compliance issue.

**「Community Discussion」** Commenters drew the line at workspace versus consumer terms: bri3d argued the issue applies specifically to consumer Gemini with Connected Apps, since Workspace Gemini still claims no human review, while hek2sch said any Gemini or NotebookLM tool with human annotators creates a risk that flagged data is read by reviewers or reused for training. rustyhancock reported a concrete symptom, saying Gemini responses were uncannily tuned to an email that had prompted an enquiry without disclosing that it had read the mail, and EMM\_386 pointed to Google Photos terms as a broader instance of the same concern.

<details><summary>References</summary>
<ul>
<li><a href="https://support.google.com/gemini/answer/13594961?hl=en">Gemini Apps Privacy Hub - Gemini Apps Help</a></li>
<li><a href="https://workspace.google.com/">Google Workspace : Secure Online Productivity &amp; Collaboration Tools</a></li>
<li><a href="https://aiweekly.co/alerts/google-gemini-routes-personal-drive-gmail-to-human-reviewers">Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>
<li><a href="https://topaihubs.com/articles/gemini-s-data-handling-sparks-privacy-concerns-for-ai-users">Gemini&#x27;s Data Handling Sparks Privacy Concerns for AI Users</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#google-gemini`, `#data-governance`, `#human-annotation`, `#consumer-ai`

---

<a id="item-tech-news-7"></a>
### [Claude Fable 5.2 Tops Artificial Analysis at 65, Doubling Cost Per Task](https://artificialanalysis.ai/models/claude-fable-5-2) ⭐️ 7.0/10

Claude Fable 5.2 has posted a score of 65 on Artificial Analysis, the highest recorded on that aggregator so far, according to the report. The headline number comes with a steep cost shift: commenters note that cost per task doubled relative to Fable 5.1 even after a price cut, with output tokens per task rising from 118k \(46k answer / 71k reasoning\) in 5.1 to 274k \(81k answer / 192k reasoning\) in 5.2. The result rests on a single aggregator&\#x27;s methodology, which some readers dispute.

hackernews · theanonymousone · Nov 9, 20:04 · [Discussion](https://news.ycombinator.com/item?id=50431144)

**「Background」** Artificial Analysis is a third-party aggregator that compares models on a composite intelligence score, cost per task, and time per task. It has scored Claude models before: the same aggregator&\#x27;s listing for the prior model, Fable 5.1, is cited in the discussion as the earlier most-expensive entry, which is the comparison point commenters use to measure the reported cost change. The benchmark&\#x27;s methodology is not fully published, a limitation raised by commenters.

**「Cost and Benchmark Caveats for Deployments」** For teams already using Fable 5.1, the reported jump in cost per task and reasoning tokens per task makes Fable 5.2 a materially more expensive choice for comparable marginal intelligence gains, so checking quality on their own workloads before switching is warranted. Because the top score comes from Artificial Analysis&\#x27;s index, which the site describes as a primarily text-based English-language evaluation suite, and commenters note its methodology is not fully published, the 65 score should be treated as one aggregator&\#x27;s measurement rather than an independently confirmed capability. Until other benchmarks or cost-efficiency data appear, treating the benchmark headline as a reason to migrate is premature.

**「Community Discussion」** Several commenters argued the cost increase outweighs the modest benchmark gain, with one calling the jump from Fable 5.1 to 5.2 an &\#x27;insane increase in cost for a modest intelligence increase&\#x27; and another framing Anthropic&\#x27;s pricing as a 100x premium over capable DeepSeek models for a few percent improvement. Others defended the result on different grounds: one reader pointed out that Fable 5.2, especially its low and medium variants, sits on the Pareto frontier between time per task and intelligence. One commenter questioned the credibility of Artificial Analysis itself, noting it is funded by AI labs and does not publish its full method.

**Tags**: `#large-language-models`, `#benchmarks`, `#model-pricing`, `#AI-industry`, `#cost-analysis`

---

<a id="item-tech-news-8"></a>
### [XGBoost Outage Forecast Beats NWS Warning Baseline 2.4×](https://www.reddit.com/r/MachineLearning/comments/1xs4hq8/forecasting_new_power_outages_per_county_hourly_2/) ⭐️ 7.0/10

A Reddit post by /u/CarRepresentative843 presents an hourly, 2-hour-ahead county-level forecast of new power outages for 216 counties in Missouri and Illinois, defined as P\(≥5% of a county&\#x27;s customers newly out in the 6 hours starting 2 hours ahead\). The model is XGBoost trained on HRRR storm variables \(gusts, shear, CAPE, icing, among others\), county-specific facts, current outages, and neighboring-county outages, trained on 2020–2024 and tested on 2025 using HRRR forecasts as issued \(the mean of the last five runs, not observed weather\). On the held-out 2025 test year it reports PR-AUC of 0.094 versus 0.039 for a baseline rate table built from NWS warnings plus the SPC Day 1 outlook, a ratio of roughly 2.4× \(95% bootstrap range 2.0–3.3×, paired over storm days\); at equal alert volume it flags 30% of new outages versus 17% for the baseline, with precision of 15% versus 11% against a 0.5% base rate. The author also reports a transfer test in which a model trained only on Missouri and Illinois caught 31% versus 19% in Iowa, Indiana, and Michigan combined, and states the system has been live since November 1 with every forecast saved for a blind test. These are single-author results on 216 counties, not independently verified.

reddit · r/MachineLearning · /u/CarRepresentative843 · Nov 9, 21:34

**「Background」** The model&\#x27;s input features come from the HRRR \(High-Resolution Rapid Refresh\), a NOAA mesoscale model that is continually updated with timely observations and offers finer spatial resolution than larger-scale models \(tool-1-1, tool-1-3\). The baseline it is compared against combines National Weather Service warnings with the Storm Prediction Center&\#x27;s Day 1 outlook, which provides individual severe-weather probabilities for tornadoes, wind, and hail \(tool-2-1, tool-2-2\). The forecast targets only newly occurring outages, a harder task than predicting outages already underway.

**「Impact」** For weather and emergency-management practitioners, the concrete comparison is that at the same alert volume the model catches nearly twice as many new outage events as an NWS-warning-plus-SPC-outlook baseline, which is the practical operating point for issuing alerts. The author explicitly notes the absolute precision remains low at about 15% against a 0.5% base rate, so any operational use would need to accept a high false-positive rate per alert; reproducibility is supported by the linked write-up, code, and leakage audit, and the live forecasts saved since November 1 are intended for a future blind evaluation.

<details><summary>References</summary>
<ul>
<li><a href="https://courses.ems.psu.edu/meteo361/l1_p5.html">The Rapid Refresh Model | METEO 361: Fundamentals of Mesoscale...</a></li>
<li><a href="https://blog.matthewgove.com/2021/12/24/the-hrrr-weather-model-how-to-add-dramatic-skies-to-your-landscape-photography/">HRRR Tutorial: Add Dramatic Weather to Your Landscape Photography</a></li>
<li><a href="https://daculaweather.com/4_spc_day1_outlook.php">Storm Prediction Center Day 1 Severe Weather Outlook</a></li>
<li><a href="https://spankthestorm.app/storm-tracker">Live Storm Tracker | Real-Time Hail &amp; Tornado... | Spank The Storm</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#weather-forecasting`, `#xgboost`, `#power-outages`, `#applied-ml`

---

<a id="item-tech-news-9"></a>
### [Using latent-agent swarms for math discovery and optimization \[R\]](https://www.reddit.com/r/MachineLearning/comments/1xrunu7/using_latentagent_swarms_for_math_discovery_and/) ⭐️ 7.0/10

A Reddit post describes SwarmEvolve, an open-source framework using swarms of latent-reasoning LLM agents to accelerate math discovery and optimization compared with existing AlphaEvolve-style implementations.

reddit · r/MachineLearning · /u/QileHQ · Nov 9, 15:30

**Tags**: `#LLM agents`, `#evolutionary optimization`, `#math discovery`, `#latent reasoning`, `#open source`

---

<a id="item-tech-news-10"></a>
### [ByteDance Releases Seedream 5.5 With 100-Round Editing](https://seed.bytedance.com/zh/blog/%E7%94%9F%E6%88%90%E6%9B%B4%E7%9C%9F%E5%AE%9E-%E7%99%BE%E8%BD%AE%E7%BC%96%E8%BE%91%E6%9B%B4%E7%A8%B3%E5%AE%9A-seedream-5-5-%E5%8F%91%E5%B8%83) ⭐️ 7.0/10

ByteDance released Seedream 5.5, an image creation model that supports up to 100 consecutive editing rounds on a single work and can natively generate assets with transparent channels. The company says the model also improves image realism and text rendering. ByteDance claims its internal evaluations show the model&\#x27;s usability rate in film/television and office scenarios is more than double that of the previous version. The model is rolling out progressively on Jimeng, Doubao, Doubao Work, and Volcano Ark.

telegram · zaihuapd · Nov 9, 08:34

**「Background」** Seedream 4.0 was ByteDance&\#x27;s earlier image creation model that unified image generation and editing in a single architecture, and its successor, Seedream 5.0 Pro Edit, supported editing with up to 10 reference images while preserving identity, lighting, and color tones. Seedream 5.5 extends that editing line from 10 references to up to 100 rounds of continuous editing on a single work, and adds native transparent-channel output alongside the earlier model&\#x27;s generation and editing capabilities.

**「Impact」** Users of Jimeng, Doubao, Doubao Work, and Volcano Ark will gain access to the model as the rollout reaches each platform, making it worth checking availability per platform rather than assuming immediate access everywhere. The 100-round editing support and transparent-channel output target workflows that require repeated iteration on one image and assets needing transparency, such as compositing or design work.

<details><summary>References</summary>
<ul>
<li><a href="https://www.atlascloud.ai/models/bytedance/seedream-v5.0-pro/edit">Seedream v5.0 Pro Edit (I2I) API Image by BYTEDANCE ...</a></li>
<li><a href="https://seed.bytedance.com/en/seedream4_0">Seedream 4.0</a></li>
<li><a href="https://wavespeed.ai/models/bytedance/seedream-v5.5">Seedream 5.5 Text-to- Image API | WaveSpeed</a></li>

</ul>
</details>

**Tags**: `#image-generation`, `#multimodal-ai`, `#bytedance`, `#model-release`, `#generative-ai`

---

<a id="item-tech-news-11"></a>
### [OPPO, vivo, Xiaomi, Honor Launch Joint ADV Developer Verification for Android Sideloading](https://mp.weixin.qq.com/s/ZiKBASSLzvsZ6WR2AUmFeg) ⭐️ 7.0/10

OPPO, vivo, Xiaomi, and Honor have jointly launched an Android developer identity verification \(ADV\) mechanism for sideloaded apps in mainland China, with mutual recognition of verification results across the four platforms. Apps already registered and listed on the four vendors&\#x27; open platforms are submitted for verification automatically, with no separate application required. Apps that have not completed verification will trigger an &quot;unverified&quot; prompt during sideload installation, requiring users to confirm manually before installation can continue. The announcement does not specify a rollout timeline or enforcement details.

telegram · zaihuapd · Nov 9, 11:44

**「Background」** Android&\#x27;s open sideloading model lets users install APKs from outside official app stores, but it has long lacked a shared way to confirm who authored an app, which sustains problems such as repackaged apps and fraudulent lookalikes. Previous identity checks were fragmented, since each vendor&\#x27;s platform or store maintained its own review process. ADV \(Android Developer Verification\) is the mechanism enabling these four vendors to recognize one another&\#x27;s verification results across devices.

**「Impact」** Developers whose apps are already listed on any of the four OEM open platforms are auto-enrolled and need no separate application, while apps distributed only outside those stores will trigger an &quot;unverified&quot; prompt that users must manually confirm before installation. The mutual recognition of verification results means a developer validated by one of OPPO, vivo, Xiaomi, or Honor is treated as verified by the other three, so a single registration covers all four storefronts — but the source does not specify a rollout timeline, enforcement date, or what happens to sideloaded apps after a user dismisses the warning.

**Tags**: `#Android`, `#Sideloading`, `#Developer Verification`, `#Mobile Security`, `#China Tech`

---

<a id="item-tech-news-12"></a>
### [EU Digital Fairness Act draft targets addictive design and in-game currency](https://www.mlex.com/mlex/articles/2546584/digital-businesses-face-addictive-design-controls-under-draft-eu-consumer-law) ⭐️ 7.0/10

A leaked draft of the EU&\#x27;s Digital Fairness Act would require digital companies to let users disable features that encourage compulsive or excessive use, such as autoplay and consecutive-use rewards. It would also mandate subscription-cancellation buttons, renewal reminders, and human customer support, plus explicit user consent before a free trial converts to a paid subscription. Games aimed at minors would be barred from paid loot boxes, pay-to-win mechanics, and profiling-based advertising, and in-game virtual currency would have to display its real-world monetary value. The European Commission is due to submit the proposal on November 11 alongside a reform of the consumer protection cooperation framework, with fines of up to 6% of global turnover; both proposals require approval from the European Parliament and EU governments before taking effect.

telegram · zaihuapd · Nov 9, 16:42

**「背景」** 《数字公平法案》将建立在欧盟现行消费保护规则之上，例如《不公平商业行为指令》（Unfair Commercial Practices Directive）——该指令已禁止误导性做法，但尚未针对游戏内货币销售或订阅取消等机制作出专门规定。同时，欧盟近年来已就数字服务通过多项法规，包括《数字服务法》（Digital Services Act），该法要求平台提高透明度并应对系统性风险。此次草案的不同之处在于，其直接针对产品设计层面的成瘾机制与暗黑模式，而非仅聚焦平台内容审核义务。

**「Impact」** If adopted as drafted, the rules would reach game developers and subscription-based digital services selling into the EU: virtual currency would need real-money value labeling, and minors-facing games would have to remove paid loot boxes, pay-to-win mechanics, and profiling ads. The measures are only a leaked draft scheduled for Commission submission on November 11 and still require approval by the European Parliament and member states, so compliance obligations are not yet in force.

<details><summary>References</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/09/eu-to-blacklist-ten-manipulative-online-design-traps-leaked-draft-shows">EU to blacklist ten online design &#x27; traps &#x27;, leaked draft shows</a></li>
<li><a href="https://www.socialistsanddemocrats.eu/newsroom/digital-fairness-act-progressive-approach-protect-all-consumers-online">Digital Fairness Act : a progressive... | Socialists and Democrats</a></li>
<li><a href="https://www.linkedin.com/posts/andreslehtmets_the-eu-digital-fairness-act-is-still-taking-activity-7434702617504677889-4tNZ">The EU Digital Fairness Act is still taking shape, but the direction is...</a></li>

</ul>
</details>

**Tags**: `#EU regulation`, `#consumer protection`, `#digital policy`, `#game monetization`, `#dark patterns`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nvidia Board Probes CEO Jensen Huang Over Reported Foreign Intelligence Targeting](https://www.cnbc.com/2026/11/09/jensen-huang-nvidia-exit-prediction-markets.html) ⭐️ 8.0/10

Nvidia&\#x27;s board is investigating CEO Jensen Huang after reports that he was targeted by a &quot;foreign intelligence effort,&quot; and Huang admitted on Sunday to an extramarital affair with a woman U.S. intelligence officials told The New York Times is a spy for China&\#x27;s Ministry of State Security. Nvidia shares fell more than 5% on Monday, while traders on Kalshi put the odds of Huang leaving by 2027 at 17%, and Polymarket traders put the odds of a resignation or ouster by the end of March 2027 at roughly one-in-four.

rss · CNBC Finance · Nov 9, 18:46

**「Background」** Prediction markets let users bet on the outcome of future events, and their prices are treated as rough, speculative signals rather than verified forecasts; Kalshi resolves Huang-departure contracts using Bloomberg information, while Polymarket uses official statements from Nvidia or Huang.

**「Impact」** The investigation and share decline affect Nvidia investors directly, since Huang is the company&\#x27;s long-serving chief executive and its public face.

**Tags**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#national security`, `#prediction markets`

---

<a id="item-finance-news-2"></a>
### [China NEV Passenger Vehicle Exports Up 138.8% in First Three Quarters of 2026](https://finance.sina.com.cn/tech/roll/2026-10-26/doc-iniwpfnc2438186.shtml) ⭐️ 7.0/10

China&\#x27;s exports of new-energy passenger vehicles reached \*\*3.887 million units\*\* in the first three quarters of 2026, up \*\*138.8%\*\* from the same period a year earlier, according to a Sina Finance report relayed on Telegram. Over the same period, domestic retail sales of such vehicles fell \*\*12.8%\*\* year-on-year to \*\*7.758 million units\*\*.

telegram · zaihuapd · Nov 10, 02:56

**「Background」** The report links weaker domestic demand to adjustments to purchase subsidies and purchase-tax incentives, as well as a high sales base in the same period of 2025. In September alone, new-energy passenger vehicle retail sales fell \*\*16.7%\*\* year-on-year and fuel-vehicle sales fell \*\*43%\*\*, making exports a key support for automakers&\#x27; overall volume growth.

**Tags**: `#New Energy Vehicles`, `#China Auto Exports`, `#Automotive Industry`, `#Domestic Demand`, `#Economic Data`

---