---
layout: default
title: "Horizon Summary: 2026-11-09 (EN)"
date: 2026-11-09
lang: en
---

> From 31 items, 6 important content pieces were selected

---

**Technology News**
1. [KetchUp: open-source SketchUp alternative in Rust and WebGPU](#item-tech-news-1) ⭐️ 7.0/10
2. [Dux v2.0 rebrands Dank Material Shell, adds atomic distro support](#item-tech-news-2) ⭐️ 7.0/10
3. [Outlook.com Begins Rejecting Email from Domains Without DMARC Records](#item-tech-news-3) ⭐️ 7.0/10
4. [Goldman Sachs pulls Claude Code from bankers and traders](#item-tech-news-4) ⭐️ 7.0/10
5. [Nvidia Board Investigates Intelligence Operation Targeting CEO Jensen Huang](#item-tech-news-5) ⭐️ 7.0/10
6. [Unpatched iOS sandbox escape PoC &\#x27;worse\_query&\#x27; released, affecting iOS 26.0–27.3 beta](#item-tech-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [KetchUp: open-source SketchUp alternative in Rust and WebGPU](https://ketchup3d.github.io/app/) ⭐️ 7.0/10

KetchUp is an early-stage, open-source 3D modeling app that runs in the browser and positions itself as a free alternative to SketchUp, written in Rust with rendering through WebGPU. The app is live at ketchup3d.github.io/app, but the project is young and its maturity is unproven. It drew 245 points and 71 comments on Hacker News, with interest driven largely by users looking for a free modeling tool for occasional projects.

hackernews · dcoulmbe · Nov 8, 22:35 · [Discussion](https://news.ycombinator.com/item?id=50418176)

**「SketchUp&\#x27;s licensing gap and the WebGPU stack」** SketchUp is a commercial 3D modeling application whose full desktop capabilities sit behind a paid subscription; one commenter notes that his detailed home model only opens in the desktop app, leaving him to request a new free trial for each occasional renovation project. On the technical side, WebGPU is the browser graphics API that gives web applications direct GPU access, and Rust libraries such as wgpu implement that standard while also running natively on Vulkan, Metal, DirectX 12, and OpenGL. That pairing of a systems language with a modern web graphics standard is what makes a responsive 3D modeler practical entirely in a browser tab.

**「Impact」** Casual SketchUp users who cannot justify a subscription — paid plans run from $129/year for Go to $819/year for Studio, with Pro at $399/year, while the free web version is licensed only for personal, non-commercial use — gain a free, open-source, browser-based alternative in KetchUp. Because the project is early-stage, anyone with existing SketchUp models should treat it as an experiment and confirm file compatibility before depending on it for real work.

**「Community reaction」** Frustration with SketchUp&\#x27;s licensing drove much of the enthusiasm: one commenter said his detailed house model only opens in the paid desktop app, making the free web version useless to him and a subscription uneconomical for occasional renovations. Others praised how responsive the Rust-based interface feels in the browser, while a side thread debated whether AI coding tools now make it more practical to build a bespoke tool than to learn an existing one — one commenter reported spending much of a year-long yard renovation building his own &quot;2D SketchUp&quot; instead of drawing.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/gfx-rs/wgpu">GitHub - gfx-rs/wgpu: A cross-platform, safe, pure- Rust graphics API.</a></li>
<li><a href="https://wgpu.rs/">wgpu: portable graphics library for Rust</a></li>
<li><a href="https://en.wikipedia.org/wiki/SketchUp">SketchUp - Wikipedia</a></li>
<li><a href="https://www.myarchitectai.com/blog/sketchup-pricing">SketchUp Pricing 2026: Go, Pro, Studio &amp; iPad Plans Compared</a></li>
<li><a href="https://visualizee.ai/blog/sketchup-pricing">SketchUp Pricing 2026: Go, Pro &amp; Studio Costs</a></li>

</ul>
</details>

**Tags**: `#rust`, `#webgpu`, `#3d-modeling`, `#open-source`, `#browser-apps`

---

<a id="item-tech-news-2"></a>
### [Dux v2.0 rebrands Dank Material Shell, adds atomic distro support](https://duxlabs.dev/) ⭐️ 7.0/10

Dux, the new name for the free and open-source Dank Material Shell \(DMS\), has released version 2.0 and added official support for atomic Linux distributions such as Bazzite, filling what a long-time user called a previously &quot;annoying gap&quot; given those distros&\#x27; popularity. The Wayland shell, commonly paired with the Niri compositor, includes a file manager and theming; a commenter notes the rebrand from DMS happened a few weeks before the release, which is documented in a v2.0 post on the project&\#x27;s site. The Hacker News thread drew 211 points and 62 comments, with multiple users reporting close to a year of daily use under the old name. One caveat: installation currently relies on a curl \| sh script rather than distro packages.

hackernews · indigodaddy · Nov 8, 19:08 · [Discussion](https://news.ycombinator.com/item?id=50416053)

**「From Dank Material Shell to Dux」** Dux is a desktop shell that runs on the Niri scrolling Wayland compositor and, until a few weeks ago, was known as Dank Material Shell \(DMS\) — a change a commenter ties to the project&\#x27;s v2.0 release. Atomic distributions such as Bazzite are immutable Linux systems that update as whole images rather than through individual packages, and the shell previously had no official support for them, a gap long-time users described as annoying given those distros&\#x27; popularity.

**「Impact」** Dux&\#x27;s newly official support for atomic distributions extends the shell to users of Bazzite, a Fedora-based distribution modeled on Valve&\#x27;s SteamOS 3.0 that targets gaming handhelds such as the Steam Deck. A long-time user described the earlier lack of such support as an annoying gap given the popularity of those distros, and the pairing fits Bazzite&\#x27;s stack, which does not support the legacy X11 display server, so any desktop shell there must be Wayland-native. One adoption caveat from the discussion: a commenter argued that the curl \| sh install method is the kind of thing that should be packaged and reviewed by a distribution before being trusted unconditionally.

**「Community reaction」** Long-term users are enthusiastic: one who has run the shell with Niri for nearly a year said they have no intention of switching, and another argued it is polished enough to help bring the Niri compositor into the mainstream. Objections came from a commenter who said the curl \| sh installer should be distro-packaged and thoroughly reviewed before being trusted unconditionally, and from a user who finds the shell becoming more all-encompassing than they want, mentioning Noctalia as an alternative they want to try.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Bazzite_%28operating_system%29">Bazzite (operating system) - Wikipedia</a></li>
<li><a href="https://docs.bazzite.gg/General/FAQ/">Frequently Asked Questions - Bazzite Documentation</a></li>

</ul>
</details>

**Tags**: `#wayland`, `#linux-desktop`, `#open-source`, `#desktop-shell`, `#niri`

---

<a id="item-tech-news-3"></a>
### [Outlook.com Begins Rejecting Email from Domains Without DMARC Records](https://mailroute.net/blog/outlook-rejecting-email-without-dmarc) ⭐️ 7.0/10

Outlook.com has begun rejecting email sent from domains that do not publish a DMARC record, according to a report discussed on Hacker News, affecting any sender whose domain lacks the authentication policy. DMARC is a DNS record that tells receiving mail servers how to handle messages failing SPF and DKIM checks, and participants described the move as an expected industry step that arrived later than many anticipated. Though the report framed the rejections as quiet, one commenter stated that sending servers actually receive 5xx permanent delivery failure responses, making the failures visible to anyone monitoring bounces.

hackernews · xmddmx · Nov 8, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50416158)

**「Background」** DMARC is an email authentication standard that works alongside SPF and DKIM, letting a domain owner publish a DNS policy that tells receiving mail servers how to treat messages that fail authentication. Microsoft&\#x27;s postmaster announcements had already required SPF, DKIM, and DMARC for domains sending more than 5,000 emails per day to Outlook.com, with that enforcement starting May 5, 2025. Those published requirements were scoped to high-volume senders, but a Microsoft Q&amp;A response noted a sudden increase in delivery-failure reports and suspected the requirements were also affecting low-volume senders.

**「What this means for email senders」** Senders whose domains lack a DMARC record will see mail to Outlook.com recipients bounce — commenters report 5xx permanent delivery failures rather than silent drops — so the immediate action is to publish a DMARC record, which satisfies the check even in monitoring-only p=none mode. The affected group is sizable: Fortra/Agari&\#x27;s 2025 analysis found more than 81% of the world&\#x27;s 10 million most popular domains had no DMARC record at all, with another 10% in non-enforcing monitoring mode, and industry reporting put adoption at 47.6% in 2025, up from 27.3% in 2023. Publishing a record alone does not guarantee delivery, though: self-hosting commenters report Outlook.com also applies undisclosed blocklists that can reject mail even from domains with SPF, DKIM, and DMARC fully configured.

**「Admins report broader opaque filtering」** Self-hosted administrators reported longer-standing grievances beyond DMARC: in their experience, Outlook.com has silently discarded mail that passed SPF, DKIM, and DMARC checks, and has blocked entire VPS providers via unpublished blocklists with no workable removal process. The DMARC requirement itself drew little objection — one commenter said every sender should have implemented it years ago — while criticism focused on Microsoft&\#x27;s broader opaque filtering behavior.

<details><summary>References</summary>
<ul>
<li><a href="https://substrate.office.com/ip-domain-management-snds/postmaster">Announcements</a></li>
<li><a href="https://learn.microsoft.com/en-us/answers/questions/6064660/how-to-fix-hotmail-com-olc-protection-outlook-com">How to fix - hotmail-com.olc.protection. outlook . com .... - Microsoft Q&amp;A</a></li>
<li><a href="https://hostgard.net/2025/08/only-1-in-10-domains-enforce-dmarc-in-2025-why-email-spoofing-still-works/">Only 1 in 10 Domains Enforce DMARC in 2025: Why Email ...</a></li>
<li><a href="https://easydmarc.com/blog/news-global-dmarc-adoption-report-2025/">UK Email Security Risk: DMARC Report 2025 - easydmarc.com</a></li>

</ul>
</details>

**Tags**: `#email`, `#dmarc`, `#microsoft`, `#email-deliverability`, `#sysadmin`

---

<a id="item-tech-news-4"></a>
### [Goldman Sachs pulls Claude Code from bankers and traders](https://www.thestateofai.com/news/goldman-sachs-claude-code-traders-bankers) ⭐️ 7.0/10

Goldman Sachs is withdrawing Anthropic&\#x27;s Claude Code from its bankers and traders, removing the agentic coding tool from non-engineering staff who had been using it, according to a report picked up on Hacker News. Discussion of the move highlights three practical obstacles for enterprises deploying agentic AI outside engineering teams: the security risk of semi-autonomous agents running on workstations with access to client and trade data, email, and internal networks; friction with consumption-based billing models; and compliance and entitlement concerns when non-engineering staff ship AI-built prototypes. The available material includes no statement from Goldman Sachs or Anthropic, and specifics such as the exact scope, timing, and stated reason for the withdrawal are not confirmed.

hackernews · TheWiggles · Nov 8, 18:16 · [Discussion](https://news.ycombinator.com/item?id=50415628)

**「Background」** Claude Code is Anthropic&\#x27;s agentic coding tool, and Goldman Sachs had deployed it well beyond its engineering staff — traders and bankers used it, alongside Microsoft&\#x27;s GitHub tools, to track client flows and build market models. The withdrawal reverses the firm&\#x27;s own recent public positioning: as recently as July, Goldman CIO Marco Argenti had publicly praised &quot;vibe coding&quot; by non-technical staff.

**「Impact」** Enterprises running agentic AI tools on non-engineering staff machines should expect security-driven access reviews: commenters argued that semi-autonomous agents operating on workstations with access to client and trade data, email, and internal networks create exfiltration risks that bank compliance functions are unlikely to accept, so deployments need isolated environments or tightly scoped entitlements rather than general staff machines. Procurement is a parallel pressure point — one commenter reported their organization clawing back Claude access over chronic billing overages because Anthropic would not offer normalized rates, with flat-rate rivals such as Gemini absorbing non-engineering users. The withdrawal also lands weeks before Anthropic&\#x27;s IPO, in which Goldman Sachs is one of the lead underwriters.

**「Community reaction」** Commenters most concretely attributed the withdrawal to what one called the &quot;lethal trifecta&quot; — semi-unattended agents operating on the same machines that hold client and trade information, email, and internal network access — while a user at another organization reported that chronic billing overages and Anthropic&\#x27;s inability to offer flat-rate pricing were pushing enterprises toward competitors like Gemini, which throttles overages instead. Others argued the deeper issue is banks&\#x27; compliance regimes around data entitlements and auditable approval chains when non-technical staff produce AI-built prototypes, and a few speculated, without supporting evidence, about an unannounced operational incident or about timing relative to Goldman&\#x27;s role in Anthropic&\#x27;s IPO.

<details><summary>References</summary>
<ul>
<li><a href="https://www.thestateofai.com/news/goldman-sachs-claude-code-traders-bankers">Goldman Sachs Is Pulling Claude Code From Its Bankers and ...</a></li>
<li><a href="https://the-decoder.com/goldman-sachs-pulls-ai-coding-tools-from-traders-and-bankers/">Goldman Sachs pulls AI coding tools from traders and bankers</a></li>
<li><a href="https://www.linkedin.com/news/story/anthropics-blockbuster-ipo-moves-a-step-closer-7709340/">Anthropic &#x27;s blockbuster IPO moves a step closer | LinkedIn</a></li>
<li><a href="https://www.nytimes.com/2026/10/27/business/in-anthropic-ipo-goldman-and-morgan-stanley-slug-it-out-for-top-bank.html">In Anthropic I.P.O., Goldman and Morgan Stanley Slug It Out for Top...</a></li>

</ul>
</details>

**Tags**: `#enterprise-ai`, `#ai-agents`, `#security`, `#finance`, `#claude-code`

---

<a id="item-tech-news-5"></a>
### [Nvidia Board Investigates Intelligence Operation Targeting CEO Jensen Huang](https://nvidianews.nvidia.com/news/statement-from-nvidia-board-of-directors) ⭐️ 7.0/10

Nvidia&\#x27;s board of directors published a statement on its official newsroom on November 8, 2026, announcing an investigation into an intelligence operation that targeted CEO Jensen Huang. The Hacker News headline, &\#x27;Nvidia Board of Directors Is Investigating Jensen Huang,&\#x27; is misleading: the board is probing the operation aimed at Huang, not investigating Huang for wrongdoing. A comment citing Bloomberg&\#x27;s headline — &\#x27;Nvidia Board to Probe Spying Case After CEO Admits Infidelity&\#x27; — connects the probe to an infidelity admission by Huang, but the statement&\#x27;s full text was not included in the available material, so the nature and scope of the operation remain unclear. No findings or personnel consequences from the board&\#x27;s investigation appear in the supplied sources.

hackernews · vincentchau · Nov 8, 20:26 · [Discussion](https://news.ycombinator.com/item?id=50416801)

**「Background」** The board&\#x27;s announcement followed a note Huang sent to Nvidia staff admitting he had been &quot;unfaithful&quot; to his wife, with press reports linking the relationship to an alleged Chinese spy. In its statement, the board said it was opening an investigation &quot;in light of recent reporting that founder and CEO Jensen Huang has been the target of a foreign intelligence effort.&quot;

**「Board probe puts CEO&\#x27;s standing under formal review」** Nvidia&\#x27;s board has launched an independent investigation into the alleged foreign intelligence operation that targeted CEO Jensen Huang, following his admission of an affair with a woman identified in press reports as a suspected Chinese spy. The immediate consequence is that the founder-CEO of the roughly $4.5 trillion chipmaker now has his personal and security exposure examined at board level, leaving his leadership continuity and any resulting governance or security changes unresolved until the probe concludes. No wrongdoing by Huang or Nvidia has been established by the reporting so far.

**「Community discussion」** The most upvoted correction came from a commenter explaining that the board is investigating something that happened to Huang — an intelligence operation targeting him — rather than investigating Huang himself. Commenters disagreed over significance: one called it a personal matter with no bearing on Nvidia&\#x27;s business, while others argued that someone of Huang&\#x27;s influence over billion-dollar decisions is a routine target for intelligence services; one commenter&\#x27;s speculation that a foreign power, China in particular, sought leverage over Nvidia was explicitly labeled unproven even by its author.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/news/articles/c3dxw10rjn9no">Nvidia launches investigation into CEO&#x27;s affair with suspected...</a></li>
<li><a href="https://www.forbes.com/sites/zacharyfolk/2026/11/08/nvidia-investigating-ceo-jensen-huangs-relationship-with-alleged-chinese-spy-after-he-admits-affair/">Nvidia Investigating If Jensen Huang Was Targeted By A ‘Foreign...</a></li>
<li><a href="https://www.businessinsider.com/nvidia-jensen-huang-investigation-chinese-spy-2026-11">Nvidia Opens Investigation Into CEO Jensen Huang - Business Insider</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-08/nvidia-board-to-probe-spying-case-after-ceo-jensen-huang-admits-infidelity">Nvidia Board to Probe Spying Case After CEO Jensen Huang Admits...</a></li>
<li><a href="https://nypost.com/2026/11/08/tech/jensen-huang-ceo-of-4-5t-chipmaker-nvidia-admits-affair-as-memo-warned-lover-was-chinese-spy/">Jensen Huang , CEO of $4.5T chipmaker Nvidia admits affair — as...</a></li>
<li><a href="https://kz.kursiv.media/en/2026-11-09/engk-yeri-nvidia-probes-foreign-spy-plot-targeting-ceo-jensen-huang/">Nvidia probes foreign spy plot targeting CEO Jensen Huang</a></li>

</ul>
</details>

**Tags**: `#nvidia`, `#corporate-governance`, `#espionage`, `#ai-industry`, `#geopolitics`

---

<a id="item-tech-news-6"></a>
### [Unpatched iOS sandbox escape PoC &\#x27;worse\_query&\#x27; released, affecting iOS 26.0–27.3 beta](https://x.com/forcequitOS/status/2119475139528020218?) ⭐️ 7.0/10

Researcher forcequitOS published a zero-day iOS sandbox escape proof-of-concept named worse\_query on November 8, which the researcher says works on iOS 26.0 through 26.7.2 and on 27.2, including the 27.3 beta. According to the post, the PoC grants access to system paths and can modify app data, requires an App Group configuration, and succeeds an earlier exploit called bad\_query; its author frames it as a development research tool unrelated to jailbreaking. The issue has reportedly been submitted to Apple but remains unpatched as of disclosure, and community-built tools based on it, such as GestaltX, have already appeared. Because this report is a secondhand summary of an X post, the affected-version range and unpatched status rest on the researcher&\#x27;s claims and have not been independently verified.

telegram · zaihuapd · Nov 9, 02:36

**「From bad\_query to worse\_query」** iOS sandboxes each app into its own container, and a &quot;sandbox escape&quot; is a technique that lets an app reach paths and data outside that boundary. forcequitOS previously published bad\_query, a sandbox-escape proof-of-concept for iOS 26 and 27 that gave apps access to PosterBoard data, letting wallpaper-customization tools such as Pocket Poster \(Nugget\) work without a desktop computer. According to its own repository, worse\_query is the direct successor that &quot;essentially replaces&quot; bad\_query, and like its predecessor it requires the app to set up an App Group container.

**「Unpatched exploit code is already powering tools」** Because the worse\_query code is public on GitHub under the GPL-3.0 license and Apple has not yet shipped a fix, working tools built on it already exist: GestaltX 1.0.0, a MobileGestalt editor for iOS 26.0–26.7.2 and 27.x powered by worse\_query, shipped the same day as the PoC. Until Apple patches the flaw, users on iOS 26.0–26.7.2, 27.2, and the 27.3 beta should be cautious about installing untrusted utilities or apps that could reuse the technique, since the same sandbox-escape capability can access system paths and modify app data.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/forcequitOS/worse_query">GitHub - forcequitOS / worse _ query : A sandbox escape for iOS 26...</a></li>
<li><a href="https://nugget.host/en/ipa/pocket-poster">Pocket Poster IPA | PosterBoard Wallpaper App | Nugget iOS</a></li>
<li><a href="https://trendshift.io/repositories/130342">forcequitOS / bad _ query — GitHub trending stats &amp; insights | Trendshift</a></li>
<li><a href="https://x.com/onejailbreak_/status/2119584204149211317">ONE Jailbreak on X: &quot; ️forcequitOS released worse_query, a ...</a></li>
<li><a href="https://onejailbreak.com/blog/worse_query-sandbox-escape-for-ios-26-and-27/">worse_query Sandbox Escape for iOS 26 and 27 Released</a></li>

</ul>
</details>

**Tags**: `#security`, `#iOS`, `#sandbox-escape`, `#zero-day`, `#vulnerability-disclosure`

---