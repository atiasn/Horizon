---
layout: default
title: "Horizon Summary: 2026-10-13 (EN)"
date: 2026-10-13
lang: en
---

> From 41 items, 11 important content pieces were selected

---

**Technology News**
1. [Hackers trigger defrost cycles in European supermarket fridges via connected controllers](#item-tech-news-1) ⭐️ 8.0/10
2. [WiFi 7 Router Hacked into a 320 Msps Software-Defined Radio](#item-tech-news-2) ⭐️ 8.0/10
3. [Codex CLI installs a persistent, self-updating background daemon by default](#item-tech-news-3) ⭐️ 7.0/10
4. [Meta launches Muse Wonder AI model to mixed community reception](#item-tech-news-4) ⭐️ 7.0/10
5. [Python 3.15 ships with lazy imports, sampling profiler; 3.10 support can be dropped](#item-tech-news-5) ⭐️ 7.0/10
6. [Looped Diffusion Transformer reuses transformer blocks per denoising step with tunable depth](#item-tech-news-6) ⭐️ 7.0/10
7. [learnc tunes constants in existing C code, improving JPEG and WebRTC VAD results](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic: New anti-distillation defenses cut extracted Claude data by 90-99%](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [中欧就混动、电动汽车贸易达成共识，中方配额不低于其他来源](#item-finance-news-1) ⭐️ 7.0/10
2. [新能源汽车出口退税率由 13% 下调至 9%](#item-finance-news-2) ⭐️ 7.0/10
3. [税务处罚新裁量基准 11 月施行，社保欠缴最高罚 3 倍](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Hackers trigger defrost cycles in European supermarket fridges via connected controllers](https://www.tomshardware.com/tech-industry/cyber-security/unprecedented-cyberattack-cripples-supermarket-fridges-across-europe-as-hackers-activate-automatic-defrosting-delivery-and-store-prices-also-impacted-by-incident) ⭐️ 8.0/10

Hackers remotely activated automatic defrost cycles in supermarket refrigeration systems across Europe, with French retailer Intermarché reporting about 150 stores targeted, according to Reuters, BBC, and Le Monde reporting cited in the source. The attack exploited internet-connected refrigeration controllers, forcing affected stores to shut or shut down refrigerators to prevent food spoilage. Delivery operations and store pricing were also reportedly disrupted. Suspicions among commenters point to known vulnerabilities in aging Danfoss controllers, but the attack method has not been officially confirmed.

hackernews · Zeekaas · Oct 12, 12:16 · [Discussion](https://news.ycombinator.com/item?id=50055304)

**「Background」** Internet-connected supermarket refrigeration controllers have long been prized for remote diagnostics and efficiency savings, but security researchers had already exposed weaknesses in this class of device. Claroty&\#x27;s Team 82 published research on Danfoss AK-SM 800A refrigeration controllers, identifying multiple vulnerabilities in the embedded web management interface — including a hidden &quot;code-of-the-day&quot; authentication mechanism that could bypass login controls and enable remote code execution — and Danfoss subsequently shipped fixes for two of the disclosed flaws affecting the AK-SM 8xxA series.

**「What This Means for Retailers and Facility Operators」** Retailers and facility operators running internet-connected refrigeration controllers should audit which devices are remotely accessible and apply available patches or network segmentation, since attackers can turn routine remote-management features like defrost cycles into a physical outage that forces store closures. Suspicion in community discussion centers on long-serving controllers such as Danfoss models that reached end of support years ago, meaning replacement or isolation—not patching alone—may be required for affected fleets. Separately, the Intermarché incident reportedly involved the theft of personal data belonging to nearly 300,000 customers, so affected shoppers have been warned to stay vigilant for phishing in the coming weeks.

**「Community discussion」** Commenters noted that suspect devices include 15–20-year-old controllers such as the Danfoss SM800 \(end of support 2021\) and SC355 \(end of support 2016\), arguing that thin margins in shift-work retail leave no budget for security reviews or timely hardware replacement. Others pushed back on the assumption that freezers should never be internet-connected, citing vendor pitches for remote diagnosis and cost savings, and one commenter pointed to a similar incident affecting US military commissary freezers in August 2026 that may involve the same Danfoss vulnerability.

<details><summary>References</summary>
<ul>
<li><a href="https://www.claroty.com/team82/research/freeze-the-controller-defrost-the-food-uncovering-vulnerabilities-in-danfoss-refrigeration-controllers">Freeze the Controller , Defrost the Food: Uncovering Vulnerabilities ...</a></li>
<li><a href="https://www.linkedin.com/posts/claroty_team82-activity-7371876691859746816-y04c"># team 82 | Claroty</a></li>
<li><a href="https://infrastructurenews.com.au/story/refrigeration-controller-flaws-threaten-cold-chains">Refrigeration controller flaws threaten cold chains</a></li>
<li><a href="https://www.connexionfrance.com/news/intermarche-cyberattack-affects-nearly-300000-customers/806317">Intermarché cyberattack 2026 : Nearly 300,000 customers&#x27; data stolen...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#IoT`, `#OT-security`, `#embedded-systems`, `#critical-infrastructure`

---

<a id="item-tech-news-2"></a>
### [WiFi 7 Router Hacked into a 320 Msps Software-Defined Radio](https://github.com/h0m3us3r/w1700k-sdr) ⭐️ 8.0/10

A developer has released an open-source project that turns a WiFi 7 router into a software-defined radio receiver capable of 320 Msps, using the router&\#x27;s WiFi chipset and gigabit LAN port for data transfer. The hack repurposes commodity WiFi hardware that costs far less than dedicated SDR equipment, and the code is publicly available on GitHub. The developer previously demonstrated a similar approach on an ESP32 WiFi microcontroller, and commenters note that a 5 GHz variant exists with broader sweep and higher resolution.

hackernews · djfergus · Oct 12, 12:41 · [Discussion](https://news.ycombinator.com/item?id=50055593)

**「What an SDR is and why WiFi hardware matters」** A software-defined radio \(SDR\) replaces dedicated radio circuitry with a general-purpose chip that samples raw radio signals and processes them in software, allowing one device to tune, decode, or monitor many frequency bands. Traditional SDRs capable of high sample rates such as 320 Msps are typically specialized hardware, while cheap consumer WiFi routers already contain wideband RF front-ends and fast ADCs designed to operate at 5 GHz and beyond — hardware that is normally locked to WiFi duties but, once its firmware is bypassed, can be repurposed as a general-purpose receiver. This project follows earlier community efforts to do the same with smaller WiFi chips, such as the developer&\#x27;s own ESP32-based receiver and the Espargos project&\#x27;s ESP32 array.

**「Cheap wideband receiver for RF work」** For RF and hardware enthusiasts, this offers an unusually low-cost path to a 320 Msps receiver at 5 GHz; one commenter notes it is not &\#x27;DC to daylight&\#x27; coverage but knows no cheaper way to get that sample rate. Community members suggest compatible hardware may extend to other boards with the same chipset, such as the Banana Pi R4, though that remains unverified by the project itself.

**「Enthusiast reactions and hardware expansion hopes」** Commenters are largely enthusiastic: yonatan8070 highlights that the same developer previously built an ESP32-based SDR \(eSpDR\) and hopes the technique extends to common WiFi cards so any laptop could double as a budget SDR. ram\_rattle points to espargos.net&\#x27;s ESP32-based work as a related effort, and aftbit calls it the cheapest 320 Msps 5 GHz receiver they know of; alightsoul&\#x27;s speculation that phone FM radio restrictions relate to software-defined radios is presented without evidence.

**Tags**: `#SDR`, `#WiFi 7`, `#RF/hardware hacking`, `#open source`

---

<a id="item-tech-news-3"></a>
### [Codex CLI installs a persistent, self-updating background daemon by default](https://github.com/openai/codex/issues/48195) ⭐️ 7.0/10

OpenAI&\#x27;s Codex CLI reportedly installs an undocumented, self-updating background daemon by default, prompting substantial community criticism and workarounds.

hackernews · whimblepop · Oct 12, 18:29 · [Discussion](https://news.ycombinator.com/item?id=50060694)

**Tags**: `#ai-coding-tools`, `#developer-tools`, `#openai-codex`, `#security-privacy`, `#cli`

---

<a id="item-tech-news-4"></a>
### [Meta launches Muse Wonder AI model to mixed community reception](https://research.meta.ai/blog/muse-wonder) ⭐️ 7.0/10

Meta has announced Muse Wonder, a new AI model published on its research blog, and the launch drew heavy discussion on Hacker News \(306 comments at the time of reporting\). No official source content was available, so Meta&\#x27;s stated claims cannot be summarized here. Early hands-on community testing reported weaker results than the model&\#x27;s benchmark numbers, with one tester saying an image-to-HTML task performed closer to Anthropic&\#x27;s Sonnet or Haiku tier than the top-tier Opus 5.5. The launch also surfaced a separate report of a login issue on the Muse Code site where one user allegedly saw other people&\#x27;s account profiles during authentication.

hackernews · meetpateltech · Oct 12, 16:48 · [Discussion](https://news.ycombinator.com/item?id=50059115)

**「Background」** Muse Wonder is the newest entry in Meta&\#x27;s Muse model line. Horizon&\#x27;s September digest reported Meta introducing Muse as a personal AI agent that executes tasks and projects rather than only answering questions, and the same line&\#x27;s Muse Spark 1.3 — released earlier — was already positioned for long-running agentic, coding, and multi-agent workflows with a 1,048,576-token context window and API pricing of $1.25 per million input tokens and $4.25 per million output tokens. Muse Wonder therefore represents the next step for a family that Meta has been iterating quickly, with Spark 1.2 in August and Spark 1.3 in September according to community testers.

**「What early testers found」** Developers evaluating the model should note that community hands-on tests so far suggest real-world coding and rendering performance may trail the reported benchmark figures; the tester&\#x27;s example comparing Muse Wonder&\#x27;s image-to-HTML output unfavorably to Opus 5.5 is one individual result, not a systematic evaluation. A reported authentication flaw on the Muse Code sign-in page—showing other users&\#x27; profiles—would be a serious privacy concern, but it is a single unverified report and developers may want to exercise caution with that site until confirmed or addressed.

**「Discussion highlights」** Commenter atleastoptimal argued that having three to four companies at the AI frontier is healthier than one dominant lab, reasoning that distributed frontier capability reduces concentration of power and pressure-cooks cooperation on safety. Beyond that debate, the most substantive contributions were individual evaluations—one user&\#x27;s image-to-HTML comparison finding Muse Wonder much worse than Opus 5.5, and Simon Willison running his standard image-generation tests alongside comparisons to earlier Muse versions—which collectively reflect skepticism that the model&\#x27;s benchmarks translate to real-world use.

<details><summary>References</summary>
<ul>
<li><a href="https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/">Introducing Muse : The World’s First Personal AI Agent Built for Everyone</a></li>
<li><a href="https://openrouter.ai/meta/muse-spark-1.3">Muse Spark 1.3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#artificial-intelligence`, `#meta`, `#large-language-models`, `#model-evaluation`, `#industry-news`

---

<a id="item-tech-news-5"></a>
### [Python 3.15 ships with lazy imports, sampling profiler; 3.10 support can be dropped](https://simonwillison.net/2026/Oct/12/python-3-15/) ⭐️ 7.0/10

Python 3.15.0 has been released, with the What&\#x27;s New guide curated by release manager Hugo van Kemenade. Headline features include PEP 810 explicit lazy imports, which defer module loading until imported symbols are first used, and PEP 798 unpacking in comprehensions \(for example \`\[\*sublist for sublist in lists\]\`\), an extension of the PEP 448 syntax from Python 3.5. The release also adds a new sampling profiler, Tachyon \(\`profiling.sampling\`\), alongside the existing tracing profiler now named \`profiling.tracing\`. Independent benchmarking by Miguel Grinberg against the 3.15.0rc3 release found performance mostly unchanged from 3.14, with the exception of the experimental JIT, which delivered a 1.2x speedup over the standard 3.15 interpreter on a Fibonacci test.

rss · Simon Willison · Oct 12, 18:15

**「What came before」** Python follows an annual release cadence, and each October release shifts the support window: with 3.15 out, Python 3.10 reaches the end of the range that open-source maintainers typically cover, freeing them to require 3.11 as a minimum. The lazy-import syntax in 3.15 comes from PEP 810, which was accepted in October 2025 with the goal of cutting startup time, memory use, and unnecessary work for command-line tools, test suites, and apps with large dependency graphs.

**「What this means for maintainers」** With 3.15 released, maintainers of libraries supporting all active Python versions can now drop Python 3.10 support and begin using Python 3.11 features. Lazy imports also address real startup costs: Willison notes his LLM CLI tool had to document manual lazy-loading because plugins using heavy dependencies like sentence\_transformers added multiple seconds to every invocation. Developers upgrading can use \`uv\` \(after upgrading uv itself\) to get Python 3.15, and the sampling profiler can attach to a running process by PID via \`python -m profiling.sampling attach &lt;pid&gt;\`, though Willison reports needing \`sudo\` on macOS.

<details><summary>References</summary>
<ul>
<li><a href="https://peps.python.org/pep-0810/">PEP 810 – Explicit lazy imports | peps.python.org</a></li>

</ul>
</details>

**Tags**: `#python`, `#release-notes`, `#lazy-imports`, `#open-source`, `#programming-languages`

---

<a id="item-tech-news-6"></a>
### [Looped Diffusion Transformer reuses transformer blocks per denoising step with tunable depth](https://www.reddit.com/r/MachineLearning/comments/1x49d61/looped_diffusion_transformer_the_same_blocks_run/) ⭐️ 7.0/10

A paper on arXiv \(2609.40305, posted 30 Sep\) proposes the Looped Diffusion Transformer, which instead of scaling up a text-to-image DiT runs a shared group of transformer blocks several times inside each denoising step. Naive looping reportedly does not reliably help, so the authors add deep supervision on every loop plus self-modulating attention; they claim a 260M looped model beats a model 6.5x larger on several benchmarks while using 4.9x less inference compute, and that at a fixed budget more loop depth helps more than more denoising steps. The B/16 code and weights are MIT-licensed \(weights on Hugging Face under sensenova\), and the poster ran the model on an M5 Pro, training at loop depth 4 with other depths working without retraining. In that hands-on test, most of the image quality change occurred by depth 3, and generation took roughly 23-24 seconds per image at depth 1 versus 43-47 seconds at depth 4.

reddit · r/MachineLearning · /u/Fit-Ant2238 · Oct 12, 18:13

**「Background」** Standard diffusion transformers \(DiTs\) scale image quality by making the network deeper or wider, which raises inference cost on every denoising step. The Looped-DiT paper takes a different route borrowed from looped and recurrent-depth language models: it reuses one shared group of transformer blocks several times within each denoising step, stabilizing this repetition with deep supervision on each loop&\#x27;s prediction and self-modulating attention to regulate feature updates inside the loop. Because the number of loop iterations is a sampling-time setting rather than a fixed architectural property, users can trade compute for refinement per image without retraining the model.

**「Why it matters」** Because loop depth is chosen at sampling time, similar to iteration counts in looped or recurrent-depth language models, users can trade inference compute against per-image refinement without retraining — the poster&\#x27;s measurements show about a 2x runtime difference between depth 1 and depth 4 on an M5 Pro. The headline benchmark results remain paper claims, so the 260M-versus-6.5x-larger comparison has not been independently validated.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2609.40305">[2609.40305] Looped Diffusion Transformer - arXiv.org</a></li>
<li><a href="https://github.com/OpenSenseNova/Looped-DiT">GitHub - OpenSenseNova/Looped-DiT: PyTorch implementation of ...</a></li>

</ul>
</details>

**Tags**: `#diffusion-models`, `#transformers`, `#efficient-inference`, `#text-to-image`, `#machine-learning-research`

---

<a id="item-tech-news-7"></a>
### [learnc tunes constants in existing C code, improving JPEG and WebRTC VAD results](https://www.reddit.com/r/MachineLearning/comments/1x4dlbm/learnc_fit_the_constants_in_existing_c_code_to/) ⭐️ 7.0/10

learnc is an MIT-licensed tool that automatically tunes named constants in unmodified C code against a user-written score function, rewriting the same file with optimized values. On held-out data, tuning the 128 quantization-table entries in stb\_image\_write.h \(trained on 12 Kodak images, tested on the other 12\) yielded a 9.1% BD-rate improvement at equal SSIM, independently verified in libjpeg with scikit-image, versus 2.7% for mozjpeg&\#x27;s tables. Tuning every constant in Google&\#x27;s WebRTC VAD vad\_core.c raised F1 from 0.810 to 0.859 on the LibriParty eval set. Stated limits: no JPEG gain below 1 bpp, and the approach works best for tens to hundreds of constants rather than large weight sets.

reddit · r/MachineLearning · /u/keep\_up\_sharma · Oct 12, 20:51

**「Background」** JPEG encoders compress images using a quantization table of 64 per-channel constants that control how aggressively different frequency coefficients are discarded; these tables are traditionally hand-designed or optimized by specialized offline processes, as with mozjpeg&\#x27;s tuned tables. Similarly, Google&\#x27;s WebRTC voice-activity detector relies on fixed threshold and weight constants in vad\_core.c to decide which audio frames contain speech, with values chosen by its original developers rather than fitted to data.

**「What this means for developers」** C developers can apply learnc \(MIT-licensed\) to tune tens to hundreds of named constants in existing code without rewriting it, since the tool modifies the same source file against a custom C score function. The measured wins — a 9.1% BD-rate improvement over stb\_image\_write.h&\#x27;s JPEG quantization tables \(independently verified in libjpeg with scikit-image, versus 2.7% for mozjpeg&\#x27;s tables\) and F1 rising from 0.810 to 0.859 for Google&\#x27;s WebRTC VAD — suggest projects shipping hardcoded constants in C could gain real performance from data-driven tuning. Caveats: tuning showed no JPEG gain below 1 bpp, the approach is unsuited to large weight sets, and evaluation covered only small image and VAD benchmarks, so teams should validate gains on their own workloads before adopting tuned values.

<details><summary>References</summary>
<ul>
<li><a href="https://prismix.dev/news/dd5fee40b9ef">learnc: fit the constants in existing C code to data (9.1% ...</a></li>
<li><a href="https://github.com/cpuimage/WebRTC_VAD/blob/master/vad/webrtc_vad.c">WebRTC_VAD/vad/webrtc_vad.c at master · cpuimage ... - GitHub</a></li>
<li><a href="https://github.com/dpirch/libfvad/blob/master/src/fvad.c">libfvad/src/fvad.c at master · dpirch/libfvad · GitHub</a></li>

</ul>
</details>

**Tags**: `#C`, `#machine-learning`, `#parameter-tuning`, `#image-compression`, `#open-source`

---

<a id="item-tech-news-8"></a>
### [Anthropic: New anti-distillation defenses cut extracted Claude data by 90-99%](https://www.anthropic.com/research/distillation-defenses) ⭐️ 7.0/10

On October 12, Anthropic reported preliminary evidence that its new defenses against model distillation attacks reduced the amount of data extracted from Claude by roughly 90% to 99%. The measures include restricting the flow of inference outputs across sessions, models, and accounts, deploying two-stage classifiers with ongoing patching of bypass techniques, and banning tens of thousands of involved accounts, some within two hours of an attack. Anthropic claims a false-positive rate below 0.1%, but some developers need to update their integrations, and blocked requests may still be billed.

telegram · zaihuapd · Oct 13, 01:25

**「Background: What distillation attacks are」** Model distillation attacks involve sending requests to a model as a normal user would and training a competing model on its responses, which is why Anthropic&\#x27;s defenses focus on making Claude&\#x27;s reasoning tokens harder for attackers to access at scale \(tool-2-2\). The company says this early anti-distillation work began with simpler measures against such passive extraction, and the newly reported two-stage classifiers, cross-session output restrictions, and account bans represent an escalation of that effort \(tool-2-2, tool-2-1\). One third-party report on the announcement ties a distillation campaign against Claude to Alibaba&\#x27;s Qwen, though that attribution comes from Anthropic&\#x27;s account of the campaign \(tool-2-3\).

**「What This Means for Developers」** Developers building on the Claude API may need to update their integrations to comply with the new restrictions, such as cross-session output limits and two-stage classifier screening, and requests blocked as suspected distillation may still be billed. Legitimate users face low disruption risk, as Anthropic reports a false-positive rate below 0.1%, though tens of thousands of accounts have been banned, some within two hours of initiating an attack. These figures are self-reported and preliminary, so real-world effects on legitimate workflows are not independently verified.

<details><summary>References</summary>
<ul>
<li><a href="https://www.explainx.ai/blog/anthropic-distillation-defenses-preserved-thinking-classifier-90-99-percent-2026">Anthropic Distillation Defenses: 90-99% Less Data Stolen ...</a></li>
<li><a href="https://www.anthropic.com/research/distillation-defenses">Strengthening our defenses against distillation attacks</a></li>
<li><a href="https://cryptobriefing.com/anthropic-claude-distillation-attack-defenses/">Anthropic says new defenses cut distillation data harvested ...</a></li>
<li><a href="https://www.anthropic.com/research/distillation-defenses">Strengthening our defenses against distillation attacks</a></li>
<li><a href="https://www.explainx.ai/blog/anthropic-distillation-defenses-preserved-thinking-classifier-90-99-percent-2026">Anthropic Distillation Defenses: 90-99% Less Data Stolen ...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#model distillation`, `#Anthropic`, `#model protection`, `#abuse detection`

---

## Financial News

<a id="item-finance-news-1"></a>
### [中欧就混动、电动汽车贸易达成共识，中方配额不低于其他来源](https://www.mofcom.gov.cn/xwfb/sjfzrfb/art/2026/art_4d502e1d49fd4480b39a6cfd0d752038.html) ⭐️ 7.0/10

China&\#x27;s Commerce Ministry says China and the EU reached consensus under their trade consultation mechanism on hybrid and EV trade, with Chinese quotas no less favorable than other import sources and EU price-undertaking reviews to continue.

telegram · zaihuapd · Oct 12, 06:19

**Tags**: `#China-EU trade`, `#electric vehicles`, `#trade policy`, `#hybrid vehicles`, `#WTO`

---

<a id="item-finance-news-2"></a>
### [新能源汽车出口退税率由 13% 下调至 9%](https://www.news.cn/20261012/9709731f470b42f9a84825c2e4eb914b/c.html) ⭐️ 7.0/10

China&\#x27;s finance and tax ministries announced that NEV VAT export rebates will fall from 13% to 9% effective April 1, 2027.

telegram · zaihuapd · Oct 12, 11:00

**Tags**: `#export tax policy`, `#new energy vehicles`, `#fiscal policy`, `#China`

---

<a id="item-finance-news-3"></a>
### [税务处罚新裁量基准 11 月施行，社保欠缴最高罚 3 倍](https://fgk.chinatax.gov.cn/zcfgk/c100012/c5252754/content.html) ⭐️ 7.0/10

China&\#x27;s State Taxation Administration will implement the 2026 national tax penalty discretion benchmarks on November 1, 2026, adding employer social insurance underpayment as a punishable offense with fines up to three times the unpaid amount.

telegram · zaihuapd · Oct 13, 02:45

**Tags**: `#China tax policy`, `#social insurance`, `#regulatory enforcement`, `#employer compliance`, `#State Taxation Administration`

---