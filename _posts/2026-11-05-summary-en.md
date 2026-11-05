---
layout: default
title: "Horizon Summary: 2026-11-05 (EN)"
date: 2026-11-05
lang: en
---

> From 46 items, 15 important content pieces were selected

---

**Technology News**
1. [OpenAI says its autonomous pipeline generated 948 Linux kernel root exploits](#item-tech-news-1) ⭐️ 9.0/10
2. [Moonshot AI releases open weights for Kimi K3.1 Pro](#item-tech-news-2) ⭐️ 8.0/10
3. [Go team announces new encoding/json/v2 API](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic publishes research on cryptographically provable LLM inference](#item-tech-news-4) ⭐️ 8.0/10
5. [AI vulnerability discovery exposes decades of software security debt](#item-tech-news-5) ⭐️ 8.0/10
6. [Tencent releases Hy4 open-weight LLM tuned for game development alongside scientific foundation models](#item-tech-news-6) ⭐️ 8.0/10
7. [AMD&\#x27;s ~$17B Q4 guidance would outsell Intel for the first time](#item-tech-news-7) ⭐️ 8.0/10
8. [Open-sourced NKI megakernels cut GLM-5.3-Flash decode on Trainium2 from 32.2 to 24.2 ms](#item-tech-news-8) ⭐️ 8.0/10
9. [Hacker group Calif demos iPhone jailbreak bypassing Lockdown Mode, surviving iOS 27.2](#item-tech-news-9) ⭐️ 8.0/10
10. [OpenAI announces agreement to acquire git-infrastructure startup Pierre Computer Company](#item-tech-news-10) ⭐️ 7.0/10
11. [Do looped transformers save HBM traffic? Profiling weight reuse in Huginn on a B200 \[P\]](#item-tech-news-11) ⭐️ 7.0/10
12. [Anthropic open-sources FlashProve, a cryptographic proof system for verifying AI model outputs](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Stocks making the biggest moves premarket: Trump Media, Tesla, CoreWeave, Novo Nordisk and more](#item-finance-news-1) ⭐️ 7.0/10
2. [Treasury yields and oil prices fall after Democrats win both chambers in midterms](#item-finance-news-2) ⭐️ 7.0/10
3. [Oracle cancels $7 billion AI chip lease with Tencent after US concerns](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI says its autonomous pipeline generated 948 Linux kernel root exploits](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 9.0/10

OpenAI reports that its autonomous vulnerability research pipeline, in a single scan of the Linux kernel in October 2026, dynamically reproduced 1,724 vulnerabilities and generated 948 working local privilege escalation \(LPE\) exploits that let an unprivileged local user gain root, along with 291 information-leak proofs of concept. The company says the run cost $1,213,430 in API fees — about $1,279 per successful LPE exploit, with the cost of actually developing each successful exploit put lower at roughly $359 — and that third-party experts confirmed at least 10 novel exploitation techniques, including new persistent objects for cache spraying, new page grooming methods, data-only privilege escalation and arbitrary-write techniques, and arbitrary type confusion. At historical Pwn2Own and TyphoonPWN bounty levels of $20,000–$70,000 per exploit, the report estimates the 948 LPEs would theoretically be worth $18.9–66.3 million, or 16 to 55 times the run&\#x27;s cost. These figures are self-reported by OpenAI and have not been independently verified.

telegram · zaihuapd · Nov 5, 03:04

**「Background」** Local privilege escalation \(LPE\) vulnerabilities are kernel flaws that let a user with only ordinary access on a machine gain root, the highest privilege level on a Linux system. Such exploits have traditionally been hand-crafted by expert researchers and demonstrated one at a time, with individual Linux kernel LPEs earning bounties in the $20,000–$70,000 range at contests like Pwn2Own and TyphoonPWN. OpenAI&\#x27;s November 4, 2026 research post says the pipeline ran on an upcoming cyber model against a commonly used Linux distribution that the announcement did not name.

**「Impact for Linux operators」** Multi-tenant Linux environments — containers, shared servers, CI runners — can no longer treat an unprivileged local account as a meaningful security boundary: OpenAI&\#x27;s run produced 948 working root exploits, and at a reported average of $1,279 per successful exploit \(about $359 counting only successful development\), regenerating comparable exploits is within reach of modest budgets. The concrete action is to prioritize kernel updates, since the pipeline also generated candidate patches for the 948 flaws, and to treat untrusted local code execution on unpatched kernels as presumptive root access.

**「Hacker News reaction」** On Hacker News, commenters debated what the findings say about kernel security: &\#x27;Plasmoid&\#x27; asked whether the kernel has simply become too complex to reason about or whether the flaw lies in its security model, and &\#x27;nas&\#x27; called the count of 948 &\#x27;kind of shocking&\#x27; while noting that local root escalation on Linux had long seemed almost inevitable. Another commenter, &\#x27;rmbryan,&\#x27; asked what mitigating factors keep vulnerabilities at this scale from being an existential threat, and a user identifying themselves as a member of the OpenAI team \(&\#x27;dangelosaurus&\#x27;\) offered to relay questions and said the team is hiring — a claim that could not be verified.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/a-thousand-fewer-paths-to-root/">A thousand fewer paths to root - OpenAI</a></li>
<li><a href="https://explainx.ai/blog/openai-linux-kernel-948-local-privilege-escalation-exploits-1-2-million-api-cost-pipeline-patch-the-planet-2026">OpenAI Linux Kernel Pipeline: 948 Root Exploits, $1.2M ...</a></li>
<li><a href="https://cybersecuritynews.com/openai-uncovers-948-linux-kernel-vulnerabilities/">OpenAI Cyber Model Uncovers 948 Linux Kernel Privilege ...</a></li>
<li><a href="https://explainx.ai/blog/openai-linux-kernel-948-local-privilege-escalation-exploits-1-2-million-api-cost-pipeline-patch-the-planet-2026">OpenAI Linux Kernel Pipeline: 948 Root Exploits, $1.2M ...</a></li>
<li><a href="https://phemex.com/news/article/openai-ai-pipeline-validates-948-linux-kernel-privilegeescalation-flaws-in-single-run-102431">OpenAI AI Finds 948 Linux Kernel Vulnerabilities in One Run ...</a></li>

</ul>
</details>

**Tags**: `#ai-security`, `#linux-kernel`, `#vulnerability-research`, `#autonomous-exploitation`, `#privilege-escalation`

---

<a id="item-tech-news-2"></a>
### [Moonshot AI releases open weights for Kimi K3.1 Pro](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

Moonshot AI has published open weights for Kimi K3.1 Pro on Hugging Face, released in MXFP4 quantization. Per a summary circulating alongside the release, it is a natively multimodal agentic model with about 2.8T total parameters, roughly 104B activated per token, and around 1M-token context, and Moonshot&\#x27;s API endpoint \(kimi-k3.1-pro\) is compatible with both OpenAI and Anthropic interfaces. Community testing reports describe it as a very strong open-weight model that sits slightly below the frontier, though some argue its benchmark scores overstate real capability.

hackernews · abrarthought · Nov 4, 15:30 · [Discussion](https://news.ycombinator.com/item?id=50366999)

**「Background」** Kimi K3.1 Pro is post-trained from Kimi K3, Moonshot AI&\#x27;s earlier open-weight, natively multimodal agentic model built on Kimi Delta Attention with a 1-million-token context window. The new release is positioned as the company&\#x27;s most capable model to date and the first entry in the K3.1 series.

**「Impact」** Third-party inference providers including OpenRouter, Together, and Modal are already hosting the model, with commenters reporting that Together achieves roughly double the throughput of Moonshot&\#x27;s own endpoint at the same price and Modal roughly double that again — suggesting meaningful headroom for providers to optimize and cut serving costs. Self-hosting, however, requires datacenter-class hardware; one commenter estimated an 8x B300-class node, so most individual users will need to rely on hosted endpoints rather than running it locally.

**「Community discussion」** Commenters are split on benchmark credibility: one argues K3.1 scores high on its own benchmarks but not on Hy4&\#x27;s internal ones, calling it &\#x27;benchmaxxed,&\#x27; while another, citing their own testing, says they did not observe this and calls it a very strong release for most use cases. At least one commenter questioned the openness of the release outright, so the open-weight claim carries some residual uncertainty.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3.1-Pro">moonshotai/ Kimi - K 3 . 1 - Pro · Hugging Face</a></li>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3">moonshotai/ Kimi - K 3 · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#open-weights`, `#large-language-models`, `#moonshot-ai`, `#inference`, `#benchmarks`

---

<a id="item-tech-news-3"></a>
### [Go team announces new encoding/json/v2 API](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

The Go team has announced a new v2 API for JSON handling in the standard library, packaged as encoding/json/v2, in a post on the official Go blog. The redesign reworks one of Go&\#x27;s most widely used packages, and the announcement includes the lower-level jsontext package that commenters report already using in production for custom, high-performance parsing. The current encoding/json package remains in place, so v2 is an addition rather than a removal of the existing API.

hackernews · olexsmir · Nov 4, 17:52 · [Discussion](https://news.ycombinator.com/item?id=50369106)

**「Background」** In 2025, the Go team first published this redesign as an experimental API, describing it as a way to deliver long-awaited improvements and fixes to the standard library&\#x27;s original encoding/json package. The design that emerged splits JSON support into two packages: encoding/json/v2 for the familiar struct-based marshaling and unmarshaling, and encoding/json/jsontext, a lower-level token-based streaming API for processing JSON without unmarshaling it into Go structs. Feedback from that experimental phase informed the final design, and the classic encoding/json API stays in place, now running on the v2 engine.

**「Why it matters」** Developers will need to evaluate migration paths for existing code: community members report that equivalents for common conveniences such as MarshalIndent are more complicated and non-obvious in v2, making migration a real cost for codebases that rely on them. For teams with demanding or non-standard parsing needs, the jsontext package is reported to deliver strong speed and fine-grained error control, and it can be recommended for anything beyond straightforward use cases.

**「Community reaction」** Discussion on Hacker News focused on migration friction rather than opposition: CamouflagedKiwi said they generally like encoding/json/v2 but regret the absence of MarshalIndent, whose replacement code they describe as complicated and painful to write by hand. Another commenter, txomon, shared a positive production experience using the jsontext package to build a parser with specific error messages for each kind of malformed input while keeping high performance.

<details><summary>References</summary>
<ul>
<li><a href="https://go.dev/blog/jsonv2">A new Go API for JSON - The Go Programming Language</a></li>
<li><a href="https://allur.co/en/blog/the-road-to-json-v2-exploring-gos-experimental-new-api">The Road to JSON V 2 : Exploring Go &#x27;s Experimental New API - Allur</a></li>
<li><a href="https://webdelo.com/blog/go-1-27-json-unmarshaling-encoding-json-v2">Go 1.27 JSON Unmarshaling: encoding / json / v 2 Guide 2026</a></li>

</ul>
</details>

**Tags**: `#go`, `#json`, `#standard-library`, `#serialization`, `#api-design`

---

<a id="item-tech-news-4"></a>
### [Anthropic publishes research on cryptographically provable LLM inference](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic published research on provable inference for large language models, a cryptographic scheme that lets clients verify that a model provider actually ran the correct weights and computations. The client downloads a commitment of about 6.5 MB — good for roughly 16 million requests before the provider must re-commit — and then one proof per request, with proof verification taking about 17 seconds on 24 threads \(21 seconds on a single thread\), including the offline phase&\#x27;s check. The scheme requires deterministic inference and is reported to carry roughly a 90–100x compute overhead. This is early-stage research, not a shipped product or deployed capability.

hackernews · ltononro · Nov 4, 17:17 · [Discussion](https://news.ycombinator.com/item?id=50368626)

**「Background」** Provable inference addresses a trust problem specific to closed-weight model APIs: a client cannot inspect the weights or independently re-run the model, so it has had to take the provider&\#x27;s word for which weights are actually running on the provider&\#x27;s servers. The technique rests on zkSNARKs, a powerful type of cryptographic proof that Anthropic describes as uniquely fit for provable inference, letting a client verify that a specific model generated a specific reply without ever holding the weights. In the FlashProve prototype, the provider first commits to the model&\#x27;s weights in an offline phase using a short hiding commitment that even resource-constrained clients can store, then produces a proof for each reply; the demonstrated target is the Mixture-of-Experts model Llama 4 Maverick.

**「Impact」** For organizations that consume model APIs and cannot audit a closed-weight provider&\#x27;s servers, the research outlines a path to cryptographically confirming the advertised model was actually used — for example, catching a routing service that silently substitutes a different model. Adopters face practical constraints for now: the 90–100x compute overhead and the per-request verification cost make the scheme a research technique rather than a production-ready control.

**「Community Discussion」** Commenters debated practicality and novelty. A commenter identifying themselves as a contributor to the prior VerInf work \(jamespetrie/verinf\) claimed Anthropic built on it with very little attribution, down to the choice of the 400B Maverick model — an unverified attribution dispute. Others argued that for open-weight models, provable inference is trivially achieved by simply re-running the deterministic computation, so the cryptographic approach mainly matters for closed providers; one commenter noted that cheaper probabilistic alternatives exist, such as comparing outputs from several independent inference providers, and others flagged the concrete overheads as the main obstacle to real-world use.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models</a></li>
<li><a href="https://assets.claude.com/8e1d181a83015078581c92d896757041713f0160.pdf">FlashProve: an open-source library for provable inference</a></li>
<li><a href="https://shattered.io/anthropic-flashprove-provable-inference-72x-overhead-2026/">Anthropic FlashProve: Provable Inference at 72x [2026]</a></li>

</ul>
</details>

**Tags**: `#llm-inference`, `#zero-knowledge-proofs`, `#cryptography`, `#verifiable-computation`, `#ai-safety`

---

<a id="item-tech-news-5"></a>
### [AI vulnerability discovery exposes decades of software security debt](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 8.0/10

IEEE Spectrum argues that AI-driven vulnerability discovery, exemplified by flaws such as the php2shell PHP vulnerability, is forcing the software industry to confront roughly 40 years of accumulated security technical debt in legacy and open source code. The piece frames AI tools as finally surfacing weaknesses that were long assumed to be audited or patched by someone else. The article is an analytical argument about an industry trend rather than a report of a shipped capability, and the immediate consequence is a growing stream of CVEs and remediation work for maintainers.

hackernews · pseudolus · Nov 4, 11:52 · [Discussion](https://news.ycombinator.com/item?id=50364336)

**「Background」** The debate centers on the php2shell vulnerability, a security flaw affecting PHP, the web programming language created in 1994 that still powers many older websites, which IEEE Spectrum uses as its case study. The core prerequisite concept is &quot;technical debt&quot;: decades of security weaknesses in legacy and open source code that went unfixed because discovery was slow and expensive, with many projects relying on the assumption that someone else had audited the code. AI-driven vulnerability discovery has changed that economics, making it possible to find such long-dormant flaws at scale.

**「What this means in practice」** Maintainers and security teams should expect a sustained rise in AI-discovered vulnerability reports — such as the php2shell PHP flaw cited by IEEE Spectrum — and plan review capacity accordingly, since many of these legacy issues may require restructuring rather than narrow patches. Per an external analysis of autonomous discovery tools like XBOW and Google&\#x27;s Big Sleep, some defenders are responding by integrating agentic security scanning into CI/CD pipelines to match AI&\#x27;s discovery pace, while open source projects face pressure to substantiate the assumption that their code has been audited by others.

**「One-time payoff or endless treadmill?」** The discussion is split on the long-term outcome: swatcoder questions whether AI is a one-time debt payoff or a permanent treadmill of feature-neutral fix work, noting many flaws require restructuring rather than narrow patches, while glennfiedler and Arbortheus expect the short-term pain to end in more robust software, with Arbortheus hoping hoarded nation-state 0-days get found incidentally. xbmcuser argues AI auditing makes open source&\#x27;s long-assumed &\#x27;someone else audited it&\#x27; promise real, though that expectation of auditability remains a community claim, not a verified fact.

<details><summary>References</summary>
<ul>
<li><a href="https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability">PHP2Shell Is a Wakeup Call for AI in Cybersecurity - IEEE ...</a></li>
<li><a href="https://vexdynamics.com/news/php2shell-vulnerability-exposes-40-years-of-technical-debt">PHP2Shell Vulnerability Exposes 40 Years of Technical Debt in ...</a></li>
<li><a href="https://grafy.ai/news/php2shell-ai-exposes-40-years-of-legacy-code-debt">PHP2Shell: AI Exposes 40 Years of Legacy — Grafy News</a></li>
<li><a href="https://xbow.com/webinars/200-zero-days">Zero-Day Webinar: AI Finds Real Vulnerabilities Fast | XBOW</a></li>
<li><a href="https://undercodetesting.com/ai-hackers-just-broke-appsec-how-xbow-big-sleep-found-zero-days-in-hours-your-move-defender-video/">AI HACKERS JUST BROKE APPSEC: How XBOW &amp; Big Sleep Found Zero ...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#vulnerability discovery`, `#technical debt`, `#open source`, `#cybersecurity`

---

<a id="item-tech-news-6"></a>
### [Tencent releases Hy4 open-weight LLM tuned for game development alongside scientific foundation models](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

Tencent released Hy4, an open-weight large language model that its announcement calls one of the strongest open-weight models available, alongside two open-sourced foundation models that the announcement says were co-developed by Hy4 and Hyra 2.0: HyCell for single-cell representation and HyPDE for physical field modeling. Hy4 includes a game-development specialization built with professional developers from Tencent&\#x27;s Interactive Entertainment Group, covering feature implementation, gameplay logic, state tracking, and asset pipelines, with adaptations for Unreal Engine, Unity, and Godot and expanded multiplayer-game capabilities. Tencent itself acknowledges that a notable gap remains between Hy4 and top proprietary models, particularly on its internal benchmarks for research-level mathematics, long-horizon coding, model self-improvement, and advanced visual question answering, and says it will continue scaling pre-training and post-training to narrow it. The headline ranking is Tencent&\#x27;s own claim rather than an independently verified result.

hackernews · Philpax · Nov 4, 14:11 · [Discussion](https://news.ycombinator.com/item?id=50365780)

**「Background」** Hy4 is the successor to Tencent&\#x27;s earlier Hy3 open-weight model and follows a &\#x27;Hy4 preview&\#x27; release that third-party coverage described as a 770B-parameter open model, with the jump from Hy3 to the preview measured on benchmarks Tencent itself published. The full release follows through on the open-source approach Tencent announced at launch, when it said model weights and system cards would be released in the coming days with a stated focus on cybersecurity and biological safety.

**「Impact for developers」** Game developers gain an open-weight model explicitly adapted to Unreal Engine, Unity, and Godot, including multiplayer workflows, making it a candidate to evaluate for feature implementation and gameplay-logic tasks. The caveat comes from Tencent&\#x27;s own announcement: Hy4 still trails top proprietary models on research-level mathematics and long-horizon coding, so teams relying on those capabilities may need to keep proprietary models in the mix.

**「Hacker News reaction」** The most substantive report came from commenter chriddyp, who linked Plotly&\#x27;s data-analytics benchmark and said Hy4 landed on its cost/accuracy frontier between GPT-6.1 Sol and GPT-6.1 Terra, but was very slow, running roughly 26 queries per question \(up to 64 on some\) with at least one query taking about an hour. Elsewhere in the thread, areoform praised the open-sourcing of scientific tooling as what they saw as a refreshing contrast to US startups, and frangonf said they appreciated Tencent&\#x27;s candid acknowledgment of the remaining gap to proprietary models.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tencent.com/tencent-launches-hy4-joining-the-ranks-of-the-worlds-leading-open-source-ai-models/">Tencent Launches Hy 4 , Joining the Ranks of the... - Tencent</a></li>
<li><a href="https://www.intelligentliving.co/tencent-hy4-preview-benchmarks/">Tencent Hy 4 Preview Benchmarks : 770B Open Model Takes on Kimi...</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#large language models`, `#Tencent`, `#scientific foundation models`, `#game development`

---

<a id="item-tech-news-7"></a>
### [AMD&\#x27;s ~$17B Q4 guidance would outsell Intel for the first time](https://www.tomshardware.com/pc-components/cpus/amd-expects-to-outsell-intel-in-q4-for-the-first-time-in-history-usd17b-guidance-would-exceed-intels-projections) ⭐️ 8.0/10

AMD has issued fourth-quarter revenue guidance of roughly $17 billion, which Tom&\#x27;s Hardware reports would exceed Intel&\#x27;s own projections and make this the first quarter in history in which AMD&\#x27;s revenue tops Intel&\#x27;s. AMD attributed the expected growth in part to strong sales of its Instinct AI accelerators. The milestone rests on forward-looking guidance rather than reported results, so it remains unconfirmed until both companies post Q4 earnings.

hackernews · rbanffy · Nov 4, 15:38 · [Discussion](https://news.ycombinator.com/item?id=50367125)

**「Background」** Intel has historically been the larger of the two x86 chipmakers by revenue, which is why a quarter in which AMD&\#x27;s total sales surpass Intel&\#x27;s would be unprecedented in their decades-long rivalry. The claim rests on forward-looking guidance rather than reported results, and the revenue being compared spans AMD&\#x27;s full business — including Instinct AI accelerators — not simply its Ryzen and EPYC processors against Intel&\#x27;s Core and Xeon lines. The milestone would therefore only be confirmed once both companies report their actual Q4 figures.

**「Guidance, not results — treat the lead as provisional」** The comparison pits AMD&\#x27;s ~$17 billion forecast against Intel&\#x27;s forecast rather than actuals, so either company&\#x27;s reported Q4 results could still change the outcome. Organizations weighing server or AI-accelerator purchases on this news should wait for both companies&\#x27; Q4 earnings reports before treating an AMD revenue lead as established.

**「Readers credit Intel&\#x27;s stumbles more than AMD&\#x27;s surge」** Commenters largely framed the shift as a verdict on Intel&\#x27;s missteps rather than an AMD breakthrough, citing one user&\#x27;s repeated voltage failures on 13th- and 14th-generation Intel CPUs, Intel&\#x27;s discontinued Optane memory line, and what another called negligible sales of Intel Arc accelerators. A commenter who disclosed owning an Arc GPU argued that AMD&\#x27;s Instinct sales remain tiny next to Nvidia&\#x27;s and questioned whether the lead reflects CPU strength or Intel&\#x27;s weakness in accelerators, while a separate user said they avoid Intel chips after a forensic team reportedly used Intel&\#x27;s DCI debug interface to extract a LUKS key from a hosted server&\#x27;s RAM.

**Tags**: `#semiconductors`, `#AMD`, `#Intel`, `#CPUs`, `#AI hardware`

---

<a id="item-tech-news-8"></a>
### [Open-sourced NKI megakernels cut GLM-5.3-Flash decode on Trainium2 from 32.2 to 24.2 ms](https://www.reddit.com/r/MachineLearning/comments/1xo0yuq/p_nki_layer_megakernels_for_glm53flash_on_aws/) ⭐️ 8.0/10

RunAnywhere engineer /u/WildCard727 open-sourced an AWS Trainium2 inference engine \(github.com/RunanywhereAI/trnrt\) that serves GLM-5.3-Flash, a 320B-parameter MoE model with 1M-token context, on a single trn2.48xlarge, replacing XLA-orchestrated op chains with one NKI megakernel per layer half and whole-layer kernels for the sparse-attention layers. Profiling an early build showed how little of a decode step was the model&\#x27;s actual math: at batch 1 in one KDA linear-attention layer, the recurrence was 2% of the attention half while the mHC pre-projection took 36% and XLA glue 33%, alongside roughly 153 ns of fixed cost per small vector-engine instruction and 125 cross-chip collectives per step. The new kernels hold a layer half&\#x27;s activations, recurrent state and in-flight weights in the 28 MiB on-core SBUF, split weight streaming across both physical cores of a logical core \(672–708 GB/s versus 340–400 GB/s for a single program\), and pull blocking all-reduces inside the kernel; on the same layout, a batch-8 decode step fell from 32.2 ms on the 17 October build to 24.2 ms on 1 November against a 6.1 ms memory floor, with the fused sparse-attention layer and the KDA and MoE kernels each saving 3.2 ms. All numbers are self-reported with no stock-AWS or GPU baseline — the vLLM Neuron plugin registers no GLM model and NxD Inference is in maintenance mode — one approximation remains in sparse-attention prefill \(on 1.2% of selections it shifted next-token log-probabilities by 0.012–0.021 nats and changed the top token at 3 of 448 positions, with no task-level eval yet\), and self-run SemiAnalysis AgentX runs measured up to 28.9 agent requests per minute and 35.9 tokens/s median decode at 16 agents.

reddit · r/MachineLearning · /u/WildCard727 · Nov 4, 21:47

**「GLM-5.3-Flash and the Trainium2 software gap」** GLM-5.3-Flash is Z.ai&\#x27;s open-weight model from August 2026, released under an MIT license on Hugging Face: a natively multimodal mixture-of-experts with 320B total parameters, 18B active per token, and a 1,048,576-token context window. Its hybrid-attention design is what the post&\#x27;s kernels target — the KDA linear-attention layers and the sparse-attention layers. On the hardware side, AWS&\#x27;s NKI is the interface for writing custom kernels that run on Trainium2&\#x27;s NeuronCores, and per the post the standard serving options on Neuron currently offer no path for this model: the vLLM Neuron plugin registers no GLM model and NxD Inference is in maintenance mode, leaving no stock baseline to compare against.

**「Impact for Trainium2 serving」** Teams that need to serve GLM-5.3-Flash on AWS Trainium2 gain an open-source, reproducible option where the stock stack currently has a gap: the post reports that the latest vLLM Neuron plugin release — the recommended serving solution for LLMs on Trainium — registers no GLM model and that NxD Inference is in maintenance mode, leaving RunAnywhere&\#x27;s trnrt engine, with commands to reproduce every number in docs/RESULTS.md, as a documented route to running this 320B MoE model on a single trn2.48xlarge. For developers writing their own NKI kernels, the failed experiments are as actionable as the wins: a dense FFN kernel that ran 84 µs instead of 145 µs in isolation made the full step 55 µs slower at batch 2, and three kernels that passed NKI&\#x27;s simulator gave wrong answers on the device, so kernel changes should be validated against whole-step latency and on-device accuracy rather than per-kernel benchmarks or simulation.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/zai-org/GLM-5.3-Flash">zai-org/GLM-5.3-Flash · Hugging Face</a></li>
<li><a href="https://www.marktechpost.com/2026/08/26/z-ai-releases-glm-5-3-flash-a-320b-a18b-natively-multimodal-moe-with-a-1m-token-context/">Z.ai Releases GLM-5.3-Flash: A 320B-A18B Natively Multimodal ...</a></li>
<li><a href="https://codepick.dev/en/guides/glm-5-3-flash-guide/">GLM-5.3-Flash Explained: Native Multimodality, 1M Context ...</a></li>
<li><a href="https://github.com/vllm-project/vllm-neuron">GitHub - vllm-project/vllm-neuron: Community maintained ...</a></li>

</ul>
</details>

**Tags**: `#AWS Trainium`, `#LLM inference optimization`, `#MoE models`, `#kernels`, `#LLM serving`

---

<a id="item-tech-news-9"></a>
### [Hacker group Calif demos iPhone jailbreak bypassing Lockdown Mode, surviving iOS 27.2](https://appleinsider.com/articles/26/11/04/apples-lockdown-mode-thwarted-by-a-new-persistent-iphone-jailbreak) ⭐️ 8.0/10

The hacker group Calif posted a video on X showing an iPhone 18 Pro with Apple&\#x27;s Lockdown Mode enabled being jailbroken and remaining jailbroken after an upgrade to iOS 27.2; the footage shows a PDF arriving over AirDrop before the update is completed in Settings. Calif released no technical details, says it is reporting the vulnerability to Apple, and states it will not publish the jailbreak tool. The claim rests on a single demonstration video without independent verification, and it cuts against Apple&\#x27;s March 2026 statement that Lockdown Mode — its optional hardened setting for users at risk of targeted spyware, launched in 2022 — had a 100% success rate against attacks. If Apple confirms the bypass, users who depend on Lockdown Mode would need a vendor patch to restore that guarantee, so applying Apple&\#x27;s fix promptly once it ships is the practical step; no exploit tooling has been made public in the meantime.

telegram · zaihuapd · Nov 4, 14:38

**「What Lockdown Mode is」** Lockdown Mode is Apple&\#x27;s most restrictive security setting, introduced in 2022 for people at elevated risk of targeted spyware such as journalists and activists; it disables most message attachments and advanced web features to shrink the iPhone&\#x27;s attack surface. Apple stated in March 2026 that the mode had blocked every attack attempt against it since launch — a 100% success rate — which is the record this jailbreak demonstration calls into question. Persistence across an OS update is also atypical for jailbreaks, which normally stop working once Apple ships a patched version of iOS that closes the exploited vulnerability.

**「Impact on at-risk users」** Lockdown Mode is built specifically for journalists, activists, and dissidents facing mercenary spyware, so a working bypass — if the single-source demo holds up — means these users can no longer treat it as an unbreakable last line of defense. The demo&\#x27;s jailbreak also survived an over-the-air update to iOS 27.2, meaning applying a system update may not by itself remove an implant that uses this technique from an already-compromised device. Until Apple ships a patch for the flaw Calif says it is reporting privately, at-risk users should keep Lockdown Mode enabled, install iOS updates promptly once a fix arrives, and continue treating Apple&\#x27;s targeted-spyware threat notifications as actionable rather than relying on the mode alone.

<details><summary>References</summary>
<ul>
<li><a href="https://appleinsider.com/articles/26/11/04/apples-lockdown-mode-thwarted-by-a-new-persistent-iphone-jailbreak">Apple&#x27;s Lockdown Mode thwarted by a new iPhone jailbreak</a></li>
<li><a href="https://tech.yahoo.com/cybersecurity/articles/apple-lockdown-mode-supposed-protect-185240625.html">Apple’s Lockdown Mode Was Supposed to Protect iPhones ...</a></li>
<li><a href="https://www.zdnet.com/article/apple-warns-targetted-spyware-attacks-what-to-do/">Apple is warning users of new spyware attacks - what to do if ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#ios`, `#jailbreak`, `#apple`, `#vulnerability-disclosure`

---

<a id="item-tech-news-10"></a>
### [OpenAI announces agreement to acquire git-infrastructure startup Pierre Computer Company](https://openai.com/index/openai-to-acquire-pierre/) ⭐️ 7.0/10

OpenAI announced an agreement to acquire Pierre Computer Company, the startup behind Code.Storage, a git-based service for storing machine-generated code and other artifacts at scale. According to announcement text quoted in the Hacker News discussion, Code.Storage claims that agentic-coding products including Lovable, Poke, Bolt, Amp, and Parahelp rely on it to store generated code, memory files, design artifacts, and other product files. Commenters identify Pierre as founded by Jacob Thornton and Mark Otto, the original creators of the Bootstrap front-end framework. The acquisition is an announced agreement rather than a completed deal, and the supplied source material links only to a tweet from Pierre&\#x27;s account, so no deal terms, price, or closing timeline are stated.

hackernews · itunpredictable · Nov 4, 15:21 · [Discussion](https://news.ycombinator.com/item?id=50366863)

**「What Pierre builds」** Pierre Computer Company is a small San Francisco startup founded in 2023 by Jacob Thornton, a co-creator of the Bootstrap front-end framework, and Ian Ownbey; it went through Y Combinator&\#x27;s Winter 2023 batch with roughly 10 employees. Its main product, Code.Storage, provides off-the-shelf Git infrastructure that lets AI applications store code and machine-generated artifacts at scale through SDKs or the native Git protocol, alongside open-source libraries such as Diffs and Trees. The startup&\#x27;s software already sits inside OpenAI&\#x27;s Codex coding agent, and OpenAI recently launched its own Git backend, Pando, so the deal deepens an existing relationship rather than introducing an unfamiliar technology.

**「Impact」** OpenAI says the acquisition will bring Pierre&\#x27;s Code.Storage distributed git infrastructure and open-source developer tools into its Codex agentic platform, expanding Codex&\#x27;s tools for building, understanding, and reviewing code. Existing Code.Storage customers — agentic coding services such as Lovable, Bolt, Amp, and Parahelp, per Pierre&\#x27;s product description quoted in community discussion — will now depend on code infrastructure owned by OpenAI, a potential competitor, so teams storing agent-generated code and artifacts there should watch for changes in terms, access, or pricing as the integration proceeds.

**「Community discussion」** Commenter tiffanyh speculated the deal relates to an OpenAI post on scaling git internally and noted that developer mitchellh has publicly endorsed Pierre and, in their words, may be an investor. Other reactions were opinion rather than fact: one commenter quipped that buying the company outright may be cheaper than paying subscription fees, and another wondered whether large labs acquire such teams partly to absorb their engineering know-how.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ycombinator.com/companies/pierre">Pierre: Pierre is a new, opinionated, git platform. | Y ...</a></li>
<li><a href="https://code.storage/">Code Storage — Git Infrastructure at Scale by The Pierre ...</a></li>
<li><a href="https://www.linkedin.com/in/jacob-thornton-13a6a5162">Jacob Thornton - Pierre Computer Company, Inc. | LinkedIn OpenAI to Buy Pierre, the Startup Behind Code Tools Already ... OpenAI acquires Pierre Computer Company to make Git keep up ... OpenAI to Acquire Pierre: Codex, Git and Code Review Pierre: Headless Git Infrastructure for AI Agents</a></li>
<li><a href="https://openai.com/index/openai-to-acquire-pierre/">OpenAI to acquire Pierre Computer Company, Inc.</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/openai-acquire-pierre-expand-codex-170249678.html?fr=sycsrp_catchall">OpenAI to acquire Pierre to expand Codex developer infrastructure</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/openai-acquire-pierre-computer-bring-192927037.html?fr=sycsrp_catchall">OpenAI to Acquire Pierre Computer, Bring Code Storage ...</a></li>

</ul>
</details>

**Tags**: `#openai`, `#acquisitions`, `#developer-tools`, `#git`, `#ai-agents`

---

<a id="item-tech-news-11"></a>
### [Do looped transformers save HBM traffic? Profiling weight reuse in Huginn on a B200 \[P\]](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

An empirical profiling study on a B200 finds that looped transformers like Huginn save weight storage but still re-read shared weights from HBM each iteration, with on-chip reuse benefits only when weights fit in L2 cache.

reddit · r/MachineLearning · /u/2dayyy6 · Nov 4, 16:26

**Tags**: `#GPU profiling`, `#looped transformers`, `#HBM memory traffic`, `#recurrent depth`, `#ML systems`

---

<a id="item-tech-news-12"></a>
### [Anthropic open-sources FlashProve, a cryptographic proof system for verifying AI model outputs](https://assets.claude.com/8e1d181a83015078581c92d896757041713f0160.pdf) ⭐️ 7.0/10

Anthropic has open-sourced FlashProve, a cryptographic proof system intended to verify that a given piece of AI output was actually generated by a specified model, and has published its technical specification and code. According to the researchers, the system would let users identify model substitution and verify third-party claims that a particular model performed a given task. The design calls for labs to publish a fingerprint for each released model that outputs can later be matched against; the fingerprint does not disclose model weights, and verification can run on local devices. The work remains at the research stage with no deployment plans, and the report is a brief secondhand summary, so the system&\#x27;s effectiveness and security have not been independently evaluated.

telegram · zaihuapd · Nov 4, 10:16

**「Why verifying model identity is hard」** Users who access AI models through APIs or third-party services currently have no independent way to confirm that a response actually came from the model the provider claims to be serving, which makes silent substitution of a cheaper model and unverifiable claims about a model&\#x27;s behavior difficult to detect. FlashProve builds on cryptographic fingerprinting techniques related to zero-knowledge proofs: a lab publishes a public fingerprint for a released model without exposing its proprietary weights, and outputs can then be matched against that fingerprint, with verification possible on local devices. Coverage of the announcement notes Anthropic developed the system together with zero-knowledge proof researchers.

**「Impact」** If model providers adopt the fingerprint-publication approach, users and enterprises could verify locally that an output came from the claimed model — catching model substitution or unverified third-party claims of task completion — without exposing proprietary weights. For now, the actionable step for developers is limited to reviewing the open specification and code, since Anthropic has announced no deployment and real-world verification would require other labs to publish fingerprints for their own models.

<details><summary>References</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-flashprove-cryptographic-model-verification">Anthropic unveils cryptographic tool to verify model outputs</a></li>
<li><a href="https://techcrunch.com/2026/11/03/anthropic-is-working-on-a-system-to-prove-ai-models-identity/">Anthropic is working on a system to prove AI models &#x27; identity</a></li>
<li><a href="https://news.aibase.com/news/32073">Claude Issues Itself an ID Card: Anthropic Uses Zero-Knowledge...</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-flashprove-cryptographic-model-verification">Anthropic unveils cryptographic tool to verify model outputs</a></li>
<li><a href="https://techcrunch.com/2026/11/03/anthropic-is-working-on-a-system-to-prove-ai-models-identity/">Anthropic is working on a system to prove AI models ... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#model provenance`, `#cryptography`, `#open source`, `#Anthropic`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Stocks making the biggest moves premarket: Trump Media, Tesla, CoreWeave, Novo Nordisk and more](https://www.cnbc.com/2026/11/04/stocks-making-the-biggest-moves-premarket-djt-tsla-crwv-nvo.html) ⭐️ 7.0/10

CNBC&\#x27;s premarket movers report election-driven declines in Trump Media, Tesla, and neocloud stocks after Democratic midterm wins, alongside CVS&\#x27;s announced two-company split, Novo Nordisk&\#x27;s earnings beat with raised guidance, and other notable earnings reactions.

rss · CNBC Finance · Nov 4, 13:32

**Tags**: `#premarket-movers`, `#midterm-elections`, `#earnings`, `#corporate-restructuring`, `#AI-data-centers`

---

<a id="item-finance-news-2"></a>
### [Treasury yields and oil prices fall after Democrats win both chambers in midterms](https://www.cnbc.com/2026/11/03/treasury-yields-fall-as-democrats-win-big-in-us-midterm-elections.html) ⭐️ 7.0/10

Democrats won majorities in both the House and Senate in the U.S. midterm elections, and the 10-year Treasury yield fell more than 6 basis points to 4.884% on Wednesday while WTI crude dropped 8.29% to close at $88.12 per barrel. Analysts at JPMorgan and BondBloxx said the bond market&\#x27;s reaction reflects expectations that divided government will make deficit growth more difficult.

rss · CNBC Finance · Nov 4, 21:18

**「Background」** The U.S.–Iran war that began in late February 2026 has kept oil prices elevated all year, with Iran&\#x27;s closure of the Strait of Hormuz, a key crude shipping route, disrupting global supply. WTI crude peaked as high as $115 per barrel in early April, so Wednesday&\#x27;s drop pulls prices back from those war-driven highs rather than from typical levels.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dallasfed.org/~/media/documents/research/papers/2026/wp2615.pdf">How Times Have Changed: The Impact of the 2026 Iran War on ...</a></li>
<li><a href="https://www.jpmorgan.com/insights/global-research/commodities/iran-us-tensions-market-effect">Economic Impact of Iran Conflict on Oil, Gold and More Iran war is driving up US gas and oil prices. Here&#x27;s how. The Impact of the 2026 Iran War on U.S. Inflation: A Scenario ... Economic impact of the 2026 Iran war - Wikipedia When war moves oil: Energy dependence and global equity ... US-Iran War Oil Price Impact 2026: Energy Markets Face ...</a></li>

</ul>
</details>

**Tags**: `#Treasury yields`, `#midterm elections`, `#oil prices`, `#fiscal policy`, `#bond market`

---

<a id="item-finance-news-3"></a>
### [Oracle cancels $7 billion AI chip lease with Tencent after US concerns](https://www.tradingview.com/news/seekingalpha:e51e68f4d094b:0-oracle-cancels-7b-ai-chip-lease-with-tencent-amid-us-concerns-ft/) ⭐️ 7.0/10

Oracle has canceled a roughly $7 billion AI chip lease under which Tencent would have rented about 100,000 advanced chips through Oracle&\#x27;s data centers in Southeast Asia, after US officials raised concerns about the deal, the Financial Times reported. Tencent had signed the five-year lease this year, with a down payment of about 30%, to reach chips it cannot obtain in China.

telegram · zaihuapd · Nov 4, 11:01

**「Background」** US export controls normally bar Chinese companies such as Tencent from accessing advanced AI chips, so the five-year deal signed this year would have let Tencent use roughly 100,000 of them through Oracle&\#x27;s data centers in Southeast Asia instead. Growing demand from Chinese AI firms in the region has pushed up prices and upfront payments on such leases, as tighter controls block the chips from reaching China through intermediary countries.

**「Why it matters」** The cancellation cuts off a route Tencent had arranged to access advanced AI chips unavailable in China, and shows US officials pressing American firms over offshore chip deals with Chinese customers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/entrepreneur-news-network_oracle-tencent-ai-activity-7511636631246987264-phQX"># oracle # tencent # ai # datacenters #artificialintelligence #nvidia...</a></li>
<li><a href="https://nypost.com/2026/11/04/business/oracle-nixes-7b-chip-leasing-deal-with-chinas-tencent-after-trump-admin-pushback-report/">Oracle nixes $7B chip leasing deal with China &#x27;s Tencent after Trump...</a></li>
<li><a href="https://www.zerohedge.com/ai/oracle-kills-7bn-tencent-ai-chip-deal-under-trump-pressure">Oracle Kills $7BN Tencent AI Chip Deal Under Trump... | ZeroHedge</a></li>

</ul>
</details>

**Tags**: `#US-China tech tensions`, `#AI chips`, `#Oracle`, `#Tencent`, `#export controls`

---