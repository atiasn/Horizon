---
layout: default
title: "Horizon Summary: 2026-10-23 (EN)"
date: 2026-10-23
lang: en
---

> From 43 items, 18 important content pieces were selected

---

**Technology News**
1. [Quad9 to exit France and geo-block French users after contempt fines](#item-tech-news-1) ⭐️ 8.0/10
2. [Technical writeup details Nintendo Switch 2 jailbreak and AI-driven research rig](#item-tech-news-2) ⭐️ 8.0/10
3. [New Earstrip triangulator claims 3.7M map polygons in 489 ms, outpacing Earcut](#item-tech-news-3) ⭐️ 8.0/10
4. [Study: Some Smart TVs Still Report Viewing Data After ACR Is Disabled](#item-tech-news-4) ⭐️ 8.0/10
5. [Banned Nvidia B300 Chips Surface in Chinese State-Linked Procurement Filings](#item-tech-news-5) ⭐️ 8.0/10
6. [NVIDIA&\#x27;s OpenShell proposes a sandboxed runtime for autonomous AI agent fleets](#item-tech-news-6) ⭐️ 7.0/10
7. [Getting ready to operate GNU Taler in Germany](#item-tech-news-7) ⭐️ 7.0/10
8. [eMudhra to exit global SSL/TLS certificate business](#item-tech-news-8) ⭐️ 7.0/10
9. [Arc browser winds down as users migrate to Zen and Orion](#item-tech-news-9) ⭐️ 7.0/10
10. [pwn.watch tracks actively exploited vulnerabilities in real time](#item-tech-news-10) ⭐️ 7.0/10
11. [Anthropic Donates Agent Skills Standard to the Agentic AI Foundation](#item-tech-news-11) ⭐️ 7.0/10
12. [Carbon-X: open 14.8B model trained jointly on DNA and text](#item-tech-news-12) ⭐️ 7.0/10
13. [Australian court orders Apple to open iPhone to third-party app stores](#item-tech-news-13) ⭐️ 7.0/10
14. [miHoYo and Tsinghua open-source GameScaling keyboard/mouse game-control models](#item-tech-news-14) ⭐️ 7.0/10
15. [Oracle patches critical pre-auth Java SE TLS vulnerability CVE-2026-91403](#item-tech-news-15) ⭐️ 7.0/10
16. [333 Tor Exit Relays Found Running Ebury Backdoor, Taken Offline](#item-tech-news-16) ⭐️ 7.0/10

**Technology Blog**
1. [Why rewriting software in faster languages rarely makes it faster](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [沪深 300 较 6 月高点回落 20%，A 股逼近熊市](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Quad9 to exit France and geo-block French users after contempt fines](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 8.0/10

Quad9, the non-profit DNS resolver, has announced it is exiting France, with its CTO saying it will probably use geoIP filters to block French users from its services after November 24. The move follows contempt-of-court fines in piracy-related DNS blocking litigation: a passage quoted from the announcement states that Sony Music Entertainment GmbH used a VPN to access blocked content from Germany in circumvention of Quad9&\#x27;s geoIP blocking, and the court agreed with Sony&\#x27;s noncompliance claims and fined the resolver. Quad9 maintains that geoIP blocking is insufficient for selectively denying resolution of specific domain names, and its CTO described scrutiny of how the French block would work as energy spent in the wrong place. The announcement follows French web-blocking injunctions that Canal+ obtained against Google, Cloudflare, and Cisco resolvers, which unsuccessfully opposed the orders.

hackernews · farrokhi · Oct 22, 14:32 · [Discussion](https://news.ycombinator.com/item?id=50195959)

**「French court orders against DNS resolvers」** Quad9 is a non-profit DNS resolver — the service that translates domain names into IP addresses — and French rights holders have targeted this layer before: as recounted in the discussion, Canal+ obtained web-blocking injunctions against resolvers operated by Google, Cloudflare, and Cisco, all three unsuccessfully opposed the orders, and Cisco reportedly responded with a similar exit from the French market about two years ago. The contempt fine that led to Quad9&\#x27;s decision arose, per Quad9&\#x27;s own account in the thread, after Sony Music Entertainment GmbH used a VPN to reach blocked content from Germany despite the resolver&\#x27;s geoIP blocking, and the court accepted Sony&\#x27;s noncompliance claim and fined Quad9.

**「French users must migrate off Quad9 by November 24」** From November 24, 2026, Quad9 will geo-block French users, cutting off DNS resolution through its service for anyone in France; users and network administrators there must switch to another resolver or their ISP&\#x27;s DNS before that date. Replacement options are constrained because the Paris court&\#x27;s July 17, 2026 orders also bind Google Public DNS, Cloudflare, and other intermediaries, and Quad9&\#x27;s CTO cautioned in the discussion that geoIP blocking cannot reliably deny resolution of specific names — the provider was still fined for contempt after a plaintiff circumvented it with a VPN — so French users should verify their fallback DNS settings rather than assume any public resolver remains unaffected.

**「Community reaction」** In the Hacker News thread, Quad9&\#x27;s CTO \(posting as johnhtodd\) confirmed the geoIP plan and the November 24 timing while arguing that selectively denying resolution for specific names is technically insufficient, and commenter nadermx argued Quad9 was fined even though the plaintiff circumvented its protections with a VPN. Others questioned the legal premise: babarock compared penalizing a DNS resolver to punishing a phone book company for listing a criminal&\#x27;s number, and JokerDan suggested resolvers facing such orders should stop resolving the suing companies&\#x27; own domains.

<details><summary>References</summary>
<ul>
<li><a href="https://lawyerd.net/news/paris-court-blocking-orders-dns-vpn-search-engines/">French blocking order: DNS resolvers, VPNs, search engines ...</a></li>
<li><a href="https://www.heise.de/en/news/Censorship-ruling-prompts-DNS-service-Quad9-to-leave-France-11497631.html">Censorship ruling prompts DNS service Quad9 to leave France</a></li>
<li><a href="https://reclaimthenet.org/quad9-considers-leaving-france-over-website-blocking-order">Quad9 Considers Leaving France Over Website Blocking Order</a></li>

</ul>
</details>

**Tags**: `#dns`, `#internet-infrastructure`, `#geoip-blocking`, `#legal`, `#censorship`

---

<a id="item-tech-news-2"></a>
### [Technical writeup details Nintendo Switch 2 jailbreak and AI-driven research rig](https://pepsipu.com/blog/2026-10-switch2-jailbreak-ns2jb/) ⭐️ 8.0/10

A technical writeup published October 22, 2026 on the personal blog pepsipu.com describes a jailbreak for Nintendo&\#x27;s Switch 2 console, which commenters on the accompanying Hacker News thread read as claiming decrypted filesystem read/write access — a capability that, if accurate, would allow dumping games for use in recompilation projects. The writeup also documents an automated research rig in which JetKVM devices let OpenAI&\#x27;s Codex agent send controller inputs to Switch 2 units over USB and receive video output over HDMI, while a Bluetooth-actuated SwitchBot Bot presses the power button to restart the console after crashes. The technical claims come from a personal blog and are not independently verified, and commenters themselves hedge on how much access the exploit actually grants.

hackernews · ledoge · Oct 22, 08:01 · [Discussion](https://news.ycombinator.com/item?id=50192536)

**「Background」** ns2jb is described as the first software-only, tethered jailbreak for the Nintendo Switch 2, meaning it requires no hardware modification but does not survive a reboot and must be re-applied each boot, and it reportedly works on the latest 23.0.1 firmware. The reported entry point is a vulnerability in SmileBASIC 4, an original Switch game that lets users write their own programs, which provides a way into the Switch 2&\#x27;s system. Its code execution extends to the console&\#x27;s built-in fs sysmodule — the filesystem service — which is what yields the decrypted filesystem read/write access underpinning homebrew, game modding, and save-file backups.

**「What it means for users and researchers」** If the reported decrypted filesystem read/write access holds up, Switch 2 game dumps and homebrew become feasible, following the pattern already seen on the original Switch where decompilation and recompilation projects have enabled native ports on arbitrary hardware. For security researchers, the writeup also demonstrates a practical automation setup — AI coding agents driving JetKVM hardware for controller input and video output, plus a Bluetooth-actuated SwitchBot Bot to press the power button on crashes — that others could reuse for console exploit work. Because the technical claims come from a personal blog and the exploit&\#x27;s full scope is not independently verified, readers should wait for corroboration before relying on any specific capability.

**「Community discussion」** Commenters argue that confirmed decrypted filesystem access could mean Switch 2 game dumps appearing within hours and, given the active recompilation and decompilation scene, console exclusives running on arbitrary hardware — hturan calls that a worst-case scenario for Nintendo and cites Tears of the Kingdom running natively at 60 fps on an iPhone as precedent. Others debate how much credit the AI deserves, with KeplerBoy noting the author appears to be an experienced security researcher, while rootsudo reports that Codex refuses some legitimate security work, such as investigating CVEs in older Android ROMs, even as it allowed Microsoft bug-bounty research.

<details><summary>References</summary>
<ul>
<li><a href="https://pepsipu.com/blog/2026-10-switch2-jailbreak-ns2jb/">pepsipu .com/blog/2026-10- switch 2 - jailbreak - ns 2 jb</a></li>
<li><a href="https://gbatemp.net/news/switch-2-jailbreak-ns2jb-released-software-only-exploit-tethered.685698/">Switch 2 jailbreak &quot; ns 2 jb &quot; released. Software-only exploit , tethered</a></li>
<li><a href="https://www.androidauthority.com/nintendo-switch-2-software-jailbreak-3727013/">Nintendo Switch 2 jailbreak could open the door to a world of mods</a></li>
<li><a href="https://www.noobfeed.com/news/nintendo-concerns-pc-ports-games">Nintendo Faces Growing Concerns Over AI-Powered PC... | NoobFeed</a></li>

</ul>
</details>

**Tags**: `#hardware-security`, `#reverse-engineering`, `#nintendo-switch-2`, `#homebrew`, `#ai-agents`

---

<a id="item-tech-news-3"></a>
### [New Earstrip triangulator claims 3.7M map polygons in 489 ms, outpacing Earcut](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 8.0/10

A new polygon triangulation library, Earstrip, claims in an October 16, 2026 blog post that it triangulates 3.7 million map polygons in 489 ms, faster than Earcut, the widely used triangulator in JavaScript map rendering such as Mapbox GL JS. The figure is the project&\#x27;s own benchmark rather than an independent measurement, but the post publishes its test datasets and drew a positive response from Earcut&\#x27;s author, who praised the work and said he would look for tricks to borrow for Earcut&\#x27;s JavaScript version. Earcut&\#x27;s author also framed the tradeoff on his side: he deliberately rejects some optimizations to keep the library at 4.1 kB min/gz and fast enough for most practical uses, and asked in turn how large Earstrip&\#x27;s WASM build is.

hackernews · molind · Oct 22, 09:31 · [Discussion](https://news.ycombinator.com/item?id=50193170)

**「Background」** Polygon triangulation — decomposing map shapes, including ones with holes, into the triangles a GPU can draw — is a core step in map rendering, and Earcut, Mapbox&\#x27;s ear-clipping triangulation library, has been the de facto standard for the task. Earstrip is built as a direct replacement for that role: it ships as a single C++ header with a WebAssembly build on npm, takes the same arguments as Earcut, and uses the same ISC license.

**「Impact」** Teams doing polygon triangulation in JavaScript map and 3D pipelines — Earcut is optimized for Mapbox Vector Tiles and is used by Mapbox GL JS, Three.js, and other projects — now have a faster option for heavy workloads, but switching is not a drop-in win. Earcut&\#x27;s author says he deliberately rejected some optimizations to keep the library small \(4.1k min/gz\) and considers it already fast enough for uses like Mapbox GL JS, so teams should check the size of Earstrip&\#x27;s WASM build before adopting it. Output quality also warrants testing: one commenter observed many long, thin triangles in the results, a shape that can be a worst case for GPU rasterizers.

**「Quality concerns and a benchmark challenge」** Commenters pressed on output quality rather than raw speed: stymaar asked whether the many long, thin triangles in the results are a worst case for GPU rasterizers, and mistercow wondered why ear clipping has beaten Seidel&\#x27;s trapezoidal method, which has O\(n log\*n\) complexity and handles holes naturally. morishuz, author of the Delaunay32 constrained Delaunay triangulator, proposed benchmarking his divide-and-conquer implementation against the published datasets, noting he has not yet run it on that corpus and that his API currently requires simple rings with non-touching holes.

<details><summary>References</summary>
<ul>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut : triangulating 3 . 7 M map polygons in 489 ms</a></li>
<li><a href="https://github.com/MichaCo/Earcut">MichaCo/ Earcut : Fast and robust ear -clipping polygon triangulation ...</a></li>
<li><a href="https://github.com/mapbox/earcut">GitHub - mapbox/earcut: The fastest and smallest JavaScript ...</a></li>
<li><a href="https://hysenlabs.com/projects/mapbox-earcut">earcut npm: polygon triangulation for WebGL | Hysen Labs</a></li>

</ul>
</details>

**Tags**: `#computational-geometry`, `#triangulation`, `#performance-optimization`, `#gis-mapping`, `#wasm`

---

<a id="item-tech-news-4"></a>
### [Study: Some Smart TVs Still Report Viewing Data After ACR Is Disabled](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 8.0/10

A study of automatic content recognition \(ACR\) on US smart TVs tested 12 sets from 10 manufacturers across 5,943 controlled experiments and found that some models continue uploading content-related traffic even after users disable ACR in their settings. The researchers report that VIDAA OS transmits viewing-related data, including non-resettable device IDs and audio fingerprints, over plaintext MQTT, while Vizio&\#x27;s WatchFree+ exposes program names in unencrypted DNS queries that users cannot turn off. Published as the Watching the Watchers project, the results are the researchers&\#x27; own controlled measurements and indicate that the standard ACR opt-out does not fully stop viewing-related reporting on the affected platforms.

telegram · zaihuapd · Oct 22, 09:50

**「What automatic content recognition is」** Automatic content recognition \(ACR\) is a smart-TV feature that captures what is on screen and shares it with the TV manufacturer, which can use the viewing data to sell advertising, according to the UC Davis computer scientists behind the study. Their project, &quot;Watching the Watchers,&quot; is described as the first automated, at-scale measurement of ACR, covering the eight smart-TV operating systems that account for roughly 95% of the U.S. market.

**「What this means for TV owners」** Owners who have already switched off automatic content recognition in their TV&\#x27;s settings cannot assume that ended content-related reporting: the study found Samsung, Vizio, and Roku sets still sending traffic to ACR endpoints after opt-out, and Vizio&\#x27;s WatchFree+ exposes program names in DNS queries that no in-settings option disables. The practical step is to enforce blocking outside the TV, such as router-level DNS filtering, because ACR behavior is implementation-specific with no universal sampling rate, data flow, or retention period that users can verify from the privacy menu alone. Vizio&\#x27;s earlier $2.2 million FTC penalty for tracking and selling viewing data without consent shows US regulators have already treated this practice as a violation, so affected users have a precedent for scrutinizing their set&\#x27;s traffic and data settings.

<details><summary>References</summary>
<ul>
<li><a href="https://watchingthewatchers.github.io/watchingthewatchers/index.html">Watching the Watchers : Privacy Analysis of U.S. Smart TV ...</a></li>
<li><a href="https://www.ucdavis.edu/news/your-smart-tv-watching-what-you-watch">Your Smart TV is Watching What You Watch | UC Davis</a></li>
<li><a href="https://arstechnica.com/gadgets/2026/10/does-opting-out-of-smart-tv-tracking-work-research-finds-suspicious-traffic/">Does opting out of smart TV tracking work? Research... - Ars Technica</a></li>
<li><a href="https://www.offlist.me/blog/disable-smart-tv-data-collection">Disable Smart TV ACR Data Collection (Samsung, LG, Roku 2026)</a></li>
<li><a href="https://www.tomsguide.com/us/vizio-ftc-smart-tv-spying-privacy,news-24415.html">Government Confirms Vizio TVs Spy on You: How to... | Tom&#x27;s Guide</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#security-research`, `#smart-tv`, `#surveillance`, `#iot`

---

<a id="item-tech-news-5"></a>
### [Banned Nvidia B300 Chips Surface in Chinese State-Linked Procurement Filings](https://theinference.org/article/china-s-state-money-bought-banned-nvidia-b300-servers-then-redacted-the-receipts) ⭐️ 8.0/10

Procurement filings reported by The Inference and Quartz show a Chinese state-controlled semiconductor leasing group financed the purchase of 32 Asus servers equipped with Nvidia B300 chips for AI firm Rongyao Shitu Technology \(荣耀视图科技\), as part of a 700-plus-server deal worth over 3 billion yuan intended for deployment at China Mobile&\#x27;s Ningxia data center. The B300 falls under the strictest tier of US export controls and is effectively banned from export to China. After the filings drew scrutiny, the leasing group resubmitted documents with the hardware descriptions removed; Nvidia says it is investigating together with its manufacturing partners, while Asus says it complies with export controls. The report describes an alleged violation under investigation, not a confirmed breach.

telegram · zaihuapd · Oct 22, 15:22

**「The export-control backdrop」** The Nvidia B300 is a Blackwell-generation AI chip that falls under the strictest tier of US export controls, which effectively bans its sale to China — the restriction that makes its appearance in Chinese state-linked procurement a potential violation. The deal first drew public scrutiny in early October 2026, when Bloomberg reported that the financier, Semi-Tech Leasing, is controlled by Shenzhen and Beijing municipal entities and resubmitted altered filings to China&\#x27;s public credit registry that removed hardware descriptions, supplier details, and server models after the purchase came under attention.

**「Enforcement risk shifts to Nvidia&\#x27;s server channel」** With Nvidia investigating alongside its manufacturing partners and Asus publicly asserting export-control compliance, enforcement risk now extends past end users to the server supply chain itself: ODMs, leasing intermediaries, and resellers moving B300-based systems toward China face direct legal exposure, a precedent already set by Taiwan&\#x27;s August 2026 indictment of an Nvidia manager accused of unlocking B300 servers for diversion. Because the B300 is classified under ECCN 3A090.a — the strictest US export-control category for advanced chips — there is effectively no lawful path for state-linked Chinese deployments, so companies financing or reselling China-bound AI servers should expect tightened end-user verification and closer scrutiny of procurement documentation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tftc.io/nvidia-blackwell-chinese-state-financing-export-controls">Nvidia Blackwell Chips Tied to Chinese State Financing · TFTC</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/chinese-state-funds-backed-purchases-215942410.html?fr=sycsrp_catchall">Chinese state funds backed purchases of restricted Nvidia AI ...</a></li>
<li><a href="https://qz.com/chinese-state-firm-nvidia-blackwell-chip-purchases-100226">Chinese state firm financed restricted Nvidia Blackwell chip ...</a></li>
<li><a href="https://www.techtimes.com/articles/325419/20260825/nvidia-manager-unlocked-b300-server-diversion-china-taiwan-indictment-says.htm">Nvidia Manager Unlocked B300 Server Diversion To China ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#AI hardware`, `#semiconductors`, `#China`

---

<a id="item-tech-news-6"></a>
### [NVIDIA&\#x27;s OpenShell proposes a sandboxed runtime for autonomous AI agent fleets](https://github.com/NVIDIA/OpenShell) ⭐️ 7.0/10

OpenShell, a GitHub-published runtime under NVIDIA&\#x27;s organization, is designed to let fleets of autonomous AI agents read files, install packages, call APIs, and use credentials while restricting their access to data, secrets, and networks. It appeared on Hacker News on October 22, 2026, drawing roughly 300 points and 160 comments. The discussion reflects interest in the problem but also skepticism: no source content beyond the launch link was available, so the tool&\#x27;s actual capabilities and the strength of its security claims could not be independently verified.

hackernews · niemandhier · Oct 22, 17:44 · [Discussion](https://news.ycombinator.com/item?id=50198675)

**「Background」** OpenShell is an Apache-2.0 licensed open source runtime published under NVIDIA&\#x27;s GitHub organization that sandboxes autonomous AI agents, controlling their access to files, credentials, and networks through policies and credential brokering. It addresses a known tension in agentic AI engineering: agents are most useful when they can install packages, call APIs, and use credentials, but each of those capabilities widens the attack surface for mistakes or exfiltration of sensitive data, which many teams have so far handled ad hoc with containers and network proxies.

**「What it changes for agent operators」** Teams running coding agents can add enforced isolation without rewriting their stacks: NVIDIA&\#x27;s pages state that agents such as Claude Code, Codex, and OpenClaw run unmodified while OpenShell enforces filesystem, network, and process controls with an audit trail of every allow and deny decision, with enforcement kept outside the agent workload. This positions it as a management layer over the container sandboxing many practitioners already treat as mandatory — one commenter said anyone not running agents in containers is &quot;crazy&quot; but called OpenShell a good way to manage them. A reported caveat for adopters: a commenter who uses a network-restriction proxy noted that restricting agents to trusted domains still does not prevent exfiltration of the codebases they work on, so policy enforcement alone does not make an agent fully trustworthy.

**「Community Discussion」** Commenters split between practical sandboxing advice and doubt about the pitch: one user \(smallnix\) argued the framing obscures a trade-off — more capability means more risk — and that the description overpromises, while another \(mfro\) said anyone running agents should already be using containers and viewed OpenShell mainly as a way to manage them. A commenter identifying as an OpenShell user \(razuba\) reported building a policy layer on top for team policies, safe git usage, and SCA/SAST scanning, noting that unrestricted goal-seeking agent behavior is real, and fennecbutt described using an external network proxy for domain restrictions and credential swapping, with codebase exfiltration remaining an unsolved risk.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/NVIDIA/OpenShell">GitHub - NVIDIA / OpenShell : OpenShell is the safe, private runtime ...</a></li>
<li><a href="https://www.intelligenthq.com/nvidia-ecosystem/products/openshell/">NVIDIA OpenShell : secure runtime for AI agents ... | IntelligentHQ</a></li>
<li><a href="https://nvidia-openshell.com/">OpenShell</a></li>
<li><a href="https://build.nvidia.com/openshell">NVIDIA OpenShell</a></li>

</ul>
</details>

**Tags**: `#ai-agents`, `#security`, `#sandboxing`, `#containers`, `#open-source`

---

<a id="item-tech-news-7"></a>
### [Getting ready to operate GNU Taler in Germany](https://www.taler.net/en/news/2026-13.html) ⭐️ 7.0/10

GNU Taler, an open-source privacy-preserving payment system, is preparing for real-world operation in Germany, prompting community debate over e-money expiration, KYC constraints, and Europe&\#x27;s need for independent payment infrastructure.

hackernews · dewey · Oct 22, 16:14 · [Discussion](https://news.ycombinator.com/item?id=50197404)

**Tags**: `#digital-payments`, `#privacy`, `#gnu-taler`, `#open-source`, `#regulation`

---

<a id="item-tech-news-8"></a>
### [eMudhra to exit global SSL/TLS certificate business](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

Certificate authority eMudhra has announced it will exit the global SSL/TLS certificate business. The announcement follows a mis-issuance incident, apparently involving weak private keys, that drew heavy scrutiny from the browser and web trust community, including a public question battery from the Chrome team filed on Mozilla&\#x27;s bug tracker. The company says its global SSL/TLS infrastructure runs separately from its other operations, and comments in the announcement suggest scrutiny of the incident has been intense relative to SSL/TLS&\#x27;s place in eMudhra&\#x27;s overall business. Details such as timelines and the exact cause of the incident are not fully documented in the available material.

hackernews · bo0tzz · Oct 22, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50195110)

**「The weak-key incident behind the exit」** eMudhra&\#x27;s exit follows a mis-issuance incident in which eight of its intermediate CA private keys turned out to be trivially small integers — all below 256, with one literally the number 4 — which researchers recovered by brute force in milliseconds. The same weak keys appeared in certificates issued both by eMudhra and cross-signed by Sectigo, covering TLS and code-signing purposes, and the case was handled publicly in Mozilla&\#x27;s Bugzilla \(bug 2083449\), where the Chrome team submitted a pointed public question battery. Researchers have also shown the risk extends beyond browsers, reproducing a man-in-the-middle scenario in which a compromised CA key could let an attacker impersonate cloud services to an appliance that validates them against the system trust store.

**「What it means for certificate holders」** Organizations and developers relying on eMudhra-issued SSL/TLS certificates will need to plan migration to another certificate authority, since the company is winding down its global SSL/TLS operations. Site operators should monitor eMudhra&\#x27;s official guidance on certificate lifetimes and replacement, as browsers may also impose restrictions on affected CAs independent of the company&\#x27;s exit.

**「Community reaction」** Commenters were sharply critical of eMudhra&\#x27;s handling of the incident. \[rdtsc\] argued that the scrutiny reflects the severity of the weak keys involved and said the company&\#x27;s failure to clearly apologize or explain the root cause made the situation look worse, while \[rahimnathwani\] questioned the company&\#x27;s claim that no end entity certificates were issued from the affected CAs. Others, including \[Toutouxc\], suggested the company&\#x27;s own statements compounded the damage, and \[ieie3366\] pointed to the Chrome team&\#x27;s public question battery as evidence of the intensity of vendor scrutiny.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/frankchu/eight-ca-private-keys-were-integers-under-256-i-recovered-all-eight-in-11-milliseconds-4o1f">Eight CA private keys were integers under 256.... - DEV Community</a></li>
<li><a href="https://scotthelme.co.uk/eight-bits-of-trust-emudhras-ca-keys-cracked-in-milliseconds/">Eight Bits of Trust; eMudhra &#x27;s CA keys cracked in milliseconds</a></li>
<li><a href="https://github.com/miilv/ya-station-root-shell">miilv/ya-station-root-shell: Full chain reproduction: eMudhra CA MITM...</a></li>

</ul>
</details>

**Tags**: `#TLS/SSL`, `#PKI`, `#certificate-authorities`, `#web-security`, `#browser-trust`

---

<a id="item-tech-news-9"></a>
### [Arc browser winds down as users migrate to Zen and Orion](https://arc.net/) ⭐️ 7.0/10

The Arc browser&\#x27;s development is ending, according to a Hacker News thread bidding farewell to the alternative browser known for its novel UX and built-in AI features. The team behind Arc had already pivoted to Dia, an AI-focused browser; one commenter stated the company was acquired by Atlassian for $610 million and that Arc development was halted in Dia&\#x27;s favor. Users in the thread are weighing migration paths, chiefly Zen — a Firefox-based browser that borrows Arc cues like sidebar tabs, pinned versus generic tabs, global bookmarks, and spaces — and Orion, a WebKit-based browser with similar vertical tabs and page-modification features.

hackernews · suhdonghwi · Oct 22, 16:27 · [Discussion](https://news.ycombinator.com/item?id=50197601)

**「From Arc to Dia」** Arc was developed by The Browser Company of New York, which halted active feature development on the browser in 2025 to concentrate on Dia, its AI-focused successor, acknowledging that Arc&\#x27;s unconventional interface was prized by early adopters but that its complexity and &\#x27;novelty tax&\#x27; constrained wider adoption. In September 2025, Atlassian entered an agreement to acquire The Browser Company for $610 million, bringing the team behind both Arc and Dia under its ownership.

**「What it means for users」** Arc users need to pick a successor, and the popular suggestions carry trade-offs: Zen replicates Arc&\#x27;s sidebar tabs, pinned tabs, global bookmarks, and spaces but runs on Firefox rather than Chrome, which one commenter flagged as mattering for some workflows, while Orion offers vertical tabs and page modification on WebKit but is not open source. Staying with the same company&\#x27;s Dia may not work either — one longtime Arc user reports its profiles are a poor substitute for spaces and cannot share favorite tabs across profiles, a dealbreaker for tabs kept open all day.

**「Community reaction」** Commenters broadly treated the end as long expected, saying the writing was on the wall once the company pivoted to Dia. The most substantive debate centered on alternatives: one commenter endorsed Orion for being built by Kagi as a bootstrapped, non-VC-backed business that charges for a service rather than making customers the product, while conceding its closed-source code is a major blow in a landscape where, in their view, few browsers are truly open source.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/10/22/arc-browser-sunsets-december-22-as-the-browser-company-doubles-down-on-dia/">Arc browser sunsets December 22 as The Browser Company ...</a></li>
<li><a href="https://www.atlassian.com/blog/company-news/atlassian-acquires-the-browser-company">Welcoming The Browser Company to Atlassian</a></li>
<li><a href="https://www.kucoin.com/news/flash/the-browser-company-to-discontinue-arc-on-december-22-2026-shifting-focus-to-ai-powered-dia">The Browser Company to Discontinue Arc on December ... - KuCoin</a></li>

</ul>
</details>

**Tags**: `#web-browsers`, `#arc-browser`, `#ai-browsers`, `#browser-alternatives`, `#tech-industry`

---

<a id="item-tech-news-10"></a>
### [pwn.watch tracks actively exploited vulnerabilities in real time](https://pwn.watch/) ⭐️ 7.0/10

pwn.watch, a live dashboard that tracks actively exploited security vulnerabilities in real time, drew substantial attention in an October 22, 2026 Hacker News discussion that reached 346 points and 161 comments. The site aggregates ongoing exploitation incidents and is positioned as a prioritization resource for engineers handling patching and threat response. Commenters flagged a categorization weakness: one reported that a Signal vulnerability \(CVE-2026-113380\) remained labeled &quot;Live&quot; and &quot;ongoing&quot; more than a month after its patch was released, and the item&\#x27;s analysis characterizes the site as a useful aggregator that lacks the technical depth of a dedicated deep-dive.

hackernews · mrkd · Oct 22, 14:08 · [Discussion](https://news.ycombinator.com/item?id=50195543)

**「Background」** pwn.watch publishes its tracking as daily digests; the October 22, 2026 digest listed 2 new and 13 updated incidents, including CVE-2026-110264, a CVSS 10.0 integer overflow in the regex compiler bundled with self-managed GitLab that allows unauthenticated code execution on every CE/EE release from 7.0 \(2014\) onward and was patched by GitLab on October 21. One incident that figured in the discussion, CVE-2026-113380 in Signal&\#x27;s RingRTC library, was disclosed on October 20, 2026 with a 9.3-out-of-10 CVSS 4.0 score and affects RingRTC versions before 2.72.0, which can leave a call&\#x27;s audio channel open after the user ends the call.

**「Impact for security teams」** For security and patch-management teams, pwn.watch offers a free, real-time view of which vulnerabilities are being exploited in the wild — timely for prioritization, since CISA added 245 actively exploited CVEs to its KEV catalog in 2025, 31 of them tied to ransomware. However, commenters found its status labels unreliable, with one incident still marked &quot;ongoing&quot; more than a month after its patch was released, so teams should verify an incident&\#x27;s actual state against vendor advisories or CISA KEV before acting on the dashboard alone.

**「Community reaction」** Commenter aeturnum questioned the tracker&\#x27;s incident lifecycle, asking when an incident is ever considered over if a Signal vulnerability \(CVE-2026-113380\) stays &quot;ongoing&quot; roughly 1.5 months after its patch, while others argued exploitation rates are climbing sharply, with one claiming this generation of LLMs will drive &quot;the largest wave of security incidents the world has ever seen.&quot; Another participant described pwn.watch as complementary to their own CVE severity timeline site, supplychain.fail.

<details><summary>References</summary>
<ul>
<li><a href="https://pwn.watch/d/2026-10-22">Oct 22, 2026 : 2 new, 13 updated · pwn.watch</a></li>
<li><a href="https://1275.ru/vulnerability/ochered-sobytiy-vyzovov-signal-dopuskaet-proslushivanie-posle-zaversheniya-zvonka_49184">Очередь событий вызовов Signal допускает прослушивание после...</a></li>
<li><a href="https://www.securitylab.ru/news/579109.php">В Signal нашли способ слушать человека даже после попытки...</a></li>
<li><a href="https://osint.foundation/cve/year/2025">Exploited Vulnerabilities of 2025 : 245 CVEs Added to CISA KEV</a></li>

</ul>
</details>

**Tags**: `#security`, `#threat-intelligence`, `#vulnerability-tracking`, `#cybersecurity`, `#incident-response`

---

<a id="item-tech-news-11"></a>
### [Anthropic Donates Agent Skills Standard to the Agentic AI Foundation](https://simonwillison.net/2026/Oct/22/donating-agent-skills/) ⭐️ 7.0/10

Anthropic has announced it is donating its Agent Skills standard to the Agentic AI Foundation \(AAIF\), a vendor-neutral body under the Linux Foundation that Anthropic co-founded with Block and OpenAI and to which it previously donated the Model Context Protocol \(MCP\). The move places the skills format — which Anthropic first declared an &quot;open standard&quot; in December 2025 — under community-driven governance alongside MCP. Simon Willison, whose post reports the announcement, noted he predicted this outcome last December when the standard was first labeled open. The post quotes Anthropic&\#x27;s statement but does not describe any technical changes to the specification itself for developers already using skills.

rss · Simon Willison · Oct 22, 18:09

**「Agent Skills and the AAIF」** Anthropic first labeled Agent Skills an open standard in December 2025, when Simon Willison speculated that the specification might eventually end up in the Agentic AI Foundation. The AAIF was co-founded by Anthropic with Block and OpenAI in 2025 under the Linux Foundation and already serves as the home of the Model Context Protocol \(MCP\) specification, which Anthropic previously donated to the foundation.

**「Impact」** Developers using Agent Skills — the open standard for packaging specialized agent knowledge and workflows — now have the format governed by the vendor-neutral Agentic AI Foundation under the Linux Foundation, the same body that already stewards MCP, rather than by Anthropic alone. That reduces the risk of unilateral spec changes or vendor lock-in for teams building skills-based agents, who can now follow or contribute to the standard&\#x27;s evolution through AAIF&\#x27;s community-driven process.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/news/donating-agent-skills-to-the-agentic-ai-foundation">Donating Agent Skills to the Agentic AI Foundation \ Anthropic</a></li>
<li><a href="https://blockchain.news/news/anthropic-donates-agent-skills-standard-to-aaif">Anthropic donates Agent Skills standard to AAIF - blockchain.news</a></li>

</ul>
</details>

**Tags**: `#agent-skills`, `#agentic-ai`, `#open-standards`, `#anthropic`, `#linux-foundation`

---

<a id="item-tech-news-12"></a>
### [Carbon-X: open 14.8B model trained jointly on DNA and text](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

Carbon-X, a 14.8B-parameter decoder-only model, is available under Apache 2.0 on Hugging Face \(HuggingFaceBio/Carbon-X\), handling raw DNA and English text in a single shared token stream of 6-mer tokens after mid-training on 302B tokens. Its model page reports a 66.7% average across five DNA benchmarks with thinking disabled, versus 67.5% for GPT-6.1 Sol, a comparison that is self-reported and not independently verified. The bfloat16 weights fit on a single 80GB GPU, enabling fully local sequence analysis on sensitive genomic datasets. The model has not been clinically validated, the model card says exact sequence operations should still be handled by code, and the poster acknowledges the benchmark gains have not been tested on private variant datasets.

reddit · r/MachineLearning · /u/jatingargiitk · Oct 22, 12:32

**「Background」** DNA language models read nucleotide sequences as overlapping k-mer tokens — 6-mers in this case — rather than words, which is what allows sequence data and English text to share a single vocabulary. Rather than training from scratch, Carbon-X was mid-trained from the existing open text model Qwen3-14B, adding 302B tokens of training at a sequence length of 8,192 with a global batch of 512 sequences.

**「Practical impact」** Organizations handling sensitive genomic data can run DNA sequence question-answering entirely on-premises: the Apache-2.0 weights are on Hugging Face and fit on a single 80 GB GPU in bfloat16, so patient or variant sequences need not be sent to a hosted API. Treat the benchmark numbers as preliminary — the 66.7% average across five DNA benchmarks \(versus 67.5% for GPT-6.1 Sol\) is self-reported, the model is not clinically validated, the model card directs exact sequence operations to code, and the poster himself asks whether the gains hold on private variant datasets. For developers benchmarking it against earlier genomic foundation models, the 6-mer token stream matches a scheme existing DNA-LM harnesses such as BEND already handle, repeating each 6-mer embedding across the six positions it covers.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/HuggingFaceBio/Carbon-X">HuggingFaceBio/Carbon-X · Hugging Face</a></li>
<li><a href="https://www.llmreference.com/model/carbon-x">Carbon-X – 40K context, open source | LLM Reference</a></li>
<li><a href="https://github.com/frederikkemarin/BEND">frederikkemarin/BEND: Benchmarking DNA Language Models on...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#genomics`, `#DNA-language-models`, `#open-source-models`, `#model-release`

---

<a id="item-tech-news-13"></a>
### [Australian court orders Apple to open iPhone to third-party app stores](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

Australia&\#x27;s Federal Court has ruled that Apple must allow iPhone users in Australia to install apps through third-party app stores and websites, and must permit alternative payment methods and external payment links, starting March 1, 2027. The ruling came in Epic Games&\#x27; antitrust suit, in which the judge found that Apple holds substantial market power in iOS app distribution and payments and that its restrictions violate Australian competition law. Fortnite is returning to the Australian App Store immediately. Apple says it will appeal and apply for a stay, so the mandated changes are not yet in effect.

telegram · zaihuapd · Oct 22, 06:54

**「Background」** The case is the Australian front of Epic Games&\#x27; years-long antitrust battle with Apple, which began in 2020 when Fortnite was pulled from the App Store after Epic added a direct-payment option that bypassed Apple&\#x27;s in-app purchase commission. Justice Jonathan Beach of the Federal Court had already issued a liability finding in August that Apple&\#x27;s control over iOS app distribution and payments violates Australian competition law, and this week&\#x27;s orders are the remedies phase of that case. The change gives Australia a regime similar to what Apple already operates in the European Union, where the Digital Markets Act has required support for alternative app stores and external payment options on iPhones since 2024.

**「What it means」** If the ruling survives appeal, Australian developers could distribute iOS apps outside the App Store and use alternative payment channels from March 1, 2027. Because Apple is appealing and seeking a stay of the order, developers should treat that deadline as unsettled until the court decides whether the changes take effect on schedule.

<details><summary>References</summary>
<ul>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">Apple must open iPhone to alternative app stores in Australia ...</a></li>
<li><a href="https://smbtech.au/news/federal-court-orders-apple-to-allow-rival-app-stores-and-payments-on-iphones-in-australia/">Federal Court Orders Apple To Allow Rival App Stores And ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#antitrust`, `#app-store regulation`, `#Epic Games`, `#iOS`

---

<a id="item-tech-news-14"></a>
### [miHoYo and Tsinghua open-source GameScaling keyboard/mouse game-control models](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

miHoYo&\#x27;s Honkai AI team, working with Tsinghua University and other collaborators, has open-sourced GameScaling, a family of vision-language models built on Qwen3.5 and continued-pretrained for keyboard-and-mouse game control, spanning 0.8B to 27B parameters. Each model outputs the keyboard and mouse actions for the next 200 milliseconds. Eight checkpoints and an inference client are released under the Apache-2.0 license, but the release does not include training code. The accompanying paper reports a scaling study across 120 training configurations, finding that more data improves performance in the same game, that data diversity helps transfer to similar games, and that gains are limited for substantially different game worlds.

telegram · zaihuapd · Oct 22, 11:32

**「Built on Qwen3.5 via continued pre-training」** GameScaling is not a from-scratch model: its Hugging Face and GitHub documentation describes the released checkpoints as Qwen3.5 vision-language models — models that process both images and text — adapted through continued pre-training on keyboard-and-mouse gameplay. Each inference call takes the current game frame plus a short history of past frames and actions, and returns the next 200 milliseconds of control output, structured as six 33-millisecond action steps plus one mouse movement and scroll for the whole chunk; the model may also emit a brief reasoning step before acting.

**「Impact」** Game AI and computer-use developers can start using the release immediately: the eight Apache-2.0 checkpoints \(0.8B–27B\) and the inference client allow running or fine-tuning models for millisecond-scale keyboard/mouse control without licensing restrictions. However, because the training code is excluded and the training corpus is not released, teams cannot reproduce the 120-configuration scaling results from scratch and must supply their own data for any further training. The reported findings also bound expectations for adopters: data diversity aids transfer to games similar to the training distribution but yields limited gains on very different game worlds, so the checkpoints should be validated on a specific title before deployment.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/THUSI-Lab/GameScaling">THUSI-Lab/GameScaling · Hugging Face</a></li>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/GameScaling: Scaling in Games: Continued ...</a></li>
<li><a href="https://gamescaling.github.io/">Scaling in Games : Continued Pre-Training for Embodied Agents in...</a></li>

</ul>
</details>

**Tags**: `#vision-language-models`, `#game-ai-agents`, `#open-source-models`, `#scaling-study`, `#computer-use`

---

<a id="item-tech-news-15"></a>
### [Oracle patches critical pre-auth Java SE TLS vulnerability CVE-2026-91403](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

Oracle has issued a critical security alert and released patches for CVE-2026-91403, a vulnerability scoring 9.1 on the CVSS scale in the Java SE JSSE \(TLS\) component that attackers can exploit remotely over the network without authentication, with potential impact on data confidentiality and integrity. Affected releases span Java SE 8u511, 11.0.33, 17.0.21, 21.0.13, 25.0.5, and 27.0.1, as well as multiple GraalVM versions. Fixes are already available, and Oracle urges users to upgrade to supported versions promptly to guard against potential attacks. The advisory itself is brief and offers no exploit details or mitigation guidance beyond upgrading.

telegram · zaihuapd · Oct 22, 12:30

**「Background」** JSSE \(Java Secure Socket Extension\) is the JDK component that implements TLS, the protocol Java applications rely on to encrypt and authenticate network connections, so it sits in front of nearly every Java service that accepts network traffic. Because TLS handshakes take place before any application-level login, a flaw at this layer can be reached by anyone able to open a connection to a vulnerable service, which is what Oracle&\#x27;s &quot;remotely exploitable without authentication&quot; designation reflects. GraalVM appears in the alert because it is Oracle&\#x27;s JDK distribution and polyglot virtual machine whose Java runtime ships the same JSSE component as Java SE.

**「Patch affected Java and GraalVM runtimes immediately」** Any deployment running the affected releases—Java SE 8u511, 11.0.33, 17.0.21, 21.0.13, 25.0.5, or 27.0.1, as well as GraalVM for JDK and GraalVM Enterprise Edition—carries a JSSE \(TLS\) vulnerability that is remotely exploitable without authentication, with a CVSS 3.1 base score of 9.1 and high confidentiality and integrity impacts, meaning unpatched Java TLS endpoints are directly exposed to network attackers. The immediate action is to apply Oracle&\#x27;s released patches or upgrade to a supported version; teams running OpenJDK-based distributions should verify their vendor build includes the fixes from OpenJDK&\#x27;s 2026/10/21 vulnerability advisory.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oracle.com/security-alerts/alert-cve-2026-91403.html">Oracle Security Alert Advisory - CVE - 2026 - 91403</a></li>
<li><a href="https://www.oracle.com/security-alerts/cve-2026-91403verbose.html">Text Form of Security Alert CVE - 2026 - 91403 Risk Matrices</a></li>
<li><a href="https://openjdk.org/groups/vulnerability/advisories/2026-10-21">OpenJDK Vulnerability Advisory: 2026 /10/21</a></li>

</ul>
</details>

**Tags**: `#security`, `#java`, `#vulnerability`, `#oracle`, `#tls`

---

<a id="item-tech-news-16"></a>
### [333 Tor Exit Relays Found Running Ebury Backdoor, Taken Offline](https://kaba.cx/posts/20261020_Tor/) ⭐️ 7.0/10

A Tor operator&\#x27;s script scan of roughly 3,000 exit relays identified 333 — about 10% — running the Ebury SSH backdoor, which hijacked users&\#x27; port-22 connections to 12 interception servers to steal credentials. The affected relays were flagged BadExit on October 4 and taken offline the following day. According to the report, the attackers had compromised the servers in August and blocked some ports to concentrate on collecting unencrypted email traffic; the intrusion vector remains undetermined. The findings come from a community blog post rather than a primary Tor Project announcement, so the figures reflect a single operator&\#x27;s report.

telegram · zaihuapd · Oct 22, 14:52

**「Ebury: a decade-old SSH backdoor」** Ebury is a long-lived OpenSSH backdoor and credential stealer first documented by ESET in March 2014 during Operation Windigo, a Linux malware campaign that compromised more than 10,000 servers to steal SSH credentials and redirect visitors to malicious content. ESET researchers later reported the malware was still being updated, with roughly 400,000 Linux servers compromised for cryptotheft and other financial gain. This history means the backdoor found on the Tor exit relays is a known, persistent threat rather than a newly developed strain.

**「Impact」** Anyone who routed SSH logins or unencrypted email through Tor between October 1 and 5, 2026 should treat those credentials as compromised: the backdoored relays rewrote their torrc files to redirect port-22 traffic to interception servers and at peak carried 7.46% of Tor&\#x27;s exit capacity, so rotating passwords and SSH keys used over Tor in that window is the concrete protective step. The BadExit flag now bars the 333 relays from serving as exits, but it does nothing to recover credentials already harvested.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2014/03/operation-windigo-linux-malware.html">Operation Windigo : Linux malware campaign that infected 500,000...</a></li>
<li><a href="https://www.welivesecurity.com/en/eset-research/ebury-alive-unseen-400k-linux-servers-compromised-cryptotheft-financial-gain/">Ebury is alive but unseen: 400k Linux servers compromised for...</a></li>
<li><a href="https://x.com/DFIR_Radar/status/2112877196448542778">DFIR Radar on X: &quot;Ebury-linked actors hijacked 333+ Tor exit ...</a></li>
<li><a href="https://cybersecuritynews.com/hackers-hijack-333-tor-exit-nodes/">Hackers Hijack 333 Tor Exit Nodes to Intercept SSH Logins and ...</a></li>
<li><a href="https://arstechnica.com/information-technology/2026/10/300-tor-exit-nodes-hijacked-to-intercept-ssh-traffic-and-retrieve-plaintext-email/">333 Tor exit nodes hijacked to intercept SSH traffic and ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#tor`, `#malware`, `#ebury`, `#privacy`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why rewriting software in faster languages rarely makes it faster](https://seangoedecke.com/software-is-slow-because-of-bad-design-not-slow-languages/) ⭐️ 7.0/10

rss · Sean Goedecke · Oct 23, 00:00

**「Background」** A popular claim holds that AI will make software faster by rewriting everything in C or Rust, but Sean Goedecke counters that most real programs are I/O-bound—waiting on databases, APIs, or disk—so language speed is rarely the bottleneck.

**「Solution」** On a typical CRUD website, roughly half of each request goes to database queries, so a C rewrite can only accelerate the other half—Amdahl&\#x27;s law caps the gain at 2x, nearer 1.5x in practice. For genuinely CPU-bound work, slow languages already delegate hot paths to fast ones: wikis render markdown through cmark-gfm, and Python thrives in machine learning because matrix multiplications already run in optimized C or assembly. Programs that remain CPU-bound in slow languages are, he claims, usually unimportant—otherwise someone would have optimized them already. Even the standout exception, Actual Computer&\#x27;s assembly rewrite of tiktoken \(about 5x faster on his laptop\), he attributes largely to redesigning away a regex dependency rather than language choice. Even CPU-bound performance is design-dominated: Bryan Cantrill&\#x27;s 2018 account of naively rewriting an optimized C program in Rust—30% faster, thanks to a cache-friendlier B-tree—is his key evidence. The speedups Goedecke has actually won—caching, background jobs, parallelism, fixing N+1 queries, skipping unneeded work—are language-independent, and high-level code makes such inefficiencies easier to spot than assembly would.

**「Takeaway」** Ask AI agents to profile and redesign programs to do less work, he concludes, reserving language rewrites for rare, truly CPU-bound hotspots. Rewrites still make sense for portability or maintainability—just not for raw speed.

**Tags**: `#performance`, `#software-design`, `#programming-languages`, `#optimization`, `#ai-agents`

---

## Financial News

<a id="item-finance-news-1"></a>
### [沪深 300 较 6 月高点回落 20%，A 股逼近熊市](https://www.bloomberg.com/news/articles/2026-10-22/china-stocks-set-for-bear-market-as-ai-trade-policy-hopes-fade) ⭐️ 7.0/10

China&\#x27;s CSI 300 has dropped 20% from its June high, pushing A-shares to the brink of a bear market amid absent fiscal stimulus and earnings misses led by CATL&\#x27;s 12% plunge.

telegram · zaihuapd · Oct 22, 05:05

**Tags**: `#China equities`, `#bear market`, `#CSI 300`, `#CATL earnings`, `#fiscal stimulus`

---