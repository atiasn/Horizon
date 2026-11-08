---
layout: default
title: "Horizon Summary: 2026-11-08 (EN)"
date: 2026-11-08
lang: en
---

> From 39 items, 12 important content pieces were selected

---

**Technology News**
1. [SemiAnalysis Tours 800MW Wind-Powered AI Data Center Campus in Inner Mongolia](#item-tech-news-1) ⭐️ 8.0/10
2. [GitHub&\#x27;s Rubicon Git storage architecture enters private preview, targeting 7,200 pushes per second](#item-tech-news-2) ⭐️ 8.0/10
3. [Microsoft Research disbands AI Frontiers group; researcher John Langford departs](#item-tech-news-3) ⭐️ 7.0/10
4. [Need for Speed Underground 2 runs in the browser via x86-to-WebAssembly recompilation](#item-tech-news-4) ⭐️ 7.0/10
5. [MaxxBench stress-tests LLM benchmark scores by varying task specifications](#item-tech-news-5) ⭐️ 7.0/10
6. [Coldframe: a Python honeypot that impersonates supermarket fridge controllers](#item-tech-news-6) ⭐️ 7.0/10
7. [Write-up claims Macs since 2022 ship undocumented daemons building personal knowledge graphs](#item-tech-news-7) ⭐️ 7.0/10
8. [Discord&\#x27;s reported native Windows 11 client claims 70% less RAM than Electron](#item-tech-news-8) ⭐️ 7.0/10
9. [Asahi Linux 7.3: same-day Fedora Asahi Remix release and license-hijack warning](#item-tech-news-9) ⭐️ 7.0/10
10. [Law firm decoded.legal publishes updated account of running entirely on free software](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Berkshire Hathaway more than doubles buybacks to $9.6 billion as quarterly profits fall](#item-finance-news-1) ⭐️ 7.0/10
2. [软银与 ABB 拟分拆中国业务挽救机器人交易](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [SemiAnalysis Tours 800MW Wind-Powered AI Data Center Campus in Inner Mongolia](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis published a first-hand account of a visit to an 800MW wind-powered AI data center campus in Inner Mongolia, which the report&\#x27;s title frames as &quot;China&\#x27;s Stargate.&quot; A 120MW build at the site was completed within a year, with the 800MW figure representing the campus&\#x27;s overall scale. The technically notable details are a 5MW pilot using solid-state transformers \(SSTs\) for native 800V DC power distribution and a cooling design that operates without central chillers. The piece is on-the-ground reporting on an operating facility rather than a vendor announcement, offering rare direct documentation of China&\#x27;s AI infrastructure buildout.

rss · Semianalysis · Nov 7, 19:01

**「Background」** 800-volt DC distribution built on solid-state transformers \(SSTs\) is an emerging power architecture for AI data centers: China has already deployed what was reported as the world&\#x27;s first commercial integrated 800V DC system, combining solid-state transformers, battery storage, and AI controls to deliver stable power to AI servers, and the approach is expected to boost performance while reducing material consumption, grey-space complexity, and operational losses. The report&\#x27;s &\#x27;Stargate&\#x27; nickname alludes to the identically named US AI data center program, framing the Inner Mongolia campus as China&\#x27;s counterpart mega-scale build. A &\#x27;chiller-free&\#x27; cooling design rejects heat without the central chilled-water plants that conventional data center cooling relies on, which are typically among a facility&\#x27;s largest non-IT power consumers.

**「Relevance for data center engineering」** For facility and power-delivery engineers, the report documents a working reference for two designs that remain rare in practice: a 5MW SST-native 800V DC distribution pilot and a large AI campus cooled without central chillers. The 120MW-built-within-a-year construction pace also serves as a concrete benchmark for organizations tracking how quickly wind-powered AI capacity is being added in Inner Mongolia.

<details><summary>References</summary>
<ul>
<li><a href="https://interestingengineering.com/energy/worlds-first-800v-dc-power-system">China debuts world&#x27;s first 800 V DC power system for smart data centers</a></li>
<li><a href="https://www.linkedin.com/posts/simon-kuo-b6340512_ai-datacenter-energy-dilemma-race-for-ai-activity-7455996705231097856-ZKZw">Transformer Shortage to Follow AI Compute Boom | LinkedIn</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#data centers`, `#power delivery`, `#solid-state transformers`, `#cooling`

---

<a id="item-tech-news-2"></a>
### [GitHub&\#x27;s Rubicon Git storage architecture enters private preview, targeting 7,200 pushes per second](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub has introduced a new Git storage architecture, codenamed Rubicon, now available in limited private preview and designed for repositories worked on by thousands of AI agents concurrently. The design stores Git objects in Azure Blob Storage, manages reference state through a component called Ref-CAS, uses virtual replicas to handle reads and writes, and compacts packfiles on background nodes. In internal tests reported by GitHub, the system sustained roughly 7,200 pushes per second with 5,000 agents collaborating on a single repository while keeping read latency low; these figures are vendor-reported and not independently verified. GitHub says it plans to gradually expand availability beyond the current preview.

telegram · zaihuapd · Nov 7, 14:12

**「GitHub&\#x27;s earlier Azure migration」** GitHub&\#x27;s migration of repository storage to Azure was already public before this announcement: an October 21, 2026 engineering post reported that copies of 99.99999% of the platform&\#x27;s repositories had been moved to Azure, with per-reference quorums planned to bring over the remainder and object storage letting reads scale independently. Rubicon builds on that foundation for write-heavy workloads, splitting Git&\#x27;s state so that mutable reference updates run through Ref-CAS, a new replicated log service, while immutable objects stay in Azure Blob Storage — a separation aimed at letting thousands of agents push to a single repository at once.

**「Impact」** Teams running large fleets of concurrent automation—AI coding agents or high-frequency CI—against a single repository are the direct beneficiaries, since the architecture is designed to absorb thousands of simultaneous writers rather than a handful of human committers. The practical step for interested organizations is narrow for now: Rubicon is only in limited private preview with a gradual rollout planned, and its headline throughput figures come from GitHub&\#x27;s internal tests rather than independent benchmarks, so teams should treat them as vendor claims until they can evaluate the system directly.

<details><summary>References</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/">Inside GitHub’s new Git storage architecture - The GitHub Blog</a></li>
<li><a href="https://github.blog/engineering/architecture-optimization/the-bridge-to-agent-scale-git-infrastructure/">The bridge to agent-scale Git infrastructure - The GitHub Blog</a></li>
<li><a href="https://daily.dev/posts/inside-github-s-new-git-storage-architecture-ttbgyxfiu">Inside GitHub’s new Git storage architecture - daily.dev</a></li>

</ul>
</details>

**Tags**: `#github`, `#git`, `#storage-architecture`, `#ai-agents`, `#infrastructure`

---

<a id="item-tech-news-3"></a>
### [Microsoft Research disbands AI Frontiers group; researcher John Langford departs](https://hunch.net/?p=13764006) ⭐️ 7.0/10

Microsoft Research has dissolved AI Frontiers, its internal group dedicated to fundamental advances in AI, and longtime researcher John Langford announced his exit in a firsthand blog post, with outside coverage corroborating the closure. The change affects the group&\#x27;s researchers and Microsoft&\#x27;s exploratory AI agenda rather than the field at large; one commenter noted the headline could mislead readers into thinking &\#x27;AI frontiers&\#x27; broadly had ended. Discussion of the post also surfaced internal strain: a commenter quoted Langford&\#x27;s line that the basic MSR bargain of &\#x27;do good work and good things happen&\#x27; has broken down, and another noted the post itself described transformer research the group had been pursuing.

hackernews · srean · Nov 7, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50406563)

**「What AI Frontiers was」** AI Frontiers was a research group within Microsoft Research focused on fundamental advances in AI rather than near-term product work, and it was reportedly disbanded or reorganized into the broader Microsoft Research organization. The firsthand account of its end comes from John Langford, a partner researcher manager at Microsoft Research New York who announced his departure from Microsoft alongside the group&\#x27;s dissolution. Langford is a longtime machine learning and learning theory researcher who publishes the Machine Learning \(Theory\) blog, where he posted the announcement.

**「Impact」** The closure removes an institutional home for exploratory AI research at Microsoft Research and cost the lab a prominent researcher in Langford. For researchers working on non-mainstream or high-risk AI directions, it shrinks industrial-lab options; commenters report the same narrowing toward transformer scaling at other large companies, though that broader pattern is anecdotal rather than established by this report.

**「Community discussion」** Commenters split on the cause: several read the closure as confirmation that large companies now discourage exploratory, non-transformer AI research in favor of scaling — one lamenting that &\#x27;billions are invested in almost one idea&\#x27; — while another argued Langford&\#x27;s post itself mentioned transformer work and blamed office politics, infighting, and poor research-to-product transfer instead. A separate commenter quoted the post&\#x27;s claim that MSR&\#x27;s long-standing &\#x27;do good work and good things happen&\#x27; deal has been &\#x27;broken and rebroken with current leadership,&\#x27; calling the shift culture-destroying.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/John_Langford_%28computer_scientist%29">John Langford (computer scientist) - Wikipedia</a></li>
<li><a href="https://businessexaminer.ca/victoria-articles/item/microsoft-researcher-john-langford-exits-as-ai-frontiers-group-is-declared/">Microsoft Researcher John Langford Exits as AI Frontiers Group Is...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50406563">The end of Microsoft Research &#x27;s AI Frontiers group | Hacker News</a></li>

</ul>
</details>

**Tags**: `#Microsoft Research`, `#AI research`, `#machine learning`, `#tech industry`, `#research labs`

---

<a id="item-tech-news-4"></a>
### [Need for Speed Underground 2 runs in the browser via x86-to-WebAssembly recompilation](https://nfsu2.xyz/) ⭐️ 7.0/10

A fan project at nfsu2.xyz runs Need for Speed Underground 2 directly in the browser by translating the game&\#x27;s x86 code to C ahead of time and compiling it to WebAssembly, an approach the project&\#x27;s GitHub README \(th0mk/nfsu2-web\) describes and commenters quote directly. The port adds online multiplayer and uses WebGPU for rendering, and Hacker News commenters report playing races with friends and running the game on a phone. Compatibility is not universal: a Linux user says Chromium must be launched with unsafe WebGPU features enabled for it to work. The site distributes the copyrighted game without a license, and commenters expect a takedown now that the post has drawn heavy attention \(832 points and 230 comments on Hacker News\).

hackernews · fluxusars · Nov 7, 09:36 · [Discussion](https://news.ycombinator.com/item?id=50403052)

**「Static recompilation, not runtime emulation」** Need for Speed Underground 2 is a 2004 commercial racing title that is no longer sold, which is why commenters treat it as abandonware. The browser port, published as the th0mk/nfsu2-web project and built on the earlier NFSU2Recomp work, does not emulate a PC at runtime: it translates the game&\#x27;s x86 code to C ahead of time and compiles the result to WebAssembly, maps the game&\#x27;s Direct3D 9 rendering onto WebGPU and its sound onto Web Audio, and asks players to supply their own copy of the game. This ahead-of-time recompilation approach, rather than runtime emulation, is what allows the complete original game to run in Chrome and Firefox.

**「Practical impact」** For players, the concrete effect is that a game commenters describe as mostly unplayable at retail on modern PCs can now be run directly in Chrome and Firefox through the free Underground 2 Revived port \(released in late October\), with online free-roam multiplayer working again. One compatibility caveat: Linux users on Chromium need to enable unsafe WebGPU features via a command-line flag before the game will run. Availability is also precarious — because the project redistributes the copyrighted game without a license and solicits donations, which one commenter called highly dubious, commenters expect a takedown as its popularity grows, so the site should not be treated as a permanent way to play.

**「Community reaction」** Commenters report the port works well in practice — one played races with friends over several days and another ran it on a phone, noting the retail version is largely unplayable on modern PCs — while warning that the site hosts the game without permission and likely faces a takedown. One commenter argued it is dubious to accept or solicit donations for copyrighted content, and a Linux user shared the Chromium WebGPU flag needed to run it.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/th0mk/nfsu2-web">GitHub - th0mk/nfsu2-web</a></li>
<li><a href="https://github.com/th0mk/nfsu2-web/blob/main/README.md">nfsu2-web/README.md at main · th0mk/nfsu2-web · GitHub</a></li>
<li><a href="https://www.techpowerup.com/354422/need-for-speed-underground-2-gets-a-free-browser-port-with-multiplayer-free-roam">Need for Speed Underground 2 Gets a Free Browser Port With...</a></li>

</ul>
</details>

**Tags**: `#webassembly`, `#reverse-engineering`, `#static-recompilation`, `#game-preservation`, `#webgpu`

---

<a id="item-tech-news-5"></a>
### [MaxxBench stress-tests LLM benchmark scores by varying task specifications](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 7.0/10

MaxxBench published a stress-testing method that re-runs LLM benchmarks with varied task specifications to check whether reported scores are robust or depend on the exact test setup. Applied to DeepSWE, the approach surfaced bugs and raised concerns that its scores may not generalize, a result relevant to practitioners who rely on benchmark numbers to compare models. The write-up drew 209 points and 64 comments on Hacker News.

hackernews · antiuniverse · Nov 7, 17:19 · [Discussion](https://news.ycombinator.com/item?id=50406222)

**「The benchmark under test」** DeepSWE is a long-horizon software engineering benchmark built to separate today&\#x27;s leading coding agents: its tasks are written from scratch across 91 repositories and 5 languages, with hand-written verifiers that test software behavior rather than implementation details. Its creators present it as contamination-free, meaning no tasks are adapted from existing commits or pull requests — and it is the benchmark whose reported scores MaxxBench stress-tests.

**「Impact for agent selection」** Teams that select coding agents using DeepSWE-based leaderboards — the benchmark appears on public indexes such as Artificial Analysis&\#x27;s coding-agent leaderboard as DeepSWE v1.1 — may be acting on scores whose robustness MaxxBench&\#x27;s spec-variation testing calls into question: the stress test surfaced bugs in DeepSWE and generalization gaps despite the benchmark&\#x27;s design goal of being contamination-free, with tasks written from scratch rather than adapted from existing commits or PRs. The practical step for practitioners is to check that a reported score holds up when task specifications are varied rather than trusting a single leaderboard number; in the discussion, one commenter observed that smaller models&\#x27; scores collapse the most under such variation, and another commenter&\#x27;s takeaway from the write-up was to avoid &quot;max mode&quot;.

**「Hacker News discussion」** In the thread, kqr endorsed varying the task specification as a sensible default for testing whether a benchmark score generalizes, while peri-cl observed that the steepest collapses in the published results came from smaller models — the &\#x27;-flash&\#x27; variants and OpenAI&\#x27;s Luna — cautioning that the GLM pair breaks the pattern because GLM-5.3 and GLM-5.3-flash are distinct lineages despite their names. rao-v offered a competing explanation, arguing the drops likely reflect labs building RL training environments that too closely mirror benchmark tasks rather than direct training on the benchmarks, and suspected smaller models overfit most to these simplified setups.

<details><summary>References</summary>
<ul>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>
<li><a href="https://deepswe.lol/">DeepSWE — Long-Horizon Software Engineering Benchmark</a></li>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>
<li><a href="https://artificialanalysis.ai/agents/coding-agents">AI Coding Agent Benchmarks &amp; Leaderboard | Artificial Analysis</a></li>

</ul>
</details>

**Tags**: `#llm-benchmarks`, `#evaluation-methodology`, `#ai`, `#benchmark-reliability`, `#machine-learning`

---

<a id="item-tech-news-6"></a>
### [Coldframe: a Python honeypot that impersonates supermarket fridge controllers](https://github.com/hedgerow-dev/coldframe) ⭐️ 7.0/10

Coldframe is a new open-source honeypot, built as a single Python file using only the standard library, that impersonates Danfoss AK-SM 800A and Dixell XWEB supermarket refrigeration controllers; author hedgerow-dev released it on GitHub to observe what attackers try against industrial cold-chain systems after recent incidents involving industrial fridge installations. The author tuned both personas against Shodan records of real devices — matching header order, page titles, certificate fields, and TLS versions, with the Danfoss persona sending nginx headers in the same order as a real AK-SM 800A and the Dixell persona omitting the Server header and padding its pages to exactly 8,202 bytes — and reports that Shodan classifies both as genuine hardware rather than honeypots. The shipped code detects CVE-2025-41450, the Danfoss &quot;code of the day&quot; login bypass, records whether a submitted code is valid for the current day, and tags attempts against three other Danfoss CVEs and the XWEB vulnerabilities, while default logins open a fake store dashboard with defrost controls so second-stage actions are visible; it builds on eppser/danfoss-ak-sm-decoy and published research from Synacktiv, Claroty, and Ironhackers. Results so far are preliminary: after one day online, two instances had recorded only generic scanners and Shodan&\#x27;s refrigerator.census.shodan.io crawler, with no genuine attacker activity observed yet.

hackernews · hedgerow-dev · Nov 7, 17:27 · [Discussion](https://news.ycombinator.com/item?id=50406292)

**「Background」** Coldframe was built in response to an October 2026 incident in which an unknown party accessed refrigeration controllers at up to 700 French supermarkets and set them to defrost mode overnight, causing refrigerators to overheat. The underlying flaws had been demonstrated in August by Claroty&\#x27;s Team82, which showed that vulnerabilities in the Danfoss AK-SM 800A allowed a login bypass and takeover of refrigeration management software, and Danfoss shipped firmware fixes for them. Around the time of the incident, BleepingComputer counted 2,752 Danfoss systems exposed online, 1,590 of them in France.

**「Patch pressure on Danfoss controllers, plus a new detection option」** Operators of Danfoss AK-SM 8xxA controllers have a concrete action to take: Danfoss&\#x27;s advisory states that CVE-2025-41450, an improper-authentication bypass with a base score of 8.2 \(HIGH\), is remediated by installing patch 4.2, and a public Python proof of concept for the predictable code-of-the-day mechanism already exists. For defenders and researchers, Coldframe offers a low-friction way to observe such attempts, since it runs as a single standard-library Python file and records CVE-2025-41450 probes along with whether the submitted code was correct for the day; however, the author&\#x27;s two instances saw only generic scanners and Shodan&\#x27;s crawler during their first day online, so current deployments provide detection capability rather than evidence of active targeting.

**「Community discussion」** Commenter supriyo-biswas questioned using Shodan records as the fidelity benchmark, reporting that when they replicated Wi-Fi cameras most internet-exposed units turned out to be honeypots or already-compromised devices, and suggested probing a real vulnerable unit instead. The author argued in a separate comment that supermarkets have no security teams, so vendors and installers should ship protections such as VPNs and strong passwords by default, while commenter xrd asked whether the recent fridge incidents were a confirmed large-scale hack or possibly a coincidental mass software update — a question the source material does not resolve.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_French_supermarket_refrigerator_hack">2026 French supermarket refrigerator hack - Wikipedia</a></li>
<li><a href="https://www.secureworld.io/industry-news/danfoss-fridge-attack">Danfoss Fridge Attack Wasn&#x27;t a Visibility Failure</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-danfoss-controller-french-retail-sabotage/">Danfoss Controller Hijacking: Physical Sabotage of French ...</a></li>
<li><a href="https://www.danfoss.com/en/service-and-support/coordinated-vulnerability-disclosure/danfoss-security-advisories/dsa-2025-03-01/">DSA-2025-03-01 | Danfoss</a></li>
<li><a href="https://github.com/Nero22k/CVE-2025-41450_poc">GitHub - Nero22k/CVE-2025-41450_poc: CVE-2025-41450</a></li>

</ul>
</details>

**Tags**: `#security`, `#honeypot`, `#ics-security`, `#industrial-control-systems`, `#open-source`

---

<a id="item-tech-news-7"></a>
### [Write-up claims Macs since 2022 ship undocumented daemons building personal knowledge graphs](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

A write-up published on 8rank.ai and posted to Hacker News on November 7, 2026 alleges that every Mac shipped since 2022 runs a pair of undocumented daemons that silently build a personal knowledge graph of the user: who they are, who they know, how those people relate to each other, and how, where, and when they communicate and move. The claim is the blog author&\#x27;s own analysis — the author appeared in the thread as infwhispers — and the supplied material contains no independent verification or confirmation from Apple. The post drew 612 points and 349 comments, with several commenters noting that related behavior is already familiar, such as the Photos app identifying and naming the faces of people and pets.

hackernews · infwhispers · Nov 7, 09:46 · [Discussion](https://news.ycombinator.com/item?id=50403097)

**「Background」** Apple already runs machine learning over personal data directly on its devices, and Photos&\#x27; face recognition — which groups and names people, and even pets, in a user&\#x27;s library — is a broadly known precedent for the people-classification behavior the write-up describes. The claimed additional layer is a personal knowledge graph: a structured, machine-readable store of entities and relationships \(who a user knows, how they communicate, where they go and when\) that software can query rather than re-derive each time. In the GraphRAG pattern, such a graph is coupled with retrieval-augmented generation so AI assistants can ground answers in personal context, which is the use case the write-up&\#x27;s Apple Intelligence framing points toward.

**「What it would mean for Mac users」** If the description is accurate, relationship and activity profiling would occur outside any feature a user explicitly enables, leaving no documented disclosure or opt-in to consult. Because the claim currently rests on one author&\#x27;s analysis without independent verification or an Apple response, the supported action for concerned users and administrators is to verify the daemons&\#x27; behavior on their own machines before changing tooling or policy.

**「HN debate: function versus consent」** Commenter aetherspawn offered a functional reading — that the graph is the context letting local models like Siri resolve who &\#x27;James&\#x27; or &\#x27;my boss&\#x27; is — while thomascountz objected on social grounds that conversations presume not everything will be remembered, and consumer451 invoked Steve Jobs&\#x27; 2010 statement that privacy means people know what they are signing up for. Others, including elgertam, said the claim was unsurprising given Photos&\#x27; existing face and pet recognition, and the author invited questions and linked follow-up research in the thread.

<details><summary>References</summary>
<ul>
<li><a href="https://8rank.ai/game/apple-intelligence-personal-knowledge-graph">Anatomy of Apple &#x27;s Personal Knowledge Graph — Eighth Rank</a></li>
<li><a href="https://www.youtube.com/watch?v=knDDGYHnnSI">GraphRAG: The Marriage of Knowledge Graphs and RAG... - YouTube</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#apple`, `#macos`, `#machine-learning`, `#on-device-ai`

---

<a id="item-tech-news-8"></a>
### [Discord&\#x27;s reported native Windows 11 client claims 70% less RAM than Electron](https://www.windowslatest.com/2026/11/06/every-windows-11-app-should-kill-electron-and-discord-just-showed-why-no-starting-screen-and-70-less-ram-even-with-two-accounts-signed-in/) ⭐️ 7.0/10

A Windows Latest report says Discord has replaced its Electron-based Windows desktop app with a native Windows 11 client that the outlet claims cuts RAM use by roughly 70% and eliminates the startup splash screen, even with two accounts signed in. These performance figures are the report&\#x27;s claims, not independently measured results. If they hold up, the shift would move one of the most widely used Electron desktop apps to native code and sharpen the long-running trade-off between Electron&\#x27;s single-codebase convenience and native apps&\#x27; memory and startup performance.

hackernews · thunderbong · Nov 7, 11:11 · [Discussion](https://news.ycombinator.com/item?id=50403507)

**「Background」** Discord&\#x27;s current Windows client is built on Electron, a framework that bundles web code with the Chromium browser engine so a single codebase can ship across desktop platforms — the same approach behind apps like VS Code and a long-standing target of criticism over memory use. Days before this report, co-founder and CTO Stanislav Vishnevskiy confirmed on November 4, 2026 that Discord is rebuilding its desktop app in Rust with the GPUI interface framework, with an early Windows build shown using about 290MB of RAM; no release date has been announced, and the performance figures remain vendor claims that have not been independently tested.

**「Fewer resources, an accessibility caveat」** If Discord&\#x27;s claimed ~70% RAM reduction and no-startup-screen behavior hold up in the shipped client, users on memory-constrained machines gain the most, but the figures remain vendor claims relayed by a secondary outlet rather than independently measured results. The concrete compatibility risk for this migration pattern, raised in the discussion, is that Electron apps ship with working screen-reader and non-English IME support out of the box, while most Rust GUI toolkits as of a 2025 survey still lagged in both — so teams attempting similar rewrites should verify accessibility and input-method behavior before dropping Electron. Users who want native performance immediately already have unofficial options: the yapfast client&\#x27;s developer measured 0.22-second startup versus 8 seconds for the official app, and larperCord reports roughly 130 MB of RAM with a real account, though both are unofficial projects with self-reported numbers.

**「Community discussion」** Hacker News commenters largely pushed back on the article&\#x27;s framing: one argues it ignores Electron&\#x27;s core value of letting a small team ship one app across platforms with minimal extra effort, and another contends Discord is a poor exemplar anyway, saying the company moved Android to React Native and is now dropping it \(attributing this to Discord&\#x27;s CTO\) when Kotlin Multiplatform would have preserved code reuse with truly native interfaces. On the other side, one commenter calls multi-gigabyte memory use for mostly reading and writing messages hard to justify with current RAM prices, while another warns that Electron&\#x27;s out-of-the-box accessibility and non-English IME support — which a linked 2025 survey found better than most Rust GUI toolkits — could regress in a native rewrite.

<details><summary>References</summary>
<ul>
<li><a href="https://windowsforum.com/news/discord-phoenix-rust-and-gpui-replace-electron-on-windows-but-290mb-ram-claims-need-testing.450993/">Discord Phoenix: Rust and GPUI Replace Electron on Windows ...</a></li>
<li><a href="https://tech-insider.org/discord-electron-rust-gpui-rebuild-290mb-ram-2026/">Discord Ditches Electron: Rust Cuts RAM to 290MB [2026]</a></li>
<li><a href="https://www.windowscentral.com/microsoft/microsoft-teams/discord-is-ditching-electron-and-the-result-is-a-faster-app-that-uses-less-ram">Discord is ditching Electron, and the result is a faster app ...</a></li>
<li><a href="https://github.com/yapfast/yapfast">yapfast/yapfast: A Discord client without the web browser. Native ...</a></li>
<li><a href="https://rshacudevidro.github.io/larperCord/">larperCord: a native Discord client whose whole UI is one file</a></li>

</ul>
</details>

**Tags**: `#Electron`, `#Discord`, `#native-apps`, `#cross-platform-development`, `#performance`

---

<a id="item-tech-news-9"></a>
### [Asahi Linux 7.3: same-day Fedora Asahi Remix release and license-hijack warning](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux&\#x27;s 7.3 progress report states that Fedora Asahi Remix shipped on 3 November, the same day upstream Fedora 45 was released — the first time the remix has launched in lockstep with a new Fedora version. The same report discloses that the project &quot;was made aware of multiple attempts to exploit our permissive licensing to hijack our work,&quot; with the stated aim of replacing the project and aggressively monetizing Linux on Apple Silicon; it names no specific party. Both statements come from the project itself: the same-day release is presented as a completed milestone, while the licensing warning is a project disclosure without independent confirmation or identified actors.

hackernews · ackyshake · Nov 7, 05:20 · [Discussion](https://news.ycombinator.com/item?id=50401867)

**「What Asahi Linux is」** Asahi Linux is a community project started by Hector Martin that ports the Linux kernel and related software to Apple Silicon Macs by reverse-engineering Apple&\#x27;s SoCs, for which Apple publishes no official documentation. The project distributes this work under the permissive MIT license, which allows anyone to reuse, modify, and redistribute the code, including in commercial products.

**「Impact for Apple Silicon users」** Owners of Apple M3, M3 Pro, and M3 Max Macs can now install Fedora Asahi Remix 45 with out-of-the-box initial support, as these systems are now officially supported by Asahi Linux upstream, and existing users can expect Remix releases to arrive the same day as upstream Fedora instead of lagging behind. One practical caveat: a commenter weighing an install reports that USB-C external display support remains a blocking gap for laptop users who depend on external monitors, so anyone relying on that feature should verify current hardware support before switching.

**「Community discussion」** In the comments, one reader said USB-C external display support is the single blocker keeping them from installing Asahi on a MacBook Air, and questioned why support for newer CPUs is prioritized above it. Another commenter speculated that the hijack warning referred to Omarchy and expressed surprise the project used MIT licensing instead of GPL, while a separate self-promotional comment claimed an unaffiliated project, Gravity Linux, already has Vulkan 1.4, all of M4, most of M5, and suspend-to-RAM working — claims that are unverified.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Asahi_Linux">Asahi Linux - Wikipedia</a></li>
<li><a href="https://asahilinux.org/2026/11/progress-report-7-3/">Progress Report: Linux 7.3 - Asahi Linux</a></li>
<li><a href="https://fedoramagazine.org/announcing-fedora_asahi_remix_45_beta/">Announcing Fedora Linux Asahi Remix 45 Beta - Fedora Magazine</a></li>

</ul>
</details>

**Tags**: `#linux`, `#apple-silicon`, `#open-source`, `#drivers`, `#fedora`

---

<a id="item-tech-news-10"></a>
### [Law firm decoded.legal publishes updated account of running entirely on free software](https://decoded.legal/blog/2026/11/running-a-law-firm-on-free-software-2026-edition/) ⭐️ 7.0/10

The law firm behind the decoded.legal blog published a &\#x27;2026 edition&\#x27; of its first-hand account of running its entire practice on free software, updating an earlier write-up of an open-source stack in a legal industry where proprietary tools such as Microsoft Word and Outlook remain the default. The post, dated November 7, 2026, is an operational case study rather than a product announcement or independently measured benchmark, and the material available for this summary does not reproduce the full text, so the specific applications in the firm&\#x27;s stack are not enumerated here. It drew substantial Hacker News engagement \(239 points, 118 comments\), with discussion centered on open-source adoption, vendor lock-in, continuity risk, and AI tools in legal work.

hackernews · DeepLogin · Nov 7, 09:39 · [Discussion](https://news.ycombinator.com/item?id=50403066)

**「Prior editions in 2022 and 2024」** decoded.legal, the English law firm run by Neil Brown, has documented its Free software setup as a recurring series, beginning in 2022 and continuing with a September 2024 edition that noted much of the stack had not changed significantly since the first post. The 2026 article is the latest installment in that series, with its biggest change from the 2024 account being the replacement of Nextcloud with Syncthing and radicale.

**「What it means for small firms」** Small firms and solo practitioners who control their own stack are the readers who can act on this; commenters inside larger firms described being stuck with mandated, add-on-laden Word environments they cannot change. The discussion framed the real barriers to copying the approach as continuity and compatibility rather than tooling: one commenter asked what happens when another lawyer has to step into a bespoke setup, and another relayed a workshop claim, attributed to a longtime American open-source lawyer, that not using Word in a law firm &\#x27;amounts to malpractice.&\#x27; Firms attempting this path should therefore plan document interchange with the Word-centric legal ecosystem and keep their systems documented for handover. Firms weighing the proprietary alternative face a mirrored risk: a 2026 review of Harvey calls the vendor dependence created by its bespoke enterprise deployments a real strategic lock-in risk.

**「Community discussion」** Commenters disagreed over whether such a setup is professionally safe: one asked what happens if the firm&\#x27;s lawyer becomes unavailable and someone else must take over a bespoke IT stack, while another reported hearing a respected American open-source lawyer claim at a workshop that not using Microsoft Word &\#x27;amounts to malpractice&\#x27; — an attributed opinion, not an established standard. In a separate thread, a commenter argued that firms adopting the legal AI tool Harvey are handing a vendor the data to &\#x27;integrate vertically&\#x27; and come to dominate the profession, and that a shared, cookie-cutter AI solution gives no firm a competitive edge.

<details><summary>References</summary>
<ul>
<li><a href="https://news.lavx.hu/article/neil-brown-lays-out-decoded-legal-s-free-software-stack-in-2026-update">Neil Brown lays out decoded.legal&#x27;s Free software stack in ...</a></li>
<li><a href="https://decoded.legal/blog/2024/09/running-a-law-firm-on-free-software-2024-edition/">Running a law firm on Free software (2024 edition) | decoded ...</a></li>
<li><a href="https://www.lawxyai.com/articles/harvey-ai-review-2026-is-it-worth-288k-a-year-for-legal-teams">Harvey AI Review 2026: Features, Pricing &amp; Honest Verdict</a></li>

</ul>
</details>

**Tags**: `#open source`, `#free software`, `#legal tech`, `#vendor lock-in`, `#AI in law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Berkshire Hathaway more than doubles buybacks to $9.6 billion as quarterly profits fall](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

Berkshire Hathaway more than doubled its share buybacks to $9.6 billion in the third quarter of 2026, up from $4.5 billion in the second quarter, while operating earnings fell 5.8% year over year to $12.705 billion and overall earnings dropped 28% to $22.112 billion. Even with the heavier repurchases, the company&\#x27;s cash pile grew 3% during the quarter to $377.4 billion.

rss · CNBC Finance · Nov 7, 15:23

**「Background」** Greg Abel became Berkshire Hathaway&\#x27;s chief executive on January 1, 2026, succeeding Warren Buffett, who remains chairman of the board. This is the company&\#x27;s first full year under its new leader, making capital-allocation choices such as the pace of share buybacks a closely watched signal of his approach.

**「Why it matters」** The buyback surge returns cash directly to Berkshire shareholders who sell, and investors in the insurance industry get a cautionary data point from the 43% year-over-year drop in the conglomerate&\#x27;s underwriting profit.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Greg_Abel">Greg Abel - Wikipedia</a></li>
<li><a href="https://www.cbsnews.com/news/greg-abel-berkshire-hathaway-warren-buffett-successor/">Greg Abel takes over as CEO of Berkshire Hathaway. What to ...</a></li>
<li><a href="https://www.berkshirehathaway.com/news/may0525.pdf">BERKSHIRE HATHAWAY INC. NEWS RELEASE</a></li>

</ul>
</details>

**Tags**: `#Berkshire Hathaway`, `#share buybacks`, `#quarterly earnings`, `#insurance`, `#cash holdings`

---

<a id="item-finance-news-2"></a>
### [软银与 ABB 拟分拆中国业务挽救机器人交易](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

SoftBank and ABB are considering carving out ABB&\#x27;s China robotics operations into a separate entity to salvage their $5.4 billion deal after China&\#x27;s foreign investment security review blocked the acquisition.

telegram · zaihuapd · Nov 7, 11:24

**Tags**: `#M&amp;A`, `#robotics`, `#China regulatory review`, `#SoftBank`, `#ABB`

---