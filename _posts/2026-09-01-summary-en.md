---
layout: default
title: "Horizon Summary: 2026-09-01 (EN)"
date: 2026-09-01
lang: en
---

> From 43 items, 8 important content pieces were selected

---

**Technology News**
1. [Google Has Removed MV2 Extensions from the Chrome Web Store, Including UBO](#item-tech-news-1) ⭐️ 8.0/10
2. [Tim Cook Steps Down as Apple CEO, Hands Leadership to John Ternus](#item-tech-news-2) ⭐️ 8.0/10
3. [wrapture: Graham Dumpleton&\#x27;s new Python library unifying mocking and tracing](#item-tech-news-3) ⭐️ 7.0/10
4. [Preprint Claims Sliding-Window Attention Beats Linear Attention on Long-Context Reasoning](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek Releases DeepSeek-V4-Flash-Vision-Exp Multimodal Weights](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [Aon CEO says insurance broker seeks to build &\#x27;premiere middle market platform&\#x27; with purchase of rival USI](#item-finance-news-1) ⭐️ 8.0/10
2. [Markets sharply raise odds of a September Fed rate hike after Warsh&\#x27;s Jackson Hole speech](#item-finance-news-2) ⭐️ 7.0/10
3. [Tim Cook Steps Down as Apple CEO; John Ternus Takes Over with AI Focus](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Has Removed MV2 Extensions from the Chrome Web Store, Including UBO](https://webiterate.dev/google-removed-extensions-ublock-origin-108/) ⭐️ 8.0/10

Google has removed Manifest V2 extensions, including uBlock Origin, from the Chrome Web Store, prompting community discussion about ad blocking, browser control, and a shift toward Firefox.

hackernews · twapi · Aug 31, 21:10 · [Discussion](https://news.ycombinator.com/item?id=49514878)

**Tags**: `#chrome`, `#browser-extensions`, `#ad-blocking`, `#manifest-v3`, `#firefox`

---

<a id="item-tech-news-2"></a>
### [Tim Cook Steps Down as Apple CEO, Hands Leadership to John Ternus](https://cj.sina.com.cn/articles/view/5115326071/130e5ae77020030d72) ⭐️ 8.0/10

Tim Cook has stepped down as Apple&\#x27;s CEO, marking his final day in the role with a company-wide memo to employees. In the memo, Cook expressed his deep affection for the company, thanked the team for their daily dedication, and emphasized that he is not leaving Apple — he is only relinquishing the CEO position, saying he feels at peace with the decision. Leadership of the company passes to John Ternus, whom Cook described as intelligent, outstanding, and exceptionally capable, and expressed confidence in his ability to lead Apple. Cook acknowledged that he will deeply miss leading the team and encouraged employees to remain proud of being part of Apple. The announcement, reported via Sina Finance, marks a major leadership transition at one of the world&\#x27;s most valuable technology companies, though the source provides limited detail on timing or strategic context beyond the memo itself.

telegram · zaihuapd · Sep 1, 00:00

**「Background」** Tim Cook has served as Apple&\#x27;s chief executive since 2011, when he succeeded co-founder Steve Jobs, and over nearly 15 years he led the company&\#x27;s growth from roughly $350 billion to about $4 trillion in market value while building its services segment into a $100 billion-plus business. His successor, John Ternus, is a 51-year-old executive who has headed Apple&\#x27;s hardware engineering, and reports indicate Cook will move into an executive chairman role rather than leaving the company. The transition, reported to take effect on September 1, marks Apple&\#x27;s first CEO change in nearly a decade and a half.

**「Impact」** Apple enters a post-Cook era with John Ternus, formerly Senior Vice President of Hardware Engineering and a key figure in the Apple Silicon transition, taking over as CEO after Cook&\#x27;s roughly 15-year tenure, while Cook reportedly remains at the company in a chairman capacity. Market reaction to the transition has so far been muted, suggesting investors see continuity rather than disruption.

<details><summary>References</summary>
<ul>
<li><a href="https://news.google.com/stories/CAAqNggKIjBDQklTSGpvSmMzUnZjbmt0TXpZd1NoRUtEd2lpa3IzNkVCRnhIa1FoMkhvVk5pZ0FQAQ?hl=en-US&amp;gl=US&amp;ceid=US:en">John Ternus named next Apple CEO as Tim Cook steps down ...</a></li>
<li><a href="https://www.linkedin.com/posts/anthonycheung10_tim-cook-steps-down-as-ceo-of-apple-after-activity-7452105713490808832-4uDl">Tim Cook Steps Down as Apple CEO , John Ternus Takes... | LinkedIn</a></li>
<li><a href="https://deepbrief.co/ai-business/tim-cook-steps-down-apple-ceo-john-ternus-successor">Tim Cook Steps Down as Apple CEO ; John Ternus Named</a></li>
<li><a href="https://www.newswall.org/summary/apples-next-ceo-announced-as-tim-cook-steps-back">Tim Cook ’s Leadership Drives Apple ’s Market Surge</a></li>
<li><a href="https://economictimes.indiatimes.com/markets/us-stocks/news/us-stock-market-john-ternus-takes-the-helm-as-apple-prepares-for-post-cook-era/articleshow/130409475.cms">US Stock Market : John Ternus takes the helm as Apple prepares for...</a></li>
<li><a href="https://news.jethrojeff.com/?p=31">The $4 Trillion Handover: Why Investors are Lauding Tim ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#Tim Cook`, `#CEO transition`, `#John Ternus`, `#tech industry`

---

<a id="item-tech-news-3"></a>
### [wrapture: Graham Dumpleton&\#x27;s new Python library unifying mocking and tracing](https://simonwillison.net/2026/Aug/31/introducing-wrapture/) ⭐️ 7.0/10

Graham Dumpleton — known for wrapt, mod\_wsgi, and New Relic&\#x27;s Python agent — has introduced wrapture, a new Python library that takes the monkeypatching ideas from wrapt and extends them to testing and tracing at the same time. Wrapture makes it easy to wrap any function or method so that all access can be traced or overridden to return a different value, and it is positioned as both an alternative to unittest.mock and a way to implement tracing against an existing project — attaching observation to code you do not control and recording what flows through it without disturbing the program being watched. It ships with OpenTelemetry support and an entirely configuration-based mechanism for adding tracing to an existing project, demonstrated as a TOML file that declares observe targets such as domain:Calculator with methods outer and inner and a lines sink writing to trace.l. A follow-up post, Unit testing with wrapture, shows the testing patterns: a context-manager binding such as wrapture.binding\(Gateway, &quot;charge&quot;\).on\_call.returns\(\{...\}\) stubs a method to return a fixed value, while transforms\_result calls the original method and then modifies its return value. Dumpleton notes that every line of code and documentation was written by an AI assistant working under his direction — his first large agent-driven project, which he distinguishes from &quot;vibe coding&quot; because he engineered the design himself — and the few-weeks-old project is described by Simon Willison as off to a very promising start.

rss · Simon Willison · Aug 31, 23:59

**「Background」** Graham Dumpleton is a well-known Python developer best known for creating wrapt, a library for correct and transparent monkeypatching and wrapping of Python functions, as well as mod\_wsgi and the original New Relic Python agent. Wrapture builds directly on the monkeypatching ideas from wrapt, extending them so that wrapping can serve both testing \(mocking and stubbing, as an alternative to unittest.mock\) and tracing \(observation of calls, with OpenTelemetry support\) at the same time.

**「Impact」** Python developers gain a new option for stubbing, mocking, and tracing functions—including in third-party code they don&\#x27;t control—via wrapture&\#x27;s wrapt-based bindings, with built-in OpenTelemetry export and a configuration-only tracing setup for existing projects. As a weeks-old pre-release library \(1.0.0a12 on PyPI\), its real-world adoption and stability remain unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Aug/31/introducing-wrapture/">Introducing wrapture | Simon Willison’s Weblog</a></li>
<li><a href="https://grahamdumpleton.me/posts/2011/11/new-relic-is-not-just-for-apachemodwsgi/">New Relic is not just for Apache/ mod _ wsgi . - Graham Dumpleton</a></li>
<li><a href="https://readwrite.com/new-relic-expands-performance/">New Relic Expands Performance Monitoring as a Service with Python</a></li>
<li><a href="https://grahamdumpleton.me/posts/2026/08/introducing-wrapture/">Introducing wrapture - Graham Dumpleton</a></li>
<li><a href="https://pypi.org/project/wrapture/1.0.0a12/">wrapture · PyPI</a></li>

</ul>
</details>

**Tags**: `#python`, `#testing`, `#tracing`, `#open-source`, `#libraries`

---

<a id="item-tech-news-4"></a>
### [Preprint Claims Sliding-Window Attention Beats Linear Attention on Long-Context Reasoning](https://www.reddit.com/r/MachineLearning/comments/1w3j1vw/slidingwindow_attention_beats_linear_on/) ⭐️ 7.0/10

A new arXiv preprint by Alexia Jolicoeur-Martineau, Rhea Sanjay Sukthanker, Pashmina Cameron, and Emy Gervais argues that sliding-window attention with sinks \(SWA\), one of the simplest fixes for the quadratic-cost problem in LLMs, matches or substantially outperforms linear-attention variants on long-context reasoning benchmarks. The abstract reports that SWA achieves &quot;2 to 10 times higher&quot; performance than linear attention on Needle-in-a-Haystack and BABILong, the two tasks the paper highlights. The authors contend that the research line producing linear-attention models through post-training &quot;has not been properly compared to simpler baselines,&quot; implying the field has benchmarked against the wrong reference point. Their proposed SWA approach requires no post-training, runs fast, and keeps memory usage low, leading to the blunt recommendation to &quot;strongly recommend switching to SWA instead of post-training linear models.&quot; The abstract concedes linear attention &quot;may have shown some promise,&quot; but likely requires training from scratch or extensive post-training just to match SWA; as a single unverified preprint surfaced via Reddit, the claims warrant caution until independently replicated.

reddit · r/MachineLearning · /u/Justgototheeffinmoon · Aug 31, 16:35

**「Background」** Standard transformer attention scales quadratically with sequence length, which has motivated two families of cheaper alternatives: sliding-window attention \(SWA\), which restricts each token&\#x27;s attention to a fixed local window, and linear-attention variants, which restructure the attention computation itself to run in linear time. Attention sinks — keeping a few initial tokens always attended to — are a known refinement that stabilizes SWA over long contexts. Linear-attention approaches have attracted substantial industry investment, often requiring training from scratch or extensive post-training, whereas SWA with sinks is a simple drop-in technique that needs no post-training and runs at low memory cost.

**「Impact」** If the preprint&\#x27;s findings hold up, teams investing in post-training pipelines to convert models to linear attention may be spending compute on an approach that scores 2 to 10 times lower than simple sliding-window attention with sinks on long-context reasoning benchmarks like Needle-in-a-Haystack and BABILong, while requiring no post-training, running fast, and using low memory. As a single unverified preprint surfaced via Reddit, the claim warrants caution until independently replicated.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2608.28444">[2608.28444] Sliding-window beats linear attention</a></li>
<li><a href="https://arxiv.org/html/2608.28444">Sliding-window beats linear attention</a></li>
<li><a href="https://arxiv.org/abs/2608.28444">[2608.28444] Sliding-window beats linear attention - arXiv.org</a></li>
<li><a href="https://aiweekly.co/alerts/sliding-window-attention-beats-linear-on-long-context-reasoning">Sliding-window attention beats linear on long-context ...</a></li>
<li><a href="https://arxivtldr.org/abs/2608.28444">TL;DR: Sliding-window beats linear attention | ArXiv TLDR</a></li>

</ul>
</details>

**Tags**: `#attention-mechanisms`, `#long-context`, `#linear-attention`, `#LLM-architecture`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [DeepSeek Releases DeepSeek-V4-Flash-Vision-Exp Multimodal Weights](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp) ⭐️ 7.0/10

DeepSeek has published the weights of DeepSeek-V4-Flash-Vision-Exp on Hugging Face, the first experimental multimodal model in its V4 series. The model adds a vision module to the V4-Flash architecture and was produced through continued training on that base. Compared with V4-Flash-0731, its multimodal agent capability improved substantially, with the ApexBench score rising from 26.2 to 36.5, while performance on text agent tasks stayed essentially flat. The release gives the open-source community an early look at DeepSeek&\#x27;s multimodal direction, though the experimental status and unchanged text results mean it is not yet a major breakthrough. The weights can be downloaded from huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp.

telegram · zaihuapd · Aug 31, 11:41

**「Background」** DeepSeek&\#x27;s V4 generation debuted in April 2026 with fully open-weight checkpoints released under the MIT license, including DeepSeek-V4-Pro, a 1.6T-parameter Mixture-of-Experts model with roughly 49 billion activated parameters and a 1M-token context window. The new model builds on the V4-Flash architecture, a variant within that family, and its &\#x27;Exp&\#x27; suffix signals an experimental checkpoint shared for community evaluation rather than a stable production release. &\#x27;Multimodal agent&\#x27; capability refers to a model&\#x27;s ability to autonomously complete multi-step tasks that require interpreting images alongside text, which is the dimension the ApexBench score cited in the release notes is used to track.

**「Impact」** Developers and researchers working with open weights can now download and experiment with DeepSeek&\#x27;s first V4-series vision-enabled model, gaining early access to its improved multimodal agent capabilities. Given the experimental label and essentially flat text-agent scores, it is best treated as an early preview rather than a drop-in replacement for V4-Flash-0731 in text-only workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.clore.ai/guides/guides_v2-zh/yu-yan-mo-xing/deepseek-v4">DeepSeek V4（1.6T MoE，多模态） | Guides | Clore.ai</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#多模态模型`, `#开源权重`, `#AI agent`, `#大语言模型`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Aon CEO says insurance broker seeks to build &\#x27;premiere middle market platform&\#x27; with purchase of rival USI](https://www.cnbc.com/2026/08/31/aon-ceo-says-usi-deal-seeks-to-build-premiere-middle-market-insurance-platform.html) ⭐️ 8.0/10

Aon announced a $17 billion debt-funded acquisition of rival broker USI Insurance Services from KKR to build a leading U.S. middle-market insurance platform, with Aon shares falling 7% on the news.

rss · CNBC Finance · Aug 31, 15:15

**Tags**: `#M&amp;A`, `#insurance`, `#Aon`, `#USI Insurance Services`, `#middle market`

---

<a id="item-finance-news-2"></a>
### [Markets sharply raise odds of a September Fed rate hike after Warsh&\#x27;s Jackson Hole speech](https://www.cnbc.com/2026/08/31/markets-see-warsh-endorsing-a-rate-hike-in-september-not-everyone-is-convinced.html) ⭐️ 7.0/10

After Federal Reserve Chairman Kevin Warsh&\#x27;s hawkish Jackson Hole speech on Friday, markets roughly doubled the probability of a rate hike at the Fed&\#x27;s September 15-16 meeting to 66.1%, according to CME Group&\#x27;s FedWatch. Warsh said recent soft inflation readings do &quot;not tell me that underlying trends have meaningfully improved,&quot; though several observers—including Treasury Secretary Scott Bessent, Citigroup&\#x27;s Andrew Hollenhorst, and JPMorgan&\#x27;s David Kelly—argue a hike is premature given restrained core inflation and three straight weak jobs reports.

rss · CNBC Finance · Aug 31, 19:38

**「Background」** Jackson Hole is the Federal Reserve&\#x27;s annual August symposium in Wyoming, where the chair&\#x27;s keynote speech often signals the direction of interest rate policy. Before this year&\#x27;s speech, markets saw little chance of a hike until December, and at the July meeting only three of the 12 FOMC voters backed one.

**「Impact」** Investors face heightened sensitivity to upcoming data: jobs reports this week and CPI and PPI figures just before the meeting could confirm or reverse the repricing, with Bank of America warning that failing to deliver a September hike could undermine the credibility Warsh gained.

<details><summary>References</summary>
<ul>
<li><a href="https://apnews.com/article/federal-reserve-warsh-interest-trump-inflation-ab896df808df3a5a3fa8b943ac5f3867">Fed Chair Warsh signals rate hikes may be needed with US inflation stubbornly elevated</a></li>
<li><a href="https://www.cnbc.com/2026/08/31/jackson-hole-fed-chair-kevin-warsh-hawkish-rate-hikes-analysts.html">Jackson Hole analyst roundup: Warsh&#x27;s speech sends hike chances higher, may put Fed `at odds&#x27; with Treasury</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Jackson Hole`

---

<a id="item-finance-news-3"></a>
### [Tim Cook Steps Down as Apple CEO; John Ternus Takes Over with AI Focus](https://www.bloomberg.com/news/articles/2026-08-30/apple-s-new-ceo-john-ternus-takes-reins-from-tim-cook-focusing-on-ai) ⭐️ 7.0/10

August 31 marks Tim Cook&\#x27;s final day as Apple CEO, with hardware engineering chief John Ternus, 51, taking over on September 1 and Cook remaining as executive chairman, according to a report attributed to Bloomberg. Ternus&\#x27;s top mandate is delivering on AI, including addressing delays to Siri upgrades.

telegram · zaihuapd · Aug 31, 10:21

**「Background」** Apple announced the succession plan in April 2026: Tim Cook, who has led the company as CEO for about 15 years, would move to the newly created role of executive chairman, while John Ternus, Apple&\#x27;s senior vice president of hardware engineering, would take over as CEO effective September 1, 2026.

**「Impact」** The leadership change puts Apple&\#x27;s AI strategy — a perceived weak spot after delayed Siri updates — in the hands of a new CEO, a development investors and the broader tech industry will watch closely. Note: this item reached readers via an unverified Telegram relay citing Bloomberg, so details should be confirmed against the original report.

<details><summary>References</summary>
<ul>
<li><a href="https://www.foxbusiness.com/markets/tim-cooks-last-day-apple-ceo-how-he-led-tech-giants-rise-4t">Tim Cook steps down as Apple CEO after 15 years, names a successor | Fox Business</a></li>
<li><a href="https://www.apple.com/newsroom/2026/04/tim-cook-to-become-apple-executive-chairman-john-ternus-to-become-apple-ceo/">Tim Cook to become Apple Executive Chairman John Ternus to become Apple CEO - Apple</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#CEO transition`, `#Tim Cook`, `#John Ternus`, `#AI strategy`

---