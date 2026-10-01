---
layout: default
title: "Horizon Summary: 2026-10-01 (EN)"
date: 2026-10-01
lang: en
---

> From 41 items, 12 important content pieces were selected

---

**Technology News**
1. [Google Announces Gemini 4 Argon, Limited to Early Testers for Now](#item-tech-news-1) ⭐️ 9.0/10
2. [Edison Design Group open-sources its C++ compiler front-end on GitHub](#item-tech-news-2) ⭐️ 8.0/10
3. [Community Survey Claims Comprehensive Coverage of Tokenization in Modern NLP](#item-tech-news-3) ⭐️ 7.0/10
4. [CO₂Jump: self-correcting sampler improves text-image consistency in concurrent generation](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek open-sources Ascend-adapted AI infrastructure components for Huawei chips](#item-tech-news-5) ⭐️ 7.0/10
6. [Cloudflare announces plan to become a public certificate authority](#item-tech-news-6) ⭐️ 7.0/10
7. [Kimi K3 available in OpenAI Codex via Baseten under existing OpenAI enterprise billing](#item-tech-news-7) ⭐️ 7.0/10
8. [Reddit Reportedly Ending RSS Feeds and Public API Access](#item-tech-news-8) ⭐️ 7.0/10
9. [OpenAI Disrupts Model Distillation Campaign, Links It to Moonshot AI Personnel](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [Kalshi and Polymarket trading volumes draw wash-trading scrutiny](#item-finance-news-1) ⭐️ 7.0/10
2. [Beijing warns of retaliation if EU restricts Chinese businesses](#item-finance-news-2) ⭐️ 7.0/10
3. [China reportedly tightens IPO criteria for humanoid robot startups](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Announces Gemini 4 Argon, Limited to Early Testers for Now](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/) ⭐️ 9.0/10

Google has announced Gemini 4 Argon, a new frontier model presented as having advanced agentic capabilities; the announcement includes the claim that Argon agents are already working on migrating C/C++ codebases to Rust across Google. The main caveat is availability: Google says it will continue gathering feedback from early testers while iterating on guardrails before making Argon available to developers, enterprises, and consumers &\#x27;as soon as possible,&\#x27; and no general availability date appears in the supplied material. The agentic capability claims are vendor-reported and community-discussed rather than backed by independent benchmarks or detailed technical documentation in the source content.

hackernews · bradleyg223 · Sep 30, 20:04 · [Discussion](https://news.ycombinator.com/item?id=49913571)

**「Gemini 4 Argon in context」** Google&\#x27;s Gemini line is the company&\#x27;s family of frontier large language models, and the September 30, 2026 announcement positions Argon as Alphabet&\#x27;s most advanced model yet, targeting complex software engineering, professional legal and finance work, and cyber defense with a 1 million token context limit. The announcement is not a general-availability release: Google states it will keep gathering feedback from early testers and iterating on guardrails before making Argon available to developers, enterprises, and consumers.

**「Not yet usable by developers」** For developers and enterprises, Argon&\#x27;s reported capabilities are currently a plan rather than a usable product: Google says it will keep gathering early-tester feedback and iterating on guardrails before making the model available to developers, enterprises, and consumers, so teams cannot yet benchmark it against their own coding or security workloads. Until general access opens, adoption decisions rest on secondhand figures — DataCamp, for example, reports a $2/$10 per million token launch price, a 1M-token output limit, and leading results on the Vals Index and DeepSWE v1.1 — and teams should treat these as unverified until they can test the model themselves.

**「Community Reaction」** Commenters debated what the staggered release signals about competition: one argued that the continued leapfrogging among frontier labs contradicts Dario Amodei&\#x27;s &\#x27;winner-takes-all&\#x27; theory of &\#x27;concentrating,&\#x27; while another quipped that leaving Argon in early testing reinforces Google&\#x27;s &\#x27;can&\#x27;t release a model&\#x27; reputation. Separately, one user reported that the existing Gemini 3.8 flash attached GDB to a GPU driver and wrote an LD\_PRELOAD C shim to fix a ROCm/llama.cpp setup, speculating they had been routed to an unreleased model under test — a personal anecdote and speculation, not a documented Argon capability.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/">Introducing Gemini 4 Argon</a></li>
<li><a href="https://www.gptunnel.ru/en/blog/gemini-4-argon">Gemini 4 Argon : what Google &#x27;s new model changes · GPTunneL</a></li>
<li><a href="https://www.cnbc.com/2026/09/30/google-gemini-4-argon-ai.html">Google rolls out Gemini 4 Argon , its most advanced model</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/">Introducing Gemini 4 Argon - The Keyword</a></li>
<li><a href="https://www.datacamp.com/blog/gemini-4-argon">Gemini 4 Argon: Benchmarks, Pricing, and Access | DataCamp</a></li>

</ul>
</details>

**Tags**: `#AI`, `#large-language-models`, `#Google Gemini`, `#machine learning`, `#AI industry`

---

<a id="item-tech-news-2"></a>
### [Edison Design Group open-sources its C++ compiler front-end on GitHub](https://edgcpp.org/#transition) ⭐️ 8.0/10

The Edison Design Group \(EDG\) has published the source code of its C++ compiler front-end on GitHub at github.com/edgcpp/compiler, with a transition announcement at edgcpp.org and online documentation. The front-end is a decades-old, highly standards-conformant component that compiler and tool vendors have long licensed commercially, reportedly including Microsoft, which uses it for Visual C++&\#x27;s IntelliSense rather than its own front-end. Per community comments, the code is released under Apache-2.0 with the LLVM exception, the repository preserves commit history dating back to 1990, and the announcement does not state that EDG the company is winding down, which commenters consider the likely reason for open-sourcing it.

hackernews · iandinwoodie · Sep 30, 19:26 · [Discussion](https://news.ycombinator.com/item?id=49913192)

**「About Edison Design Group」** Edison Design Group \(EDG\) is an American company that builds compiler front ends — the preprocessing and parsing stages of a compiler — for C++, and formerly for Java and Fortran. Rather than shipping its own end-user compiler, EDG licensed these front ends to commercially available compilers and code-analysis tools, which is why the code was long known in the industry without ever being publicly available.

**「Open access, uncertain maintenance」** Teams building C++ tools that previously had to negotiate a commercial EDG license can now inspect, fork, and integrate the front-end under a permissive license. However, organizations whose products depend on EDG support or updates should assess continuity plans, since the company is reportedly winding down and no long-term maintainer for the open-source project is confirmed.

**「What commenters flagged」** In the most substantive comment, jabl noted that the announcement omits that EDG the company is winding down, calling that the likely motive for the release and citing Wikipedia and a November 2025 Herb Sutter trip report as context. Other commenters focused on what the code enables: trebligdivad highlighted the unusually complete commit history reaching back to 1990, and badsectoracula speculated about using its source-to-source compilation to transpile C++ libraries into other languages.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Edison_Design_Group">Edison Design Group - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#C++`, `#compilers`, `#open-source`, `#language-tooling`, `#Edison-Design-Group`

---

<a id="item-tech-news-3"></a>
### [Community Survey Claims Comprehensive Coverage of Tokenization in Modern NLP](https://www.reddit.com/r/MachineLearning/comments/1wuccjf/tokenization_a_survey_for_modern_nlp_r/) ⭐️ 7.0/10

A Reddit post on r/MachineLearning announces a survey titled &quot;Tokenization: A Survey for Modern NLP,&quot; which its authors describe as the field&\#x27;s most comprehensive treatment of tokenization, hosted at alphaxiv. According to the post, roughly 32 tokenizer researchers spent about eight months on the effort, covering tokenization algorithms, evaluation, multilinguality, encodings, and theory, as well as potential alternatives such as latent and visual tokenization. The survey also reportedly addresses adjacent topics including constrained generation, token healing, and tokenizer security concerns. These claims about scope, authorship, and effort come from the community post itself and are not independently verified by the supplied content.

reddit · r/MachineLearning · /u/mcmcmcmcmcmcmcmcmc\_ · Sep 30, 18:13

**「Background」** Tokenization is the step that converts raw text into the discrete units a language model actually reads, and decisions made here ripple through model behavior in areas like multilingual coverage and tokenizer-level security risks, which is why alternatives such as latent or visual tokenization have attracted research interest. The survey is being shared via alphaXiv, a platform for exploring trending arXiv papers and following discussions around them.

**「Impact」** If the survey delivers on its stated scope, NLP researchers and practitioners get a single reference consolidating scattered tokenization knowledge, including how tokenizers are evaluated, where multilingual weaknesses arise, and which security concerns are documented. Teams weighing tokenizer design choices or tokenizer-free alternatives such as latent or visual tokenization could use the linked alphaxiv paper as a starting point.

<details><summary>References</summary>
<ul>
<li><a href="https://www.alphaxiv.org/">Explore | alphaXiv</a></li>

</ul>
</details>

**Tags**: `#tokenization`, `#NLP`, `#survey`, `#language-models`, `#tokenizer-security`

---

<a id="item-tech-news-4"></a>
### [CO₂Jump: self-correcting sampler improves text-image consistency in concurrent generation](https://www.reddit.com/r/MachineLearning/comments/1wtyl5m/concurrent_image_understanding_and_generation/) ⭐️ 7.0/10

Researchers from Google, Google DeepMind, and Stony Brook University shared a NeurIPS 2026 paper introducing CO₂Jump, a training-free sampling method that improves consistency when a model produces a text answer and an image at the same time, such as describing a maze&\#x27;s solution while drawing its path. During sampling, CO₂Jump uses text-token confidence and cross-modal attention to guide image updates and re-masks low-confidence tokens so earlier decisions can be revised; it runs one model forward pass per denoising step and requires no additional sampler training, with all comparisons made on the same task-specific fine-tuned model. The authors evaluated image editing plus maze solving and nonograms, where joint accuracy requires both the textual answer and the generated image to be correct, and introduced three datasets: JEdit-1M, JMaze-200K, and JNono-200K; they report that across 8–512 sampling steps CO₂Jump was the only sampler they compared that improved monotonically on both editing quality and grounding. The evidence so far is the authors&\#x27; own Reddit post, which shows no quantitative results or independent evaluation, so the monotonic-improvement claim remains an author claim rather than an externally verified result.

reddit · r/MachineLearning · /u/Upstairs\_Theme2785 · Sep 30, 07:28

**「Masked diffusion models and the consistency gap」** CO2Jump operates on masked diffusion models \(MDMs\), which generate text and images together by iteratively denoising tokens of both modalities in one model, an approach the paper motivates by the observation that human cognition does not separate understanding from generation, as when a teacher speaks and draws at a whiteboard simultaneously. Per the paper&\#x27;s July 2026 arXiv preprint, existing MDM samplers either decode text and image interleavedly or update the two modalities independently, so nothing in sampling forces them to agree, which is what allows a model to describe one maze solution while drawing a different path.

**「Practical impact」** Teams already running joint text-image generation models can try CO2Jump at inference time without retraining, since the sampler is training-free and keeps the cost to one model forward pass per denoising step, and they can measure text-image consistency with the newly released JEdit-1M, JMaze-200K and JNono-200K benchmarks; JNono-200K alone contains 200,000 synthetic nonogram puzzles where both the textual answer and the generated image must be correct. The project page and a Hugging Face paper page are now live, with the latter reporting the method&\#x27;s best joint performance on editing and visual reasoning tasks. Because the reported gains come from the authors&\#x27; own evaluations using one task-specific fine-tuned model per task, practitioners should validate the sampler on their own model families and workloads before relying on it.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2607.13188">[2607.13188] Concurrent Image Understanding and Generation ...</a></li>
<li><a href="https://www.emergentmind.com/topics/jnono-200k">JNono - 200 K : Multimodal Nonogram Benchmark</a></li>
<li><a href="https://huggingface.co/papers/2607.13188">Paper page - Concurrent Image Understanding and Generation...</a></li>
<li><a href="https://coupled-jump.github.io/">Concurrent Image Understanding and Generation: Self-Correcting...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#generative-models`, `#multimodal-ai`, `#markov-jump-processes`, `#research-paper`

---

<a id="item-tech-news-5"></a>
### [DeepSeek open-sources Ascend-adapted AI infrastructure components for Huawei chips](https://mp.weixin.qq.com/s/X41mKH4Ds-VXUAnK6M8Eww) ⭐️ 7.0/10

On September 30, 2026, DeepSeek open-sourced Ascend-adapted versions of its core AI infrastructure components, porting its NVIDIA-platform software stack to Huawei&\#x27;s Ascend hardware. The release covers TileLang high-level compiler tooling, the DeepGEMM compute library, the DeepEP distributed communication library, TileKernels, FlashMLA, and DeepSelect. DeepSeek states the components perform close to hardware limits in multiple tests and that it is working with Huawei on a 128-card Ascend 950 supernode solution; these are the company&\#x27;s own claims reported via a secondary repost, not independently measured results.

telegram · zaihuapd · Sep 30, 03:09

**「Background」** FlashMLA, DeepGEMM, and DeepEP are components of the open-source infrastructure stack DeepSeek previously released for NVIDIA&\#x27;s CUDA platform: FlashMLA provides optimized attention kernels, and DeepGEMM is a compact matrix-multiplication library that its repository describes as matching or exceeding expert-tuned alternatives. The new Ascend release mirrors those GPU components one-for-one on Huawei&\#x27;s NPU platform, and the FlashMLA repository now describes the library as powering inference of the DeepSeek-V4.1 model on both NVIDIA GPUs and Huawei Ascend NPUs.

**「Impact for developers on Ascend」** Teams running DeepSeek workloads on domestic Chinese accelerators can now target the company&\#x27;s newest model directly: Huawei says its Ascend 950 PR and 950 DT chips received day-zero adaptation for DeepSeek&\#x27;s V4 model at launch, removing the wait for hand-ported kernels before a new DeepSeek release becomes usable. Engineers evaluating the newly open-sourced Ascend stack should treat the &quot;near hardware limits&quot; performance figures as DeepSeek&\#x27;s own, independently unverified claims and benchmark the components against their own workloads before committing production deployments.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/deepseek-ai/FlashMLA">GitHub - deepseek-ai/FlashMLA: FlashMLA: Efficient Multi-head ...</a></li>
<li><a href="https://github.com/deepseek-ai/DeepGEMM">GitHub - deepseek-ai/DeepGEMM: DeepGEMM: clean and efficient ...</a></li>
<li><a href="https://www.qbitai.com/2026/09/499263.html">DeepSeek官方开源昇腾基础组件，与昇腾共建高效易用的AI芯片软件生态</a></li>
<li><a href="https://www.scmp.com/tech/big-tech/article/3351349/huawei-deepseek-strengthen-chinas-ai-self-reliance-collaboration-v4-model">Huawei , DeepSeek strengthen China’s AI self-reliance with...</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#Huawei-Ascend`, `#open-source`, `#AI-hardware`, `#ML-systems`

---

<a id="item-tech-news-6"></a>
### [Cloudflare announces plan to become a public certificate authority](https://blog.cloudflare.com/cloudflare-certificate-authority/) ⭐️ 7.0/10

Cloudflare announced plans to enter the public certificate authority business, stating it has applied to join the Chrome, Apple, Microsoft, and Mozilla root programs and has signed an agreement with GlobalSign to acquire a widely trusted root certificate. The planned CA will prioritize ACME-based automated issuance and renewal, and Cloudflare intends to begin issuing production-grade Merkle Tree Certificates \(MTC\) in the first quarter of 2027, a format aimed at supporting post-quantum web security. The effort remains at the announcement stage: no certificates have been issued yet, and inclusion in the root programs is still pending.

telegram · zaihuapd · Sep 30, 06:26

**「Background」** A website&\#x27;s TLS certificate is trusted by default only if its issuer is included in the root certificate programs maintained by browser and operating-system vendors—Chrome, Apple, Microsoft, and Mozilla—so Cloudflare&\#x27;s applications to all four are the entry requirement for public trust. To avoid starting from an untrusted root, Cloudflare has signed a definitive agreement to acquire a GlobalSign root that has been trusted since 2012. Its planned issuance model is ACME-only, requiring client support for ARI renewal signaling \(RFC 9773\), the automated issuance path that has become standard for web certificates.

**「Impact for site operators and developers」** Once Cloudflare&\#x27;s applications to the Chrome, Apple, Microsoft, and Mozilla root programs are accepted, site operators gain another fully automated, ACME-first option for TLS issuance, and from Q1 2027 the CA plans production-grade Merkle Tree Certificates as a post-quantum-ready choice. Because no certificates have been issued yet and trust hinges on root program inclusion, organizations should not move certificate issuance to the new CA until acceptance is confirmed and should check that their clients can handle the new Merkle Tree certificate format before adopting it.

<details><summary>References</summary>
<ul>
<li><a href="https://ppc.land/cloudflare-targets-q1-2027-for-its-first-quantum-safe-web-certificates/">Cloudflare targets Q1 2027 for its first quantum-safe web certificates</a></li>
<li><a href="https://www.captaindns.com/en/blog/cloudflare-certificate-authority-acme-ari">Cloudflare wants to become a certificate authority (CA)</a></li>
<li><a href="https://www.cloudflare.com/press/press-releases/2026/cloudflare-announces-public-certificate-authority-for-the-post-quantum-web/">Cloudflare Announces Public Certificate Authority for the ...</a></li>
<li><a href="https://www.helpnetsecurity.com/2026/09/30/cloudflare-certificate-authority-2027/">Post-quantum website certificates from Cloudflare are ...</a></li>

</ul>
</details>

**Tags**: `#cloudflare`, `#certificate-authority`, `#tls`, `#web-pki`, `#post-quantum`

---

<a id="item-tech-news-7"></a>
### [Kimi K3 available in OpenAI Codex via Baseten under existing OpenAI enterprise billing](https://36kr.com/newsflashes/4005691489112198) ⭐️ 7.0/10

Baseten, a US AI infrastructure company, announced that enterprise users can run Moonshot AI&\#x27;s Kimi K3 inside OpenAI&\#x27;s Codex coding tool, with usage charges billed directly against the enterprise&\#x27;s existing OpenAI purchase commitments and no new vendor procurement process required. As reported by 36kr, the company frames this as Kimi K3 entering the mainstream paid settlement channel for OpenAI&\#x27;s enterprise customers, and as the first time a Chinese open-source model has entered this procurement system. The item is a brief single-source newsflash with no primary announcement link or technical specifics, so the integration&\#x27;s mechanics and scope rest on Baseten&\#x27;s claim as relayed by the report.

telegram · zaihuapd · Sep 30, 11:23

**「Background」** OpenAI Codex is the company&\#x27;s coding agent aimed at enterprise developers, and what makes this integration notable is that usage in Codex is billed directly against the OpenAI procurement commitments customers have already signed, removing the usual need to run a new vendor procurement process. The enabling mechanism is Baseten&\#x27;s announced partnership with OpenAI, under which the US inference provider serves open-weight models natively through Codex and the Responses API on US-based infrastructure with zero data retention for all prompts. Kimi K3, the model now entering this channel, is a 2.8T-parameter open-weight multimodal reasoning model from Moonshot AI, listed on OpenRouter at roughly $1.03 per million input tokens and $9.04 per million output tokens.

**「No new procurement needed for enterprises」** Enterprises with existing OpenAI agreements can now run Kimi K3 inside Codex — or call it via the Responses API — with usage billed against their existing OpenAI commitments, so adopting the model no longer requires setting up a new vendor relationship or procurement process. Baseten&\#x27;s announcement confirms this applies to the open models it serves in the OpenAI B2B Marketplace, with Kimi K3 reported as the first Chinese open-source model to enter this billing channel.

<details><summary>References</summary>
<ul>
<li><a href="https://www.baseten.co/blog/baseten-openai-partnership/">Announcing our partnership with OpenAI</a></li>
<li><a href="https://openrouter.ai/moonshotai/kimi-k3">Kimi K 3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://www.baseten.co/blog/baseten-openai-partnership/">Announcing our partnership with OpenAI - baseten.co</a></li>
<li><a href="https://phemex.com/news/article/kimi-k3-becomes-first-chinese-model-in-openai-enterprise-billing-via-codex-integration-98316">Kimi K3 Joins OpenAI Codex: First Chinese Model in ... - Phemex</a></li>

</ul>
</details>

**Tags**: `#OpenAI Codex`, `#Kimi K3`, `#enterprise AI procurement`, `#open-source models`, `#AI industry`

---

<a id="item-tech-news-8"></a>
### [Reddit Reportedly Ending RSS Feeds and Public API Access](https://techcrunch.com/2026/09/30/reddit-is-killing-rss-feeds-ending-public-api-access-because-of-ai-bots/) ⭐️ 7.0/10

Reddit has reportedly announced that it will discontinue RSS feed support on November 13 and close public API access by March 2027, citing large-scale scraping and automated abuse driven largely by AI bots. According to the report, third-party app and bot developers must register by January 12, 2027 or lose API access, while moderators are being advised to migrate to a replacement referred to as &\#x27;Discord Relay.&\#x27; These claims come from a Telegram repost of a TechCrunch article and could not be independently verified from the supplied material, and atypical details — such as the &\#x27;Discord Relay&\#x27; replacement — add to the uncertainty.

telegram · zaihuapd · Oct 1, 00:27

**「Background」** RSS is a decades-old syndication standard that lets people and automated tools follow site updates without an account or an official app; Reddit has long published RSS feeds for its subreddits and user pages, making them a lightweight channel for readers, moderators, and bots. The shutdown extends the access tightening Reddit began in 2023, when it introduced paid API tiers that forced popular third-party apps such as Apollo to shut down and pushed more automation toward scraping. Covering the September 30 announcement made in a moderator channel, Mashable framed the change as AI bots making it harder for &quot;a human who just wants to read Reddit,&quot; with no replacement for the feeds.

**「Impact」** Moderators and developers now face hard deadlines: moderation alerts must migrate to Reddit&\#x27;s Discord Relay Devvit app before RSS support ends on November 13, 2026, and operators of approved third-party apps and bots must complete registration by January 12, 2027 to retain API access through the March 2027 shutdown. RSS consumers outside moderation—personal feed readers, archiving tools, and research pipelines—have no announced replacement, and old Reddit access is being restricted to recent logged-in users, so anyone depending on unauthenticated access to Reddit data should verify their registration path now or plan for loss of access.

<details><summary>References</summary>
<ul>
<li><a href="https://sea.mashable.com/tech/55351/reddit-is-ending-rss-feeds-with-no-replacement-you-can-blame-ai-bots">Reddit is ending RSS feeds — with no replacement. You can ...</a></li>
<li><a href="https://mangodeveloper.com/articles/reddit-kills-rss-and-public-api-access-cites-ai-scraping-as-the-culprit">Reddit kills RSS and public API access, cites AI scraping as ...</a></li>
<li><a href="https://techbeat.co/story/reddit-ends-rss-feeds-and-public-api-as-ai-data-revenue-grows">Reddit Ends RSS Feeds and Public API as AI Data Revenue Grows</a></li>
<li><a href="https://aiweekly.co/alerts/reddit-ends-rss-nov-13-closes-public-api-by-march-2027">Reddit Ends RSS Nov 13, Closes Public API by March 2027</a></li>

</ul>
</details>

**Tags**: `#Reddit`, `#API`, `#RSS`, `#AI bots`, `#developer ecosystem`

---

<a id="item-tech-news-9"></a>
### [OpenAI Disrupts Model Distillation Campaign, Links It to Moonshot AI Personnel](https://openai.com/index/disrupting-a-coordinated-model-distillation-campaign/) ⭐️ 7.0/10

OpenAI says it disrupted a coordinated model distillation campaign in which attackers manipulated chat interactions to extract protected reasoning content from its models. According to OpenAI, the activity first appeared in early July 2026, peaked on July 24–25 with roughly 16,000 extraction requests from more than 4,000 users, and by July 28 the company had disrupted related activity from more than 15,000 users. OpenAI attributed the core campaign to individuals linked to Moonshot AI, the developer of the Kimi model, and says it shared information about the operation with industry and government through the Frontier Model Forum. The attribution and figures come from OpenAI&\#x27;s own announcement relayed via a Telegram channel digest and have not been independently verified.

telegram · zaihuapd · Oct 1, 01:18

**「Model distillation, explained」** Model distillation is the practice of training one AI system on the outputs of another, and OpenAI defines the adversarial form as the systematic and unauthorized use of a rival model&\#x27;s outputs or reasoning to help train, reproduce, or improve a different model. That framing makes the attribution pointed: Moonshot AI is the developer of the Kimi chatbot, a competing model, and unauthorized reuse of another provider&\#x27;s outputs runs against that provider&\#x27;s terms of service. OpenAI says it shared its findings with industry and government through channels including the Frontier Model Forum, the cross-industry venue it uses to coordinate on such threats.

**「Vendor-risk implications for Kimi users」** Enterprises evaluating or using Kimi K3, which Moonshot AI currently serves through its commercial API platform \(a 2.8-trillion-parameter model with a 1M-token context window\), now face a vendor-risk question based on a unilateral OpenAI attribution that has not been independently verified — Anthropic has previously raised similar distillation accusations against Moonshot AI, DeepSeek, and MiniMax, and ongoing coverage of the related Kimi K3 dispute notes the evidence has not yet formed a closed case. Because OpenAI says it has already shared its findings with industry and government through the Frontier Model Forum, organizations relying on Kimi models should treat this as an active, escalating dispute and watch for concrete measures rather than dismissing it as a routine vendor allegation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.unite.ai/openai-disrupts-coordinated-model-reasoning-extraction-campaign/">OpenAI Disrupts Coordinated Model -Reasoning Extraction Campaign</a></li>
<li><a href="https://cellcog.ai/blog/openai-moonshot-distillation/">OpenAI Distillation Campaign : What It Says About Moonshot</a></li>
<li><a href="https://www.ic.work/article/kimi-k3-fable-distillation-claims-two-week-gap">Kimi K3遭 蒸 馏 指 控 ：两周时间窗不足以证明“复制Fable” - ic.work</a></li>
<li><a href="https://platform.kimi.ai/">Kimi API Platform</a></li>

</ul>
</details>

**Tags**: `#AI安全`, `#模型蒸馏`, `#OpenAI`, `#月之暗面`, `#行业动态`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Kalshi and Polymarket trading volumes draw wash-trading scrutiny](https://www.cnbc.com/2026/09/30/kalshi-polymarket-trading-volume-scrutiny.html) ⭐️ 7.0/10

Unusual trading patterns are raising wash-trading concerns at prediction markets Kalshi and Polymarket: a CNBC analysis found nearly half of the dollar volume on Kalshi&\#x27;s ether perpetual futures on Sept. 20 came from trades sized between $5,495 and $5,505, while Polymarket&\#x27;s offshore international exchange shows outsized activity on contracts with very low odds. Both companies deny any wash trading or inorganic activity, and the Wall Street Journal reported — which CNBC could not independently verify — that the Commodity Futures Trading Commission is examining Kalshi&\#x27;s ether perpetuals.

rss · CNBC Finance · Sep 30, 21:09

**「Background」** Both companies have used surging trading volumes to help justify their private valuations, with Polymarket currently raising at more than $20 billion and Kalshi reportedly in talks at $40 billion. Wash trading refers to traders buying and selling among themselves to create a false appearance of economic activity.

**「Impact」** Finance professor Andre Guettler, in a working paper on the Kalshi patterns, warns that if a material share of reported volume is manufactured, headline figures may overstate actual trading demand — most affecting retail investors, who are the natural buyers of such exchanges at a public listing.

**Tags**: `#prediction markets`, `#Kalshi`, `#Polymarket`, `#wash trading`, `#CFTC scrutiny`

---

<a id="item-finance-news-2"></a>
### [Beijing warns of retaliation if EU restricts Chinese businesses](https://www.cnbc.com/2026/09/30/china-warns-europe-increases-trade-pressure.html) ⭐️ 7.0/10

China&\#x27;s commerce ministry warned it will &quot;respond firmly&quot; if the EU imposes curbs on Chinese businesses or products, saying such moves during ongoing trade talks would &quot;seriously undermine mutual trust.&quot; The warning comes as the EU, which reported 880 billion euros \(nearly $1 trillion\) in combined goods-and-services trade with China last year, presses to shrink its record trade deficit with Beijing by an October deadline and reportedly weighs &quot;301&quot;-style measures that could cut China off from the European market.

rss · CNBC Finance · Sep 30, 03:39

**「Background」** The EU has been in trade talks with China this summer and has set an October deadline for Beijing to help shrink its record goods trade deficit—about 360 billion euros last year—or face harsher measures, EU Trade Commissioner Maroš Šefčovič has said. The &\#x27;301&\#x27;-style measures Europe is weighing are named after a U.S. trade law that lets one country unilaterally impose tariffs or market restrictions on a trading partner.

**「Who could be affected」** European exporters and Chinese companies that rely on access to each other&\#x27;s markets could face disruption if the EU adopts curbs and Beijing follows through on its warning to &quot;respond firmly&quot; — a relationship the EU says totaled 880 billion euros in combined goods and services trade last year.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.biggo.com/news/ef5288b0-393d-4bd3-9b62-f62a48cfe009">China Threatens Retaliation If EU Targets Its... — BigGo Finance</a></li>
<li><a href="https://www.cnbc.com/2026/09/30/china-warns-europe-increases-trade-pressure.html">Beijing warns of retaliation if Europe imposes curbs on Chinese ...</a></li>

</ul>
</details>

**Tags**: `#EU-China trade`, `#trade policy`, `#tariffs`, `#trade deficit`, `#retaliation threat`

---

<a id="item-finance-news-3"></a>
### [China reportedly tightens IPO criteria for humanoid robot startups](https://www.cnbc.com/2026/09/29/china-criteria-humanoid-robot-ipos.html) ⭐️ 7.0/10

China&\#x27;s securities regulator has issued unconfirmed &quot;window guidance&quot; requiring humanoid robot startups seeking IPOs to show sustainable revenue, narrowing losses, and core technology such as robotic brains or hands, according to three anonymous sources cited by CNBC. With at least two dozen such companies filed to list in Hong Kong alone and flagship listing Unitree&\#x27;s Shanghai shares nearly halving from 845 yuan since their August debut, sources expect only a handful — or none — of the startups to reach public markets; the CSRC did not respond to a request for comment.

rss · CNBC Finance · Sep 30, 02:50

**「Background」** Mainland Chinese companies need the securities regulator&\#x27;s approval to list in Hong Kong, where at least two dozen humanoid-related startups have filed, aided by confidential IPO filing rules the exchange introduced in May 2025. The scrutiny follows a boom of more than 100 Chinese humanoid companies and 47.09 billion yuan \($6.95 billion\) of second-quarter investment, with Unitree&\#x27;s Aug. 19 Shanghai debut raising about 6.1 billion yuan \($905 million\) before its shares nearly halved from their first-day close of 845 yuan.

**「Impact」** The new criteria could stall IPO plans across the crowded sector — at least two dozen humanoid-related companies have already filed to list in Hong Kong alone — and narrow the exit route for early-stage investors, since mainland Chinese firms listing in Hong Kong still need CSRC approval.

<details><summary>References</summary>
<ul>
<li><a href="https://tradersunion.com/news/financial-news/show/3552922-china-humanoid-robot-ipo-standards-tighten/">China humanoid robot IPO standards tighten as listing ...</a></li>
<li><a href="https://vff.ai/article/2026/09/10/china-curbs-humanoid-ipos-after-unitree-s-volatile-debut">China Tightens Humanoid Robot IPO Rules After Unitree Debut</a></li>
<li><a href="https://www.cnbc.com/2026/09/29/china-criteria-humanoid-robot-ipos.html">China&#x27;s criteria for humanoid robot IPOs may be hard to meet</a></li>

</ul>
</details>

**Tags**: `#China regulation`, `#humanoid robots`, `#IPOs`, `#embodied AI`, `#AI bubble`

---