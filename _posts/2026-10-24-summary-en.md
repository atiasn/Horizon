---
layout: default
title: "Horizon Summary: 2026-10-24 (EN)"
date: 2026-10-24
lang: en
---

> From 33 items, 5 important content pieces were selected

---

**Technology News**
1. [Today, we hacked what we&\#x27;d set out to hack: the iPhone](#item-tech-news-1) ⭐️ 8.0/10
2. [Moonshot&\#x27;s Kimi K3.1 Pro debuts on API, open weights promised by November 4](#item-tech-news-2) ⭐️ 8.0/10
3. [Amazon&\#x27;s Trainium Expands From Inference Into Training, SemiAnalysis Argues](#item-tech-news-3) ⭐️ 8.0/10
4. [Google says it might use Gmail and Google Photos data for ad targeting](#item-tech-news-4) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s State Council Office Issues Guidance to Ease AI-Driven Job Displacement](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Today, we hacked what we&\#x27;d set out to hack: the iPhone](https://blog.calif.io/p/iphone) ⭐️ 8.0/10

A security research team reports successfully hacking an iPhone, prompting wide discussion of the exploit demos, root access, defensive mitigations like Lockdown Mode, and Apple&\#x27;s ecosystem lock-in.

hackernews · pavel\_lishin · Oct 23, 16:21 · [Discussion](https://news.ycombinator.com/item?id=50211474)

**Tags**: `#security`, `#ios`, `#exploits`, `#jailbreak`, `#apple`

---

<a id="item-tech-news-2"></a>
### [Moonshot&\#x27;s Kimi K3.1 Pro debuts on API, open weights promised by November 4](https://simonwillison.net/2026/Oct/23/kimi-k31-pro/) ⭐️ 8.0/10

Moonshot AI&\#x27;s Kimi K3.1 Pro is now available through the Kimi API, with the company promising that full model weights will be released by November 4, 2026 — until then it is API-only. Pricing is $2.00 per million input tokens and $10 per million output tokens, the same as GPT-6.1 Sol and half the price of Claude Opus 5.5, and a &quot;Highspeed&quot; variant runs 2-3x faster at twice the price \(input cache hits priced the same\). Artificial Analysis scored the model at 55, ahead of Claude Fable 5.1, GPT-6 Astra, and Gemini 4 Argon \(all at 53\) and behind only Claude Opus 5.5 \(58\), which Simon Willison notes is the highest placement yet for a soon-to-be open weight model against the frontier; Moonshot&\#x27;s own benchmarks claim rough parity with Opus 5.5 and GPT-6 Astra. In a hands-on test via Moonshot&\#x27;s OpenAI-compatible API, Willison found the model produced a solid pelican-on-a-bicycle SVG at max reasoning effort, though with both legs on the same side of the frame.

rss · Simon Willison · Oct 23, 19:40

**「Kimi K3 open-weights lineage」** Kimi K3.1 Pro succeeds Kimi K3, which Moonshot AI released in July 2026 with its full weights published under the Kimi K3 License; at 2.8 trillion parameters, K3 was the largest open-weights model at the time. That precedent is why the new model&\#x27;s promised November 4, 2026 weight release reads as a continuation of Moonshot&\#x27;s established open-weights practice rather than a first for the series, even though K3.1 Pro itself is initially API-only.

**「Impact」** Developers choosing models on price-performance can prompt kimi-k3.1-pro immediately through Moonshot&\#x27;s OpenAI-compatible API at half of Claude Opus 5.5&\#x27;s output price. The open question is the promised November 4, 2026 weights release: if it ships as stated, self-hosting and fine-tuning become possible at this benchmark level for the first time, but until then the model is API-only.

**「Community discussion」** On Hacker News, one user shared third-party Pac-Man benchmark results showing K3.1 Pro tying Claude Sonnet 5.5 at 93 while costing $0.68 versus Sonnet&\#x27;s $1.61, and another quoted Moonshot&\#x27;s disclosure that K3.1 Pro&\#x27;s offensive cyber capability was deliberately kept below what its training pipeline can produce, questioning why the company would withhold capability it says it already has. A $99/month subscriber separately reported hitting the 5-hour usage quota within 47 minutes of a single session, warning others to temper expectations about subscription limits.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kimi_%28AI%29">Kimi (AI) - Wikipedia</a></li>
<li><a href="https://www.yottalabs.ai/post/kimi-k3-specs-benchmarks-how-to-access-2026">Kimi K3 Model Size, Open Weights, and Hardware Requirements ...</a></li>
<li><a href="https://github.com/MoonshotAI/Kimi-K3">GitHub - MoonshotAI/Kimi-K3: Open Frontier Intelligence</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#model releases`, `#Moonshot AI`, `#open weights`, `#AI benchmarks`

---

<a id="item-tech-news-3"></a>
### [Amazon&\#x27;s Trainium Expands From Inference Into Training, SemiAnalysis Argues](https://newsletter.semianalysis.com/p/amazons-trainium-takes-a-strike-at) ⭐️ 8.0/10

A SemiAnalysis deep-dive argues that Amazon&\#x27;s Trainium accelerators, long considered best suited for inference, are becoming competitive for large-scale training workloads. The piece credits this shift to native Trainium support in PyTorch, high-quality continuous integration, integration with the TorchTitan training framework, and a new profiler the newsletter brands the &quot;GPU Impossible Profiler.&quot; If the assessment holds, organizations buying large-scale training compute would gain a credible alternative to NVIDIA, whose dominance in training hardware Trainium had not previously challenged. The claims represent SemiAnalysis&\#x27;s own technical argument rather than an independently measured benchmark, and the supplied material is limited to the article&\#x27;s headline and teaser, so the magnitude of Trainium&\#x27;s training competitiveness cannot be fully verified here.

rss · Semianalysis · Oct 23, 19:06

**「Background」** Amazon&\#x27;s Trainium is a custom AI accelerator that has historically been used mainly for inference, while NVIDIA GPUs have dominated large-scale model training. The shift described in the analysis rests on TorchNeuron, an open-source native PyTorch backend for Trainium that AWS recently announced; it builds on PyTorch&\#x27;s accelerator-agnostic extension points, including the PrivateUse1 device backend and torch.accelerator APIs, so existing model code, libraries, and tools can run on Trainium. TorchNeuron supports Trainium2 and Trainium3 and integrates with TorchTitan, PyTorch&\#x27;s native distributed training framework, giving developers a standard path to scale training across Trainium instances using Fully Sharded Data Parallelism \(FSDP\).

**「Impact」** Teams planning large-scale training runs on AWS now have a concrete alternative to price against NVIDIA GPUs: cost comparisons report AWS claiming 30–50% savings for Trainium 3 over the H200, and find Trainium usually cheaper for large, repeated, Neuron-supported training workloads. The catch is compatibility — capturing those savings means migrating to AWS&\#x27;s Neuron SDK, and the same comparisons still steer frontier architectures, one-off experiments, and portability-sensitive workloads toward GPUs.

<details><summary>References</summary>
<ul>
<li><a href="https://pytorch.org/blog/introducing-torchneuron-native-pytorch-backend-for-aws-trainium/">Introducing TorchNeuron: Native PyTorch backend for AWS Trainium</a></li>
<li><a href="https://www.aboutamazon.com/news/innovation-at-amazon/torchneuron-pytorch-aws-trainium-chips-ai">Amazon&#x27;s TorchNeuron runs PyTorch on AWS Trainium chips</a></li>
<li><a href="https://cryptobriefing.com/amazon-trainium3-native-pytorch-torchneuron/">Amazon gives Trainium3 native PyTorch support to win over AI ...</a></li>
<li><a href="https://www.spheron.network/blog/aws-trainium-3-vs-nvidia-h200-b200-llm-training-inference-2026/">AWS Trainium 3 vs NVIDIA H200 and B200 for LLM Training and ...</a></li>
<li><a href="https://cloudcostroom.com/blog/aws-trainium-vs-gpu-for-training-a-cost-comparison">AWS Trainium vs GPU for Training: Cost Compared</a></li>

</ul>
</details>

**Tags**: `#AI hardware`, `#Amazon Trainium`, `#PyTorch`, `#ML training infrastructure`, `#NVIDIA competition`

---

<a id="item-tech-news-4"></a>
### [Google says it might use Gmail and Google Photos data for ad targeting](https://www.theverge.com/tech/1017600/google-personal-intelligence-privacy-policy-ads-update) ⭐️ 7.0/10

An October 23, 2026 Verge report says Google has indicated it might begin using Gmail and Google Photos data to target ads, a step that would extend ad personalization into the contents of two of the company&\#x27;s most widely used consumer services. The claim is a hedged vendor statement of possibility rather than a confirmed shipped capability, and no details on scope, timing, or opt-out mechanics accompany it.

hackernews · JustSkyfall · Oct 23, 19:34 · [Discussion](https://news.ycombinator.com/item?id=50214218)

**「Background」** Google&\#x27;s &quot;Personal Intelligence&quot; beta connects the Gemini app to a user&\#x27;s Gmail, Google Photos, YouTube history, and Search data to provide more personalized AI assistance. That feature is the immediate context for this report, which describes a privacy policy update under which such personal content could also be used for ad targeting. In the EU, Google&\#x27;s help documentation quoted in the discussion states that Article 5\(2\) of the Digital Markets Act, in effect since March 6, 2024, requires the company to let users choose whether to link services such as Search, YouTube, and its ad services — the framework behind the service-linking options being discussed alongside this report.

**「What it means for users」** If Google implements the reported change, the contents of Gmail messages and Google Photos libraries could feed ad targeting for users who leave ad-personalization settings at their defaults. Google documents how to move data in and out of its products and how to opt out of ad personalization, including a search-personalization opt-out page, so users who object have concrete controls available now. One caveat: Google&\#x27;s own Google Photos page still states that photos and videos are never used for advertising — a vendor claim in tension with this report — so users should verify the current policy language and their settings rather than assume their media is either included or excluded.

**「Community reaction」** Commenters on the Hacker News thread read the hedged wording skeptically — one flatly equates &\#x27;might&\#x27; with &\#x27;absolutely will&\#x27; — and another shared a 2023 anecdote alleging Google was already using Google Docs content for ad targeting after he tracked weight loss only in a spreadsheet, though that remains an unverified personal claim. Others traded practical mitigations: quoting Google&\#x27;s DMA disclosure under which EU users can choose whether to link services such as Search, YouTube, and Ad services, pointing to an opt-out page at google.com/search-personalization, and exporting photos via Google Takeout to self-hosted Immich, which its proponent argues works better than Google Photos.

<details><summary>References</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/shellypalmer_google-launched-personal-intelligence-activity-7417596850314334208-eqxa">Google &#x27;s Personal Intelligence connects Gemini to Gmail , Photos ...</a></li>
<li><a href="https://www.webroot.com/in/en/resources/tips-articles/protecting-your-privacy-on-google-services/">Protecting Your Privacy on Google Services | Webroot</a></li>
<li><a href="https://www.youtube.com/watch?v=yFMC-DvDA5k">Google Privacy Tools - Search Personalization Opt - out - YouTube</a></li>
<li><a href="https://www.google.com/photos/about/">Google Photos : Edit, Organize, Search , and Backup Your Photos</a></li>

</ul>
</details>

**Tags**: `#google`, `#privacy`, `#ad-targeting`, `#tech-policy`, `#self-hosting`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s State Council Office Issues Guidance to Ease AI-Driven Job Displacement](https://mp.weixin.qq.com/s/St8URoMYcV-voM7kLAK3Bw) ⭐️ 7.0/10

China&\#x27;s State Council General Office has issued a guidance document, the &quot;Opinions on Adapting to Artificial Intelligence Technology Development to Help Build an Employment-Friendly Development Model,&quot; setting out measures to soften AI&\#x27;s displacement of jobs. It calls for prioritizing AI in labor-shortage and high-hazard roles, moving cautiously on the scope, intensity, and pace of AI adoption in labor-intensive industries, and encouraging companies to establish unemployment buffer periods with advance notice and job-transition support for affected workers.

telegram · zaihuapd · Oct 23, 12:54

**「Background」** The State Council General Office is the administrative arm of China&\#x27;s cabinet, and its directives are circulated to all ministries and provincial governments for implementation. This document, issued as Guobanfa \[2026\] No. 29 on October 23, 2026, is an &quot;opinion&quot; \(意见\) — a form of policy guidance that sets direction and expectations without binding targets, funding, or deadlines.

**「Who is affected」** Workers in labor-intensive industries are the main intended beneficiaries: employers are encouraged to give them early warning and provide transition or redeployment support before AI displaces their jobs, while companies deploying AI in China face official guidance to move cautiously in those sectors. PwC projects Chinese industrial employment will keep shifting from lower-value, labor-intensive production toward higher-value roles, so displacement pressure is concentrated where the policy intervenes — though as guidance without binding measures or timelines, its effect depends on implementation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gov.cn/zhengce/zhengceku/202610/content_7084108.htm">国务院办公厅关于适应人工智能技术发展助力构建就业友好型发展方式的...</a></li>
<li><a href="https://rst.hubei.gov.cn/bmdt/rsyw/202610/t20261023_6040324.shtml">国务院办公厅印发《关于适应人工智能技术发展助力构建就业友好型发展...</a></li>
<li><a href="https://www.pwc.com/gx/en/issues/artificial-intelligence/impact-of-ai-on-jobs-in-china.pdf">What will be the net impact of AI and related technologies on jobs in...</a></li>

</ul>
</details>

**Tags**: `#China policy`, `#AI regulation`, `#labor market`, `#employment`, `#State Council`

---