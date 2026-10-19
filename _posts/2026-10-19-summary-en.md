---
layout: default
title: "Horizon Summary: 2026-10-19 (EN)"
date: 2026-10-19
lang: en
---

> From 35 items, 8 important content pieces were selected

---

**Technology News**
1. [vLLM v0.32.0 adds structured-decision endpoint, generic HF parsers, wider low-precision KV cache](#item-tech-news-1) ⭐️ 8.0/10
2. [HybridAgent: LLM agents that reason in latent space and act through text](#item-tech-news-2) ⭐️ 8.0/10
3. [RepRapMicron: open-source project aims to shrink self-replicating 3D printing to micron scale](#item-tech-news-3) ⭐️ 7.0/10
4. [DeepSeek launches search-and-fetch API at $0.75 per 1,000 requests](#item-tech-news-4) ⭐️ 7.0/10
5. [TempoPFN: synthetic-data pre-training of linear RNNs for zero-shot forecasting](#item-tech-news-5) ⭐️ 7.0/10
6. [Google 开源递归智能体框架 Harness²](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [外卖大战一年后：平台利润回升，商家与骑手却额外承压](#item-finance-news-1) ⭐️ 7.0/10
2. [美国 AI 基建热潮出现裂痕，巨额投资面临回报考验](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.32.0 adds structured-decision endpoint, generic HF parsers, wider low-precision KV cache](https://github.com/vllm-project/vllm/releases/tag/v0.32.0) ⭐️ 8.0/10

vLLM v0.32.0 is a large community release \(814 commits from 363 contributors, 121 of them new\) whose headline additions for inference operators are a structured-decision endpoint, POST /v1/systemone, that answers choice, noul, and score questions over a structured state and is served by default, plus generic \`hf\` tool and reasoning parsers \(\`--tool-call-parser hf\`, \`--reasoning-parser hf\`\) that read the checkpoint&\#x27;s \`response\_template\`, so models that ship it no longer need model-specific parsers. Low-precision KV cache support now covers more hardware: NVFP4 runs on SM8x, SM90, and SM12x \(including XQA decode and MiniMax-M3 sparse attention on SM100\), GLM-5.x defaults to an FP8 KV cache on SM100 — halving KV memory per rank with 2.3–5.5% more throughput at a 7–11% TTFT cost in the PR&\#x27;s benchmark — \`fp8\_ds\_mla\` on SM90 gives GLM-5.3-Flash up to 31% more output throughput, and ROCm gains a 4-bit \`ultraquant\_4bit\` KV cache with about 2x the density of FP8. Startup and serving also improve via \`vllm download-kernels\` for FlashInfer&\#x27;s precompiled kernels, a \`--api-server-count\` mode that routes each connection to the least-loaded API worker \(43–85% more req/s on short requests in the PR&\#x27;s benchmark\), and Model Runner V2 becoming the default on ROCm; three security advisories are fixed and CORS no longer allows every origin by default. Upgraders should note the breaking changes: Python 3.10 support is dropped, \`transformers&gt;=5.16.1,&lt;5.20.0\` and \`tokenizers&gt;=0.23.2\` are now required, cascade attention and \`mamba\_cache\_mode=&quot;all&quot;\` are removed, \`max\_tokens\` is no longer reserved from the context window, and Responses API reasoning stream events are renamed; wheels and Docker images are published for CUDA 13.0/12.9, ROCm, CPU, and XPU.

github · khluu · Oct 18, 06:50

**「Background」** vLLM is an open-source engine that serves large language models behind an OpenAI-compatible HTTP API, with builds for NVIDIA CUDA, AMD ROCm, Intel XPU, and CPU targets. Its KV cache holds each request&\#x27;s attention state in GPU memory, so the cache&\#x27;s numeric precision \(for example FP8 or 4-bit NVFP4 versus higher-precision formats\) directly controls how many concurrent requests fit on a GPU and how fast tokens are produced. Tool-call and reasoning parsers are the components that convert a model&\#x27;s raw text output into structured function calls or separated reasoning sections, and before this release they generally had to be written separately for each model family.

**「Upgrade considerations for operators」** Teams running vLLM in production have a concrete reason to plan an upgrade: v0.32.0 fixes three security advisories \(chat template resource exhaustion, tokenizer \`max\_token\_id\` handling, and P2P ZMQ socket exhaustion\) and no longer allows every origin by default under CORS, which matters most for internet-facing deployments. The same upgrade carries breaking changes — Python 3.10 support is dropped, dependencies are pinned to \`transformers&gt;=5.16.1,&lt;5.20.0\` and \`tokenizers&gt;=0.23.2\`, cascade attention is removed, and \`max\_tokens\` is no longer reserved from the context window — so operators should audit pinned dependencies, client CORS expectations, and token-budget behavior before rolling out via \`pip install vllm\` \(CUDA 13.0\) or the \`vllm/vllm-openai:v0.32.0\` Docker image.

<details><summary>References</summary>
<ul>
<li><a href="https://aicoder.com/news/news-20261018-vllm-0-32-0-systemone-nvfp4-kv-mrv2">vLLM v0.32.0: 814 commits, built-in /v1/systemone structured ...</a></li>
<li><a href="https://e-acc.ai/items/d1ql9rmkyl5kuuhg7jmmkabck">vLLM v0.32.0 adds a structured-decision endpoint and low ...</a></li>

</ul>
</details>

**Tags**: `#vllm`, `#llm-inference`, `#kv-cache`, `#quantization`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [HybridAgent: LLM agents that reason in latent space and act through text](https://arxiv.org/abs/2610.18861) ⭐️ 8.0/10

HybridAgent, a new open research release, introduces LLM agents that reason in latent space and act through text, published as arXiv paper 2610.18861 with runnable artifacts: code at github.com/togethercomputer/HybridAgent, model weights and data in the togethercomputer Hugging Face collection, and evaluations in Section 5 of the paper. Shipping code, weights, and evaluations together means practitioners can run and inspect the system now rather than rely on claimed results alone. Early third-party testing surfaced a limitation: a Hacker News user running the 14B model in llama.cpp with an 8-bit quantization reported it looping on variations of the same paragraph for five minutes until its turn budget ran out, on a simple web-search-and-summarization request that similarly sized models such as Gemma 4 12B handle without trouble. That commenter suggested llama.cpp may need updates to support the model, so the release is usable today but not yet proven robust across inference runtimes.

hackernews · allinonai · Oct 18, 20:48 · [Discussion](https://news.ycombinator.com/item?id=50145337)

**「Background: latent reasoning」** Latent reasoning is an approach in which a model works through intermediate steps by iterating on its internal hidden states rather than decoding each thought as text, which the HybridAgent paper frames as fast, inspectable inner thinking. The complication for agents is that text output is still required for tool calls, final answers, and external monitoring, so latent thinking and text-based acting must coexist in one system. HybridAgent&\#x27;s HybridLink component maps last-layer hidden states back into the input-embedding space so the model can enter latent mode to think and return to text mode to act, while a continuous working memory preserves hybrid context across multiple turns.

**「Practical impact」** Developers can try the system now through the public code and Hugging Face weights, but third-party runtime support is not yet dependable: one early tester reported the released 14B model \(8-bit quantization\) looping on variations of the same paragraph for five minutes and exhausting its turn budget on a simple web-search-and-summarization prompt that similar-size models such as Gemma 4 12B handle, while noting llama.cpp may simply need updates for this architecture. Until runtime compatibility is confirmed, practitioners should evaluate through the reference implementation and check results against the paper&\#x27;s Section 5 evaluations rather than assuming quantized third-party builds reproduce the published numbers.

**「Hacker News reaction」** Commenters focused on design questions: one asked whether the latent vector could simply be added to token embeddings so latent reasoning could continue during text generation, another asked how the approach differs from Astra&\#x27;s looped transformer, which they noted also reasons in latent space, and a third hoped to see it applied to Qwen 3.8 27B to keep that model&\#x27;s repetitive reasoning output in latent space. On reliability, the user who hit the llama.cpp looping problem suggested the cause may be llama.cpp needing updates rather than a flaw in the model itself.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2610.18861">[2610.18861] Hybrid Reasoning Agents - arXiv.org</a></li>
<li><a href="https://arxiv.org/html/2610.18861v1">Hybrid Reasoning Agents - arXiv.org</a></li>
<li><a href="https://github.com/togethercomputer/HybridAgent">GitHub - togethercomputer/HybridAgent</a></li>

</ul>
</details>

**Tags**: `#LLM agents`, `#latent reasoning`, `#machine learning research`, `#open source`, `#inference`

---

<a id="item-tech-news-3"></a>
### [RepRapMicron: open-source project aims to shrink self-replicating 3D printing to micron scale](https://github.com/VikOlliver/RepRapMicron/wiki) ⭐️ 7.0/10

RepRapMicron, an open-source project hosted on GitHub, aims to extend RepRap-style self-replicating 3D printing down to micron scale, a goal of interest to open-source hardware builders. What is documented so far is a project wiki describing that ambition; micron-scale self-replication is a stated objective, not a demonstrated or independently verified capability. The project drew substantial Hacker News discussion \(329 points, 54 comments\), ranging from comparisons to the birth of precision manufacturing in the 1790s to skepticism that such a printer could ever produce working chips.

hackernews · RobotToaster · Oct 18, 13:48 · [Discussion](https://news.ycombinator.com/item?id=50141076)

**「From RepRap to micron scale」** RepRapMicron extends the RepRap project, the open-source self-replicating-printer effort that gave rise to desktop 3D printing, and reuses the same fundamentals the original developed at macro scale — including a 3-axis positioning system — toward a goal of producing structures at one micron or less. The project has so far demonstrated a 0.650mm \(650-micron\) 3DBenchy printed in a 13-hour job, reported as the first-ever microscale print of that test model, which still sits well above the one-micron target.

**「Access, not resolution」** For makers, researchers, and small labs, the meaningful consequence would be access rather than resolution: commercial two-photon polymerization systems such as Nanoscribe&\#x27;s Photonic Professional GT+ already fabricate microscale structures with submicron features, so RepRapMicron&\#x27;s distinguishing promise is an open-source, potentially self-replicating alternative to proprietary equipment. Because the project exists so far only as an early-stage wiki, the practical step for interested developers is to follow or contribute to the repository while treating micron-scale self-replication and chip-fabrication applications as unproven goals.

**「Community discussion」** Commenters split between historical optimism and skepticism: one compared the project to the 1790s, when Ramsden&\#x27;s circle-dividing work, Maudslay&\#x27;s thread-cutting lathe, and Wilkinson&\#x27;s boring machine turned precision scale-marking and screw-making from craft into reliable mass production, while another sarcastically welcomed &quot;making our own RAM&quot; in 18 months to voice doubt about near-term chip fabrication. Others were more hopeful or curious — one noted that many chip designs exist only as software and asked whether cheap printing could bring them to life, and another questioned why the machine building a 1/1000-scale copy of itself is dismissed as preposterous.

<details><summary>References</summary>
<ul>
<li><a href="https://makeprintable.com/reprap-micron-achieves-0-650mm-3dbenchy-print/">RepRap Micron Achieves 0.650mm 3DBenchy Print - makeprintable</a></li>
<li><a href="https://reprap.org/wiki/RepRapMicron">RepRapMicron - RepRap</a></li>
<li><a href="https://www.4additive.com/en/reprap-micron-3dbenchy-smallest/">RepRap Micron : the smallest 3DBenchy is 0.650 mm - 4Additive</a></li>
<li><a href="https://www.mdpi.com/2673-8023/1/2/13">Micro 3D Printing by Two-Photon Polymerization ... - MDPI</a></li>
<li><a href="https://www.nanoscribe.com/en/microfabrication-technologies/2pp-two-photon-polymerization/">Two-Photon Polymerization (2PP) 3D printing - Nanoscribe</a></li>

</ul>
</details>

**Tags**: `#open-source-hardware`, `#3d-printing`, `#microfabrication`, `#self-replication`, `#hardware`

---

<a id="item-tech-news-4"></a>
### [DeepSeek launches search-and-fetch API at $0.75 per 1,000 requests](https://api-docs.deepseek.com/guides/search/) ⭐️ 7.0/10

DeepSeek has launched a search-and-fetch API priced at $0.75 per 1,000 successful requests, giving developers building AI agents a low-cost option for web access; the pricing appears in DeepSeek&\#x27;s API documentation. Commenters on the Hacker News thread put competing services at roughly $5 per 1,000 requests for the Brave Search API and about $12 for Kagi&\#x27;s API, though those comparison figures come from the discussion rather than from DeepSeek&\#x27;s announcement. The available material includes no documentation text, so details such as coverage, rate limits, or result quality are not confirmed here.

hackernews · fagnerbrack · Oct 18, 06:50 · [Discussion](https://news.ycombinator.com/item?id=50138531)

**「Background」** AI agents and LLM applications typically get live web access through hosted search APIs, and paid per-request providers such as Brave and Kagi have been the established options in this market. DeepSeek introduced the Search and Fetch interfaces alongside an update to its models that the Global Times described as faster and cheaper, and its API pricing documentation lists Search and Fetch as standalone APIs billed per request rather than capabilities bundled into model usage.

**「Cheaper hosted search for AI agent developers」** Developers building AI agents that need web access can cut a recurring cost sharply: at $0.75 per 1,000 successful requests, DeepSeek&\#x27;s API is roughly 5–7x cheaper than Brave Search API&\#x27;s $4–$5 per 1,000 queries and far below Kagi&\#x27;s $15–$25 per 1,000 queries \(October 2026 pricing\), making hosted search viable for high-volume agent pipelines where per-query fees were a major expense. Teams comparing providers should note the billing basis differs, since DeepSeek charges only for successful requests, and commenters report free self-hosted alternatives such as searxng-based kits for personal-scale use.

**「Community discussion」** Commenters framed the price as the headline: thombles cited roughly $5 for Brave&\#x27;s Search API and $12 for Kagi&\#x27;s as comparisons, while mjmvisser argued the third-party search-API market exists at all only because Google declines to offer a paid search API. Others pushed back on the need for hosted providers — nikvdp reported that self-hosted tools like searxng-ai-kit, which scrape results without an API key, are free for personal use — and londons\_explore speculated that agent-driven demand could eventually push search API prices toward zero or even negative as providers compete to influence what agents retrieve.

<details><summary>References</summary>
<ul>
<li><a href="https://www.globaltimes.cn/page/202610/1372476.shtml">DeepSeek unveils faster, cheaper AI model, with... - Global Times</a></li>
<li><a href="https://api-docs.deepseek.com/quick_start/pricing/">Models &amp; Pricing | DeepSeek API Docs</a></li>
<li><a href="https://costbench.com/compare/brave-search-api-vs-kagi-search-api/">Brave Search API vs Kagi Search API Pricing (2026)</a></li>
<li><a href="https://costbench.com/software/ai-search-apis/brave-search-api/">Brave Search API Pricing 2026: Free-$30 per 1K queries</a></li>

</ul>
</details>

**Tags**: `#deepseek`, `#search-api`, `#llm-agents`, `#pricing`, `#web-search`

---

<a id="item-tech-news-5"></a>
### [TempoPFN: synthetic-data pre-training of linear RNNs for zero-shot forecasting](https://www.reddit.com/r/MachineLearning/comments/1x97v19/tempopfn_synthetic_pretraining_of_linear_rnns_for/) ⭐️ 7.0/10

Researchers including Vladyslav Moroshan and Frank Hutter&\#x27;s AutoML group released TempoPFN, a time series foundation model pre-trained entirely on synthetic data that performs zero-shot forecasting using a DeltaProduct-based linear RNN; the post reports acceptance at NeurIPS 2026. The release ships reproducible artifacts — the arXiv paper \(2510.25502\), GitHub code under automl/TempoPFN, and Hugging Face weights — together with a library of synthetic time series generators and augmentations used for training. According to the announcement, those generators have already been adopted by other time series models, Toto-2 and TS-ICL, meaning the synthetic-data approach is already being reused beyond the original model.

reddit · r/MachineLearning · /u/Yossarian\_1234 · Oct 18, 16:43

**「Background」** Zero-shot forecasting means a model predicts future values of time series it was never trained on, an ability the prior-data fitted network \(PFN\) approach enables by training on synthetic data sampled from a probabilistic prior so the model learns to solve the task in-context. TempoPFN&\#x27;s choice of a DeltaProduct-based linear RNN as its backbone is relevant to this setting because, as a linear RNN, it compresses the entire observed past into a single hidden state and supports streaming inference with constant memory. The released model is univariate, forecasting one series at a time rather than multivariate datasets.

**「Reusable synthetic data pipeline」** Teams training time series foundation models can reuse TempoPFN&\#x27;s open-source synthetic data generators instead of assembling real-world training corpora: the Toto 2.0 paper confirms it already adopted TempoPFN&\#x27;s synthetic data generation method, and the TempoPFN paper reports performance comparable to models trained on real-world data on the GIFT-Eval benchmark. The generators, code, and pretrained weights are publicly released on GitHub and HuggingFace, so practitioners can reproduce the pipeline or integrate the generators into their own model training.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/html/2510.25502v3">TempoPFN : Synthetic Pre - training of Linear RNNs for Zero-shot...</a></li>
<li><a href="https://paperswithcode.co/paper/2510.25502">TempoPFN : Synthetic Pre - training of Linear ... | Papers with Code</a></li>
<li><a href="https://arxiv.org/html/2605.20119">Toto 2 .0: Time Series Forecasting Enters the Scaling Era</a></li>
<li><a href="https://openreview.net/pdf?id=Iqex1gfnvc">TempoPFN : Towards Synthetic Pre-training of Linear</a></li>

</ul>
</details>

**Tags**: `#time-series-forecasting`, `#foundation-models`, `#synthetic-data`, `#linear-rnns`, `#zero-shot-learning`

---

<a id="item-tech-news-6"></a>
### [Google 开源递归智能体框架 Harness²](https://github.com/google-research/harness2) ⭐️ 7.0/10

Google Research has open-sourced Harness², an Apache-2.0 framework that boosts LLM agent performance via two-layer recursive optimization without weight tuning, reportedly gaining up to 11.5 points on agent benchmarks.

telegram · zaihuapd · Oct 18, 11:24

**Tags**: `#llm-agents`, `#open-source`, `#google-research`, `#agent-frameworks`, `#recursive-optimization`

---

## Financial News

<a id="item-finance-news-1"></a>
### [外卖大战一年后：平台利润回升，商家与骑手却额外承压](https://www.latepost.com/news/dj_detail?id=3762) ⭐️ 7.0/10

A year after China&\#x27;s food delivery subsidy war, platform profits have rebounded and combined daily orders rose ~50% to ~140 million, but the cost burden has shifted to merchants facing compressed margins and riders whose per-order pay has fallen.

telegram · zaihuapd · Oct 18, 07:40

**Tags**: `#food-delivery`, `#China-platform-economy`, `#Meituan`, `#Alibaba`, `#gig-economy`

---

<a id="item-finance-news-2"></a>
### [美国 AI 基建热潮出现裂痕，巨额投资面临回报考验](https://www.ft.com/content/9ea5a37d-15c9-4d5b-94d6-719048c9cd3c?syn-25a6b1a6=1) ⭐️ 7.0/10

Citing FT reporting, this item describes mounting financing costs, public opposition, and project cancellations \(47+ large data centers\) casting doubt on the multi-trillion-dollar US AI infrastructure boom, reflected in falling chip and AI-cloud stocks.

telegram · zaihuapd · Oct 18, 08:52

**Tags**: `#AI infrastructure`, `#data centers`, `#semiconductors`, `#capital expenditure`, `#market selloff`

---