---
layout: default
title: "Horizon Summary: 2026-10-12 (EN)"
date: 2026-10-12
lang: en
---

> From 36 items, 6 important content pieces were selected

---

**Technology News**
1. [Terence Tao: Math 2.0 \[pdf\]](#item-tech-news-1) ⭐️ 8.0/10
2. [Karpathy sparks Hacker News debate over widening gap in LLM capability understanding](#item-tech-news-2) ⭐️ 7.0/10
3. [Op-ed calls passkeys a trap, igniting debate over lock-in and attestation](#item-tech-news-3) ⭐️ 7.0/10
4. [AI Vibe-Coded Browser Ports of Halo, GTA: Vice City, and CoD Proliferate](#item-tech-news-4) ⭐️ 7.0/10

**Financial News**
1. [China Seeks Public Comment on Food Safety Law Overhaul Covering Livestream Sales and School Meals](#item-finance-news-1) ⭐️ 7.0/10
2. [韩国股市失宠，外资年内撤离超 8700 亿元](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Terence Tao: Math 2.0 \[pdf\]](https://teorth.github.io/tao-web/slides/math-2-0-caltech-2026.pdf) ⭐️ 8.0/10

Terence Tao&\#x27;s &\#x27;Math 2.0&\#x27; presentation explores how AI tools are reshaping mathematical research, sparking significant community discussion about AI&\#x27;s impact on problem-solving and scientific fields.

hackernews · Anon84 · Oct 11, 13:16 · [Discussion](https://news.ycombinator.com/item?id=50043026)

**Tags**: `#artificial intelligence`, `#mathematics`, `#Terence Tao`, `#AI-assisted research`, `#academic impact`

---

<a id="item-tech-news-2"></a>
### [Karpathy sparks Hacker News debate over widening gap in LLM capability understanding](https://twitter.com/karpathy/status/2109361546505966046) ⭐️ 7.0/10

Andrej Karpathy posted on X \(October 11, 2026\) arguing that the gap in shared understanding of LLM capability is widening. The post, shared to Hacker News by albertzeyer, drew a large discussion of roughly 436 comments focused on agentic coding claims and how the public perceives AI progress. The item itself links to the tweet rather than presenting original technical analysis.

hackernews · albertzeyer · Oct 11, 20:20 · [Discussion](https://news.ycombinator.com/item?id=50047422)

**「Who is Karpathy and why this debate matters」** Andrej Karpathy, a former OpenAI researcher and former Tesla AI director whose posts on AI regularly anchor public debate \(per his own X profile\), has been documenting how LLM-based coding tools changed his own workflow — third-party write-ups of his Claude Code field notes describe a shift in which he now spends far more of his time on review and steering rather than writing code himself. His claim that the gap in shared understanding of what LLMs can actually do is widening is therefore best read against that insider perspective, while the Hacker News thread shows the divide runs through practitioners too: commenters disagree over whether agents can genuinely complete large, complex projects, with some warning about unreviewed AI code, maintenance, and future token costs.

**「Community Discussion」** Commenters disagreed sharply over agentic coding claims: rico735 argued the divide is not about whether agents can complete large projects from a prompt, but between developers who review code and worry about maintenance, token costs, code erosion, and LLM mistakes, and those who do not review AI-generated code at all. Others pushed back on the framing from different angles—nsainsbury argued AI has not improved or has worsened everyday life for the average person, NichoPaolucci questioned what the general public could realistically do with agentic LLMs, and danpalmer drew parallels to past overhyped tech predictions like taxis, cryptocurrency, and rapid delivery.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/jasonguo/karpathys-claude-code-field-notes-real-experience-and-deep-reflections-on-the-ai-programming-era-4e2f">Karpathy &#x27;s Claude Code Field Notes: Real... - DEV Community</a></li>
<li><a href="https://x.com/karpathy">x.com/ karpathy</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#AI-capability-debate`, `#developer-tools`, `#AI-discourse`

---

<a id="item-tech-news-3"></a>
### [Op-ed calls passkeys a trap, igniting debate over lock-in and attestation](https://nonfunctional.substack.com/p/passkeys-are-a-trap-do-not-use-them) ⭐️ 7.0/10

A Substack opinion piece argues that passkeys can function as a trap for users, primarily because attestation and platform-bound credential storage can create vendor lock-in and usability problems. The author acknowledges that attestation has legitimate uses, such as rejecting fake passkey applications, but warns that websites could use it to restrict which credential providers users are allowed. The article drew substantial engagement on Hacker News, where commenters debated whether the risks it describes reflect common real-world deployments.

hackernews · laurex · Oct 11, 21:59 · [Discussion](https://news.ycombinator.com/item?id=50048312)

**「What passkeys are」** Passkeys are phishing-resistant login credentials based on the WebAuthn/FIDO2 standards, in which a private key stays on the user&\#x27;s device and only signs per-site challenges, so accounts are never protected by a reusable password. A related mechanism, attestation, lets a site verify the make and model of the authenticator when a credential is first registered — the crux of this article&\#x27;s criticism, since it can be used to restrict which devices or password managers are accepted. Because passkeys are tied to syncing ecosystems like Apple&\#x27;s or Google&\#x27;s, portability across platforms remains a practical concern for users.

**「Practical takeaway」** Users considering passkeys should check whether a site&\#x27;s implementation supports cross-platform or synced credentials before adopting them, since device-bound passkeys can leave credentials stranded if the device is lost. The debate also suggests that current mainstream sites are unlikely to reject unattested passkeys, but users remain attentive to attestation prompts during registration.

**「Community reaction」** Commenters pushed back on the piece&\#x27;s framing: danpalmer highlighted that the article&\#x27;s own footnote admits passkeys&\#x27; domain-binding resists man-in-the-middle attacks, calling it odd that the author saved this key security benefit for an addendum. On the technical side, agwa argued that attestation can only be required at credential registration \(not retroactively at login\) and that browsers show a permission prompt, expressing doubt that major sites like Netflix or Twitter actually reject unattested passkeys today. Others, like bmitch3020, shared the author&\#x27;s practical concern, saying they avoid passkeys because they lack the portability, backup, and user-controlled strength that password managers offer.

**Tags**: `#authentication`, `#passkeys`, `#security`, `#web-standards`, `#vendor-lock-in`

---

<a id="item-tech-news-4"></a>
### [AI Vibe-Coded Browser Ports of Halo, GTA: Vice City, and CoD Proliferate](https://kotaku.com/we-might-be-cooked-as-these-vibe-coded-web-browser-ports-of-halo-the-simpsons-hit-and-run-and-gta-vice-city-seem-to-work-perfectly-2000743300) ⭐️ 7.0/10

Kotaku reports that in recent weeks hundreds of browser-based ports and emulators of classic PS2/PS3-era games have appeared, built via AI-assisted decompilation. According to the report, Claude Opus 5.5 handles source-code reconstruction so quickly that work that previously took months of manual reverse engineering can now be done overnight. Ports including Call of Duty: Black Ops, Halo: Combat Evolved, and GTA: Vice City reportedly run near-flawlessly, with one Halo port even supporting online multiplayer servers. The article notes that because these ports are fast and easy to produce, publisher takedowns would amount to playing whack-a-mole.

telegram · zaihuapd · Oct 11, 03:10

**「What decompilation means here」** Decompilation is the reverse-engineering practice of converting a game&\#x27;s compiled machine code back into readable, rebuildable source code; fan communities have used it for years to recompile classic games and port them to other platforms, a process that traditionally took skilled volunteers months per title. Kotaku attributes the recent surge of browser ports to AI coding tools such as Claude dramatically accelerating that source-code reconstruction, while modern browsers&\#x27; WebAssembly and WebGL capabilities already provide a runtime that can handle these PS2/PS3-era games.

**「Why It Matters」** For rights holders, this dramatically lowers the cost of unauthorized ports: enforcing takedowns against quickly regenerated ports may be impractical, shifting enforcement pressure toward the AI tools and hosting platforms rather than individual port developers. Readers should also treat the specific game and model claims as a single press report, not independently verified results.

**Tags**: `#AI`, `#game-emulation`, `#decompilation`, `#browser-ports`, `#intellectual-property`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China Seeks Public Comment on Food Safety Law Overhaul Covering Livestream Sales and School Meals](https://weibo.com/1642634100/Rm8MOi0jg) ⭐️ 7.0/10

China&\#x27;s market regulator has opened public comment on a draft revision of the Food Safety Law that would, for the first time, bring livestream e-commerce food sales under the law and codify a school meal accompaniment system with principals responsible for campus food safety.

telegram · zaihuapd · Oct 11, 06:02

**「Background」** China&\#x27;s Food Safety Law, in force since 2009, is undergoing another large-scale systematic revision; an earlier draft released in March 2026 already pushed to hold kindergarten principals directly responsible for food safety with daily, weekly, and monthly risk-control routines. The new draft extends this approach, adding a school meal accompaniment system in which adults eat alongside students, and for the first time brings livestream e-commerce food sales under the law by regulating livestream operators through online food trading platforms.

**「Who Is Affected」** The draft would make online food trading platforms responsible for overseeing sellers and livestream operators on their sites, while schools and kindergartens would face formal principal accountability and adult supervision during student meals.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dzwww.com/xinwen/guoneixinwen/202603/t20260325_17575111.htm">dzwww.com/xinwen/guoneixinwen/202603/t20260325_17575111.htm</a></li>

</ul>
</details>

**Tags**: `#food-safety-regulation`, `#China-policy`, `#livestream-commerce`, `#school-food-safety`

---

<a id="item-finance-news-2"></a>
### [韩国股市失宠，外资年内撤离超 8700 亿元](https://m.gelonghui.com/live/2705107) ⭐️ 7.0/10

Foreign investors have pulled roughly $131 billion out of Korean equities this year as the KOSPI fell about 22% from its strength in H1, with confidence shaken by heavy reliance on Samsung Electronics and SK Hynix.

telegram · zaihuapd · Oct 11, 12:13

**Tags**: `#South Korea`, `#foreign capital outflows`, `#KOSPI`, `#semiconductors`, `#market sentiment`

---