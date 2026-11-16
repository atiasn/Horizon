---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 37 items, 8 important content pieces were selected

---

**Technology News**
1. [Sebastian Raschka Explains Positional Embeddings in Modern LLMs](#item-tech-news-1) ⭐️ 8.0/10
2. [Meta FAIR and NYU unbundle vision encoders in MLLMs via 200+ model ablation](#item-tech-news-2) ⭐️ 8.0/10
3. [🦘 美团开源 LongCat-2.5 称其未使用英伟达 GPU 训练](#item-tech-news-3) ⭐️ 8.0/10
4. [Alibaba Launches Qwen4-Max Flagship, Plans Smaller Open-Source Qwen4 Models](#item-tech-news-4) ⭐️ 8.0/10
5. [Microsoft 365 outage left hotel chlorine alerts undelivered; 15 guests poisoned](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s slowdown deepens in October as retail, output and investment all miss forecasts](#item-finance-news-1) ⭐️ 8.0/10
2. [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](#item-finance-news-2) ⭐️ 7.0/10
3. [中美俄领导人定于11月19日在深圳APEC场边举行首次三方会晤](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Sebastian Raschka Explains Positional Embeddings in Modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

Sebastian Raschka published an in-depth article explaining how positional embeddings work in modern large language models, covering how transformers encode token order information. The piece is a technical deep-dive aimed at ML engineers and researchers rather than an announcement of new software or results. It drew substantial engagement on Hacker News \(213 points, 27 comments\), where discussion turned to the theoretical foundations of positional embeddings.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** Transformers process all tokens in parallel and have no built-in sense of order, so positional embeddings must be added to token embeddings to convey sequence position; the simplest form is a one-hot vector per position added before the transformer layers \(tool-1-2\). The article follows up on learned absolute positional embeddings of the kind used in GPT, a topic Raschka says many readers had requested expanded into relative positional embeddings such as RoPE \(tool-1-1\).

**「Community Discussion」** Commenter programjames argued that the article covers only implementation details and that a full understanding of positional embeddings requires theory: positional embeddings are group representations, which is both how they are derived and how they can be parameterized to be differentiable and learnable. As an example, they noted that rotary positional embeddings are representations of the translation group, and that the n-dimensional translation group ℝⁿ is abelian.

<details><summary>References</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://archive.md/R5CbU">Understanding Positional Embeddings in Transformers: From...</a></li>

</ul>
</details>

**Tags**: `#llms`, `#transformers`, `#positional-embeddings`, `#machine-learning`, `#deep-dive`

---

<a id="item-tech-news-2"></a>
### [Meta FAIR and NYU unbundle vision encoders in MLLMs via 200+ model ablation](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR and NYU researchers trained over 200 multimodal LLMs from scratch on identical data to isolate which vision-encoder design choices actually matter, publishing a paper and blog/FAQ. The study compares Qwen3-1.7B and 4B configurations with 0.4B parameters of vision capacity, a scaling ladder from 0.6B to 6.4B backbones, and evaluates on 16 Cambrian VQA benchmarks at 448 px plus 12 language benchmarks, with encoder pretraining counted against the same compute budget. Three findings stand out: separate encoder pretraining is optional \(even 6.5x longer MetaCLIP pretraining raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA\), dedicated vision-only parameters are essential \(encoder-free models trail at every size and need roughly 3x the compute to catch up\), and placing vision processing before the LLM is optional — an &quot;in-fusion&quot; scheme adding zero-initialized vision-only weights to the first 8 LLM layers matched the encoder from 1.7B to 6.4B with about 13% lower time to first token.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Why the debate exists」** Standard multimodal LLMs typically use a separate vision encoder that bundles three design choices into one: pretraining the encoder on its own, giving it dedicated vision-only parameters, and placing it as a module before the language model. Because published models differ in data and compute, recent releases—dropping, retraining, or restoring encoders—could not settle which of these choices actually matter. The study also builds on Meta FAIR&\#x27;s earlier from-scratch pretraining work, which found unified multimodal training outperforms bolt-on approaches and that vision needs far more data than language at scale.

**「Why it matters」** The results address a live disagreement among recent releases — the authors note Gemma 4 12B dropped the encoder, Kimi K3 trains its encoder from scratch, and Inkling 2 Small brought an encoder back — but those models differ in data and compute, so they could not settle the question. For practitioners, the paper suggests MLLM designers can skip separate encoder pretraining and even the standalone encoder itself, but must preserve parameters that only vision tokens use; redistributing those parameters to text improves language performance, not VQA. Note that the claims come from the authors&\#x27; own paper and blog \(one author posted the submission\) and have not been independently verified.

<details><summary>References</summary>
<ul>
<li><a href="https://toknow.ai/posts/meta-fair-beyond-language-modeling-multimodal-pretraining/">Meta FAIR Finds That Training Vision and Language Together From...</a></li>

</ul>
</details>

**Tags**: `#multimodal-models`, `#vision-encoders`, `#ablation-study`, `#machine-learning-research`, `#MLLM-training`

---

<a id="item-tech-news-3"></a>
### [🦘 美团开源 LongCat-2.5 称其未使用英伟达 GPU 训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

据报道，美团以 MIT 许可证开源了 LongCat-2.5，这是一个面向智能体的大规模 MoE 模型，其声称仅使用华为昇腾芯片进行训练，而不使用英伟达 GPU。

telegram · zaihuapd · Nov 15, 11:08

**Tags**: `#open-source-models`, `#LLM`, `#ai-hardware`, `#huawei-ascend`, `#agents`

---

<a id="item-tech-news-4"></a>
### [Alibaba Launches Qwen4-Max Flagship, Plans Smaller Open-Source Qwen4 Models](https://mp.weixin.qq.com/s/pJUt0xwD6H-WMyzd8TjZaQ) ⭐️ 8.0/10

Alibaba&\#x27;s Tongyi Qianwen team has released Qwen4-Max, a new flagship model built on a sparse mixture-of-experts architecture with 2.4 trillion total parameters, native vision understanding, and million-token context. The team claims strong coding, office, and long-horizon task performance, with front-end coding ranked near the top of Code Arena blind testing, though no independent benchmarks are provided beyond that claim. Costs dropped substantially versus the previous generation: average per-task cost fell from 26.58 yuan to 11.16 yuan \(about 58%\), token consumption fell nearly 50%, and API pricing was lowered accordingly. The model is live now, and the team says smaller Qwen4 models will follow with publicly released weights.

telegram · zaihuapd · Nov 16, 02:52

**「Background」** Qwen4-Max succeeds Alibaba&\#x27;s previous flagship Qwen model in the Tongyi Qianwen \(Qwen\) series, which Alibaba has offered both as a hosted API and, for smaller variants, as open-weight releases. The predecessor&\#x27;s cost profile is the concrete benchmark here: the same task that averaged 26.58 yuan on the prior generation now averages 11.16 yuan on Qwen4-Max, a reduction of nearly 58%. Alibaba&\#x27;s stated plan to publish open weights for smaller Qwen4 models continues the release pattern of earlier Qwen generations.

**「Practical impact」** Developers can now access Qwen4-Max via its live API following the November 11 Token Plan-only preview, with Alibaba cutting per-task cost roughly 58% \(from 26.58 to 11.16 yuan\) and halving token consumption, which directly lowers the expense of running long-context and vision workloads. Teams building with the Qwen family should also note that smaller Qwen4 models with publicly released weights are planned, making self-hosted or fine-tuned deployments of the architecture a realistic option once those variants ship.

<details><summary>References</summary>
<ul>
<li><a href="https://aicoder.com/news/news-20261116-alibaba-qwen4-max-official-launch-api-live-qwencloud-1-5-4-5-per-m-tokens">Alibaba Officially Launches Qwen4-Max: New MoE Architecture ...</a></li>
<li><a href="https://technode.com/2026/11/11/alibaba-opens-qwen4-max-preview-with-a-million-token-context-window/">Alibaba opens Qwen4-Max preview with a million-token context ...</a></li>

</ul>
</details>

**Tags**: `#large-language-models`, `#mixture-of-experts`, `#alibaba-qwen`, `#model-release`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [Microsoft 365 outage left hotel chlorine alerts undelivered; 15 guests poisoned](https://www1.wdr.de/nrw/rheinland/rhein-erft-kreis/technischer-defekt-chlor-phantasialand-100.html) ⭐️ 7.0/10

A German hotel&\#x27;s chlorine monitoring alerts, routed through Microsoft 365, failed to arrive during a Microsoft 365 outage while the pool dosing system was simultaneously defective and dispensing too much chlorine, contributing to chlorine gas exposure that sickened 15 guests. According to a translation of the WDR report shared in the discussion, 13 guests initially complained of airway irritation \(two more later\), four were taken to hospital with one classified as a medium injury, and the rest were discharged. The report describes two distinct failures — a dosing system defect and the failed email-based monitoring — rather than the outage alone causing the incident.

hackernews · DeepLogin · Nov 15, 18:36 · [Discussion](https://news.ycombinator.com/item?id=50509411)

**「Background」** Hotel pools use automated chlorination systems that dose disinfectant into the water, and these systems are known to fail in ways that cause them to measure low or zero chlorine and overdispense, so operators are expected to maintain independent human oversight or redundant monitoring rather than rely on a single alerting path. In this incident, German reporting indicates a dual failure: the dosing system itself was defective and dosing too high, while alerts from a separate monitoring system routed through Microsoft 365 went out during an outage, with 13 guests initially reporting airway irritation, four taken to hospital, and one described as moderately injured.

**「Lesson for safety-critical alerting」** The incident illustrates that routing safety alarms through a third-party cloud email service introduces a single point of failure; operators of pools or similar facilities should ensure alarms have redundant, on-site delivery paths and human oversight rather than depending solely on email notification. Commenters also noted that closed-loop chlorination systems tend to fail by measuring low or zero chlorine and over-dispensing, so operators must actively guard against both excessive and insufficient chlorine.

**「Commenters fault the design, not only Microsoft」** Commenters largely blamed the hotel&\#x27;s architecture rather than Microsoft, arguing that anything capable of causing such harm should have a redundant design and that relying entirely on email for dangerous-gas monitoring is unacceptable; an Azure worker explicitly said this was not a defense of the outage. One commenter, amluto, drew on personal experience running a closed-loop chlorination system to explain why such systems commonly fail toward over-dispensing, while another noted the German source article reads far less dramatic than the Hacker News headline.

**Tags**: `#cloud-outage`, `#safety-critical-systems`, `#incident-report`, `#microsoft-365`, `#failure-analysis`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s slowdown deepens in October as retail, output and investment all miss forecasts](https://www.cnbc.com/2026/11/16/china-retail-sales-october-industrial-output-investment.html) ⭐️ 8.0/10

China&\#x27;s October data released Monday showed retail sales up 0.4% year-on-year \(below the 0.8% forecast\), industrial output up 4.8% \(below 5.3% expected\), and fixed-asset investment down 8.1% for the first ten months of 2026 \(worse than the expected 7% decline\), deepening the economy&\#x27;s slowdown.

rss · CNBC Finance · Nov 16, 02:52

**「Background」** Consumer spending has languished for five years as a property downturn erodes household wealth, leaving growth increasingly dependent on exports, which surged 35.2% in October largely on global AI-related demand.

**「Why it matters」** Analysts warn that this reliance on external demand makes China — and trading partners exposed to its record trade surplus, which hit $1 trillion by October — vulnerable to any pullback in AI spending or new EU trade restrictions next year.

**Tags**: `#China economy`, `#industrial output`, `#retail sales`, `#fixed-asset investment`, `#trade surplus`

---

<a id="item-finance-news-2"></a>
### [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Cantor Fitzgerald, led by Commerce Secretary Howard Lutnick&\#x27;s sons, sharply reduced its Nvidia stake and maintained financing ties to the chipmaker while Lutnick resisted a crackdown on firms suspected of smuggling Nvidia chips to China, raising ethics questions.

rss · CNBC Finance · Nov 15, 19:58

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#conflict of interest`

---

<a id="item-finance-news-3"></a>
### [中美俄领导人定于11月19日在深圳APEC场边举行首次三方会晤](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 7.0/10

据中国外交部宣布，中美俄三国领导人计划于11月19日在深圳APEC峰会场边举行首次专门的三方会晤；该会晤不属于APEC正式议程，目前尚未举行，具体议程与预期成果尚未公布。

telegram · zaihuapd · Nov 16, 01:38

**「背景」** 亚太经济合作组织（APEC）领导人会议将于11月18日至19日在中国深圳举行，中美两国领导人均计划出席；据《华尔街日报》报道，三方会晤的形式由普京在10月9日与特朗普通话时提出 \[tool-1-2\]。此前三方领导人是否会在峰会期间举行会谈一直未获确认，近期中美之间还围绕稀土出口等釜山协议的落实存在摩擦 \[tool-1-1\]\[tool-1-2\]。

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/zhongwen/articles/cwe85djzkkv5o/simp">APEC ... - BBC News 中 文</a></li>
<li><a href="https://www.dw.com/zh/%E6%B7%B1%E5%9C%B3apec%E5%89%8D%E5%A4%95-%E7%BE%8E%E5%9B%BD%E5%82%AC%E4%B8%AD%E5%9B%BD%E5%85%91%E7%8E%B0%E7%A8%80%E5%9C%9F%E6%89%BF%E8%AF%BA/a-79884476">美 促 中 国落实釜山协议 中 美 俄 三 方 会 晤 各怀心思</a></li>

</ul>
</details>

**Tags**: `#中美关系`, `#APEC峰会`, `#地缘政治`, `#外交政策`

---