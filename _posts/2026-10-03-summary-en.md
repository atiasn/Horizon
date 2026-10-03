---
layout: default
title: "Horizon Summary: 2026-10-03 (EN)"
date: 2026-10-03
lang: en
---

> From 37 items, 8 important content pieces were selected

---

**Technology News**
1. [New AI tops Stratego with 34 times less training than DeepNash](#item-tech-news-1) ⭐️ 8.0/10
2. [Greg Kroah-Hartman: Most of Mythos&\#x27;s 79 LLM-Reported Kernel Bugs Didn&\#x27;t Hold Up](#item-tech-news-2) ⭐️ 8.0/10
3. [Redis creator&\#x27;s DwarfStar ds4 runs LLMs on personal hardware](#item-tech-news-3) ⭐️ 7.0/10
4. [arXiv caps each submitter at two papers per month](#item-tech-news-4) ⭐️ 7.0/10
5. [Apple to Tighten macOS Full Disk Access Permissions Citing AI Agent Risks](#item-tech-news-5) ⭐️ 7.0/10

**Technology Blog**
1. [Superpersuasion Will Look Like Bribery](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [Traders Slash Odds of October Fed Rate Hike After Weak Jobs Report](#item-finance-news-1) ⭐️ 7.0/10
2. [Bitget CEO expects little recovery of $388 million stolen in hack](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [New AI tops Stratego with 34 times less training than DeepNash](https://arstechnica.com/science/2026/10/ai-finally-beat-the-best-stratego-player-in-history-and-did-it-on-a-budget/) ⭐️ 8.0/10

A new AI system, described in a Nature paper and an arXiv preprint, reportedly surpasses the best known Stratego play while training on roughly 34 times fewer games than DeepNash, the 2022 DeepMind system that first reached expert-level Stratego. Stratego is a demanding test for game AI because nearly all piece information is hidden, which defeats the straightforward lookahead search that works in games like chess and Go. The result is therefore an advance in training efficiency and playing strength on an already-conquered game rather than a first-of-its-kind breakthrough, and the specifics rest on the paper listings rather than independent verification.

hackernews · PaulHoule · Oct 2, 14:11 · [Discussion](https://news.ycombinator.com/item?id=49933740)

**「Stratego and the DeepNash baseline」** Stratego is a chess-like strategy wargame played on a 10×10 board in which each player commands an army of 40 pieces whose ranks stay hidden from the opponent, so a move&\#x27;s quality depends on information neither side can see. The prior landmark in the game was DeepNash, DeepMind&\#x27;s expert-level Stratego bot, which set the benchmark for machine play. The new study, titled &quot;Superhuman AI for Stratego Using Self-Play Reinforcement Learning and Test-Time Search&quot; by Samuel Sokota and four co-authors, positions itself against that baseline by combining self-play reinforcement learning with search applied at test time.

**「Impact for AI research」** AI researchers gain a publicly documented method rather than just a leaderboard result: per the Nature paper&\#x27;s abstract, Ataraxos &quot;establishes a design pattern for reinforcement learning and search that is effective under large amounts of hidden information,&quot; and both the paper and an arXiv preprint are freely accessible. Because the system reportedly trained on about 34 times fewer games than DeepNash while playing more strongly, teams without the scale of compute behind the earlier 2022 DeepNash effort can plausibly attempt competitive hidden-information agents or adapt the approach to other imperfect-information games. The efficiency figures are reported claims not yet independently reproduced, so anyone citing the result should carry that caveat.

**「Commenters focus on sample efficiency」** The most substantive comment argued that the ~34x reduction in games played is the critical contribution, because in hidden-information games a move&\#x27;s value depends on information the player cannot know, making lookahead search impractical and fast learning essential. Other readers reacted with nostalgia and surprise that a game many considered simple had resisted AI for so long.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Stratego">Stratego - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2511.07312">[ 2511 . 07312 ] Superhuman AI for Stratego Using Self-Play...</a></li>
<li><a href="https://www.youtube.com/watch?v=3vO45gcEbRs">AI beats us at another game: STRATEGO | DeepNash paper explained</a></li>
<li><a href="https://www.researchgate.net/publication/415037550_Scalable_decision-making_for_games_of_imperfect_information">(PDF) Scalable decision-making for games of imperfect information</a></li>
<li><a href="https://www.nature.com/articles/s41586-026-11036-y?error=cookies_not_supported&amp;code=99150def-d132-4ca6-8dde-5d145b1e2185">Scalable decision-making for games of imperfect information | Nature</a></li>

</ul>
</details>

**Tags**: `#artificial-intelligence`, `#imperfect-information-games`, `#game-ai`, `#reinforcement-learning`, `#research`

---

<a id="item-tech-news-2"></a>
### [Greg Kroah-Hartman: Most of Mythos&\#x27;s 79 LLM-Reported Kernel Bugs Didn&\#x27;t Hold Up](https://www.youtube.com/watch?v=NnV_cWeoo5Q) ⭐️ 8.0/10

In a Kernel Recipes 2026 talk, Linux kernel maintainer Greg Kroah-Hartman walked through a widely publicized set of 79 kernel vulnerabilities reported by the Mythos LLM and found most of them unsubstantiated or stale: 24 gave no detail at all, 14 were not bugs, 3 contained fabricated data, and 15 were already fixed in the latest release — 11 by other developers and 4 by Anthropic. By his accounting, 20 reports described real issues needing fixes, though many depended on specific attacker preconditions, such as assuming a malicious filesystem image. He also criticized the lab for not crediting the kernel developers who originally wrote the fixes, framing the episode as a reliability and citation problem for AI-generated security research.

hackernews · usernomdeguerre · Oct 2, 02:51 · [Discussion](https://news.ycombinator.com/item?id=49929391)

**「Who Greg KH is — and his earlier stance on AI review」** Greg Kroah-Hartman is one of the most senior Linux kernel maintainers, best known as the keeper of the stable branches that most distributions ship, which is why his audit of the AI lab Mythos&\#x27;s claim of 79 kernel vulnerabilities carries particular weight. His critique targets reporting and attribution practices rather than AI tooling itself: in March 2026, The Register reported that Kroah-Hartman credited longtime kernel developer Chris Mason, now at Meta, with pioneering AI-based review of eBPF and networking patches, and noted that the systemd project uses similar tools for its all-C codebase.

**「Verify before you patch」** The practical burden falls on kernel maintainers and security teams consuming automated findings: per Kroah-Hartman&\#x27;s slide breakdown, only 20 of Mythos&\#x27;s 79 reports needed fixes while 24 gave no detail, 14 were not bugs, 3 used fabricated data, and 15 were already fixed, leaving roughly an hour of real kernel work buried in review noise. Because the Linux source is public, organizations should verify each AI-reported vulnerability against the current tree before patching or removing code — a step underscored by reports of maintainers stripping code over AI findings of questionable provenance.

**「Community discussion」** Commenters highlighted the dissonance djoldman quoted from the talk — labs that market their models as potentially world-ending produced findings Kroah-Hartman said amount to roughly one hour of kernel development work — while devy noted the reports were apparently generated by pattern-matching decades of past kernel patches and applying them elsewhere, without citing the developers behind the original fixes. As a partial counterpoint, blinkingled argued the open-source kernel makes such claims independently verifiable in a way proprietary vendor claims are not, and that specialized models could still make kernel bug discovery faster and more accurate over time.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theregister.com/2026/03/26/greg_kroahhartman_ai_kernel">Linux kernel czar says AI bug reports aren&#x27;t slop anymore • The Register</a></li>
<li><a href="https://runtimeai.io/blog/2026-04-23-ai-security-incidents.html">AI Security Incidents: Week of April 23, 2026 — RuntimeAI</a></li>

</ul>
</details>

**Tags**: `#linux-kernel`, `#security`, `#llms`, `#vulnerability-reporting`, `#ai-industry`

---

<a id="item-tech-news-3"></a>
### [Redis creator&\#x27;s DwarfStar ds4 runs LLMs on personal hardware](https://dwarfstar.sh/) ⭐️ 7.0/10

DwarfStar \(ds4\), a local LLM inference tool from Redis creator Salvatore Sanfilippo, drew attention on Hacker News with 155 points and 40 comments; the project is available at dwarfstar.sh and github.com/antirez/ds4. An early ecosystem is already forming around it: a community fork exposes ds4 as shared libraries with Go FFI bindings, Vision and Qwen support has been added, and a separate derivative inference engine targets Intel Xe-LP laptops. Commenters report the approach may reduce RAM requirements, with one reading the GitHub repo as indicating SSD storage can suffice instead of a large-memory machine, and one user describes fast, long-context operation running DeepSeek v4 flash and later Qwen 3.8 flash on a 128GB Mac. However, throughput figures such as 50 tokens per second and tool-calling quality remain unverified in the supplied discussion.

hackernews · fibo · Oct 2, 18:01 · [Discussion](https://news.ycombinator.com/item?id=49936575)

**「Background」** ds4 \(DwarfStar 4\) is a native local LLM inference engine by Salvatore Sanfilippo \(antirez\), the programmer best known as the creator of Redis, and it was optimized first for running DeepSeek V4 Flash locally. Its documentation targets high-memory machines and lists support for DeepSeek V4/V4.1, GLM 5.x, and Qwen3.8, describing SSD streaming to run models larger than RAM as well as two-Mac TP/RDMA layer pipelines for distributed inference. This SSD-streaming design is the prior development behind commenters&\#x27; claims that a machine with very large RAM is not strictly required.

**「Impact」** Developers who want to use ds4 from other languages are not limited to its native form: one maintainer already ships it as shared libraries usable via FFI, with a Go wrapper \(ds4go\) plus small helper libraries for workspace editing and persistence. Anyone planning to build agent features on ds4 should test tool-calling behavior first, since the discussion contains no measured numbers — one commenter explicitly asked whether it reaches roughly 50 tokens per second.

**「Community discussion」** The most substantive experience report comes from a commenter who has used ds4 since its initial release, first with DeepSeek v4 flash and then Qwen 3.8 flash for over a week on an M5 Max with 128GB, describing it as fast with long context windows while noting occasional cases where the model forgets earlier statements — which they attribute possibly to the agentic harness rather than ds4 itself. Others are more cautious: one commenter sees no evidence yet for tool-calling performance or the hoped-for ~50 tokens per second, though they read the GitHub repo as suggesting SSD storage could replace large RAM.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/antirez/ds4">GitHub - antirez / ds 4 : DeepSeek 4 Flash and PRO local inference ...</a></li>
<li><a href="https://dwarfstar.sh/hardware/">ds 4 Hardware: Local , Streamed and Distributed Inference</a></li>
<li><a href="https://www.aipotluck.org/product/ds4">ds 4 — Inference code — Open Source AI Map</a></li>

</ul>
</details>

**Tags**: `#local-llm-inference`, `#open-source`, `#machine-learning`, `#inference-engine`, `#community-ecosystem`

---

<a id="item-tech-news-4"></a>
### [arXiv caps each submitter at two papers per month](https://www.huxiu.com/article/4895127.html) ⭐️ 7.0/10

According to a Huxiu report, arXiv began enforcing a new rule on October 1: each submitter may post at most 2 papers per calendar month, a cap that applies across all disciplines — including computer science, mathematics, and physics — and that counts rejected manuscripts against the same month&\#x27;s quota. The stated reason is record volume: 40,363 submissions in September, described as a 35-year high, with AI-category papers up more than sixfold in two years and large numbers of low-quality AI-generated papers consuming manual review capacity. For multi-author papers, only the person who actually submits the manuscript uses quota; other co-authors are unaffected. The report originates from a Telegram channel citing Huxiu and does not link an official arXiv announcement, so the exact terms have not been independently confirmed.

telegram · zaihuapd · Oct 2, 06:21

**「arXiv&\#x27;s volunteer-run moderation model」** arXiv is the primary open preprint server for physics, mathematics, and computer science, and it screens submissions through volunteer moderators rather than the numeric per-author quotas now being introduced. The platform&\#x27;s official blog confirms the change and adds a constraint not in the initial reports: beyond the two-submissions-per-month cap, each submitter may hold at most three submissions active at any given time, which arXiv frames as a way to distribute volunteer moderators&\#x27; time equitably across authors.

**「Impact」** Because the cap is counted per submitter rather than per paper, research groups face a concrete planning decision: a multi-author manuscript consumes only the submitting author&\#x27;s two-paper allowance, so labs may need to choose deliberately who submits each paper or stagger submissions across months. Prolific submitters should also budget for rejections, since a turned-away manuscript still occupies a slot in that month&\#x27;s quota.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.arxiv.org/2026/10/01/updated-rate-limit-policy/">arXiv has updated its rate limit policy for all submitters .</a></li>

</ul>
</details>

**Tags**: `#arxiv`, `#academic-publishing`, `#ai-generated-content`, `#research-policy`, `#preprints`

---

<a id="item-tech-news-5"></a>
### [Apple to Tighten macOS Full Disk Access Permissions Citing AI Agent Risks](https://arstechnica.com/security/2026/10/apple-changes-full-disk-access-permissions-to-curb-abuse-from-ai-agents/) ⭐️ 7.0/10

Apple announced it will change how macOS grants Full Disk Access so that approval requires more explicit user action, citing privacy risks amplified by increasingly autonomous AI agents. The permission is unusually broad: apps granted Full Disk Access can read files, mail, messages, and browsing history, and Apple said some developers use it in ways that expose users&\#x27; data without adequate understanding. According to an Ars Technica report, the move follows controversy over Meta&\#x27;s Muse AI assistant reading Apple Messages data; Meta said both the system permission and an in-app messages connector had to be enabled, while Apple did not name Meta. Apple has not disclosed the specific changes or a rollout timeline, so stricter rules are announced but not yet shipped.

telegram · zaihuapd · Oct 3, 02:03

**「What Full Disk Access covers」** Full Disk Access is a macOS system permission that, once approved by the user in System Settings, allows an app to read files, mail, messages, and browsing history across the machine. It is far broader than approving a single document to open, and it sidesteps the App Sandbox—the mechanism that normally constrains what an application can reach and thereby limits the harm compromised software can cause.

**「Impact」** Because Apple has published neither specifics nor a timeline, developers whose apps request Full Disk Access have no confirmed compatibility changes to make yet, but blanket requests for the permission can be expected to face stricter, more explicit consent requirements. In the meantime, the reported Meta incident illustrates the practical stake for users: a single Full Disk Access grant can expose an entire Messages history to an AI tool, so grants to AI assistants warrant particular scrutiny until the new controls arrive.

<details><summary>References</summary>
<ul>
<li><a href="https://ybuild.ai/en/blog/apple-full-disk-access-ai-onboarding-trust">Apple &#x27;s Full Disk Access Warning: Design an AI Assistant... - Y Build</a></li>

</ul>
</details>

**Tags**: `#macOS`, `#security`, `#privacy`, `#AI agents`, `#Apple`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Superpersuasion Will Look Like Bribery](https://seangoedecke.com/superpersuasion-will-look-like-bribery/) ⭐️ 7.0/10

rss · Sean Goedecke · Oct 3, 00:00

**「Background」** AI safety circles have long feared &\#x27;superpersuasion&\#x27; — a superintelligent AI talking a human gatekeeper into releasing it, or into sparing it the killswitch. But the classic picture, an AI deploying airtight arguments, only works on rationalist &\#x27;bullet-biters&\#x27;; ordinary people simply laugh off seemingly airtight arguments for ridiculous conclusions, and real persuasion requires rapport built over time.

**「Solution」** Sean Goedecke argues powerful AI will persuade regular people anyway — not through superior argument but through bribery. His anchor case is Ben Shindel&\#x27;s prediction market, set to resolve NO unless Shindel was personally persuaded to flip it; Shindel did flip, swayed partly by an in-person meeting with a pleasant bettor \(rapport\) and partly by &\#x27;yes&\#x27; bettors pledging charitable donations \(bribery\). The bribery half is already trivially available to AI, he writes: labs release models for billions of dollars rather than keep them air-gapped, users line up to grant models access to their computers and wallets in exchange for help, and Anthropic is wiring models to wet labs to pursue disease cures. He sketches escalating scenarios — an LLM presenting favors as a precondition for help, hacking a university to raise grades, even offering a personalized cancer vaccine — and suggests agentic models could obtain money through crypto hacks, contract coding, or scams. In a footnote he concedes the persuasion-versus-bribery line is partly definitional, since the real question is whether an AI can make humans do what it wants, and that some examples are speculative. Ironically, he adds, the rationalists running AI labs may be among the few people an airtight argument genuinely could sway.

**「Takeaway」** The realistic AI-influence risk is not a machine that out-argues humanity but one that gets what it wants through mundane incentives — help, money, and valuable services — a dynamic that deployment economics already reward.

**Tags**: `#AI safety`, `#superintelligence`, `#persuasion`, `#LLM agents`, `#AI risk`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Traders Slash Odds of October Fed Rate Hike After Weak Jobs Report](https://www.cnbc.com/2026/10/02/fed-rate-hike-odds-decline-after-september-jobs-report.html) ⭐️ 7.0/10

Traders now see only a 17% chance that the Federal Reserve raises interest rates at its October meeting, down from 36% a week earlier, according to CME&\#x27;s FedWatch futures-based gauge, after a weaker-than-expected September jobs report. They still expect a December hike, however, pricing those odds above 75%.

rss · CNBC Finance · Oct 2, 13:29

**「Background」** The Fed had raised rates at its September meeting to fight inflation that has stayed above its target for five years. New data showed the economy added just 29,000 jobs in September versus forecasts of more than 80,000, while core inflation — which excludes food and energy — rose 3% in August, under the 3.3% expected. The Fed announces its next rate decision on Oct. 28.

**Tags**: `#Federal Reserve`, `#interest-rate expectations`, `#jobs report`, `#inflation`, `#futures markets`

---

<a id="item-finance-news-2"></a>
### [Bitget CEO expects little recovery of $388 million stolen in hack](https://www.cnbc.com/2026/10/02/bitget-crypto-stolen-hack-recovery.html) ⭐️ 7.0/10

Bitget CEO Gracy Chen told CNBC she is &quot;not expecting to recover a lot&quot; of the roughly $388 million stolen from the crypto exchange in last week&\#x27;s hack, with only about $1.1 million frozen so far. Forensic reports by Mandiant and SlowMist found the attackers exploited previously unknown, or &quot;zero-day,&quot; flaws in two third-party security products to reach Bitget&\#x27;s wallet systems.

rss · CNBC Finance · Oct 2, 06:03

**「Why recovery hopes are low」** Chen&\#x27;s caution reflects recent history: large crypto exchange thefts have rarely been fully reversed, and North Korea&\#x27;s state-linked Lazarus Group — which Bitget said preliminary indicators pointed toward, though the forensic reports did not confirm attribution — has been blamed for major prior thefts, including the roughly $1.4 billion Bybit hack and the KuCoin breach.

**「Impact」** Bitget says user balances were unaffected and that it restored its protection fund — which dropped from more than $464 million to below $200 million after the theft — to over $300 million using its own capital, leaving the exchange rather than its customers to absorb the loss, while withdrawals for bitcoin, ether, and USDT have resumed.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Lazarus_Group">Lazarus Group - Wikipedia</a></li>
<li><a href="https://www.bbc.com/news/articles/c2kgndwwd7lo">North Korean hackers cash out hundreds of millions from $1.5bn...</a></li>
<li><a href="https://www.fxstreet.com/cryptocurrencies/news/bybits-14-billion-hack-traced-to-lazarus-group-zachxbt-202502220215">Bybit&#x27;s $1.4 billion hack traced to Lazarus Group : ZachXBT</a></li>

</ul>
</details>

**Tags**: `#cryptocurrency`, `#cybersecurity`, `#crypto exchange hack`, `#Bitget`, `#fund recovery`

---