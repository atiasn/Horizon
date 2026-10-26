---
layout: default
title: "Horizon Summary: 2026-10-26 (EN)"
date: 2026-10-26
lang: en
---

> From 27 items, 4 important content pieces were selected

---

**Technology News**
1. [Decade-old Inception v3 CNN outperforms frontier LLMs at skin cancer diagnosis](#item-tech-news-1) ⭐️ 7.0/10
2. [Brotli decoder flaw CVE-2026-111497 extends to Python HTTP components; patches released](#item-tech-news-2) ⭐️ 7.0/10
3. [Apple reportedly set to unveil first touchscreen MacBook Pro with OLED displays](#item-tech-news-3) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s Population Fell by 3.39 Million in 2025, Nearing 1.4 Billion](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Decade-old Inception v3 CNN outperforms frontier LLMs at skin cancer diagnosis](https://lynchlab.net/llm-skin-cancer) ⭐️ 7.0/10

A lab blog post reports that Inception v3, a convolutional neural network architecture roughly a decade old, fine-tuned on 68,011 dermoscopic and clinical images from the ISIC Archive, outperformed two frontier multimodal LLMs at skin cancer diagnosis. The author pretrained the network on everyday photographs, fine-tuned all layers on a single H100 GPU, and evaluated on 200 test lesions after removing every photograph of the same lesion or patient from the training and validation sets, so the test cases were never seen during training and were not used for model selection or threshold setting. The result is the author&\#x27;s own blog-post comparison rather than a peer-reviewed study, and commenters questioned whether fine-tuning directly on the benchmark distribution makes the matchup fair to the LLMs.

hackernews · sungam · Oct 25, 17:15 · [Discussion](https://news.ycombinator.com/item?id=50233779)

**「CNNs already matched dermatologists in 2017」** Specialized CNNs for skin-lesion classification are not new: in January 2017, Esteva and colleagues reported in Nature that a single Inception v3 network, pretrained on ImageNet and fine-tuned on skin-lesion images, matched the accuracy of at least 21 board-certified dermatologists across diagnostic tasks. The CNN in the current report uses that same architecture and a comparable fine-tuning recipe on ISIC dermoscopic images, so the finding that a decade-old specialized classifier beats frontier multimodal LLMs extends a result established nearly a decade ago rather than demonstrating a new capability.

**「Practical impact」** Teams considering multimodal LLMs for clinical image interpretation should benchmark them head-to-head against a fine-tuned, task-specific classifier on their own data before deployment, because strong performance on standardized medical benchmarks does not guarantee accuracy on a narrow diagnostic task. The comparison carries a validity caveat raised in discussion — the CNN was fine-tuned on the same ISIC distribution as the test lesions — so the result argues for task-specific validation rather than proving specialized models universally superior. This action aligns with external evidence: multimodal LLMs are being positioned for scalable image-based decision support, but prospective benchmarking against clinicians and a robust reference standard remains limited.

**「Community discussion」** Most commenters were unsurprised by the outcome, arguing that small specialized models routinely beat generalist LLMs on narrow tasks—one cited a 30-million-parameter KataGo network being superhuman at Go while far larger LLMs are not, and another compared the finding to a calculator outperforming LLMs at arithmetic. The sharpest objection, from one commenter, called the setup &quot;benchmaxxing,&quot; arguing that a CNN fine-tuned on the same ISIC distribution used for testing will always beat generalist models on that benchmark, while another suggested the practical takeaway is using LLMs to cheaply build dedicated classifiers rather than deploying LLMs directly.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nature.com/articles/nature21056">Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ... Dermatologist–level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer... : Nature Dermatologist-level classification of skin cancer with deep ... Dermatologist-level classification of skin cancer with deep ...</a></li>
<li><a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC8382232/">Dermatologist–level classification of skin cancer with deep ...</a></li>
<li><a href="https://link.springer.com/article/10.1186/s13049-026-01577-6">Multimodal large language model versus emergency physicians for...</a></li>
<li><a href="https://www.researchgate.net/publication/386734427_Comparing_Large_Language_Model_and_Human_Reader_Accuracy_with_New_England_Journal_of_Medicine_Image_Challenge_Case_Image_Inputs">Comparing Large Language Model and Human Reader Accuracy with...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#computer-vision`, `#medical-imaging`, `#llm-evaluation`, `#fine-tuning`

---

<a id="item-tech-news-2"></a>
### [Brotli decoder flaw CVE-2026-111497 extends to Python HTTP components; patches released](https://www.aikido.dev/blog/python-packages-vulnerable-node2shell-brotli-cve-2026-111497) ⭐️ 7.0/10

Google&\#x27;s Brotli decoder has a high-severity memory-corruption vulnerability, tracked as CVE-2026-111497 with a CVSS 4.0 score of 9.2, affecting versions 1.0.3 through 1.2.0 in HTTP components across both Node.js and Python. According to the report, a remote unauthenticated attacker can send a crafted compressed stream that causes memory corruption, sensitive data leakage, process crashes, or potentially arbitrary code execution; the flaw was first disclosed as Node2Shell and later referred to as HTTP2Shell. Fixed releases are already available: Python&\#x27;s Brotli 1.2.1, brotlicffi 1.2.1.0, and Node.js 22.23.4, 24.22.1, or 26.12.1. The account comes from an Aikido Security blog post relayed via Telegram, which also credits OpenAI with discovering the issue in February 2026 — a claim not independently verified against primary advisories.

telegram · zaihuapd · Oct 25, 02:42

**「Background」** Brotli is Google&\#x27;s lossless compression format whose decoder library is embedded in HTTP stacks to compress web traffic, including Node.js and the Python Brotli and brotlicffi packages. The flaw in this report, CVE-2026-111497, is a buffer overflow in the decoder&\#x27;s c/dec/decode.c affecting Google Brotli versions 1.0.3 through 1.2.0 on all platforms; per NVD, a remote unauthenticated attacker can send a crafted Brotli-compressed stream to corrupt adjacent decoder state memory, disclose sensitive memory contents, cause denial of service, or potentially execute arbitrary code.

**「Patch Brotli decoders in Node.js and Python HTTP stacks」** Any service that decodes attacker-supplied Brotli streams, including Node.js and Python HTTP components, is exposed to remote unauthenticated memory corruption that can disclose memory contents, crash the process, or potentially execute arbitrary code, and the buffer overflow affects Google Brotli 1.0.3 through 1.2.0 on all platforms. Operators should upgrade Python&\#x27;s Brotli package to 1.2.1 or brotlicffi to 1.2.1.0, move Node.js to 22.23.4, 24.22.1, or 26.12.1, and audit dependencies that bundle an older Brotli decoder rather than relying on the system library.

<details><summary>References</summary>
<ul>
<li><a href="https://nvd.nist.gov/vuln/detail/cve-2026-111497">NVD-CVE-2026-111497</a></li>
<li><a href="https://www.tenable.com/cve/CVE-2026-111497">CVE-2026-111497 | Tenable®</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-111497">CVE-2026-111497 - Vulnerability Details - OpenCVE</a></li>

</ul>
</details>

**Tags**: `#security`, `#Brotli`, `#Node.js`, `#Python`, `#HTTP`

---

<a id="item-tech-news-3"></a>
### [Apple reportedly set to unveil first touchscreen MacBook Pro with OLED displays](https://www.bloomberg.com/news/newsletters/2026-10-25/apple-to-unveil-touch-screen-macbook-pro-executive-promotions-in-box-checker) ⭐️ 7.0/10

Apple is reportedly set to unveil its first touchscreen MacBook Pro this Wednesday, according to a Bloomberg report, bringing touch support, OLED displays, and the Dynamic Island to the Mac for the first time. The laptops are planned in 14- and 16-inch models with starting prices above the current MacBook Pro&\#x27;s $2,499 base. The move reverses a long-standing Apple position, as executives have rejected touchscreens on laptops for years on ergonomic grounds; the report frames touch as a complement to the keyboard and trackpad rather than a replacement. All details remain unconfirmed until Apple&\#x27;s announcement.

telegram · zaihuapd · Oct 25, 14:25

**「Background」** Apple&\#x27;s current 14-inch MacBook Pro starts at $2,499, and its executives have for years rejected touch-enabled laptops on ergonomic grounds, keeping touch input off the Mac line entirely. The new models are expected to be unveiled at Apple&\#x27;s October 28 &quot;Pro and Tell&quot; event, and prior reporting suggested a $300–$500 price increase over comparable current configurations, tied to surging memory prices.

**「Impact」** Prospective MacBook Pro buyers should expect a higher entry price than the current $2,499 base, with touch input positioned as an addition to the keyboard and trackpad rather than a replacement. Because these details come from a pre-announcement report, anyone considering a purchase may want to wait for Wednesday&\#x27;s event to confirm specifications and pricing before committing to a current model.

<details><summary>References</summary>
<ul>
<li><a href="https://appleworld.today/2026/10/apples-oled-touchscreen-macbook-pro-may-face-a-300-to-500-price-hike-to-protect-their-profits-from-ramageddon/">Apple&#x27;s OLED touchscreen MacBook Pro may face a $300 to $500 ...</a></li>

</ul>
</details>

**Tags**: `#apple`, `#macbook-pro`, `#touchscreen`, `#oled`, `#hardware`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s Population Fell by 3.39 Million in 2025, Nearing 1.4 Billion](https://weibo.com/1796087453/5357878513767954) ⭐️ 7.0/10

China&\#x27;s total population fell by 3.39 million during 2025 to about 1.405 billion at year-end, leaving the country just above the 1.4 billion mark, according to figures from the China Statistical Yearbook 2026. The year saw 7.92 million births, a birth rate of 5.63 per 1,000 people, and a natural growth rate of minus 2.41 per 1,000, meaning deaths outnumbered births.

telegram · zaihuapd · Oct 25, 12:02

**「Background」** The figures come from the China Statistical Yearbook 2026, cited via Litchi News, with 2025 totals measured against the end-2024 population. The negative natural growth rate — births minus deaths per 1,000 people — means deaths outnumbered births; the lowest birth rates were in the northeastern provinces of Heilongjiang, Jilin and Liaoning, while nine mostly western and southern provinces still exceeded 7‰.

<details><summary>References</summary>
<ul>
<li><a href="https://t.me/zaihuapd/44691">在花 科技圈 – Telegram</a></li>

</ul>
</details>

**Tags**: `#China demographics`, `#population decline`, `#birth rate`, `#macroeconomic data`, `#regional statistics`

---