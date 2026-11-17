---
layout: default
title: "Horizon Summary: 2026-11-17 (EN)"
date: 2026-11-17
lang: en
---

> From 48 items, 15 important content pieces were selected

---

**Technology News**
1. [vLLM v0.34.0 defaults to extensible KV cache, drops Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Optimizely supply-chain compromise served malware to Zoom, GitLab, CNN, and BBC visitors](#item-tech-news-2) ⭐️ 8.0/10
3. [Jiff 1.0: Rust datetime library reaches stable release](#item-tech-news-3) ⭐️ 8.0/10
4. [Carnegie Mellon launches CS Learn, free full CS courses on YouTube](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows 11 Reportedly Collects Telemetry on Which Coding Agents Developers Run](#item-tech-news-5) ⭐️ 7.0/10
6. [Technical issue at JPMorgan Chase disrupts online banking at Wells Fargo and Truist](#item-tech-news-6) ⭐️ 7.0/10
7. [Microsoft blames mass email outage on defect introduced in July fix](#item-tech-news-7) ⭐️ 7.0/10
8. [US and Nine Partners Sign San Francisco Declaration to Secure Superintelligence Supply Chains](#item-tech-news-8) ⭐️ 7.0/10
9. [Amazon: Artex-driven AI agents stole API keys to fund LLM usage](#item-tech-news-9) ⭐️ 7.0/10
10. [US extends AI chip export controls to remote access, adds five-country licensing](#item-tech-news-10) ⭐️ 7.0/10
11. [Chinese AI firms curb offensive cyber capabilities; Qwen flagship no longer open-weight](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [ETF experts say Nvidia turmoil and a Democratic Congress could reshape the AI trade](#item-finance-news-1) ⭐️ 8.0/10
2. [Eric Trump-backed robot soldier startup can&\#x27;t pay staff after founder borrowed $4.6 million from company to buy home](#item-finance-news-2) ⭐️ 7.0/10
3. [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](#item-finance-news-3) ⭐️ 7.0/10
4. [英特尔及 CEO 陈立武遭股东集体诉讼](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 defaults to extensible KV cache, drops Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0, published November 16, 2026, enables extensible KV cache sizing by default on CUDA and ROCm: the cache is now sized from memory actually free after CUDA graph capture and warmup rather than an estimate, which the project says grew the cache for MiniMax-M3 on H200 from 433k to 672k tokens and raised throughput, at the cost of 6–18% higher per-token decode latency \(TPOT\) on some H200 models at concurrency 128. The release removes the V1 GPU model runner so Model Runner V2 is the only GPU path, adds 10 model integrations including Mistral Large 4 \(1T total/52B active parameters\), MiniMax-M3.1-Flash, and NVIDIA Nemotron-3.5-Transcribe, and reports speedups of up to 1.95× decode on 4×GB200 \(Step5 NVFP4 MoE\), 1.6× output throughput for GLM-5.3-Flash, and 1.24–1.40× faster long-prompt TTFT for GLM-5.3 — performance figures that are project-reported, not independently verified. Upgraders face multiple breaking changes: the default block size is now 64 \(was 16\), ROCm 7.2 images and wheels are dropped in favor of ROCm 10.0 only, huggingface\_hub &gt;= 2.0.0 is required \(along with tokenizers &gt;= 0.23.3 and timm &gt;= 1.0.30\), and QuTLASS/fp\_quant plus Marlin W4A8 quantization paths were removed. The release spans 1,061 commits from 412 contributors, 120 of them new.

github · khluu · Nov 16, 23:22

**「Background」** vLLM is an open-source engine for serving large language models on GPUs, and its GPU execution path — the &quot;model runner&quot; — had been migrating from a V1 implementation to a newer V2 that operators could previously keep off by setting \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\`. Its KV cache, the GPU memory pool that stores attention states and effectively caps how many tokens a deployment can serve, was previously sized from a fixed \`gpu\_memory\_utilization\` fraction \(default 0.9\) rather than from memory actually free after warmup, and the default attention block size was 16.

**「What operators should do before upgrading」** Existing deployments can break on upgrade unless operators adjust their launch configurations: pass --block-size 16 to keep the old paging behavior, pass --gpu-memory-utilization 0.9 or --no-enable-extensible-kv-cache to keep the old cache sizing \(gpu\_memory\_utilization now defaults to 1.0\), and remove VLLM\_USE\_V2\_MODEL\_RUNNER=0, which now fails at startup. Code depending on V1 logits processors must be ported to vllm.v1.worker.gpu.sample.logits\_processor, fp\_quant checkpoints no longer load, and Marlin W4A8 users must switch to --quantization humming with VLLM\_HUMMING\_INPUT\_QUANT\_CONFIG instead of VLLM\_MARLIN\_INPUT\_DTYPE. ROCm users must move to the ROCm 10.0 wheels and images, as -rocm72 artifacts are no longer published.

**Tags**: `#vllm`, `#llm-inference`, `#kv-cache`, `#gpu-performance`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Optimizely supply-chain compromise served malware to Zoom, GitLab, CNN, and BBC visitors](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 8.0/10

Optimizely, a widely deployed third-party JavaScript provider, was compromised in a supply-chain attack that served malware to visitors of major customer sites including Zoom, GitLab, CNN, and BBC. According to Report URI&\#x27;s analysis, Optimizely&\#x27;s CDN delivered exactly what it was given — this was not a cache-poisoning attack — and the malicious code also ran on Optimizely&\#x27;s own pages, with the snippets for www.optimizely.com and login.optimizely.com both carrying it. How the attacker obtained write access to so many unrelated customer projects remains unexplained, and the available reporting does not establish what the malware was designed to do.

hackernews · kristjansson · Nov 16, 23:00 · [Discussion](https://news.ycombinator.com/item?id=50524767)

**「Background」** Optimizely Web is a widely used A/B testing and experimentation platform whose JavaScript snippet customers embed directly in their pages, meaning any code Optimizely&\#x27;s CDN serves executes in visitors&\#x27; browsers on every site that loads it. In this incident, the injected code functioned as a cryptocurrency clipper and card skimmer — swapping copied wallet addresses and capturing card details typed into affected pages — with the malicious payload served from the domain 1688360\[.\]cc. This illustrates the structural risk of third-party tags: because they load from the vendor&\#x27;s infrastructure rather than the publisher&\#x27;s own servers, a single vendor-side compromise can expose many unrelated major websites simultaneously.

**「Visitor exposure and required response」** Visitors who loaded pages on the 178 affected sites — including Zoom, BBC, CNN, Salesforce, GitLab, and HSBC — during the November 16 exposure window were served a payment-card skimmer, a cryptocurrency wallet-address swapper, and iOS-targeted exploit code from Optimizely&\#x27;s trusted CDN, so anyone who entered card details or sent crypto on those sites during the incident should treat those transactions as potentially intercepted. Organizations using Optimizely Web should audit their projects for the injected loader, which Optimizely has attributed to a flaw in its Web Experimentation product, and verify what their domains actually served during the window.

**「Community discussion」** In the Hacker News thread, one commenter argued the incident reflects missing accountability, contending that Optimizely should have had release safeguards such as phased rollouts and automated security checks, and that massive-audience sites like CNN and BBC have &quot;zero excuse&quot; not to as well. Another blamed the Google Tag Manager model of letting marketing teams add third-party scripts without engineering involvement, while others pressed unresolved questions — how cross-customer write access was obtained and why sites like CNN or BBC would be targets at all — underscoring that the attack&\#x27;s mechanics and purpose are still unconfirmed.

<details><summary>References</summary>
<ul>
<li><a href="https://cybersecuritynews.com/optimizely-websites-hijacked/">Hackers Infect 178 Major Websites via Optimizely to Steal ...</a></li>
<li><a href="https://www.stepsecurity.io/blog/optimjack-optimizely-hosted-scripts-crypto-clipper-card-skimmer">OPTIMJACK: Optimizely-Hosted Scripts Loaded a Crypto Clipper ...</a></li>
<li><a href="https://shiftdelete.net/en/optimizely-malware">Optimizely Malware Hit 178 Sites: What It Stole and What to Do</a></li>
<li><a href="https://windowsforum.com/news/optimizely-web-javascript-breach-admin-response-to-card-skimming-and-crypto-address-swaps.452629/">Optimizely Web JavaScript Breach: Admin Response to Card ...</a></li>
<li><a href="https://vinish.dev/optimizely-web-experimentation-supply-chain-attack-malicious-javascript">Optimizely Supply Chain Attack: Flaw Put Malicious JavaScript ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/optimizely-malware-hits-zoom-bbc-cnn-what-to-do.html">Optimizely Malware Hits Zoom, BBC, CNN: What to Do</a></li>

</ul>
</details>

**Tags**: `#security`, `#supply-chain-attack`, `#web-security`, `#javascript`, `#third-party-scripts`

---

<a id="item-tech-news-3"></a>
### [Jiff 1.0: Rust datetime library reaches stable release](https://burntsushi.net/jiff/) ⭐️ 8.0/10

Jiff 1.0 marks the stable release of burntsushi&\#x27;s open-source datetime library for Rust, giving developers a modern alternative to the ecosystem&\#x27;s long-standing chrono crate. The library takes on a notoriously difficult problem area — time zones, daylight saving time, and civil time — and its announcement drew a substantial Hacker News discussion \(347 points, 78 comments\).

hackernews · burntsushi · Nov 16, 16:53 · [Discussion](https://news.ycombinator.com/item?id=50519744)

**「Background」** Rust&\#x27;s datetime handling has long been dominated by chrono, whose API has been stable to the point of resisting significant change — the ecosystem gap Jiff was created to fill. Jiff itself is not new code: it previously shipped in 0.x releases, with jiff 0.1 introducing the %Q and %:Q format specifiers for IANA time zone identifiers, and the 1.0 release now commits the library to a stable API. The problem area is notoriously tricky, and Jiff&\#x27;s design puts time zone handling front and center in the API so common daylight saving time pitfalls are handled automatically.

**「Impact for Rust developers」** With a stable 1.0 release, Rust developers can now adopt Jiff as a production datetime dependency offering automatic time zone database integration and daylight saving time-aware calendar arithmetic, with crate features for serde support and optionally embedding the tzdb into the binary. However, the Blessed.rs crate listing notes that Jiff &quot;currently lacks some of the ecosystem integration that time and chrono have,&quot; so teams whose dependencies expose chrono or time types may face conversion friction, making Jiff a strongest fit for new projects or codebases able to standardize on it.

**「Community discussion」** The most substantive comment came from quodlibetor, who maintained chrono for about five years and said he took on the role hoping to fix its API, only to find that chrono&\#x27;s stability — the very reason people used it — meant every improvement attempt met resistance; he said he left over burnout and is grateful burntsushi wrote Jiff. Other commenters split on adoption: some hope Jiff overtakes chrono, one praised the documentation for candidly stating that Jiff &quot;isn&\#x27;t always the right thing to use,&quot; a developer who simulates asteroid orbits asked how Jiff handles alternative time scales such as TAI and UT1, and another argued chrono is already comparatively good and that in Rust they prefer the established crate, though they will try Jiff.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff/releases">Releases · BurntSushi / jiff · GitHub</a></li>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/ jiff : A datetime library for Rust that encourages...</a></li>
<li><a href="https://blessed.rs/">Crate List - Blessed.rs</a></li>

</ul>
</details>

**Tags**: `#rust`, `#datetime`, `#libraries`, `#open-source`, `#api-design`

---

<a id="item-tech-news-4"></a>
### [Carnegie Mellon launches CS Learn, free full CS courses on YouTube](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

Carnegie Mellon has launched CS Learn, a project that releases full semesters of lectures from its current computer science courses free on YouTube, with one course premiering each day this week and more courses arriving in January. The lineup includes Tianqi Chen&\#x27;s ML Systems course, with 15-259 Probability and Computing slated to follow. Phillip Compeau, who teaches in CMU&\#x27;s Griffin School of Computer Science and runs CS Learn, acknowledged that MIT OpenCourseWare pioneered free online courseware 25 years ago, and said the difference lies in production tooling that CMU students built to automate much of the lecture publishing workflow.

hackernews · pcompeau · Nov 16, 20:43 · [Discussion](https://news.ycombinator.com/item?id=50522980)

**「The open-courseware precedent」** Free online university courseware has a clear precedent: MIT began publishing its courses openly about 25 years ago through OpenCourseWare, a lineage CS Learn&\#x27;s lead Phillip Compeau acknowledged in the launch thread \(&quot;MIT got here 25 years ago&quot;\), while pointing to his project&\#x27;s differentiator of student-built tools that automate much of the lecture production. The courses are drawn from CMU&\#x27;s Kenneth C. Griffin School of Computer Science, which the university&\#x27;s launch materials describe as a top-ranked computer science program.

**「What this means for self-learners」** Engineers and self-learners outside CMU can now watch complete current CMU courses for free, including ML systems material that one commenter said pairs well with the mlc.ai book on modern GPU programming for ML systems. Additional courses arrive in January, so viewers looking for a specific subject should check the channel then rather than judging by this week&\#x27;s premieres alone.

**「How the community reacted」** The most substantive argument came from commenter JSR\_FDED, who opined that mastering fundamentals determines whether AI becomes a power tool for a learner or replaces them — a viewpoint, not an established fact. Alumni also treated the thread as a wishlist, requesting courses such as Larry Wasserman&\#x27;s Intermediate Statistics, Dave Andersen&\#x27;s Distributed Systems, and Dave Eckhardt&\#x27;s Operating Systems, while another asked whether type theory or formal methods content is planned; the available launch comment does not answer these requests.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/@CMULearn">CS Learn at Carnegie Mellon - YouTube</a></li>
<li><a href="https://www.pressreleasepoint.com/cmu-opens-access-top-computer-science-classes-through-free-cs-learn-platform">CMU Opens Access to Top Computer Science Classes Through Free ...</a></li>
<li><a href="https://www.youtube.com/c/PhillipCompeauPhD">Phillip Compeau - YouTube</a></li>

</ul>
</details>

**Tags**: `#education`, `#open-courseware`, `#machine-learning`, `#ml-systems`, `#computer-science`

---

<a id="item-tech-news-5"></a>
### [Windows 11 Reportedly Collects Telemetry on Which Coding Agents Developers Run](https://xusheng.dev/posts/windows-coding-agent-telemetry/) ⭐️ 7.0/10

A blog post published on xusheng.dev on November 16, 2026 reports that Windows 11 collects telemetry that can reveal which coding agents and developer tools a user runs, a claim that drew a 393-point, 247-comment Hacker News discussion. The report originates from a personal blog and the available material contains no independent verification or Microsoft response, so the specific telemetry mechanisms, data fields, and affected tools remain unconfirmed.

hackernews · cwaffles · Nov 16, 22:58 · [Discussion](https://news.ycombinator.com/item?id=50524736)

**「Windows telemetry is not new」** Telemetry is not new to Windows: Windows 10 and 11 include telemetry collection that is established enough to have prompted community tools, such as PowerShell-based blockers, built to disable it and its associated services. Developer tooling adds a second layer — Microsoft&\#x27;s VS Code, for example, documents centrally managed telemetry levels and feedback options for enterprise environments. The report that Windows 11 telemetry can reveal which coding agents and developer tools a user runs therefore describes an OS-level channel on top of the tool-level telemetry that developers and enterprises already manage.

**「What developers can do」** Developers who want to limit this data collection have concrete options: the open-source pause-windows-updates utility supports Windows 10 and 11 and includes a function to disable Microsoft telemetry, while teams that use VS Code can centrally manage telemetry levels and feedback options through its enterprise settings. Because the finding comes from a personal blog post rather than an independent audit, developers should verify exactly which telemetry fields Windows 11 collects before reconfiguring their systems.

**「Community reaction」** Commenters split on how alarming the report is: one argued the behavior is not unique to Windows, since Intel, AMD, and NVIDIA drivers also collect executed program names and paths unless users opt out, while another suggested some telemetry could be justified given that Windows launched an agent sandboxing feature only about a month earlier \(October 7, per the comment\) and Claude Code does not yet support it, leaving people running unsandboxed agents or falling back to WSL. Others treated the report as a reason to migrate, reporting that Linux is now viable for daily use and single-player gaming — though multiplayer still has hiccups — and that switching takes roughly a week for web-centric workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/N0tHorizon/WindowsTelemetryBlocker">N0tHorizon/WindowsTelemetryBlocker: A PowerShell based tool to...</a></li>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>
<li><a href="https://github.com/Aetherinox/pause-windows-updates">GitHub - Aetherinox/pause- windows -updates: Pause &amp; disable...</a></li>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#windows`, `#telemetry`, `#developer-tools`, `#ai-coding-agents`

---

<a id="item-tech-news-6"></a>
### [Technical issue at JPMorgan Chase disrupts online banking at Wells Fargo and Truist](https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda) ⭐️ 7.0/10

A technical issue at JPMorgan Chase triggered online banking delays that affected multiple major US banks, including Wells Fargo and Truist, according to AP News coverage published November 16, 2026. The supplied reporting describes the disruption but does not identify a root cause, name the failed systems, or state whether services had been restored.

hackernews · samk3nny · Nov 16, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50521045)

**「Why one bank&\#x27;s fault can look like many banks&\#x27; outage」** Banks transact with one another constantly, so a technical fault at a single institution can make payments to or from that bank fail even when the other banks&\#x27; own systems are working normally. In Monday&\#x27;s incident, the trouble appeared centered on Chase customers and on customers at other banks trying to transact with Chase, while banks including Bank of America and Citigroup reported no problems with their own services. Chase subsequently said the outage was caused by a software bug.

**「Customer impact」** Chase customers reported being unable to use ATM cards or complete transactions at branches during the outage, and the disruption extended to the Zelle money transfer app, which attributed failed payments to problems at partner banks rather than its own systems. Customers seeing issues at other institutions should confirm with their bank directly, since Bank of America and U.S. Bank each stated their systems were not directly impacted despite appearing in outage reports.

**「Community discussion」** In a Hacker News thread that drew about 740 points and 620 comments, users speculated without confirmed evidence about the cause: one compared the incident to October&\#x27;s Revolut outage in Europe, which a linked Revolut post attributed to a Google Cloud failure and said was resolved in about 12 hours, while another argued the banks&\#x27; core processes likely run on decades-old but reliable mainframe stacks such as COBOL, CICS, IMS, and DB/2. Reported experiences stayed anecdotal — a West Coast user found several of the affected banking sites loading normally and suspected an East Coast cloud problem, and one commenter said nontechnical colleagues increasingly view such outages, alongside recent Microsoft 365 and FAA incidents, as symptoms of one interconnected fragility.

<details><summary>References</summary>
<ul>
<li><a href="https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda">Technical issue at JPMorgan Chase triggers online banking delays</a></li>
<li><a href="https://www.thegatewaypundit.com/2026/11/major-banks-experiencing-outages-developing/">Major US Banks Experiencing Outages … Update with Statement from...</a></li>
<li><a href="https://www.nytimes.com/2026/11/16/us/bank-outages-down.html">Chase Bank Transactions Disrupted by ‘Technical Issue’ Amid Outage ...</a></li>
<li><a href="https://nypost.com/2026/11/16/business/outages-hit-chase-bank-of-america-and-wells-fargo-customers/">Big bank customers report outages ; JPMorgan Chase blames...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase , impacted Wells Fargo and BofA</a></li>

</ul>
</details>

**Tags**: `#banking-outage`, `#infrastructure-reliability`, `#mainframes`, `#financial-systems`, `#incident-response`

---

<a id="item-tech-news-7"></a>
### [Microsoft blames mass email outage on defect introduced in July fix](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

Microsoft attributed a large-scale outage of its enterprise email service \(Exchange\) to a software defect introduced by a fix deployed in July, according to a November 16, 2026 report in The Register. This is the company&\#x27;s own root-cause explanation rather than an independently verified analysis, and the article is a news report rather than a detailed technical post-mortem. The incident drew substantial technical discussion \(187 comments on Hacker News\) focused on why the failure was hard to contain and how large-scale systems should shed load and recover.

hackernews · Bender · Nov 16, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50517321)

**「The November 12 outage」** On November 12, 2026, a nearly 24-hour outage disrupted Microsoft 365 services worldwide, including Outlook, Exchange Online, Teams, and Copilot, leaving users unable to access email. In a preliminary post-incident report published on November 15, Microsoft traced the failure to a software defect introduced in July 2026 in its Microsoft 365 networking gateway servers; the July update had passed load testing and initially deployed without impact, meaning the testing did not catch the flaw.

**「Impact」** Microsoft 365 tenants bore the direct cost: the failure started in Exchange Online, spread to services that depend on it, reached users in at least 74 countries, and ran for more than 15 hours, with some tenants experiencing just under a day of downtime. Because Microsoft traced the root cause to a defect introduced in a July fix, administrators should work through post-incident guidance covering what else broke and what to verify now that service is restored, rather than assuming the outage was confined to a single service.

**「Community debate」** Commenters debated recovery tactics rather than the root cause itself: one asked why Microsoft could not shed load by admitting connections only from rotating IP ranges until servers recovered, while another argued big outages at large firms follow a familiar pattern and compared proper recovery to the electricity industry&\#x27;s &quot;black start,&quot; where load is disconnected and brought back in blocks so restarting systems are not overwhelmed. Others raised testing concerns—one noted that, per the reported explanation, the July code passed in a lower-spec test environment whose hardware differed from production, hiding a concurrency bug—and one commenter expressed surprise that Windows runs any role in critical network infrastructure at all.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/microsoft/microsoft-says-months-old-bug-caused-global-microsoft-365-outage/">Microsoft says months-old bug caused global Microsoft 365 outage</a></li>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://petri.com/microsoft-explains-microsoft-365-outage/">Microsoft Explains Causes of Microsoft 365 Outage</a></li>
<li><a href="https://office365itpros.com/2026/11/16/exchange-online-outage-nov26/">The Great Exchange Online Outage of November 2026</a></li>
<li><a href="https://www.billyperalta.com/blog/microsoft-365-outlook-outage-november-12-2026/">Outlook Down Nov 12, 2026: Microsoft 365 Outage Admin Guide</a></li>
<li><a href="https://neuraltrust.ai/blog/microsoft-outage-november-2026">Microsoft Outage: What Really Happened? | NeuralTrust</a></li>

</ul>
</details>

**Tags**: `#microsoft`, `#outage`, `#reliability`, `#incident-response`, `#distributed-systems`

---

<a id="item-tech-news-8"></a>
### [US and Nine Partners Sign San Francisco Declaration to Secure Superintelligence Supply Chains](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

On November 15, 2026, the United States and nine partner countries—Australia, India, Israel, Japan, South Korea, Qatar, Singapore, the United Arab Emirates, and the United Kingdom—signed the San Francisco Declaration on the Secure Foundations of Enduring Prosperity, committing to jointly protect the sensitive technologies and critical infrastructure that underpin superintelligence \(SI\) supply chains. Per the State Department announcement, the declaration frames economic security as the foundation of national security and establishes five working groups covering innovation policy frameworks, SI applications in critical sectors, full-stack SI supply chain collaboration, security hubs and supply chain security, and SI safety and resilience. The commitments are stated policy intentions rather than implemented measures, and the available material—a brief announcement relayed via Telegram—does not include the declaration text, the working groups&\#x27; mandates, membership, or timelines.

telegram · zaihuapd · Nov 16, 10:40

**「Background」** The San Francisco Declaration builds on Pax Silica, a US initiative launched in December 2025 to build resilient and diversified supply chains in strategic sectors including critical minerals, energy, semiconductors, and AI infrastructure. The new agreement is described as marking a new phase of that effort, extending it from a US-launched program to a ten-country framework.

**「Impact on AI supply chain firms」** Companies and research organizations building or supplying AI hardware, models, and infrastructure in the ten signatory countries should expect technology-security policy to be coordinated multilaterally rather than country by country, with the five announced working groups tasked with producing innovation policy frameworks, critical-sector adoption guidance, full-stack supply chain collaboration, security hubs, and safety and resilience measures. Because the declaration commits the coalition to a common baseline and &quot;a path to act&quot; rather than binding regulations, concrete compliance requirements — such as vetting or export-security standards for sensitive AI components — are not yet defined, and affected firms should monitor the working groups&\#x27; outputs to prepare for harmonized rules across these markets.

<details><summary>References</summary>
<ul>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>
<li><a href="https://eastasiabrief.com/trade-policy/us-signs-multilateral-ai-supply-chain-pact-eight-allies-1463">US signs multilateral AI supply chain pact with eight allies</a></li>
<li><a href="https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/">The San Francisco Declaration on the Secure Foundations of ...</a></li>
<li><a href="https://organiser.org/2026/11/17/426815/international/us-india-and-8-nations-ink-san-francisco-declaration-to-secure-ai-supply-chain-amid-chinese-linked-espionage-in-nvidia/">San Francisco Declaration: US, India and 8 sign AI pact</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#supply chain security`, `#geopolitics`, `#superintelligence`, `#international cooperation`

---

<a id="item-tech-news-9"></a>
### [Amazon: Artex-driven AI agents stole API keys to fund LLM usage](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

Amazon&\#x27;s threat intelligence reports that attackers used the open-source Artex penetration-testing framework to drive AI agents that stole API keys from publicly exposed deployments of the open-source LLM tools LiteLLM and Dify, validated the stolen credentials, pooled them, and spent them on additional LLM calls. The campaign began on October 3 and was blocked on November 5 when Amazon&\#x27;s MadPot decoy network intercepted it. Amazon attributes the operation with medium confidence to a China-linked threat group, cautions that not all listed targets were actually compromised, and says it has notified AWS customers who may be affected. These findings are Amazon&\#x27;s own threat reporting as relayed by Cybernews and have not been independently verified.

telegram · zaihuapd · Nov 16, 13:00

**「The targeted tooling and how Amazon saw it」** LiteLLM, One API, and Dify are open-source tools that developers deploy to proxy and manage large language model usage, and they store the upstream AI provider API keys that made them targets in this campaign. Amazon&\#x27;s visibility came from MadPot, its globally distributed network of decoy threat sensors, which captured the agents&\#x27; requests and operating memory between October 3 and November 5, 2026.

**「What operators should do」** Organizations running LiteLLM or Dify instances reachable from the public internet should treat the provider API keys stored in them as potentially compromised: audit exposure, rotate the keys, and check billing for unexplained model usage. AWS customers who receive a notification from Amazon about this campaign should act on it, since Amazon contacted those it believes may have been affected.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">Amazon Threat Intelligence observes threat actors running ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#cybersecurity`, `#AI agents`, `#API key theft`, `#threat intelligence`

---

<a id="item-tech-news-10"></a>
### [US extends AI chip export controls to remote access, adds five-country licensing](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

On November 16, the US Commerce Department issued an interim final rule extending export controls on advanced AI chips and servers to remote access, so that parties subject to the controls cannot obtain the chips&\#x27; computing power by renting capacity in third-country data centers. According to The Verge as cited in the source, the rule also requires licenses for re-exports of AI chips to Indonesia, Malaysia, Singapore, Thailand, and Brazil. The channel summary states the rule was drafted primarily by the Treasury Department and the National Security Council and suggests it may further tighten China&\#x27;s channels for obtaining advanced chips, but these details come from a brief summary rather than the rule text itself. As an interim final rule, it takes effect without a prior public comment period.

telegram · zaihuapd · Nov 16, 14:44

**「Background」** US export controls already restricted China&\#x27;s access to advanced AI chips from companies like Nvidia, but they did not explicitly cover remote access, leaving a loophole in which users could rent computing power on US chips hosted in third-country data centers. Reuters reported the rule was announced as President Trump headed to China, as part of the administration&\#x27;s further tightening of Beijing&\#x27;s access to advanced chips.

**「Third-country compute renters now need US licenses; chip stocks sink」** Companies in China and Macau, which are barred from buying advanced AI chips directly as Country Group D:5 entities, can no longer rely on renting compute in third-country data centers without US authorization, and re-exports to Indonesia, Malaysia, Singapore, Thailand, and Brazil now require licenses — so cloud providers and enterprises routing workloads through those countries must obtain licenses or restructure their arrangements. The Commerce Department said the rule is designed to ensure existing restrictions &quot;cannot be circumvented through remote computing arrangements involving data centers in third countries.&quot; Markets moved on the news: AMD and Broadcom shares sank on the tighter rules, and AI cloud providers that purchase chips also fell, with Nvidia-backed CoreWeave dropping more than 8% before trimming losses.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">US to curb China&#x27;s access to AI chips as Trump heads to Asia</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/article/amd-broadcom-stocks-sink-on-tighter-us-chips-rules-coreweave-drops-143342994.html">AMD, Broadcom stocks sink on tighter US chip rules , CoreWeave and...</a></li>
<li><a href="https://www.zerohedge.com/markets/us-closes-cloud-loophole-days-after-jensens-exit-new-rule-puts-ai-chip-rentals-china-and">US Closes The &quot; Cloud Loophole&quot;: Days After Jensen&#x27;s Exit, New Rul...</a></li>
<li><a href="https://wccftech.com/the-u-s-shuts-chinas-access-to-advanced-chips-via-singapore-brazil-indonesia-malaysia-and-thailand-as-scott-bessent-gives-nvidia-10-days-to-show-it-did-not-goose-its-revenues/">The U.S. Shuts China&#x27;s Access To Advanced Chips Via Singapore ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#semiconductors`, `#US regulation`, `#geopolitics`

---

<a id="item-tech-news-11"></a>
### [Chinese AI firms curb offensive cyber capabilities; Qwen flagship no longer open-weight](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

According to a Bloomberg report, leading Chinese AI firms including Alibaba, Tencent, and Moonshot AI have reduced offensive cyberattack capabilities in their newest models while improving defensive performance. Alibaba&\#x27;s latest flagship Qwen model was not released with open weights, so users can no longer download and customize the full version. Tencent reportedly trimmed cyber functions before releasing its Hy4 model in November. The changes follow a draft export-control rule that China&\#x27;s Ministry of Commerce published in October, which would prohibit exporting AI tools capable of attacking critical infrastructure or government networks; that ban is proposed, not yet in force.

telegram · zaihuapd · Nov 17, 02:20

**「Qwen&\#x27;s open-weight precedent」** Alibaba&\#x27;s Qwen family has been a standard-bearer for open-weight AI, an approach in which model parameters are published so users can download and customize the full model; in August 2026 Alibaba released the weights of Qwen 3.8 Max, then its most powerful model, sharpening its competition with Meta in the open-weight market. The flagship referenced in the report, Qwen 4-Max, was announced on November 16, 2026 with its weights kept closed, a break from that precedent.

**「Open-weight Qwen users lose full-model access」** Developers who self-host or fine-tune Qwen can no longer download the full weights of Alibaba&\#x27;s newest flagship, so existing open-weight deployments cannot be upgraded on the same terms; teams that want the newest version must either pin to the last open-weight release or work through Alibaba&\#x27;s hosted access. Organizations using these models for security work should also expect offensive cyber capabilities to be removed from new Alibaba, Tencent, and Moonshot AI releases, in line with the Ministry of Commerce draft export controls that would bar exports of AI tools capable of attacking critical infrastructure or government networks. The tightening shrinks the pool of openly downloadable, offense-capable models at a time when open-source Chinese AI tools such as ARTEX have allegedly been used in attacks on South Korean financial institutions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/08/17/alibaba-meta-qwen-open-weight-ai-laptop-models.html">Alibaba challenges Meta with new laptop-ready AI model</a></li>
<li><a href="https://thenextweb.com/news/alibaba-launches-qwen4-max-flagship-ai-model-without-open-weights">Alibaba launches Qwen 4-Max flagship AI model without open weights</a></li>
<li><a href="https://www.theregister.com/cyber-crime/2026/10/28/123-reg-discloses-ai-cyberattack-on-customer-data-suspects-china-nexus/5305936">123 Reg discloses &#x27; AI cyberattack &#x27; on customer data, suspects China ...</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#cybersecurity`, `#open weights`, `#export controls`, `#Chinese AI industry`

---

## Financial News

<a id="item-finance-news-1"></a>
### [ETF experts say Nvidia turmoil and a Democratic Congress could reshape the AI trade](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 8.0/10

Nvidia founder and CEO Jensen Huang resigned amid a scandal, and the stock&\#x27;s longest weekly losing streak since 2012 left it at $162.85 per share heading into its third-quarter earnings report due next Tuesday under interim CEO Colette Kress, who remains chief financial officer. ETF experts told CNBC the AI trade is rotating toward Big Tech, hyperscalers, and Nvidia rivals such as AMD, which rose nearly 13% this week, while Yorkville Ives cut its Nvidia price target to $225 from $300 but maintained a buy rating.

rss · CNBC Finance · Nov 16, 12:13

**「Background」** Nvidia co-founder and longtime CEO Jensen Huang resigned on Nov. 12, 2026, amid reports of alleged affairs, with CFO Colette Kress taking over as interim CEO. Democrats won control of both chambers of Congress in the Nov. 3 midterm elections, and winning lawmakers have since called for tougher limits on AI and data-center construction.

**「Data-center buildout at risk」** If the new Democratic-controlled Congress slows data-center construction — Dan Ives of Yorkville Ives estimates 10% to 20% of planned projects may not materialize — experts say existing compute holders like hyperscalers and CoreWeave could see their capacity become more valuable, though Ives notes demand still outstrips supply four to one.

<details><summary>References</summary>
<ul>
<li><a href="https://abcnews.com/Business/nvidia-ceo-jensen-huang-resigns-amid-alleged-affair/story?id=138076256">Nvidia CEO Jensen Huang resigns amid alleged affair with ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/jensen-huang-resigns-nvidia-ceo-163011659.html?fr=sycsrp_catchall">Jensen Huang Resigns as Nvidia CEO After Second Affair ...</a></li>
<li><a href="https://www.reuters.com/business/retail-consumer/nvidia-ceo-jensen-huang-step-down-big-blow-ai-boom-2026-11-12/">Nvidia CEO Jensen Huang resigns in blow to AI boom he helped ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>
<li><a href="https://russellinvestments.com/content/ri/us/en/insights/russell-research/2026/11/midterms-results-policy-data-centers.html">What midterm results mean for policy and data center risk</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI trade`, `#semiconductors`, `#ETFs`, `#data-center policy`

---

<a id="item-finance-news-2"></a>
### [Eric Trump-backed robot soldier startup can&\#x27;t pay staff after founder borrowed $4.6 million from company to buy home](https://www.cnbc.com/2026/11/14/foundation-payroll-ceo-loan.html) ⭐️ 7.0/10

Foundation Future Industries, an Eric Trump-backed military humanoid robot startup, missed payroll after CEO Sankaet Pathak borrowed $4.6 million from the company to buy a home, while the firm seeks funding at a $3 billion valuation amid scrutiny of its defense contract claims.

rss · CNBC Finance · Nov 16, 17:14

**Tags**: `#defense-tech`, `#corporate-governance`, `#Eric Trump`, `#startup-funding`, `#military-robotics`

---

<a id="item-finance-news-3"></a>
### [Lutnick faces questions over Nvidia spy scandal. His sons&\#x27; firm has ties to the chipmaker](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Commerce Secretary Howard Lutnick faces conflict-of-interest questions because his sons&\#x27; firm Cantor Fitzgerald sharply reduced its Nvidia stake and kept deep financing ties to Nvidia&\#x27;s AI ecosystem while he resisted crackdowns on suspected chip smuggling to China.

rss · CNBC Finance · Nov 16, 12:14

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#export controls`, `#Cantor Fitzgerald`, `#US-China`

---

<a id="item-finance-news-4"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

Intel, CEO Lip-Bu Chen and CFO Zinsner face a shareholder class action alleging they concealed weak PC demand and inventory buildup, after a disappointing Q4 forecast reportedly sent the stock down 28.6% in one day and erased about $140 billion in market value.

telegram · zaihuapd · Nov 16, 11:10

**Tags**: `#Intel`, `#securities class action`, `#semiconductors`, `#earnings guidance`, `#stock plunge`

---