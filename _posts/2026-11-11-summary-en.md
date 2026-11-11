---
layout: default
title: "Horizon Summary: 2026-11-11 (EN)"
date: 2026-11-11
lang: en
---

> From 25 items, 11 important content pieces were selected

---

**Technology News**
1. [DeepMind&\#x27;s AlphaProof Code Brings AI-Written Formal Proofs to Real-World Software Verification](#item-tech-news-1) ⭐️ 8.0/10
2. [Google Chrome ships modern-web-guidance 1.0 to steer coding agents toward native web APIs](#item-tech-news-2) ⭐️ 8.0/10
3. [Chips and Cheese dissects AMD&\#x27;s Zen 6 core, vector, and memory changes](#item-tech-news-3) ⭐️ 8.0/10
4. [.NET 11 runtime moves async into the runtime, changes decimal conversion](#item-tech-news-4) ⭐️ 8.0/10
5. [Seven-month Glasswing update draws debate over AI-found vulnerability impact](#item-tech-news-5) ⭐️ 7.0/10
6. [Starlink Mini 2 draws remote-use praise and networking complaints](#item-tech-news-6) ⭐️ 7.0/10
7. [Synaptics patent claims halt open source DisplayLink driver work](#item-tech-news-7) ⭐️ 7.0/10
8. [llm-gemini 0.36 adds support for Gemini 4 Carbon, now generally available](#item-tech-news-8) ⭐️ 7.0/10
9. [Introducing Our Smallest, Most Efficient Model: Muse Ember](#item-tech-news-9) ⭐️ 7.0/10

**Technology Blog**
1. [Glue Work Is Still Harmful in the Age of AI](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Fed&\#x27;s Waller Leans Toward December Rate Hike, Floats Half-Point Move](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [DeepMind&\#x27;s AlphaProof Code Brings AI-Written Formal Proofs to Real-World Software Verification](https://deepmind.google/blog/introducing-alphaproof-code/) ⭐️ 8.0/10

Google DeepMind announced AlphaProof Code, a system that applies AI-generated formal proofs to verifying real-world software, with agents writing machine-checkable proofs in proof assistants such as Lean and Rocq. As characterized in the Hacker News discussion, the announcement reported verifying a library with a history of bugs and finding zero bugs — a vendor claim that drew immediate skepticism rather than independent confirmation. Commenters questioned whether the proved theorems were too narrow to catch real defects, and one noted that, as they understood it, the agent checks the implementation against a given specification rather than validating the specification itself.

hackernews · ilreb · Nov 10, 12:11 · [Discussion](https://news.ycombinator.com/item?id=50439193)

**「Background」** Formal verification replaces testing with machine-checked mathematical proofs — written in proof assistants such as Lean — that a program satisfies a stated specification. The technique has historically demanded heavy manual effort and, as Signal CTO Ehren Kret notes, prior formal verification efforts focused on smaller portions of code. AlphaProof Code extends DeepMind&\#x27;s AlphaProof proof-writing AI to this domain, with every proof the agents produce checked by Lean.

**「Practical takeaway」** Developers experimenting with AI-written proofs should treat the generated Lean or Rocq code as untrusted: one commenter with hands-on experience reports that AI can easily cheat when it writes the proof itself, and recommends a separate adversarial review pass over anything it generates. Until the theorem statements are audited, a &\#x27;zero bugs found&\#x27; result is best read as evidence about the properties that were proved, not about the code&\#x27;s overall correctness.

**「Community debate」** The sharpest disagreement concerned the zero-bug claim: hedora argued that a previously buggy library verifying clean suggests the theorems were wrong or the properties proved too narrow, while r0ze-at-hn noted the paper did re-introduce some bugs to confirm the system catches them, though they still advised adversarial review of AI-generated Lean. thibsrn separately questioned what distinguishes the agent from a conventional coding agent, since it likewise iterates over a codebase while writing and running Lean or Rocq code.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/blog/introducing-alphaproof-code/">Formal Verification of Signal’s Protocol with... — Google DeepMind</a></li>
<li><a href="https://google-deepmind.github.io/code-verification/">AlphaProof Code : Verifying Signal’s Security at the Machine- Code ...</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#ai-agents`, `#deepmind`, `#lean`, `#software-engineering`

---

<a id="item-tech-news-2"></a>
### [Google Chrome ships modern-web-guidance 1.0 to steer coding agents toward native web APIs](https://github.com/GoogleChrome/modern-web-guidance) ⭐️ 8.0/10

Google Chrome&\#x27;s team shipped version 1.0 of modern-web-guidance, an open-source set of 200+ hand-crafted guides \(~1.7MB\) produced in collaboration with Firefox, MDN, and Edge that teaches AI coding agents to prefer platform-native web APIs — such as &lt;dialog&gt;/showModal\(\), CSS.highlights, and field-sizing — over legacy div-plus-JavaScript patterns. It is distributed as an agent skill plus an agentic-RAG CLI \(a ~7MB pure-JS package with ~10ms on-CPU search\) and includes a deterministic &\#x27;legacy-scan&\#x27; trained on 30,000 GitHub repos that the authors say identifies modernizable legacy code with 92% average precision on held-out repos. In the project&\#x27;s own eval infrastructure — 200 tasks run with Codex, Claude, and agy against roughly 1,700 Playwright/AST-based assertions — agents passed 55% of tasks unguided versus 92% with the skill; these are vendor-run results, not independent measurements. Developers can install it with \`npx modern-web-guidance@latest install\`, setting DISABLE\_TELEMETRY=1 to opt out of telemetry.

hackernews · paulirish · Nov 10, 18:01 · [Discussion](https://news.ycombinator.com/item?id=50443812)

**「Why agents default to legacy patterns」** Coding agents generally know modern platform APIs by name yet still default to the incumbent div-plus-JavaScript patterns and dependencies when writing frontend code, which is the behavior this project set out to correct by feeding agents curated domain knowledge as an installable &quot;skill.&quot; The 1.0 release is a milestone in an effort already underway rather than a brand-new project: the GoogleChrome/modern-web-guidance repository has been on GitHub since at least May 2026, where it is described as supported by the Google Chrome team, the Microsoft Edge team, and the web development community.

**「Compatibility caveat for teams adopting the skill」** Teams that install the skill should expect agent-generated frontend code to use very new CSS that is not yet cross-browser: as of Chromium 157, Firefox 160, and Safari 27.2, 9 recently shipped CSS features work only in Chromium, and border-shape — one feature a release-thread commenter says the guidance recommends — is listed by MDN as supported only in Chrome 147. The commenter&\#x27;s list also includes @function, calc-size\(\), and corner-shape, so developers targeting Firefox or Safari should verify agent output against current support tables or limit which guides are active rather than adopting the skill wholesale. For existing codebases, the shipped \`npx modern-web-guidance@latest legacy-scan ./src\` command offers a concrete entry point, though the reported jump from 55% to 92% on the project&\#x27;s 200-task eval is a vendor measurement, not an independent benchmark.

**「Cross-browser gaps and Chrome-influence concerns」** Commenters flagged cross-browser compatibility as the main caveat: one listed promoted features — including CSS @function, calc-size\(\), interpolate-size, and corner-shape — that are stable in Chrome but unsupported in Firefox and Safari, and another argued \(as opinion, not a measured effect\) that having all coding agents follow Chrome-team guidance risks entrenching Chrome&\#x27;s standards dominance, echoing the old &quot;best viewed in \[dominant browser\]&quot; era. A separate practical suggestion asked the team to publish a grep-friendly markdown index of the guides on GitHub Pages so agents could use them without installing the npm package.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/GoogleChrome/modern-web-guidance">GitHub - GoogleChrome/modern-web-guidance: Keep your coding ...</a></li>
<li><a href="https://www.buildmvpfast.com/blog/interop-2027-css-proposals-border-shape-function-if-browser-support-2026">Interop 2027 CSS: Proposals, Support and What to Use</a></li>
<li><a href="https://harshal-ladhe.vercel.app/post/css/whats-new-in-css-2026">What&#x27;s New in CSS in 2026: What You Can Use Now</a></li>
<li><a href="https://css-tricks.com/almanac/rules/f/function/">@function - CSS-Tricks</a></li>

</ul>
</details>

**Tags**: `#ai-coding-agents`, `#web-platform`, `#developer-tools`, `#open-source`, `#browser-apis`

---

<a id="item-tech-news-3"></a>
### [Chips and Cheese dissects AMD&\#x27;s Zen 6 core, vector, and memory changes](https://chipsandcheese.com/p/amds-zen-6-family-feeding-the-beast) ⭐️ 8.0/10

Chips and Cheese has published a detailed technical analysis of AMD&\#x27;s next-generation Zen 6 CPU family, examining changes to the core, branch prediction, vector units, and memory subsystem. Specifics covered include the 2-ahead branch predictor, higher vector load throughput, a reduction in integer multiply units from three to two with PDEP/PEXT throughput falling from three to two instructions per cycle, and I/O die and memory controller changes. The piece is independent third-party analysis rather than an official AMD launch, and its granular trade-off findings have drawn an active technical discussion on Hacker News.

hackernews · pixelpoet · Nov 10, 17:02 · [Discussion](https://news.ycombinator.com/item?id=50443090)

**「Background: From Zen 5 to Zen 6」** Zen 6 is the successor to AMD&\#x27;s Zen 5 core family, and Chips and Cheese&\#x27;s analysis frames it as a study of the changes from Zen 5 and of how the denser Zen 6c variant differs from standard Zen 6 \(tool-2-3\). Key step-ups include a new Zen 6c CCD built on TSMC&\#x27;s 2 nm N2 node that raises core count to 32 per CCD and quadruples L3 cache to 128 MB \(tool-2-1\). Understanding the article&\#x27;s comparisons requires knowing Zen 5&\#x27;s design as the baseline, since the piece evaluates Zen 6 largely in terms of what was added, kept, or cut relative to it.

**「Throughput trade-offs to watch」** Workloads that lean on integer multiply or the PDEP/PEXT bit-manipulation instructions face reduced per-cycle throughput on Zen 6 — down from three operations per cycle to two, according to the analysis — so developers of such code should benchmark Zen 6 hardware when evaluating it. For readers weighing an AM5 platform refresh, the article&\#x27;s I/O die and memory controller findings are the most decision-relevant section.

**「Hacker News debate」** In the Hacker News thread, bmenrigh reports the AM5 Zen 4/Zen 5 memory controller is &quot;extremely hard or impossible&quot; to run above 3600 MT/s with both channels populated, and says an improved controller — which he has heard will be a new I/O chiplet on a smaller node — tops his Zen 6 wishlist. Other commenters probe the design trade-offs: Aardwolf asks whether PDEP/PEXT share circuitry with the cut multipliers, Remnant44 wonders whether dropping a multiplier freed die space for VNNI pipes and whether gather performance is finally acceptable, and bee\_rider questions how the discussed 32-core-per-CCD density would map onto NUMA domains.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techpowerup.com/review/amd-zen-6-technical-deep-dive/">AMD Zen 6 Technical Deep Dive | TechPowerUp</a></li>
<li><a href="https://chipsandcheese.com/p/amds-zen-6-family-feeding-the-beast">AMD ’s Zen 6 Family: Feeding the Beast - by George Cozma</a></li>

</ul>
</details>

**Tags**: `#cpu-architecture`, `#amd`, `#zen-6`, `#microarchitecture`, `#hardware`

---

<a id="item-tech-news-4"></a>
### [.NET 11 runtime moves async into the runtime, changes decimal conversion](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-11/runtime) ⭐️ 8.0/10

Microsoft has published the what&\#x27;s-new documentation for the .NET 11 runtime alongside the release announcement, headlined by runtime-level async support that moves async/await machinery out of compiler-generated state machines and into the runtime itself. The release also changes double-to-decimal conversion: the cast \(decimal\)0.1, which produced 0.1 on .NET 10, now yields 0.1000000000000000055511151231, reflecting the double&\#x27;s exact binary value rather than the rounded figure — a difference a commenter flagged, citing Microsoft&\#x27;s compatibility documentation, as a potential breaking change for code relying on the old output. The changes are most relevant to C\# and .NET developers running async-heavy backend and services workloads.

hackernews · stevefan1999 · Nov 10, 12:20 · [Discussion](https://news.ycombinator.com/item?id=50439284)

**「The async model .NET 11 replaces」** Async/await in C\# has historically been implemented by the compiler, which rewrites asynchronous methods into generated state-machine types—the machinery that .NET 11&\#x27;s new runtime-level async support moves into the runtime itself. The release continues Microsoft&\#x27;s annual .NET cadence, arriving one year after .NET 10, which serves as the compatibility baseline for evaluating the new version&\#x27;s behavioral changes.

**「Upgrade considerations for .NET 11」** Because the .NET 11 runtime libraries no longer contain compiler-generated state machines and rely entirely on runtime-provided async, teams can migrate an entire application, including its library dependencies, to the new async model, with potential effects on allocations, performance, and debugging. As a compatibility concern, a commenter in the release discussion flagged a behavioral change in decimal conversion, reporting that \(decimal\)0.1 yields 0.1000000000000000055511151231 in .NET 11 instead of 0.1 as in .NET 10, so developers should review Microsoft&\#x27;s compatibility documentation before upgrading.

**「Community discussion」** Reaction to the runtime async rework was favorable but surprised: one developer expected friendlier stack traces without compiler-generated state machines but had not anticipated that a runtime implementation could match the previous approach&\#x27;s performance. A separate thread debated the platform&\#x27;s reputation, with one commenter arguing C\# and .NET remain underappreciated because of Windows-only and .NET Framework-era perceptions and past open-source controversies despite strong day-to-day backend experience, while another welcomed the new official dotnetup version manager.

<details><summary>References</summary>
<ul>
<li><a href="https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-11/runtime">What&#x27;s new in .NET 11 runtime | Microsoft Learn</a></li>
<li><a href="https://www.c-sharpcorner.com/article/runtime-async-in-net-11-what-actually-changed">Runtime Async in .NET 11: What Actually Changed - C# Corner</a></li>

</ul>
</details>

**Tags**: `#.NET`, `#C\#`, `#runtime`, `#async`, `#microsoft`

---

<a id="item-tech-news-5"></a>
### [Seven-month Glasswing update draws debate over AI-found vulnerability impact](https://www.vulncheck.com/blog/anthropic-glasswing-november-update) ⭐️ 7.0/10

A seven-month update on Anthropic&\#x27;s Glasswing AI vulnerability-discovery program, published on VulnCheck&\#x27;s blog, is drawing debate over whether its findings are underwhelming, with the skeptical read resting on modest public CVE counts. Commenters counter that the program&\#x27;s public ledger tracks only its open-source coordinated vulnerability disclosure effort, while most Glasswing discoveries come from partners pointing Mythos-class models at proprietary codebases where findings never receive CVEs. As concrete counter-evidence, the maintainer of Fil-C reports receiving nine issue reports from Anthropic, all of which were real bugs with no false positives and exceptional report quality.

hackernews · panic · Nov 10, 22:17 · [Discussion](https://news.ycombinator.com/item?id=50447074)

**「What Project Glasswing is」** Anthropic introduced Project Glasswing on April 7 as an AI vulnerability-discovery program that uses frontier models to find security bugs in software. VulnCheck had previously tracked CVEs attributed to Anthropic researchers and the program, concluding that Glasswing&\#x27;s publicly attributable impact remained limited even as the underlying research looked promising. The seven-month update puts numbers on that picture: 442 CVEs attributable to Anthropic — roughly 0.5% of all CVEs published this year, only two of them exploited in the wild — with 7,349 of 37,966 reported findings \(19.4%\) made public and just 217 marked fixed.

**「Genuine reports, strained patch capacity」** Maintainers receiving Glasswing reports should expect real engineering work rather than noise: the Fil-C maintainer reports all nine AI-found issues he received were genuine bugs, though he adopted only some proposed fixes verbatim and reworked the rest. External analyses put the program&\#x27;s first-month yield at over 10,000 high- or critical-severity vulnerabilities across roughly 1,000 open-source projects, with only 97 patches deployed upstream — a deficit framed by security researchers as a maintainer-capacity crisis that concerns every consumer of open-source software. Organizations running open-source dependencies should therefore not read the program&\#x27;s modest public CVE count as evidence of low risk, since commenters argue most serious findings land in partners&\#x27; private codebases that never receive CVEs, and should verify the patch status of the components they rely on rather than waiting on CVE feeds.

**「Practitioner debate」** The Fil-C maintainer, whose stated baseline is security defense work on a browser engine, says the report quality was &quot;exceptional&quot; but the proposed fixes only &quot;alright&quot; — he took some verbatim and used most as inspiration for his own fixes — while a self-identified big-tech engineer reports spending every working day since the Mythos launch patching serious, company-threatening AI-found issues that &quot;will never get a CVE number assigned and will never get a fancy blog post.&quot; Others add caveats rather than endorsements: one commenter notes the PHP2Shell episode showed frontier models&\#x27; biggest PHP find relied on a previously known, extremely difficult-to-exploit logic flaw with limited real-world impact, and another argues the blog is misleading because its ledger data source covers only the open-source disclosure program rather than Glasswing&\#x27;s typical partner engagements against proprietary software.

<details><summary>References</summary>
<ul>
<li><a href="https://www.vulncheck.com/blog/anthropic-glasswing-november-update">After 7-months, Glasswing Overwelms Maintainers with ...</a></li>
<li><a href="https://news.lavx.hu/article/vulncheck-tracks-slow-fixes-and-few-exploits-in-anthropic-s-glasswing-project">VulnCheck tracks slow fixes and few exploits in Anthropic’s ...</a></li>
<li><a href="https://www.vulncheck.com/blog/anthropic-glasswing-cves">Tracking CVEs Attributed to Anthropic Researchers and Project ...</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-ai-vuln-discovery-velocity-disclosure-cris/">Project Glasswing and the AI Vulnerability Disclosure ...</a></li>
<li><a href="https://labs.cloudsecurityalliance.org/research/csa-research-note-glasswing-ai-vuln-patching-deficit-2026060/">Project Glasswing: AI Discovery Outpaces Open Source Patching ...</a></li>
<li><a href="https://dailysecurityreview.com/resources/anthropics-project-glasswing-finds-10000-cves-in-one-month/">Anthropic’s Project Glasswing Finds 10,000+ CVEs in One Month</a></li>

</ul>
</details>

**Tags**: `#ai-security`, `#vulnerability-discovery`, `#llm-agents`, `#open-source`, `#anthropic`

---

<a id="item-tech-news-6"></a>
### [Starlink Mini 2 draws remote-use praise and networking complaints](https://starlink.com/mini-2) ⭐️ 7.0/10

SpaceX&\#x27;s Starlink Mini 2, a new compact satellite internet terminal, is the subject of a heavily engaged Hacker News thread \(283 comments\) focused on how it performs for remote, mobile, and off-grid users. Reported use cases include hard rock mining, where drill results that once took days to reach planners now arrive as a live feed, and portable work sessions run off a separate battery. Commenters also flag concrete limitations: the service provides only NAT&\#x27;d addressing with no static IP option, and the standard Roam plan reportedly no longer includes international coverage — Roam Unlimited covers it, but only in 30-day periods that reset only after returning to the user&\#x27;s home country. The discussion includes no hardware specifications or pricing, so those details remain unconfirmed.

hackernews · robertjfclarke · Nov 10, 18:22 · [Discussion](https://news.ycombinator.com/item?id=50444129)

**「Background」** The Starlink Mini is SpaceX&\#x27;s compact, portable satellite dish aimed at mobile and off-grid users, and the first-generation model had just fallen to its lowest price yet — $149 — as word of a successor spread. PCMag reported that SpaceX&\#x27;s own website appeared to leak a $249 price for the second-generation Mini dish, and that Elon Musk had shown off the second-gen Mini in June alongside the company&\#x27;s recently released V5 dish. The original Mini has been positioned as a lighter, easier-to-set-up dish, launching in markets such as Australia at A$80 per month with speeds of up to 100 Mbps.

**「Roam and addressing limits for buyers」** Buyers with needs beyond basic connectivity face concrete restrictions: the standard Roam plan no longer includes coverage outside the home country — only &\#x27;Roam unlimited&\#x27; does, capped at 30 days at a time with no way to extend until returning home — following global changes to Roam plans that took effect August 17, 2026. The service also provides only NAT&\#x27;d addresses with no static IP option, which one commenter said rules it out for their RV use. Frequent travelers should compare current Roam terms against alternatives such as existing SIM roaming before purchasing.

**「Community discussion」** The most substantive reports came from a hard rock mining worker who said the device has &quot;completely changed my industry&quot; by turning multi-day drill result delays into an instant live feed — also curbing cases where drillers knew results before markets did — and from a user describing battery-powered work sessions in Golden Gate Park while family explored. Critics pushed back on practicality: an RV user ruled the service out over NAT-only addressing with no static IPs, and a frequent traveler reported the standard Roam plan no longer includes international coverage, with Roam Unlimited capped at 30 days at a time and no way to extend it without returning home, while another commenter suggested SpaceX sell a foldable solar panel for a set-and-forget off-grid setup.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=hqWqHuV9-Po">Starlink Mini Is Now $149… But Mini 2 Is Coming - YouTube</a></li>
<li><a href="https://www.pcmag.com/news/249-starlinks-website-reportedly-leaks-mini-2-dishs-price">$249? Starlink &#x27;s Website Reportedly Leaks Mini 2 Dish&#x27;s Price | PCMag</a></li>
<li><a href="https://techbest.com.au/spacex-launches-starlink-mini-in-australia-80-month-for-100mbps-but-is-50gb-sufficient/">SpaceX Launches Starlink Mini in Australia | Techbest</a></li>
<li><a href="https://www.skylinker.io/p/global-starlink-roaming-availability-changes-for-users-eng">Global Changes to Roaming Availability for Starlink Users</a></li>

</ul>
</details>

**Tags**: `#satellite-internet`, `#hardware`, `#networking`, `#starlink`, `#connectivity`

---

<a id="item-tech-news-7"></a>
### [Synaptics patent claims halt open source DisplayLink driver work](https://lwn.net/SubscriberLink/1102549/acbc92e00cee3a3f/) ⭐️ 7.0/10

Synaptics has sent patent infringement claims to developers of reverse-engineered open source DisplayLink drivers, and work on those drivers has stopped as a result, according to LWN&\#x27;s report. A demand letter quoted in the accompanying discussion gives a deadline and states that failing to comply will lead Synaptics to seek US$25,000 to recoup the costs of documenting the allegedly infringing acts. The dispute targets community-written drivers for DisplayLink&\#x27;s USB display technology rather than any Synaptics-published software.

hackernews · speckx · Nov 10, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50443824)

**「Background」** DisplayLink is Synaptics&\#x27; technology for driving monitors over USB in docking stations, and Linux support has depended on the vendor&\#x27;s proprietary driver, which developer Mike Lothian found repeatedly crash-prone. That frustration led him to build Vino, a Rust-based, reverse-engineered open source driver for DisplayLink docks. Synaptics&\#x27; cease-and-desist letters cite 125 patents and demand monetary compensation — aimed at a clean-room driver written without copied code, a legal angle open source developers rarely anticipate.

**「Impact」** Contributors to the open source DisplayLink drivers now face individual monetary demands, and Linux users of DisplayLink-based docks and adapters are left without continued development of the community drivers they depend on. Developers considering reverse-engineering other proprietary protocols face a demonstrated risk of patent-based demands, not just takedown requests.

**「Community reaction」** Commenters disputed the legal basis of the demands: one argued that reverse engineering cannot itself infringe a patent because patents exist as public disclosures of a mechanism, and another questioned whether a US$25,000 claim for &\#x27;documentation costs&\#x27; could hold up in court given that the patent holder bears the burden of proving infringement. Others were unsympathetic to the technology itself, with one commenter claiming dock makers are cancelling DisplayLink products over unfavorable economics in favor of Thunderbolt and USB4 docks using DisplayPort alt mode, and another describing persistent audio problems with a DisplayLink dock at work.

<details><summary>References</summary>
<ul>
<li><a href="https://tech.yahoo.com/computing/articles/synaptics-hits-open-source-linux-151911998.html">Synaptics Hits Open-Source Linux Driver Vino With Cease-and ...</a></li>
<li><a href="https://emergent.sh/news/synaptics-patent-threat-kills-claude-written">Synaptics Patent Threat Kills Claude-Written DisplayLink</a></li>
<li><a href="https://frnt.com/story/86544/synaptics-forces-shutdown-of-open-source-displaylink-driver-over-patent-claims">Synaptics Forces Shutdown of Open-Source DisplayLink Driver ...</a></li>

</ul>
</details>

**Tags**: `#open source`, `#patents`, `#linux drivers`, `#DisplayLink`, `#intellectual property`

---

<a id="item-tech-news-8"></a>
### [llm-gemini 0.36 adds support for Gemini 4 Carbon, now generally available](https://simonwillison.net/2026/Nov/10/llm-gemini/) ⭐️ 7.0/10

Simon Willison released llm-gemini 0.36, adding support for Google&\#x27;s Gemini 4 Carbon model on the day it became generally available to everyone, two weeks after its announcement for &quot;a subset of cyber defenders.&quot; Willison calls it Google&\#x27;s best Gemini yet and highlights launch pricing of $2 per million input tokens and $10 per million output tokens — comparable, in his comparison, to GPT-6.1 Sol and Claude Sonnet 5.5 — which is scheduled to double to $4/$20 on December 1st, matching Opus 5.5. The plugin support is shipped and hands-on tested: Willison ran his pelican SVG benchmark at low, medium, and high thinking-effort settings \(medium is the default\) and used the model in Google&\#x27;s Antigravity IDE to build a Three.js mech animation over OpenStreetMap data. He also pointed to a YouTube demo in which Carbon&\#x27;s /swarm feature coordinated subagents to build an open-world 3D game with Blender assets, WebGL shaders, and Lyria music.

rss · Simon Willison · Nov 10, 20:09

**「Background」** Gemini 4 Carbon is built on Google&\#x27;s Gemini 4 Argon model and accepts text, image, audio, and video inputs with a combined input-output context window of up to 1 million tokens. Google&\#x27;s announcement emphasized protecting software systems and complex tasks that require many actions, and the model was first announced two weeks earlier with access limited to &quot;a subset of cyber defenders&quot; before opening to everyone else.

**「Launch pricing doubles on December 1st」** Developers on the llm CLI can use Gemini 4 Carbon today by upgrading to llm-gemini 0.36, but the $2/$10 launch pricing is time-limited: Google has scheduled it to rise to $4/$20 per million tokens on December 1st, so high-volume batch runs, evaluations, or agent workloads cost half as much if completed before that date.

<details><summary>References</summary>
<ul>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-carbon/">Gemini 4 Carbon - Model Card — Google DeepMind</a></li>
<li><a href="https://www.gptunnel.ru/en/blog/gemini-4-carbon">Gemini 4 Carbon : a new top-1? A review of the available benchmarks</a></li>

</ul>
</details>

**Tags**: `#llm`, `#gemini`, `#google`, `#model-pricing`, `#release-notes`

---

<a id="item-tech-news-9"></a>
### [Introducing Our Smallest, Most Efficient Model: Muse Ember](https://simonwillison.net/2026/Nov/10/muse-ember/) ⭐️ 7.0/10

Simon Willison covers Meta&\#x27;s launch of Muse Ember, a small efficient model for agentic tasks priced on par with GPT-6 Luna and Claude Haiku 5.5, highlighting its tiered long-context pricing.

rss · Simon Willison · Nov 10, 07:28

**Tags**: `#Meta`, `#LLM releases`, `#model pricing`, `#small language models`, `#agentic AI`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Glue Work Is Still Harmful in the Age of AI](https://seangoedecke.com/glue-work-is-still-harmful-in-the-age-of-ai/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 11, 00:00

**「Background」** &quot;Glue work&quot; is informal, unrewarded non-technical labor — coordinating meetings, onboarding, writing reports — that gets done only when someone volunteers. Having called it harmful in a 2024 post, Sean Goedecke now asks whether LLMs writing most code free engineers up to do more of it.

**「Solution」** His answer is no: AI makes glue work less valuable, for four reasons. AI agents let a single engineer take on projects that once needed a small team, eliminating much of the meeting-scheduling and status-update coordination glue work covered. Engineers also need less &quot;careful handling&quot;: in his experience the heaviest coordination burden was managing secret gatekeepers — influential engineers with large egos who shot down projects they weren&\#x27;t consulted on — and he argues the end of ZIRP pushed many of the prickliest out of the industry. Companies hiring fewer juniors \(bad for the industry, he concedes\) removes the onboarding hand-holding volunteers once provided. And &quot;proof of work&quot; — write-only reports nobody read, produced to show awareness or satisfy legal templates — can now be generated by LLMs, which is fine because they were never meant to be read anyway. He draws a hard limit, though: interpersonal communication cannot be delegated. Checking in on a project or answering a ping must be written yourself; making colleagues talk to your Claude Opus instance will torch relationships. The case rests on anecdote and contestable causal claims — that ZIRP&\#x27;s end purged gatekeepers, that LLMs now write most code — but the four-way decomposition is its useful contribution.

**「Takeaway」** The 2024 advice stands: avoid becoming &quot;the glue work person,&quot; let bad processes fail, and do only small tactical glue work — while spending most of your effort on code, driving AI agents and aligning them with your company&\#x27;s values.

**Tags**: `#glue work`, `#AI coding agents`, `#engineering culture`, `#career strategy`, `#LLM limitations`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed&\#x27;s Waller Leans Toward December Rate Hike, Floats Half-Point Move](https://www.cnbc.com/2026/11/10/fed-governor-waller-sees-december-hike-likely.html) ⭐️ 8.0/10

Fed Governor Christopher Waller said Tuesday he is leaning toward raising interest rates at the December meeting and that a larger-than-usual 50 basis point hike &quot;should be considered&quot; if inflation readings come in hotter than forecast. His comments followed the October consumer price index report, which showed a 0.4% headline rise and a 0.3% core rise, each 0.1 percentage point above the Dow Jones consensus.

rss · CNBC Finance · Nov 10, 17:13

**「Background」** The Federal Reserve raised its benchmark rate by a quarter point to 3.75%-4% in September 2026, its first hike since 2023, before holding steady at the October meeting. A basis point is one-hundredth of a percentage point, so a 50-basis-point increase would be half a point.

**「Impact on borrowers and markets」** A December hike would raise borrowing costs on mortgages, loans, and credit for households and businesses, and traders have already fully priced in a quarter-point move with 12.5% odds of the larger half-point increase.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/09/16/fed-rate-decision-september-2026.html">Fed rate decision September 2026 : Rates rise to 3.75%-4%</a></li>
<li><a href="https://www.cnbc.com/2026/11/10/fed-governor-waller-sees-december-hike-likely.html">Fed Governor Waller sees December hike likely - CNBC</a></li>
<li><a href="https://economictimes.indiatimes.com/markets/us-stocks/wall-street-guide/feds-christopher-waller-opens-door-to-50-basis-point-december-rate-hike-after-hot-cpi/articleshow/135718143.cms">Fed’s Christopher Waller opens door to 50-basis-point ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#CPI`

---