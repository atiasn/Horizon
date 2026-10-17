---
layout: default
title: "Horizon Summary: 2026-10-17 (EN)"
date: 2026-10-17
lang: en
---

> From 40 items, 11 important content pieces were selected

---

**Technology News**
1. [Claude traces NIST elliptic curve seeds to lrand48 and Unix timestamps](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic details the Claude Code team&\#x27;s AI-heavy code review process](#item-tech-news-2) ⭐️ 8.0/10
3. [Researchers Exploit a 37-Year-Old Kernel Bug in OpenBSD](#item-tech-news-3) ⭐️ 8.0/10
4. [Apple&\#x27;s MLX Runs Trillion-Parameter Muse Spark Open Across Mac Studio Clusters](#item-tech-news-4) ⭐️ 7.0/10
5. [JPEG XL vs. AVIF: Jake Archibald compares the two codecs for web delivery](#item-tech-news-5) ⭐️ 7.0/10
6. [Mercor study: 90% of US working hours lack AI benchmark coverage](#item-tech-news-6) ⭐️ 7.0/10
7. [StarSkirmish Bench v0.2 Ranks LLMs by Writing StarCraft Brood War Bots](#item-tech-news-7) ⭐️ 7.0/10
8. [阶跃星辰发布 Step 5 Preview 智能体旗舰模型](#item-tech-news-8) ⭐️ 7.0/10
9. [Court Filings Reveal Telegram Has Shared Data on 2,253 Users with U.S. Authorities](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [China Proposes Temporary Export Registration for 40 AI, Biopharma, and Solar Technologies](#item-finance-news-1) ⭐️ 8.0/10
2. [U.S. pushes China on Mastercard and Citigroup market access in Bangkok talks](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Claude traces NIST elliptic curve seeds to lrand48 and Unix timestamps](https://www.anthropic.com/research/ecdsa-curve-origins) ⭐️ 8.0/10

Claude determined that the seeds behind NIST&\#x27;s elliptic curves P-192, P-224, P-256, P-384, and P-521 were not outputs of any hash function, but of the C library&\#x27;s lrand48 random-number generator seeded with Unix timestamps. In under half an hour, it found the matching generation method, largely deflating roughly 25 years of speculation that the unexplained seeds hid an NSA backdoor. One seed, B-163, still fits nothing that was tried and remains unexplained, and because the candidates generated and discarded during selection cannot be inspected, the seed-selection process itself remains unverifiable even though the production method is now known.

hackernews · ahlCVA · Oct 16, 18:55 · [Discussion](https://news.ycombinator.com/item?id=50122800)

**「Background」** In 1997–98, NIST standardized its ECDSA elliptic curves \(P-192 through P-521\) using published &quot;seeds&quot; that were widely believed to be hashes of some memorable, verifiable string—a ritual meant to prove the curves weren&\#x27;t secretly engineered. Because the seeds&\#x27; actual origin was never documented, critics spent roughly 25 years speculating that the NSA could have searched for weak curve parameters behind the scenes, a suspicion sharpened by unrelated revelations about NSA influence on cryptography standards. Filippo Valsorda&\#x27;s bounty on the seed question drew renewed attention to the puzzle, and the reported solution—that the seeds came from lrand48 seeded with a Unix timestamp, not any hash function—is what Claude is said to have found.

**「What it changes for cryptography」** For cryptographers and security auditors, the finding removes the main evidentiary basis for backdoor theories about how the NIST P-curve seeds were produced, but it does not prove the seeds were selected honestly, since timestamp-searched candidates could in principle still have been filtered for desired properties. The practical takeaway is that the result is primarily historical: it does not change the security of curves already in deployment, though it reinforces the case for standardized, verifiable seed-generation procedures going forward.

**「Community reaction」** Commenters largely treated the result as a blow to NIST-curve conspiracy theories, with Thomas Ptacek calling it &\#x27;devastating news&\#x27; for a generation of such claims and one commenter quipping that 13 years of &\#x27;tinfoil hats&\#x27; traced back to srand48\(time\(NULL\)\). More cautious voices, such as fidotron, argued the finding confirms only the production method, not the selection, since discarded candidates generated over months cannot be audited; teddyh offered the speculation that the still-unexplained B-163 seed may simply contain a typo from publication.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/anthropic-claude-traced-nist-ecdsa-seeds-to-unix-timestamps">Anthropic: Claude Traced NIST ECDSA Seeds to Unix Timestamps</a></li>
<li><a href="https://words.filippo.io/seeds-solved/">The NIST Elliptic Curves Seeds Bounty Has Been Claimed</a></li>

</ul>
</details>

**Tags**: `#cryptography`, `#elliptic-curves`, `#AI-assisted-research`, `#security`, `#history`

---

<a id="item-tech-news-2"></a>
### [Anthropic details the Claude Code team&\#x27;s AI-heavy code review process](https://claude.dev/blog/solving-code-review-at-anthropic/) ⭐️ 8.0/10

Anthropic has published an engineering blog post describing how the Claude Code team handles code review when a large share of its code is produced by AI agents. The post describes an automated review pipeline in which most of the path is automated and human attention is directed to the highest-risk changes, with risk-tiered requirements — for example, low-risk changes such as docs or additive work behind flags need no human review once automated and security checks pass. The team also maintains an eval that grows with every incident, and changes to the automated reviewer are scored against that eval. The post sparked substantial Hacker News debate \(233 points, 219 comments\), with commenters questioning whether humans can meaningfully oversee the claimed volume of changes, with one commenter citing roughly 30,000 pull requests per day.

hackernews · pretext · Oct 16, 19:04 · [Discussion](https://news.ycombinator.com/item?id=50122951)

**「Background」** The Claude Code team at Anthropic builds the command-line coding agent of the same name, and its engineering blog has previously covered how to structure agent-driven development workflows. According to the post, the team reached its current review process after first establishing high test coverage and deep automated reviews, then optimizing for the minimum amount of human review time that does not increase reverts or incidents. That framing—treating human attention as a scarce resource to be allocated by risk—is the context behind the Hacker News debate over whether teams can actually keep pace when AI agents generate pull requests at very large scale.

**「What it means for engineering teams」** For teams adopting AI-assisted development, the post offers a concrete template: tier changes by risk, automate the low-risk tier&\#x27;s checks, and route scarce human review time to high-risk code. The caveat visible in the discussion is that the described scale appears to push human oversight toward supervising automated reviewers rather than reading code directly — a dependency teams would need to weigh, especially since Anthropic itself gates that reviewer&\#x27;s quality on an internal eval rather than on per-change human inspection.

**「HN: skepticism about scale and skipped review」** Commenters were skeptical that meaningful human control survives at the described volume: vb-8448 argued no human can stay on par with roughly 30,000 PRs per day and guessed the cost per line of code may be &\#x27;insane&\#x27; with code rewritten repeatedly, while koolba called it &\#x27;pure insanity&\#x27; that the workflow allows LLM-written docs to ship with no human reading them once automated checks pass. Others criticized the writing and claims on their own terms — mk12 noted the polished style suggests Anthropic does use AI for external writing despite rumors of a rule against it, and dieortin pushed back on a quoted claim that slowing down lowers error rate, arguing that is not how rates work.

<details><summary>References</summary>
<ul>
<li><a href="https://claude.dev/blog/solving-code-review-at-anthropic/">How the Claude Code team does code review / claude .dev Blog</a></li>
<li><a href="https://claude.com/resources/articles/code-review">Code Review for Claude Code | Claude by Anthropic</a></li>

</ul>
</details>

**Tags**: `#code-review`, `#anthropic`, `#claude-code`, `#ai-assisted-development`, `#software-engineering`

---

<a id="item-tech-news-3"></a>
### [Researchers Exploit a 37-Year-Old Kernel Bug in OpenBSD](https://calif.io/research/big-fish) ⭐️ 8.0/10

Security researchers at Calif detail &\#x27;Big Fish,&\#x27; a write-up demonstrating exploitation of a kernel bug that survived in OpenBSD for 37 years, in one of the most heavily audited codebases in open source. The disclosure documents concrete exploitation of the flaw rather than just reporting it. Per community commentary, the same code was incidentally fixed in NetBSD during a rewrite in August 1999, underscoring how long such bugs can persist across descendants of the same codebase. No source content was supplied, so details of the affected versions and any patch status could not be verified from the primary material.

hackernews · rs\_rs\_rs\_rs\_rs · Oct 16, 14:44 · [Discussion](https://news.ycombinator.com/item?id=50118977)

**「Background」** OpenBSD is widely regarded as one of the most heavily audited operating systems, which makes a bug surviving in its kernel for 37 years especially notable. The flaw traces back to the original BSD source code: a signed 16-bit attachment counter in the SysV shared memory implementation, a code path inherited by the many systems descended from BSD. Modern OpenBSD ships layered kernel defenses such as KARL \(kernel address randomization\) and SMAP/SMEP hardware protections, which the researchers&\#x27; exploit chain had to defeat to achieve local root.

**「Impact」** OpenBSD administrators should update promptly: security firm Calif published working proof-of-concept exploit code on October 16, 2026 that chains a roughly 37-year-old integer overflow inherited from the original BSD source code with a kernel use-after-free to gain root privileges from a local account on OpenBSD 7.9. Both flaws have since been patched, so unpatched multi-user OpenBSD deployments remain exposed to a publicly available local privilege-escalation path until they upgrade.

**「What the discussion says」** Commenter phendrenad2 noted that the buggy code appears to have been accidentally fixed in NetBSD during an August 1999 rewrite, offering historical context for the bug&\#x27;s lineage. Others debated whether fuzzing or static analysis could realistically catch this bug class, or whether it required a human reasoning about the exploit primitive — an open question, not a settled conclusion.

<details><summary>References</summary>
<ul>
<li><a href="https://daily.dev/posts/big-fish-exploiting-a-37-year-old-kernel-bug-in-openbsd-u6hc8g4lt">Big Fish: Exploiting a 37-Year-Old Kernel Bug in OpenBSD</a></li>
<li><a href="https://zeli.app/story/50118977">Calif Researchers Exploit 37-Year-Old · Hacker News | Zeli</a></li>
<li><a href="https://thedailytechfeed.com/37-year-old-kernel-bug-in-openbsd-finally-patched-after-root-exploit-poc/">37-Year-Old Kernel Bug in OpenBSD Finally Patched After Root ...</a></li>
<li><a href="https://cybersecuritynews.com/37-year-old-kernel-openbsd-flaw/">37-Year-Old Kernel Flaw Exploited to Gain Root Access on ...</a></li>
<li><a href="https://thehackernews.com/2026/10/researchers-demonstrate-openbsd-root.html">Researchers Demonstrate OpenBSD Root Exploit Chaining 37-Year ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#kernel`, `#OpenBSD`, `#vulnerability-research`, `#operating-systems`

---

<a id="item-tech-news-4"></a>
### [Apple&\#x27;s MLX Runs Trillion-Parameter Muse Spark Open Across Mac Studio Clusters](https://machinelearning.apple.com/research/mlx-distributed-inference) ⭐️ 7.0/10

Apple&\#x27;s machine learning research team published a demonstration showing a new MLX release running the open-weight Muse Spark Open model, with nearly a trillion parameters, across a cluster of four Mac Studios at over 36 tokens per second. The post begins with a single Mac Studio with up to 512GB of unified memory and scales out across multiple machines. Apple frames this as running a frontier-class model &\#x27;right from your desk,&\#x27; noting the throughput exceeds average human reading speed. The demonstration was accompanied by a new MLX version released the same day.

hackernews · antipaul · Oct 16, 13:43 · [Discussion](https://news.ycombinator.com/item?id=50118320)

**「Background」** MLX is Apple&\#x27;s open-source array framework optimized for its unified-memory Apple Silicon chips, which allow a single Mac Studio with up to 512GB of memory to hold very large model weights that would normally require multi-GPU servers. Muse Spark Open is an 816-billion-parameter open-weight model that Apple and Meta jointly released, optimized to run locally on Apple hardware. The new result combines these pieces: a fresh MLX release that scales inference across multiple Mac Studios, decoding roughly 36.7 tokens per second at 8,192-token context on a four-machine cluster with M5 Ultra chips.

**「Practical impact」** Teams and individuals with access to Mac Studio clusters can now run frontier-scale \(~816B-parameter\) open-weight models locally at readable speeds — over 36 tokens per second across four machines via the new MLX release — without renting cloud GPUs. However, commenters report that single machines already run strong alternatives: one user cites a 256GB M5 Ultra running DeepSeek 4.1 Flash at roughly 45 tokens per second with ~3,200 tokens/s prefill, and questions the post&\#x27;s benchmarking choices, such as comparing Muse Spark Open at 4-bit quantization against Qwen at native BF16. Buyers should therefore benchmark candidate models on their own workloads rather than assuming the Apple-demonstrated setup is the best use of the hardware, and should note that the reported 15-36 tokens/s figures apply to an 8,192-token context, which one commenter calls too limited for many current uses.

**「Community Debates Benchmarks and Economics」** Commenters questioned the benchmarking methodology: peri-cl argued Apple &\#x27;sandbagged&\#x27; Qwen by benchmarking Meta&\#x27;s Muse Spark at 4-bit quantization against Qwen only at native BF16, and said Muse Spark would not rank among their top ten model choices for a 512GB M5 setup, while tony\_cannistra noted the 15-36 tokens/s figures apply to an 8,192-token context, which they called &\#x27;not nearly enough context to be useful these days.&\#x27; Others focused on economics — ks2048 observed wryly that Meta spends billions building open-weight models while Apple collects the hardware revenue — and liuliu reported alternative single-machine setups, claiming an M5 Ultra with 256GiB runs DeepSeek 4.1 Flash at about 45 tok/s and an M5 Max with 128GiB handles GLM-5.3-Flash 5.3 Flash, with quality benchmarked against official numbers. These are individual reports and opinions, not independently verified results.

<details><summary>References</summary>
<ul>
<li><a href="https://machinelearning.apple.com/research/mlx-distributed-inference">Local and Distributed Large LLM Inference with MLX and RDMA on...</a></li>
<li><a href="https://www.youtube.com/watch?v=XIxUnKQx92s">Apple and Meta Launch Muse Spark Open for Mac Studio - YouTube</a></li>
<li><a href="https://the-decoder.com/muse-spark-open-is-metas-answer-to-qwen-glm-and-kimi-in-the-open-weight-race/">Muse Spark Open is Meta&#x27;s answer to Qwen, GLM, and Kimi in ...</a></li>

</ul>
</details>

**Tags**: `#MLX`, `#distributed-inference`, `#Apple-Silicon`, `#open-weight-models`, `#local-llm`

---

<a id="item-tech-news-5"></a>
### [JPEG XL vs. AVIF: Jake Archibald compares the two codecs for web delivery](https://jakearchibald.com/2026/jpeg-xl-vs-avif/) ⭐️ 7.0/10

Jake Archibald published a detailed comparison of JPEG XL and AVIF for web image delivery, weighing compression efficiency, encoding speed, and practical encoder settings. Among the concrete trade-offs discussed \(and echoed in the community\): libjxl at maximum effort produces files 2–7% smaller than its default for photos and around 25% smaller for screenshots and illustrations, but takes 9–46 seconds per image — 50–180x longer than its default — while the third-party encoder jixel achieves similar results in a couple of seconds. The piece is evaluative analysis rather than a new capability announcement, aimed at helping web developers pick a codec and settings for real-world use.

hackernews · farlight · Oct 16, 16:12 · [Discussion](https://news.ycombinator.com/item?id=50120224)

**「Why this comparison matters now」** JPEG XL is an image format designed as a modern successor to JPEG, while AVIF \(based on the AV1 video codec\) has been the leading alternative for high-efficiency web image delivery in recent years. The comparison gained new relevance because JPEG XL support has now landed in all major browsers, removing the compatibility barrier that previously held it back and making a head-to-head evaluation of the two formats practical for web developers.

**「What this means for web developers」** Despite JPEG XL&\#x27;s compression advantages shown in the comparison, developers cannot yet rely on it for direct image delivery: as of mid-2026 the decoder ships in Chrome behind a flag \(enabled via --enable-jxl-image-format since Chrome 145 in February 2026\), and no major browser enables JPEG XL by default, while Safari is reported to ship it. Until default support lands, teams adopting JPEG XL need content negotiation or fallback formats \(such as AVIF, which already works in production per community reports\), and should be aware of AVIF&\#x27;s reported artifact risks on detail-critical imagery like highlights.

**「Community discussion」** On Hacker News \(196 points, 143 comments\), commenters shared encoder tuning tips — one reported AVIF achieving roughly 10x+ smaller files with transparency support via a specific ffmpeg pix\_fmt pipeline, while another argued the codecs are still immature, drawing a parallel to the years it took LAME to make MP3 shine and warning against declaring a winner early. Others pushed back on AVIF&\#x27;s quality claims, with one commenter pointing to an F1 test image where fine car highlights were visibly erased and replaced with plausible-looking detail, suggesting AVIF suits impressionistic hero images more than detail-critical uses.

<details><summary>References</summary>
<ul>
<li><a href="https://jakearchibald.com/2026/jpeg-xl-vs-avif/">JPEG XL vs AVIF for web use-cases - JakeArchibald.com</a></li>
<li><a href="https://jpegxlconvert.com/en/chrome-jpeg-xl-support/">Does Chrome Support JPEG XL? (Updated July 2026)</a></li>
<li><a href="https://freetoolonline.com/news/jpeg-xl-returns-chrome-firefox.html">JPEG XL Browser Support 2026 - Chrome, Firefox, Safari - Free ...</a></li>
<li><a href="https://theimagecdn.com/docs/jpeg-xl-explained">JPEG XL in 2026: Back in Chrome, Still Not Ready for Your ...</a></li>

</ul>
</details>

**Tags**: `#jpeg-xl`, `#avif`, `#image-compression`, `#web-performance`, `#codecs`

---

<a id="item-tech-news-6"></a>
### [Mercor study: 90% of US working hours lack AI benchmark coverage](https://www.mercor.com/research/labor-index/benchmark-map/) ⭐️ 7.0/10

A research study published by Mercor, an AI labor-market company, claims that 90% of US working hours are spent on tasks with little or no coverage by existing AI benchmarks, meaning current evaluations say little about how well AI models perform the work Americans actually do. The company also reports that O\*NET tasks from occupations with larger wage bills are significantly overrepresented among benchmark prompts, even after controlling for AI exposure. Both figures are the vendor&\#x27;s own analysis, not an independently verified result, and the definition of &quot;covered well&quot; is contestable. The work was shared on Hacker News, where it drew substantial debate.

hackernews · speckx · Oct 16, 17:08 · [Discussion](https://news.ycombinator.com/item?id=50121179)

**「Background: AI benchmarks and Mercor&\#x27;s role」** AI benchmarks are standardized task suites used to measure model capabilities, but they typically concentrate on a narrow slice of tasks, such as coding, math, and knowledge questions, which is why coverage of broader occupational work has become a contested question. Mercor, the company behind this labor-index analysis, is a labor-market business that matches professionals with remote work at client companies and also develops its own evaluation suites, including the APEX benchmark family described as measuring AI&\#x27;s impact on professional work; it is reported as a profitable Series C company valued at $10 billion. That dual role—as both a talent marketplace and an eval publisher—means the study&\#x27;s framing of &\#x27;covered well&\#x27; comes from a firm with a commercial interest in how AI labor capability is assessed.

**「Practical implication for model selection」** Teams that pick AI models based on public leaderboards may be buying capability signals that say little about their actual work: per Mercor&\#x27;s analysis, roughly 90% of US working hours fall in tasks with little or no benchmark coverage, yet widely used rankings such as BenchLM&\#x27;s leaderboard of 212+ models across 645 benchmarks \(SWE-bench, MMLU-Pro, GPQA Diamond, and similar\) are dominated by well-covered categories like coding and knowledge reasoning. The practical step is to treat benchmark scores as a coarse filter and supplement them with evaluations built from a sample of the organization&\#x27;s own tasks, since the study suggests even &quot;well covered&quot; categories can rest on as few as 13 prompts. Note the finding comes from Mercor, a labor-market AI company with a potential promotional stake, and commenters argue its &quot;covered well&quot; threshold is loose, so the 90% figure itself should not be treated as independently measured.

**「Community discussion」** Commenters questioned the methodology, with one arguing that &quot;covered well&quot; is effectively being treated as &quot;covered at all&quot; — for example, a social-work counseling category deemed well covered on the basis of only 13 prompts. Others invoked economic framings: one commenter applied Baumol&\#x27;s cost disease at a personal scale \(reporting being 20x more productive at coding while spending more time on presentations, Jira, and QA\), another likened the situation to the Doorman Fallacy, where replaced workers&\#x27; unmeasured functions go unaccounted for, and one commenter saw the wage-bill overrepresentation as evidence that benchmarking incentives favor automating higher-paid occupations.

<details><summary>References</summary>
<ul>
<li><a href="https://work.mercor.com/">Mercor | Find Remote Work Opportunities</a></li>
<li><a href="https://wellfound.com/jobs/4817944-senior-pmm-evals">Senior PMM, Evals at Mercor • San Francisco | Wellfound</a></li>
<li><a href="https://benchlm.ai/">LLM Leaderboard &amp; AI Model Benchmarks — October 2026</a></li>
<li><a href="https://llm-stats.com/benchmarks">AI &amp; LLM Benchmarks 2026 : Rankings, Scores &amp; Results</a></li>

</ul>
</details>

**Tags**: `#ai-benchmarks`, `#ai-evaluation`, `#labor-economics`, `#research-analysis`, `#ai-industry`

---

<a id="item-tech-news-7"></a>
### [StarSkirmish Bench v0.2 Ranks LLMs by Writing StarCraft Brood War Bots](https://starskirmish.com/bench/v0-2/) ⭐️ 7.0/10

Developer \_\_cayenne\_\_ has released version 0.2 of StarSkirmish Bench \(starskirmish.com\), a community benchmark that evaluates flagship LLMs by having each model write code for a StarCraft: Brood War bot. The refresh adds results from the flagship models of OpenAI, Anthropic, Google, and Muse. Each model runs inside its own lab&\#x27;s first-party CLI coding agent at its highest reasoning setting — Claude Code for Anthropic, Codex for OpenAI, Antigravity CLI for Google, and Muse Code for Meta — with web search and fetch tools disabled so the agent has no internet access during the run. The benchmark is an early-stage community project \(v0.2\), not an industry-standard evaluation, so the significance of the current rankings remains uncertain.

hackernews · \_\_cayenne\_\_ · Oct 16, 14:18 · [Discussion](https://news.ycombinator.com/item?id=50118688)

**「Background」** StarCraft: Brood War has long served as a benchmark for game AI, from hand-coded scripted bots to DeepMind&\#x27;s AlphaStar, because it demands real-time planning under partial information. StarSkirmish Bench applies that setting to LLMs differently: instead of playing directly, each model is run in its lab&\#x27;s first-party coding CLI \(Claude Code for Anthropic, Codex for OpenAI, Antigravity for Google, Muse Code for Meta\) with web search and fetch disabled, and must write a bot within a limited time. The referenced v0.2 leaderboard places GPT-6 Astra ahead of GPT-6.1 Sol, Gemini 4 Argon, and several Claude models.

**「What it means for AI evaluation」** For developers and researchers tracking agentic coding ability, StarSkirmish Bench v0.2 offers a concrete, reproducible setup — each model gets one hour in its lab&\#x27;s first-party CLI harness to write a C++ Protoss bot \(BWAPI 4.4.0 on OpenBW\), scored by win rate against human-written bots — and GPT-6 Astra currently leads with a 57% score, though top models still lose to elite human bots \(tool-2-2, tool-2-3\). A commenter reported that the benchmark&\#x27;s model ranking exactly matches an independent 9x9 Go benchmark using KataGo Elo anchors, which, if it holds up, suggests game-based agentic benchmarks may converge on a general capability signal rather than measuring game-specific skill \(tool-2-2\). However, community skepticism remains about what the bots actually demonstrate: commentators raised unresolved questions about training-data contamination from existing human-written bots and whether agent-written bots generalize beyond the one-hour format, so readers should treat the rankings as an early community project \(v0.2\) rather than an established evaluation \(tool-2-2\).

**「What does the benchmark actually measure?」** Commenter GodelNumbering reports that StarSkirmish v0.2&\#x27;s ranking order \(GPT-6 Astra &gt; GPT-6.1 Sol &gt; Gemini 4 Argon &gt; Claude Opus 5.5 &gt; Claude Fable 5.1 &gt; Claude Sonnet 5.5\) exactly matches a friend&\#x27;s independent 9x9 Go benchmark anchored by KataGo Elo, suggesting the two tests may capture a shared capability despite being different games — though this is a personal observation, not a verified correlation. Other commenters raised methodological questions: cgearhart asks whether the agent-written bots are merely inferior copies of human-written bots, whether models were trained on existing bot code, and how much the agents apply the same techniques each run, arguing these questions matter more than the ranking itself.

<details><summary>References</summary>
<ul>
<li><a href="https://zeli.app/story/50118688">StarSkirmish Bench v0.2 - LLMs write · 72 HN comments | Zeli</a></li>
<li><a href="https://agihunt.info/en/p/1a0df1121cc29262c8dbf3fe399">StarSkirmish Bench: LLMs write StarCraft Brood… · AGI Hunt</a></li>

</ul>
</details>

**Tags**: `#llm-benchmarks`, `#ai-agents`, `#code-generation`, `#game-ai`, `#starcraft`

---

<a id="item-tech-news-8"></a>
### [阶跃星辰发布 Step 5 Preview 智能体旗舰模型](https://huggingface.co/stepfun-ai/Step-5-Preview) ⭐️ 7.0/10

StepFun \(阶跃星辰\) has released Step 5 Preview on Hugging Face, a 600B-total/27B-active sparse MoE agentic flagship model supporting 1M-token context and text, image, and video inputs, deployable via OpenAI-compatible APIs with vLLM or SGLang.

telegram · zaihuapd · Oct 16, 06:36

**Tags**: `#large-language-models`, `#mixture-of-experts`, `#agentic-AI`, `#model-release`, `#multimodal`

---

<a id="item-tech-news-9"></a>
### [Court Filings Reveal Telegram Has Shared Data on 2,253 Users with U.S. Authorities](https://www.404media.co/heres-what-telegram-giving-data-to-the-u-s-government-looks-like/) ⭐️ 7.0/10

Newly disclosed court filings, reported by 404 Media, show that Telegram provided a user&\#x27;s phone number, user ID, and IP address to U.S. law enforcement in response to a court order, describing the disclosure in a letter as voluntary while stating it did not acknowledge U.S. jurisdiction. The case involved Mahmoud Al-Muhtadi, who is accused of participating in the October 7, 2023 attack on Israel. According to the filings, Telegram had supplied data on 2,253 users to U.S. authorities as of January. The documents offer a concrete look at how a platform long marketed as privacy-focused responds to U.S. legal demands.

telegram · zaihuapd · Oct 16, 14:57

**「Background」** Telegram was long regarded as a privacy-focused messenger, but in January 2025 reports revealed that its data disclosures to U.S. authorities had risen sharply, with the company fulfilling 900 U.S. government requests covering 2,253 users&\#x27; phone numbers or IP addresses in the prior year \(Horizon&\#x27;s digest reported this at the time\). The newly disclosed court filings now show what one of those handovers looks like in practice: a letter in which Telegram says it provided the data &quot;voluntarily&quot; while stating it is &quot;not conceding that we are subject to U.S. jurisdiction for this or any other request or any purpose,&quot; in response to a court order issued under the Stored Communications Act.

**「Why It Matters」** Users who rely on Telegram for private communications should treat phone numbers, user IDs, and IP addresses as data the company may hand over under legal process, and consider mitigations such as hiding their IP address from contacts or using communications with stronger metadata protections, since IP addresses were among the disclosed data points.

<details><summary>References</summary>
<ul>
<li><a href="https://www.404media.co/heres-what-telegram-giving-data-to-the-u-s-government-looks-like/">Here’s What Telegram Giving Data to the U.S. Government Looks ...</a></li>
<li><a href="https://www.404media.co/telegram-hands-u-s-authorities-data-on-thousands-of-users/">Telegram Hands U.S. Authorities Data on Thousands of Users</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#telegram`, `#government-surveillance`, `#messaging-platforms`, `#data-sharing`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China Proposes Temporary Export Registration for 40 AI, Biopharma, and Solar Technologies](https://aqygzj.mofcom.gov.cn/flzc/gzjgfxwj/art/2026/art_c99f95ca0cd043829ac9991495fc283c.html) ⭐️ 8.0/10

China&\#x27;s Ministry of Commerce has opened public comment on a draft revision of its prohibited and restricted technology export catalog that would add 40 technologies — 23 in artificial intelligence \(large models, agents, computing clusters\), 5 in biopharmaceuticals \(cell and gene therapy, small nucleic acid drugs\), and 12 in photovoltaics \(polysilicon, wafer, and cell manufacturing\) — while applying temporary registration requirements to related technology exports. The draft excludes technologies already in the public domain via open-source release or academic publication, extends control to key equipment carrying photovoltaic technologies, and offers automatic-licensing facilitation for biopharma out-licensing that does not transfer ownership.

telegram · zaihuapd · Oct 16, 09:12

**「Background」** The China Prohibited and Restricted Technology Export Catalog is the government&\#x27;s list of technologies that companies may not transfer to foreign parties, or may export only with official approval, so adding an item means that know-how needs government clearance before it leaves the country. While this revision is still at the public-comment stage, exports of the listed AI, biopharmaceutical, and photovoltaic technologies must be registered with the commerce authorities in advance — the &quot;temporary registration&quot; requirement.

**「Impact」** Chinese AI, biopharmaceutical, and solar companies and their foreign partners now face a registration step before completing technology export or licensing deals, adding a compliance hurdle to cross-border transactions in sectors already strained by US-China tech restrictions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.independent.co.uk/asia/china/china-export-controls-ai-solar-biotech-us-trade-war-b3068046.html">China proposes export controls on AI, solar and biopharma ...</a></li>
<li><a href="https://apnews.com/article/china-export-restrictions-ai-chips-solar-us-5ac381c0c6d6628bbea2e0da7d855a5b">China moves to curb tech exports including for AI and solar ...</a></li>

</ul>
</details>

**Tags**: `#China`, `#export controls`, `#artificial intelligence`, `#photovoltaics`, `#biotechnology`

---

<a id="item-finance-news-2"></a>
### [U.S. pushes China on Mastercard and Citigroup market access in Bangkok talks](https://www.cnbc.com/2026/10/16/us-china-mastercard-citigroup-market-access.html) ⭐️ 7.0/10

U.S. Treasury officials, in meetings with China&\#x27;s central bank and finance ministry on the sidelines of the G20 and IMF-World Bank gatherings in Bangkok, pressed for market access for Mastercard and Citigroup, following China&\#x27;s Oct. 13 approval letting Visa begin preparing a wholly owned domestic card-clearing business.

rss · CNBC Finance · Oct 16, 16:46

**「Background」** Mastercard currently operates in China through a joint venture that began in 2024 and is seeking approval to operate independently, while Citigroup applied in late 2021 for a license to do A-share securities business onshore and reportedly plans to grow its China securities staff to about 100 people.

**「Impact」** Approval of the pending applications would let these U.S. financial firms expand directly in China&\#x27;s payments and securities markets, and analysts at Eurasia Group said the continued openings may marginally bolster investor confidence in Chinese assets.

**Tags**: `#US-China relations`, `#financial market access`, `#payments industry`, `#Citigroup`, `#trade diplomacy`

---