---
layout: default
title: "Horizon Summary: 2026-09-02 (EN)"
date: 2026-09-02
lang: en
---

> From 51 items, 14 important content pieces were selected

---

**Technology News**
1. [Anthropic releases Claude Fable 5.1 and Mythos 5.1 with system card and price cuts](#item-tech-news-1) ⭐️ 9.0/10
2. [Small transformer trained in 1.5 hours reportedly beats many LLMs on ARC-1](#item-tech-news-2) ⭐️ 8.0/10
3. [Claude Fable 5.1 made me a really nice animated pelican](#item-tech-news-3) ⭐️ 8.0/10
4. [Virtualizor update infrastructure hit by BGP hijacking, malicious updates installed root backdoor](#item-tech-news-4) ⭐️ 8.0/10
5. [Dan Luu Grades Ed Zitron&\#x27;s AI-Skeptic Prediction Record](#item-tech-news-5) ⭐️ 7.0/10
6. [AnkiDroid: Google Play no longer allowing Open Collective donation link](#item-tech-news-6) ⭐️ 7.0/10
7. [Korea’s Trillion-Dollar Sovereign AI Investment: Nvidia Wins, Hynix Loses](#item-tech-news-7) ⭐️ 7.0/10
8. [Reddit post maps latent reasoning landscape: Coconut, HRM/TRM, BDH-CQ](#item-tech-news-8) ⭐️ 7.0/10
9. [EvoUndo Framework Tests Whether LLM Agent Self-Modifications Can Be Safely Reversed](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s Solar Capacity Overtakes Coal for First Time as Largest Power Source](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed Governor Barr Open to Rate Hike if Inflation Stays High](#item-finance-news-2) ⭐️ 7.0/10
3. [Qualcomm to Raise Chip Prices by Double Digits for Products Shipped After September 1](#item-finance-news-3) ⭐️ 7.0/10
4. [China to Tax Foreign Individuals&\#x27; Dividends at 20% from September 2026](#item-finance-news-4) ⭐️ 7.0/10
5. [日本放宽加班规定，45 小时上限不再强制](#item-finance-news-5) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Anthropic releases Claude Fable 5.1 and Mythos 5.1 with system card and price cuts](https://www.anthropic.com/claude-fable-and-mythos-5-1) ⭐️ 9.0/10

Anthropic released Claude Fable 5.1 and Claude Mythos 5.1, publishing an official system card \(PDF\) and a &\#x27;What&\#x27;s new in Claude Fable 5.1&\#x27; documentation page for this point release of its frontier model family. The most concrete change flagged in discussion is pricing: cache read costs reportedly fell from $1 per million tokens to $0.25 per million, making Fable 5.1&\#x27;s cache reads half the price of Opus&\#x27;s \($0.5/M\) and fueling speculation that Anthropic cut prices because the original Fable pricing saw limited adoption. Community testing of the new thinking-effort settings found the &\#x27;xhigh&\#x27; level notably capable, while an &\#x27;effort max&\#x27; test generation took just under 14 minutes to complete. An Anthropic employee also highlighted a less stereotypical, more natural writing style and more reliable adherence to style instructions. The supplied material consists mainly of links and truncated comments, so specific capability-improvement claims cannot be independently verified from the evidence given.

hackernews · denysvitali · Sep 1, 17:53 · [Discussion](https://news.ycombinator.com/item?id=49525378)

**「Background」** Claude Fable and Claude Mythos are model lines within Anthropic&\#x27;s Claude family of frontier large language models, and Claude Mythos 5.1 is identical to Fable 5.1 except that it offers more permissive safeguards for vetted individuals and organizations whose work is affected by Anthropic&\#x27;s cybersecurity and life sciences restrictions. Alongside the release, Anthropic published a system card dated September 1, 2026, based on the final snapshots of both models, following its practice of documenting new frontier releases. This point release arrives roughly three months after the original Fable 5, with coverage describing gains in coding precision and complex reasoning along with lower developer pricing.

**「Impact」** Developers running Claude Fable 5.1 through the API face substantially lower costs for cache-heavy workloads, since cache reads now cost $0.25 per million tokens \(a 75% reduction from $1/M\), while input and output pricing stays at $10/M and $50/M respectively. This pricing shift may pressure broader LLM pricing, as community analysis notes Fable 5.1&\#x27;s cache reads now cost half of Opus&\#x27;s $0.5/M, suggesting limited demand at the original price point.

**「Community reaction」** Reactions were mixed: Anthropic&\#x27;s felixrieseberg praised Fable 5.1&\#x27;s more natural prose and better style-instruction following, and simonw benchmarked the new effort levels \(finding xhigh strong and max slow at roughly 14 minutes per generation\), while GodelNumbering argued the cache-read cut to $0.25/M signals weak uptake at the original price, a possible ceiling on LLM pricing generally, and that excluding terminal-bench-science results the benchmark gains are hard to see. A dissenting commenter \(exabrial\) claimed Fable was nerfed, that Mythos functions as marketing by being withheld as &\#x27;too good to release&\#x27;, and that thought traces were removed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-1">Introducing Claude Fable 5.1 and Claude Mythos 5.1 \ Anthropic \ Anthropic</a></li>
<li><a href="https://www-cdn.anthropic.com/0339e6a7c5c7b87f5c07798616dc32c215d14235/Claude+Fable+5.1+&amp;+Claude+Mythos+5.1+System+Card.pdf">System Card: Claude Fable 5.1 &amp; Claude Mythos 5.1 September 1, 2026</a></li>
<li><a href="https://www.androidheadlines.com/2026/09/anthropic-upgrades-claude-fable-5-1-model.html">Claude AI Gets Smarter: Anthropic Debuts Fable 5.1 and Mythos 5.1 Upgrades</a></li>
<li><a href="https://openrouter.ai/anthropic/claude-fable-5.1">Claude Fable 5 . 1 - API Pricing &amp; Providers | OpenRouter</a></li>
<li><a href="https://llm-stats.com/models/claude-fable-5-1">Claude Fable 5 . 1 API Pricing , Context Window &amp; Benchmarks</a></li>
<li><a href="https://www.anthropic.com/claude-fable-and-mythos-5-1">Introducing Claude Fable 5 . 1 and Claude Mythos 5 . 1 \ Anthropic</a></li>

</ul>
</details>

**Tags**: `#anthropic`, `#claude`, `#llm`, `#model-release`, `#api-pricing`

---

<a id="item-tech-news-2"></a>
### [Small transformer trained in 1.5 hours reportedly beats many LLMs on ARC-1](https://mvakde.github.io/blog/44-on-arc-1/) ⭐️ 8.0/10

An independent researcher reports in a personal blog post that a small autoregressive transformer trained from scratch in about 1.5 hours outperforms many LLMs on the ARC-1 reasoning benchmark. The author stresses the model is not an LLM, noting that until this result&\#x27;s first version the benchmark had mainly been scaled by LLMs or their finetunes at enormous training cost, while other attempts relied on very complex architectures or extremely high compute. The largest reported score increases came from modern architecture choices \(SwiGLU instead of GELU, RMSNorm instead of LayerNorm\), greater data diversity with better data shuffling, and scaling from 4 to 8 layers. The author rejects the &\#x27;training on test&\#x27; criticism, explaining that this specifically means training on the labels of test data, which were not used, and that ARC is a metalearning benchmark where learning from the eval puzzles is expected. The result is self-reported and unreviewed, so independent replication would be needed to confirm the scores.

hackernews · porridgeraisin · Sep 1, 09:52 · [Discussion](https://news.ycombinator.com/item?id=49519939)

**「Background」** ARC-AGI-1 is a benchmark of abstract visual grid puzzles that, as framed by the author&\#x27;s accompanying open-source mdlARC project, serves as a testbed for sample efficiency — measuring how well a model generalizes rather than how much compute it consumes. Top scores at this level have historically come either from large pretrained LLMs or their finetunes, trained at substantial cost, or from specialized small reasoning architectures such as the Hierarchical Reasoning Model \(HRM\) and Tiny Recursive Model \(TRM\), which the new model reportedly matches in score. From-scratch training here means the model learned all its weights without any pretrained LLM foundation — trained on a single rented RTX 5090 for roughly $0.67 of compute, improving on the author&\#x27;s earlier 27.5%-for-about-$2 attempt — so the claim rests on what a compact vanilla transformer can learn in a couple of GPU-hours rather than on knowledge inherited from internet-scale pretraining.

**「Impact」** ML researchers and hobbyists without frontier-scale budgets gain a concrete proof of concept that strong ARC-1 reasoning performance can reportedly be reached by a small from-scratch autoregressive transformer trained in about 1.5 hours, challenging the assumption that only LLMs, highly complex architectures, or enormous training compute can scale a benchmark whose 2024 competition grand prize remained unclaimed. Because the result is self-reported on an unreviewed personal blog and defended rather than independently replicated, its practical influence on research practice depends on outside validation.

**「Community discussion」** In a 570-point Hacker News thread with 149 comments, the author actively answered questions and defended the methodology against &\#x27;training on test&\#x27; accusations, while other commenters engaged with the argument about poor sample efficiency in modern LLMs. Reaction was broadly positive but not uncritical: one commenter warned that the main gains came from standard tuning — SwiGLU, RMSNorm, better shuffling, and going from 4 to 8 layers — commonly called &\#x27;squeezing the lemon&\#x27; and usually a last resort, while another congratulated the author on a top-5 Kaggle placement.

<details><summary>References</summary>
<ul>
<li><a href="https://mvakde.github.io/blog/44-on-arc-1/">44% on ARC-AGI-1 in 67 cents - Mithil Vakde’s Homepage</a></li>
<li><a href="https://mvakde.github.io/blog/new-pareto-frontier-arc-agi/">New Pareto Frontier on ARC-AGI - Mithil Vakde’s Homepage</a></li>
<li><a href="https://github.com/mvakde/mdlARC">GitHub - mvakde/mdlARC: Goal is to solve sample efficiency by using ARC-AGI as a benchmark · GitHub</a></li>
<li><a href="https://arcprize.org/competitions/2024">ARC Prize 2024</a></li>

</ul>
</details>

**Tags**: `#machine learning`, `#transformers`, `#ARC benchmark`, `#sample efficiency`, `#AI research`

---

<a id="item-tech-news-3"></a>
### [Claude Fable 5.1 made me a really nice animated pelican](https://simonwillison.net/2026/Sep/1/claude-fable-5-1/) ⭐️ 8.0/10

Simon Willison reports on Anthropic&\#x27;s Claude Fable 5.1 release day, summarizing its benchmark claims and putting it through his informal animated-pelican coding test.

rss · Simon Willison · Sep 1, 23:57

**Tags**: `#AI`, `#LLM`, `#Anthropic`, `#benchmarks`, `#model-release`

---

<a id="item-tech-news-4"></a>
### [Virtualizor update infrastructure hit by BGP hijacking, malicious updates installed root backdoor](https://www.virtualizor.com/blog/security-incident-bgp-hijacking/) ⭐️ 8.0/10

Virtualizor&\#x27;s update infrastructure was compromised via BGP route hijacking between August 28 and 30, 2026, during which attackers used a valid TLS certificate to deliver malicious update packages to customers&\#x27; servers. The company, operated by Softaculous, confirmed that only a small number of installations updated during this window were affected and emphasized that this was a distribution-channel compromise rather than a vulnerability in the software code itself. Independent forensics show the malicious package wrote an SSH key for the root user, installed a Java payload, and established persistence services on compromised hypervisors; hosting provider AlbaHost found indicators of compromise on 5 of its 34 hypervisors. Softaculous stated there is currently no evidence that its other products were affected. The incident is a supply-chain attack on the software distribution path, and while its scope appears limited, a root-level backdoor on hypervisors poses a serious risk to the hosting and virtualization industry and highlights broader concerns about update-channel security and BGP protection.

telegram · zaihuapd · Sep 1, 06:05

**「Background」** Virtualizor is a virtualization control panel developed by Softaculous, a vendor whose software is widely used by web hosting providers and administrators to deploy and manage virtual private servers. BGP \(Border Gateway Protocol\) is the routing system that directs internet traffic between networks, and BGP hijacking occurs when an attacker announces unauthorized routes to divert traffic destined for a victim&\#x27;s IP ranges to a server they control. In this incident, between August 28 and 30, 2026, such a hijack redirected Softaculous traffic for roughly 33 hours, allowing the attacker to impersonate the Virtualizor update system and deliver a malicious update to a small number of installations.

**「Impact」** Hosting providers running Virtualizor to manage VPS nodes on KVM, Xen, LXC, OpenVZ, and Proxmox face direct risk, since a single compromised master can control hundreds of virtualization servers and place a root-level backdoor high in the hosting stack. Affected operators should immediately inspect their nodes for indicators such as unauthorized root SSH keys, rogue accounts, and systemd persistence, even if they did not manually update during the August 28–30, 2026 window.

<details><summary>References</summary>
<ul>
<li><a href="https://www.softaculous.com/blog/security-incident-bgp-hijacking-update/">Security Incident - BGP Hijacking - Update - Softaculous Blog</a></li>
<li><a href="https://www.theregister.com/security/2026/09/01/33-hour-bgp-hijack-of-softaculous-traffic-prompts-security-scramble/5293608">33-hour BGP hijack of Softaculous traffic prompts security scramble</a></li>
<li><a href="https://cybersecuritynews.com/virtualizor-compromise/">BGP Hijack Diverts Softaculous Traffic to Deliver Malicious Virtualizor ...</a></li>
<li><a href="https://teramont.net/blog/virtualizor-hacked-bgp-hijack-malicious-update">Virtualizor hacked: BGP hijack , scope and IOC</a></li>

</ul>
</details>

**Tags**: `#security`, `#supply-chain-attack`, `#bgp-hijacking`, `#virtualization`, `#incident-response`

---

<a id="item-tech-news-5"></a>
### [Dan Luu Grades Ed Zitron&\#x27;s AI-Skeptic Prediction Record](https://danluu.com/zitron/) ⭐️ 7.0/10

A new essay on danluu.com, the long-running blog of engineer Dan Luu known for heavily researched technical analysis, offers a retrospective, annotated assessment of how Ed Zitron&\#x27;s AI-skeptic predictions have held up against actual outcomes. Zitron is one of the most prominent voices arguing that the AI industry is a financial bubble, and the piece applies prediction accountability to a leading critic, a standard more often demanded of industry boosters than of skeptics. The Hacker News submission drew roughly 398 points and 480 comments, indicating an active community debate over whether AI critics and industry leaders alike should be judged by their prediction records. The available material does not specify which predictions were graded or the essay&\#x27;s final tally, so readers should consult the full post for the detailed scoring.

hackernews · jatins · Sep 1, 18:35 · [Discussion](https://news.ycombinator.com/item?id=49526069)

**「Who Is Ed Zitron and Why Grade His Predictions?」** Ed Zitron is a prominent AI skeptic — CEO of the PR firm EZPR, author of the Where&\#x27;s Your Ed At newsletter, and host of the Better Offline podcast — known for arguing that the AI industry is a bubble in which most startups are fundamentally unprofitable. Dan Luu, the author of danluu.com, is a software engineer and writer with a reputation for long-form, data-driven analysis of technology claims. The article in question applies a retrospective scorecard approach to Zitron&\#x27;s public predictions about AI progress and business outcomes, a form of accountability analysis that Luu has previously applied to technology futurists, several of whom he found to be nearly completely wrong while still framing their records favorably.

**「Impact」** For followers of AI industry debate, the analysis supplies an annotated scorecard for checking a prominent skeptic&\#x27;s forecasts against actual outcomes, such as his February 2024 claim that generative AI was reaching the upper limits of what it can do and how accurate its outputs can be. The discussion it sparked also shows readers demanding the same prediction accountability from AI boosters like Sam Altman and Dario Amodei, not just from critics.

**「Community discussion」** Many commenters endorsed symmetric scorekeeping, arguing that Sam Altman, Dario Amodei, and other AI leaders deserve the same annotated treatment because, in their view, breathless claims about white-collar work ending within months are as overstated as Zitron&\#x27;s rhetoric, while others contended that AI skepticism&\#x27;s evolution into a political identity has given Zitron a captive audience and made it hard for him to concede a miss. Pushback on the thread focused on method: one commenter observed that readers were projecting their own predictions onto Zitron&\#x27;s statements instead of engaging with the essay&\#x27;s literal text, and another argued the post overlooked a claimed accounting effect in which hyperscalers&\#x27; equity investments in OpenAI and Anthropic inflate reported earnings as rising valuations flow through as other income.

<details><summary>References</summary>
<ul>
<li><a href="https://danluu.com/zitron/">How accurate have Ed Zitron&#x27;s AI skeptic predictions been?</a></li>
<li><a href="https://www.wheresyoured.at/optimistic-cowardice/">The Phony Comforts of AI Optimism | Ed Zitron &#x27;s Where&#x27;s Your Ed At</a></li>
<li><a href="https://www.forbes.com/sites/johnnavin/2025/10/01/ai-skeptic-ed-zitron-says-artificial-intelligence-is-not-all-that/">AI Skeptic Ed Zitron Says Artificial Intelligence Is Not All That</a></li>
<li><a href="https://danluu.com/zitron/?ref=taaft">How accurate have Ed Zitron &#x27;s AI skeptic predictions been?</a></li>

</ul>
</details>

**Tags**: `#AI industry`, `#AI skepticism`, `#prediction analysis`, `#AI bubble`, `#tech commentary`

---

<a id="item-tech-news-6"></a>
### [AnkiDroid: Google Play no longer allowing Open Collective donation link](https://github.com/ankidroid/Anki-Android/issues/21656) ⭐️ 7.0/10

Google Play is no longer permitting AnkiDroid&\#x27;s Open Collective donation link, reigniting debate over app-store gatekeeping and the precarious position of donation-funded open-source apps.

hackernews · hexa555 · Sep 1, 10:11 · [Discussion](https://news.ycombinator.com/item?id=49520022)

**Tags**: `#google-play`, `#open-source`, `#android`, `#app-store-policy`, `#funding`

---

<a id="item-tech-news-7"></a>
### [Korea’s Trillion-Dollar Sovereign AI Investment: Nvidia Wins, Hynix Loses](https://newsletter.semianalysis.com/p/koreas-trillion-dollar-sovereign) ⭐️ 7.0/10

A SemiAnalysis analysis of Korea&\#x27;s sovereign AI investment push, examining its national AI tournament, the elimination of a top non-Chinese open source model, Nvidia&\#x27;s reliance on open source, and consequences for Hynix and Samsung.

rss · Semianalysis · Sep 1, 20:14

**Tags**: `#sovereign-ai`, `#semiconductors`, `#nvidia`, `#open-source-models`, `#south-korea`

---

<a id="item-tech-news-8"></a>
### [Reddit post maps latent reasoning landscape: Coconut, HRM/TRM, BDH-CQ](https://www.reddit.com/r/MachineLearning/comments/1w4evwo/latent_reasoning_landscape_in_2026_mapping_bdhcq/) ⭐️ 7.0/10

A r/MachineLearning post by /u/Typical-Scene-5794 surveys latent reasoning research from 2024 to 2026 and argues that progress toward stronger reasoning systems may depend less on ever-longer verbalized chains of thought \(CoT\) than on architectures that compute beyond the token stream, motivated by evidence that LLMs can reach correct answers through flawed or fabricated CoT steps and produce logical steps that still end in wrong answers \(Kambhampati, 2025\). The author organizes the field into five families, starting with continuous thoughts in autoregressive LMs, where Coconut \(Hao et al., 2024\) feeds the model&\#x27;s final hidden state back in as the next input embedding and Soft Thinking \(Zhang et al., 2025\) reasons in a continuous concept space, with theory suggesting a single continuous state can hold several search frontiers and expand them in parallel \(Zhu et al., 2025\). A second cluster covers compressed discrete non-linguistic tokens, exemplified by Abstract-CoT \(Ramji et al., 2026\), which replaces verbal rationales with a short sequence from a learned vocabulary, and recurrent-depth or looped Transformer models \(Geiping et al., 2025; Saunshi et al., 2025; Zhu et al., 2026\) that reapply a shared block to a latent state, framed mostly as parameter efficiency and test-time-compute scaling rather than a new reasoning interface. The remaining families are task-trained recursive solvers, HRM \(Wang et al., 2025\) and TRM \(Jolicoeur-Martineau, 2025\), whose ARC pipelines the post characterizes as transductive because evaluation-task demonstrations are augmented into optimization with learned per-puzzle identities so an unseen task needs a backward pass before it can be answered, and in-context recurrent latent solvers such as BDH-CQ \(Engdahl et al., 2026\), built on the Dragon hatchling architecture \(Kosowski et al., 2025\), which writes demonstrations directly into a recurrent memory at inference time and solves test inputs by iterative computation in a separate continuous latent space, with reported results beyond the previously published cost-accuracy Pareto frontier on public ARC-AGI-1 and early pretraining experiments showing transformer-like scaling laws up to 600B parameters while preserving latent reasoning behavior. The post highlights two distinctions—how a system acquires a new task \(context, memory, or gradient-based optimization and finetuning\) and where intermediate computation happens \(language tokens, abstract tokens, or continuous latent states\)—and closes by asking whether CoT legibility, on which much of industry&\#x27;s interpretability and evaluation work depends, was a temporary consequence of how LLMs were scaled or a safety property worth paying an efficiency penalty to keep; as a community synthesis rather than primary research, its classifications and reported figures reflect the author&\#x27;s reading of the cited papers and are not independently verified within the post itself.

reddit · r/MachineLearning · /u/Typical-Scene-5794 · Sep 1, 15:14

**「Background」** Chain-of-thought \(CoT\) prompting is the prevailing way large language models work through problems: the model emits explicit natural-language intermediate steps before its final answer, and these readable traces are what much interpretability and evaluation work inspects. Latent reasoning is an emerging alternative family of techniques that performs intermediate computation in continuous hidden-state vectors, learned non-linguistic tokens, or recurrent memory rather than visible text; Coconut \(&quot;chain of continuous thought&quot;\) is the early representative, and because its latent thoughts have no surface form, they complicate step-level reward modeling and lack the auditable trace CoT provides. Several of the models the post discusses—the recursive solvers HRM and TRM and the in-context latent reasoner BDH-CQ—are evaluated on ARC, a puzzle benchmark used as a controlled, verifiable testbed for in-context generalization.

**「Impact」** If latent reasoning architectures such as Coconut, HRM/TRM, and BDH-CQ prove more efficient than verbalized chains of thought, interpretability and evaluation practitioners whose monitoring, auditing, and benchmarking methods depend on readable reasoning traces would lose the legible intermediate outputs those methods are built on. The urgency is partly tempered by existing evidence that chain-of-thought text is already often unfaithful to a model&\#x27;s actual computation, meaning current trace-based oversight may be weaker than it appears.

<details><summary>References</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/coconut-chain-of-continuous-thought">Coconut : Continuous Chain - of - Thought for LLMs</a></li>
<li><a href="https://aiwiki.ai/wiki/coconut_reasoning">Coconut ( Chain of Continuous Thought ) | AI Wiki</a></li>
<li><a href="https://www.alphaxiv.org/abs/2608.09888">BDH - CQ : In-Context Learning with Recurrent Latent Reasoning</a></li>
<li><a href="https://arxiv.org/pdf/2608.09888">BDH - CQ : In-Context Learning with Recurrent Latent Reasoning</a></li>
<li><a href="https://www.anthropic.com/research/reasoning-models-dont-say-think">Reasoning models don&#x27;t always say what they think \ Anthropic</a></li>
<li><a href="https://arxiv.org/abs/2307.13702">[2307.13702] Measuring Faithfulness in Chain - of - Thought Reasoning</a></li>
<li><a href="https://thetesserapress.com/articles/is-ai-reasoning-right-for-the-wrong-reasons">AI reasoning works, but the chains of thought may be mumblings...</a></li>

</ul>
</details>

**Tags**: `#latent-reasoning`, `#llm-architectures`, `#chain-of-thought`, `#machine-learning-research`, `#reasoning-models`

---

<a id="item-tech-news-9"></a>
### [EvoUndo Framework Tests Whether LLM Agent Self-Modifications Can Be Safely Reversed](https://www.reddit.com/r/MachineLearning/comments/1w4m0hq/evoundo_recoverabilityconstrained_selfevolution/) ⭐️ 7.0/10

A Reddit-posted research summary introduces EvoUndo, a framework for representing, synthesizing, diagnosing, and independently verifying whether self-modifications made by LLM agents to their own prompts, tools, middleware, resources, and execution harnesses can be reliably reversed across counterfactual states. Across 600 unseen one-shot self-evolution tasks, the authors identified 197 capability-improving mutations that failed recoverability verification, and conventional repair strategies under the original recovery representation recovered none of them \(0/197\). Deterministic oracle analysis recovered 48/197 under the original recovery language L0, while an extended recovery calculus raised empirical oracle recovery to 191/197. A protocol-locked 2x2 intervention separated two bottlenecks: exact state-address grounding improved recovery from 0/48 to 38/48 \(79.2%\) when the original language sufficed, and extending the recovery language enabled recovery on 142/143 \(99.3%\) of failures in the oracle-defined S1 stratum. On the primary gpt-oss-120b backbone, combining exact-address diagnostics with the richer language reduced recovery to 133/143 \(93.0%\), a negative interaction not reproduced in a Qwen3.8-27B replication, suggesting the effect is model-dependent; the authors conclude that reliable agent self-evolution requires co-designing verification, state grounding, witness semantics, and recovery-language expressivity rather than relying on iterative prompting alone.

reddit · r/MachineLearning · /u/AccomplishedLeg1508 · Sep 1, 19:17

**「Background」** LLM agents increasingly rely on a runtime &\#x27;harness&\#x27;—the surrounding scaffolding of prompts, tools, middleware, and resources that wraps the model—and some agent systems can modify this harness themselves at runtime to improve capability. This kind of self-evolution creates a safety concern: a mutation that helps in one state may leave persistent effects that cannot be undone in other, counterfactual states, so researchers have begun formalizing &\#x27;recoverability&\#x27; as a property that must be verified rather than assumed. EvoUndo, presented in an arXiv preprint, addresses this by coupling harness mutations with witness capture, counterfactual verification, typed diagnosis, and closed-loop recovery synthesis, and it builds on related work such as EvoHarness-RL on self-evolving runtime harnesses for long-horizon agents.

**「Relevance for Agent Safety Research」** For researchers and engineers building self-modifying LLM agent systems, the results suggest that rollback and recoverability cannot be assumed from successful mutations alone and may require explicit verification mechanisms and richer recovery representations. The findings are preliminary, however, as the work appears as a Reddit-posted summary linked to an arXiv preprint without a stated peer-review venue or independent replication.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2608.28363">[2608.28363] EvoUndo: Recoverability-Constrained Self-Evolution for LLM Agent Harnesses</a></li>
<li><a href="https://arxiv.org/html/2608.28363">EvoUndo: Recoverability-ConstrainedSelf-Evolution for LLM Agent Harnesses</a></li>
<li><a href="https://arxiv.org/html/2608.05446v1">EvoHarness-RL: Learning Self-Evolving Runtime Harness for Long-Horizon LLM Agents</a></li>

</ul>
</details>

**Tags**: `#LLM agents`, `#AI safety`, `#self-modification`, `#recoverability`, `#research`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s Solar Capacity Overtakes Coal for First Time as Largest Power Source](https://content-static.cctvnews.cctv.com/) ⭐️ 8.0/10

By the end of July 2026, China&\#x27;s installed solar power capacity had reached 1.286 billion kilowatts, or 31.5% of the national total, overtaking coal for the first time to become the country&\#x27;s largest power source by capacity, according to CCTV News. From January to July 2026, solar generated more than 802.4 billion kilowatt-hours, up 15.5% from a year earlier — roughly one of every eight kilowatt-hours of Chinese electricity.

telegram · zaihuapd · Sep 1, 02:42

**「Background」** Coal had long been China&\#x27;s largest power source by installed capacity, and the National Energy Administration&\#x27;s data show solar \(1.286 billion kilowatts, including 704 GW utility-scale and 582 GW distributed\) edging past coal&\#x27;s 1.285 billion kilowatts as of end-July 2026. Note that &quot;largest power source&quot; here refers to installed capacity, not actual output—solar still supplied only about one-eighth of electricity generated \(802.4 billion kWh from January to July\), since panels produce power only when the sun shines.

**「Impact」** The shift directly affects China&\#x27;s coal power sector, which no longer holds the top spot in installed capacity, though the one-in-eight generation share shows coal and other sources still supply most of the country&\#x27;s actual electricity.

<details><summary>References</summary>
<ul>
<li><a href="https://cn.investing.com/news/stock-market-news/article-3545883">国家能源局：截至7月底我国光伏发电装机容量达到12.86亿千瓦 首次超过煤电 提供者 智通财经</a></li>
<li><a href="https://www.chinanews.com.cn/cj/2026/09-01/10687699.shtml">国家能源局：我国光伏发电装机历史性超过煤电-中新网</a></li>

</ul>
</details>

**Tags**: `#China power sector`, `#solar energy`, `#energy transition`, `#installed capacity`, `#coal`

---

<a id="item-finance-news-2"></a>
### [Fed Governor Barr Open to Rate Hike if Inflation Stays High](https://www.cnbc.com/2026/09/01/fed-governor-barr-says-hell-support-rate-hike-if-inflation-doesnt-ease.html) ⭐️ 7.0/10

Fed Governor Michael Barr, a permanent voter on the rate-setting committee, said Tuesday he would support raising interest rates if inflation does not moderate toward the Fed&\#x27;s 2% target, with the latest readings at 3.7% headline and 3.3% excluding food and energy. Markets were pricing in roughly a 66% chance of a hike at the next meeting in two weeks, per CME Group&\#x27;s FedWatch tool.

rss · CNBC Finance · Sep 1, 14:01

**「Background」** Inflation has run above the Fed&\#x27;s 2% target for nearly 5½ years, and the central bank held its benchmark rate at 3.5%-3.75% in July; Fed Chairman Kevin Warsh&\#x27;s remarks last week were also widely read as leaning toward a hike.

**「Impact」** The comments reinforce expectations of higher borrowing costs, and the 10-year Treasury yield rose Tuesday to its highest level since mid-January 2025, affecting borrowers and investors tracking rate-sensitive markets.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#Treasury yields`

---

<a id="item-finance-news-3"></a>
### [Qualcomm to Raise Chip Prices by Double Digits for Products Shipped After September 1](https://www.macrumors.com/2026/08/31/qualcomm-chip-price-increase/) ⭐️ 7.0/10

Qualcomm will raise prices across its full chip lineup by double-digit percentages for products shipped after September 1, 2026, with exact increases to be negotiated with each customer; CEO Cristiano Amon said the company can no longer absorb rising supplier costs itself. Apple continues to buy Qualcomm modem chips for the iPhone 17 series, per MacRumors.

telegram · zaihuapd · Sep 1, 04:10

**「Background」** Qualcomm first announced the coming price hike in July 2026, warning customers that chips shipped after September 1 would cost more, and CEO Cristiano Amon has said the company can no longer absorb rising supplier costs on its own.

**「Impact」** Smartphone makers, including Apple and Android device manufacturers that rely on Qualcomm chips, face higher component costs that could feed into device prices.

<details><summary>References</summary>
<ul>
<li><a href="https://www.macrumors.com/2026/08/31/qualcomm-chip-price-increase/">Qualcomm Raising Chip Prices Starting Tomorrow - MacRumors</a></li>
<li><a href="https://en.shiftdelete.net/qualcomm-announces-double-digit-price-hikes-for-smartphone-chips/">Qualcomm Announces Double - Digit Price Hikes for Smartphone Chips</a></li>

</ul>
</details>

**Tags**: `#Qualcomm`, `#semiconductors`, `#chip pricing`, `#smartphone supply chain`, `#Apple`

---

<a id="item-finance-news-4"></a>
### [China to Tax Foreign Individuals&\#x27; Dividends at 20% from September 2026](https://m.cnfin.com/wx/share?url=//m.cnfin.com/yw-lb//zixun/20260901/4463424_1.html) ⭐️ 7.0/10

China&\#x27;s Ministry of Finance and State Taxation Administration announced that, starting September 1, 2026, foreign individuals receiving dividends from foreign-invested enterprises in China will pay individual income tax at a 20% rate, with the paying company required to withhold the tax and file it by the 15th of the month after payment. The rule repeals the relevant clauses of a 1994 circular that had previously governed this treatment.

telegram · zaihuapd · Sep 1, 09:33

**「Background」** Under a 1994 notice from the Ministry of Finance and State Taxation Administration \(Cai Shui Zi \[1994\] No. 20\), dividends and bonuses that foreign individuals received from foreign-invested enterprises in China had been temporarily exempt from individual income tax, a preference the new announcement now repeals.

**「Who is affected」** Foreign individual shareholders of foreign-invested enterprises in China will see 20% withheld from their dividend payments, ending the previous tax treatment in place since 1994.

<details><summary>References</summary>
<ul>
<li><a href="https://ailegal.baidu.com/?fr=seo_qadetail&amp;template=business&amp;articleType=qadetail&amp;articleId=538ba236b74f55251016">财 税 字 1994 20 ... | 法行宝</a></li>
<li><a href="https://m.163.com/dy/article/HGMQPL6C0519R487.html">m.163.com/dy/article/HGMQPL6C0519R487.html</a></li>

</ul>
</details>

**Tags**: `#China tax policy`, `#individual income tax`, `#foreign investors`, `#dividends`, `#fiscal policy`

---

<a id="item-finance-news-5"></a>
### [日本放宽加班规定，45 小时上限不再强制](https://www.orientaldaily.com.my/news/international/2026/09/01/844683) ⭐️ 7.0/10

Japan stops enforcing the monthly 45-hour overtime cap from September 1 as part of a pro-growth policy shift, drawing union criticism over karoshi risks.

telegram · zaihuapd · Sep 1, 12:56

**Tags**: `#Japan`, `#labor policy`, `#overtime regulation`, `#karoshi`, `#economic deregulation`

---