---
layout: default
title: "Horizon Summary: 2026-10-16 (EN)"
date: 2026-10-16
lang: en
---

> From 46 items, 7 important content pieces were selected

---

**Technology News**
1. [AdFection: Targeted ads turned into a pipeline for zero-click mercenary spyware](#item-tech-news-1) ⭐️ 9.0/10
2. [Meta releases Muse Spark Open, an 816B open-weight MoE model](#item-tech-news-2) ⭐️ 8.0/10
3. [Goodfire&\#x27;s &\#x27;Clean Networks&\#x27; Interpretability Claim Draws Skepticism](#item-tech-news-3) ⭐️ 7.0/10
4. [Libreboot 26.10 adds UEFI support and 233 Chromebooks](#item-tech-news-4) ⭐️ 7.0/10
5. [Anthropic reports quarterly revenue up nearly 50% to $16.8bn ahead of possible IPO](#item-tech-news-5) ⭐️ 7.0/10
6. [Self-Organizing Plasticity Rules Yield Networks Matching Backpropagation on Classification](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [China signals rare earth exports to EU will continue regardless of U.S. trade truce deadline](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [AdFection: Targeted ads turned into a pipeline for zero-click mercenary spyware](https://citizenlab.ca/research/how-discover-tech-turned-targeted-ads-into-a-pipeline-for-spyware/) ⭐️ 9.0/10

Citizen Lab reports that targeted advertising infrastructure was exploited as a delivery channel for zero-click mercenary spyware, raising serious concerns about ad-tech security and the commercial spyware ecosystem.

hackernews · jcomp · Oct 15, 10:43 · [Discussion](https://news.ycombinator.com/item?id=50101813)

**Tags**: `#security`, `#spyware`, `#adtech`, `#surveillance`, `#mobile`

---

<a id="item-tech-news-2"></a>
### [Meta releases Muse Spark Open, an 816B open-weight MoE model](https://research.meta.ai/blog/muse-spark-open) ⭐️ 8.0/10

Meta has released Muse Spark Open, an open-weight 816B-parameter mixture-of-experts model with roughly 42B active parameters \(per the Hugging Face listing Muse-Spark-Open-816B-A42B\). The release is optimized to run on Mac Studio hardware according to 9to5mac&\#x27;s coverage, and Meta documents deployment support across a wide range of runners. The model ships under a custom license that permits most uses but restricts offering the model as a hosted service when the provider&\#x27;s aggregate gross revenue exceeds $20 million.

hackernews · bigwheels · Oct 15, 17:47 · [Discussion](https://news.ycombinator.com/item?id=50107379)

**「Context」** Muse Spark Open is Meta&\#x27;s new open-weight model release: an 816B-parameter mixture-of-experts model with 42B active parameters, a 1M-token context window, and native multimodality aimed at coding and agentic work, published under the restrictive Muse Model License rather than a fully permissive one. The license permits most uses but requires attribution and a separate agreement once model-service revenue exceeds $20 million, a clause similar in spirit to previous Meta open-weight licensing limits. It continues Meta&\#x27;s strategy of releasing open-weight models, and it has been positioned to run on modest hardware, with reports that two Mac Studios can host the model entirely on a desktop.

**「Licensing and deployment caveats」** Organizations that resell model access via API and earn more than $20 million in aggregate revenue are blocked by the license&\#x27;s &quot;Model as a Service&quot; clause, so most enterprises can self-host but large cloud providers cannot offer it as a hosted endpoint. Smaller teams should find adoption straightforward: Meta has made the model runnable on major runners from Unsloth to MLX, and it is reportedly tuned to run on Mac Studio hardware.

**「Debate over performance and openness」** Commenters disagreed on the model&\#x27;s competitiveness: one cited Artificial Analysis results showing Muse Spark Open underperforming Qwen3.8 Flash Next and GLM 5.3 Flash \(each of which runs on a single B300\), while others praised the broad deployment support. Community members also debated the license terms, with one summarizing the Model-as-a-Service revenue cap as the only significant restriction, and Simon Willison reported benchmarking the model at multiple reasoning levels via OpenRouter because it is too large to self-host locally.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/meta-models/Muse-Spark-Open-816B-A42B">meta-models/Muse-Spark-Open-816B-A42B · Hugging Face</a></li>
<li><a href="https://www.unite.ai/metas-816b-parameter-muse-spark-open-weights-are-now-public/">Meta’s 816B-Parameter Muse Spark Open Weights Are Now Public</a></li>

</ul>
</details>

**Tags**: `#open-weights`, `#large-language-models`, `#meta`, `#model-licensing`, `#model-benchmarks`

---

<a id="item-tech-news-3"></a>
### [Goodfire&\#x27;s &\#x27;Clean Networks&\#x27; Interpretability Claim Draws Skepticism](https://already-clean.goodfire.com/) ⭐️ 7.0/10

Goodfire, via Nick Cammarata&\#x27;s announcement, published a mechanistic interpretability claim that neural networks are &\#x27;clean&\#x27; — that neurons carry simple, interpretable roles rather than the overloaded, polysemantic concepts much prior work described. The claim is presented as a large evidentiary brief revisiting famously messy neurons and cataloging how polysemanticity arises. It is a contested research claim, not an independently verified result, and it arrived via a promotional-adjacent source linked on Hacker News \(501 points, 195 comments\).

hackernews · themgt · Oct 15, 16:04 · [Discussion](https://news.ycombinator.com/item?id=50105647)

**「The polysemanticity debate」** A long-standing problem in mechanistic interpretability is that individual neurons often appear polysemantic — responding to many unrelated concepts — which the field has typically attributed to superposition, where networks pack more features than neurons into their parameters. The Goodfire essay challenges this by arguing that polysemanticity in earlier studied models came from ordinary, mostly fixable issues rather than superposition, and reports that roughly 90% of Qwen3-32B neuron poles have one main job, allowing most neurons to be understood in models up to trillions of parameters. Nick Cammarata, who co-authored early mechanistic interpretability work at OpenAI and came away pessimistic then, frames the claim as good news for alignment, on the view that alignment cannot be solved without knowing what models are doing internally.

**「Why it matters」** If the claim holds up under review, it would make model internals easier to inspect, which Cammarata argues is a prerequisite for alignment: &\#x27;I don&\#x27;t think we can solve alignment if we don&\#x27;t know what we&\#x27;re building.&\#x27; Until the evidence is independently validated, practitioners should treat the &\#x27;clean networks&\#x27; framing as a hypothesis rather than an established finding.

**「Community reaction」** Hacker News commenters pushed back hard: bluejay2387 argued the claims &\#x27;seem to be an overreach of what is actually proven,&\#x27; noting long-known phenomena like the Lottery Ticket Hypothesis and condensed representations \(citing the Multimodal Gap paper\) are not mutually exclusive with parameter overloading. Others, like antics, read the work more charitably as a brief arguing AI interpretability could become like &\#x27;sequencing the AI genome,&\#x27; showing the discussion split between skepticism and enthusiasm.

<details><summary>References</summary>
<ul>
<li><a href="https://www.explainx.ai/blog/goodfire-neural-networks-are-already-clean-cammarata-neurons-interpretable-90-percent-qwen3-32b-2026">Goodfire: Neural Networks Are Already Clean, Claim Checked ...</a></li>
<li><a href="https://www.goodfire.com/research/already-clean">Neural Networks Are Already Clean - Goodfire</a></li>

</ul>
</details>

**Tags**: `#mechanistic-interpretability`, `#neural-networks`, `#AI-safety`, `#machine-learning`, `#interpretability-debate`

---

<a id="item-tech-news-4"></a>
### [Libreboot 26.10 adds UEFI support and 233 Chromebooks](https://libreboot.org/news/libreboot2610.html) ⭐️ 7.0/10

Libreboot has released version 26.10, codenamed &quot;Ominous Olive,&quot; which integrates UEFI/EDK and imports all 233 currently supported Chromebooks from MrChromebox&\#x27;s coreboot distribution. The Chromebook support is source-only in this release: users must build from source, as no prebuilt binaries are provided, and per the release notes only the Baytrail \(Kip\) device has been tested so far. The project&\#x27;s maintainer highlighted an AI-related policy as a headline feature of the release, though commenters largely focused on the hardware expansion.

hackernews · iamnothere · Oct 15, 12:52 · [Discussion](https://news.ycombinator.com/item?id=50102923)

**「Background」** Libreboot is a libre-software distribution based on coreboot, a community firmware project that replaces proprietary BIOS/UEFI firmware on motherboards. The project has historically restricted itself to hardware that can be initialized without proprietary firmware blobs and maintained only a small list of supported boards, while MrChromebox separately maintains a coreboot distribution that has long supported a large set of Chromebooks. The 26.10 release brings these lines together by integrating UEFI/EDK and importing MrChromebox&\#x27;s Chromebook support directly into Libreboot.

**「Impact」** Libreboot users now have access to a far wider range of libre-firmware-compatible hardware, and the Chromebook ports reuse MrChromebox&\#x27;s upstream work, which should make adding future devices easier. Owners of the newly imported Chromebooks should note the source-only constraint and limited testing: beyond Baytrail, ports are untested and require building the firmware themselves.

**「Community discussion」** Commenters mostly welcomed the UEFI/EDK integration and Chromebook expansion as a large step for hardware coverage, with one noting related ChromeOS ports to the Heads firmware project using MrChromebox&\#x27;s code as an upstream dependency. Some commenters also discussed the project&\#x27;s strict policy against LLM-assisted contributions, with opinions divided between seeing it as a refreshing stance and considering the policy the less significant part of the release.

**Tags**: `#open-source firmware`, `#libreboot`, `#coreboot`, `#UEFI`, `#chromebooks`

---

<a id="item-tech-news-5"></a>
### [Anthropic reports quarterly revenue up nearly 50% to $16.8bn ahead of possible IPO](https://simonwillison.net/2026/Oct/15/anthropic-tells-investors/) ⭐️ 7.0/10

According to FT reporting summarized by Simon Willison, Anthropic hosted investors and disclosed quarterly revenue of about $4.8bn in Q1, $11.5bn in Q2, and $16.8bn in Q3 2026 — a roughly 46% quarter-over-quarter increase. The company said Q3 generated $1.70 in revenue per $1 spent on computing, with adjusted operating margins \(excluding stock-based compensation\) of 11%. Anthropic also told investors it had materially cut back &quot;distillation&quot; — rivals training models on Anthropic&\#x27;s outputs — which had accounted for 5% to 7% of revenue. The FT&\#x27;s account relies on unnamed &quot;people with knowledge of the matter,&quot; and the disclosures come ahead of a possible IPO, so the figures are reported claims rather than audited results.

rss · Simon Willison · Oct 15, 13:04

**「Why this matters」** Anthropic is preparing a potential IPO as soon as next month, and this investor-day briefing is part of its effort to build support among prospective backers. Willison notes that Anthropic appears to have stopped emphasizing &quot;annualized run-rate revenue&quot; in these communications, as it did previously, instead disclosing actual quarterly figures — a shift that makes the disclosed numbers easier to evaluate. The Financial Times, New York Times, and Reuters all reported the same investor-day figures, including the $16.8 billion third-quarter revenue and quarterly profitability.

**「Distillation crackdown and shift in revenue framing」** Willison&\#x27;s &quot;napkin maths&quot; suggests that if distillation was 5% of Q2 revenue before the cutback, unnamed rival labs spent over half a billion dollars in a single quarter using Anthropic&\#x27;s models to train their own — spending Anthropic has now reduced. The company also appears to have stopped leaning on &quot;annualized run-rate revenue&quot; in investor communications, presenting quarterly figures instead.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/11632d03-358c-454b-af95-d06d4072932b?syn-25a6b1a6=1">Anthropic tells investors quarterly revenue up nearly 50% to ...</a></li>
<li><a href="https://www.nytimes.com/2026/10/14/technology/anthropic-ipo-revenue-profit.html">Anthropic Says Revenue Jumped 45% to $16.8 Billion in Third ...</a></li>
<li><a href="https://www.reuters.com/technology/anthropic-revenue-jumps-168-billion-third-quarter-ft-reports-2026-10-14/">Anthropic revenue jumps to $16.8 billion in third quarter, FT ...</a></li>

</ul>
</details>

**Tags**: `#AI industry`, `#Anthropic`, `#business-of-AI`, `#model distillation`, `#IPO`

---

<a id="item-tech-news-6"></a>
### [Self-Organizing Plasticity Rules Yield Networks Matching Backpropagation on Classification](https://www.reddit.com/r/MachineLearning/comments/1x6hmyg/how_artificial_neural_networks_build_their_own/) ⭐️ 7.0/10

A PNAS study published on 9 October 2026, covered by MIT on 13 October, shows that randomly interconnected neuron-like units governed by shared local plasticity rules can self-assemble learning motifs and learn pattern recognition and image classification. On the tasks tested, the self-organized networks performed similarly to backpropagation-trained networks. The approach differs from standard practice in that learning circuitry is not designed directly; instead, local rules are specified from which the learning machinery organizes itself. The authors explicitly caution that self-organization does not establish that the brain uses this mechanism, and the work is motivated by biological plausibility rather than as a replacement for backpropagation in large-scale models.

reddit · r/MachineLearning · /u/Dorian182 · Oct 15, 10:01

**「Background」** Backpropagation, the standard algorithm behind most modern neural networks, trains a network by propagating an explicit error signal backward through the entire architecture, a process widely considered biologically implausible because real synapses have no access to such a global signal. The alternative approach in this study instead specifies only local plasticity rules that each neuron-like unit follows, letting the learning circuit&\#x27;s internal motifs organize themselves—shifting the design problem from building the machinery directly to defining the rules from which it emerges. The authors and the researcher emphasize that this biological plausibility is a motivation, not evidence that the brain actually learns this way.

**「Relevance for researchers」** For ML researchers, the demonstrated tasks are limited to classification, so the result should be evaluated alongside open questions about the stability of the motifs under different initial connectivity and whether the approach extends beyond those tasks, rather than treated as a drop-in alternative to backpropagation.

**Tags**: `#machine-learning`, `#neural-networks`, `#biologically-inspired-learning`, `#self-organization`, `#research`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China signals rare earth exports to EU will continue regardless of U.S. trade truce deadline](https://www.cnbc.com/2026/10/15/china-rare-earth-exports-europe.html) ⭐️ 7.0/10

China&\#x27;s Commerce Ministry said it will keep approving rare earth export licenses for Europe regardless of whether the U.S.-China trade truce is extended past January, when current suspension of export restrictions is set to lapse.

rss · CNBC Finance · Oct 15, 09:02

**「Background」** Rare earths are minerals essential to products like electric vehicles, wind turbines, and electronics, and China dominates their global supply. In October 2025, Beijing tightened rare earth export controls in response to a U.S. rule expanding its blacklist to subsidiaries of Chinese companies, before both sides agreed at a leaders&\#x27; summit to suspend those measures for one year — a truce since extended by two months to January.

**「Impact」** European industries that depend on rare earths for products like electric vehicles and electronics gain more certainty on supply, as China offered a &quot;green channel&quot; licensing mechanism while asking the EU to support Chinese imports in dual-use sectors.

<details><summary>References</summary>
<ul>
<li><a href="https://tradersunion.com/news/financial-news/show/3823115-china-rare-earth-exports-europe/">China rare earth exports to Europe set to continue beyond U.S ...</a></li>
<li><a href="https://www.zetik.com/news/article/story_id-p008-224175">China Pledges Rare Earth Exports to EU Beyond January ...</a></li>

</ul>
</details>

**Tags**: `#China`, `#rare earths`, `#EU trade`, `#US-China trade truce`, `#export controls`

---