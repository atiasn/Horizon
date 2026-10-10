---
layout: default
title: "Horizon Summary: 2026-10-10 (EN)"
date: 2026-10-10
lang: en
---

> From 44 items, 6 important content pieces were selected

---

**Technology News**
1. [Cloudflare acquires Deno, plans to end runtime development after a year](#item-tech-news-1) ⭐️ 9.0/10
2. [Telegram Desktop one-click file-theft flaw fixed in version 7.2.9](#item-tech-news-2) ⭐️ 8.0/10
3. [Oxide Computer raises $445M Series D](#item-tech-news-3) ⭐️ 7.0/10
4. [JetBrains Releases Open-Source Coding Model Mellum 2.1](#item-tech-news-4) ⭐️ 7.0/10

**Technology Blog**
1. [Software&\#x27;s centaur age may last decades](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Telecom stocks plunge on Starlink threat; Humana jumps on 2027 Medicare Star Ratings](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Cloudflare acquires Deno, plans to end runtime development after a year](https://deno.com/blog/cloudflare) ⭐️ 9.0/10

Cloudflare has acquired Deno, the open-source JavaScript/TypeScript runtime, as announced on Deno&\#x27;s blog. According to the announcement, Cloudflare will support the Deno runtime for one more year with monthly releases containing bug fixes and security updates, after which it will end development of the runtime; Deno remains open source, and the team says it welcomes others who want to continue its development. Unless an external maintainer picks the project up, active development will therefore stop once that year of maintenance ends. The blog post also notes that the Deno team released the first version of celld in August, an open-source implementation of the Durable Objects pattern from Cloudflare Workers.

hackernews · ilreb · Oct 9, 13:03 · [Discussion](https://news.ycombinator.com/item?id=50019911)

**「Deno&\#x27;s origins and Cloudflare connection」** Deno is a JavaScript and TypeScript runtime created by Ryan Dahl, the original author of Node.js, and the company behind it also operated the Deno Deploy hosting platform and the JSR package registry. The New Stack reports that as part of the deal Deno Deploy will shut down in six months with migration assistance for paying customers, while JSR will continue operating under Cloudflare. The acquisition follows the Deno team&\#x27;s August release of the first version of celld, an open-source implementation of the Durable Objects pattern from Cloudflare Workers.

**「What it means for users」** Developers and organizations running on Deno now have a bounded window: roughly one year of monthly maintenance releases covering bugs and security, after which official patches and new features stop unless a third party continues the project. The practical step is to inventory Deno-dependent code and plan a migration path or a community-maintained continuation before that maintenance window closes.

**「Community reaction」** In Hacker News comments, some readers characterized the deal as an acquihire that effectively shuts down Deno&\#x27;s development, and one commenter who said he left the ecosystem argued the project bloated when it prioritized npm compatibility over its original simpler design under VC funding pressure. Others took a more positive view, contending that Deno&\#x27;s lasting value was pressuring Node to modernize its TypeScript and standards support, and one user hoped Cloudflare&\#x27;s workerd runtime would adopt Deno&\#x27;s security sandbox mechanisms.

<details><summary>References</summary>
<ul>
<li><a href="https://thenewstack.io/cloudflare-acquires-deno-ryan-dahl/">Cloudflare acquires Node.js creator’s startup that... - The New Stack</a></li>

</ul>
</details>

**Tags**: `#javascript`, `#deno`, `#cloudflare`, `#acquisition`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Telegram Desktop one-click file-theft flaw fixed in version 7.2.9](https://telegram.me/zaihuapd/44307) ⭐️ 8.0/10

Telegram Desktop versions below 7.2.9 are affected by CVE-2026-107181, in which clicking a single malicious tg:// link allows arbitrary files — including documents, browser sessions, SSH keys, and cryptocurrency wallets — to be quietly exfiltrated without any confirmation prompt. According to a report relayed by a Telegram channel citing OpenNET, the root cause is that semicolons inside tg:// links are not escaped and are parsed by the client as separate IPC commands; combined with the interpret: handler, this enables one-click file theft. The developers fixed the flaw in version 7.2.9, and users are advised to upgrade promptly, be wary of unusual tg:// links, and enable the app&\#x27;s local passcode.

telegram · zaihuapd · Oct 9, 09:51

**「Background」** Telegram Desktop registers tg:// as a custom URL scheme, so a single click on such a link passes its contents to the client, which parses them through the Core::Sandbox inter-process communication layer where semicolons act as record separators between commands. Independent vulnerability databases classify CVE-2026-107181 as an IPC record-separator injection in Core::Sandbox, and the dbugs tracker lists it as exploited in the wild.

**「Upgrade to Telegram Desktop 7.2.9」** Anyone still running Telegram Desktop below version 7.2.9 can have arbitrary files silently sent to an attacker from a single click on a crafted tg:// link — including tdata session files, which are sufficient for full account takeover — and the CVE record flags the flaw as exploited in the wild. The immediate action is to upgrade to 7.2.9; until that is done, enabling the local passcode, turning on the &quot;Ask where to save each file&quot; setting, limiting who can add the account to groups, and avoiding unexpected tg:// links reduce exposure.

<details><summary>References</summary>
<ul>
<li><a href="https://dbu.gs/vulnerability/PT-2026-107506">CVE - 2026 - 107181 — Telegram Telegram Desktop | dbugs</a></li>
<li><a href="https://securityvulnerability.io/vulnerability/CVE-2026-107181">CVE - 2026 - 107181 : IPC Record-Separation Injection Vulnerability in...</a></li>
<li><a href="https://beaksec.github.io/posts/telegram-desktop-one-click-account-takeover/">Telegram Desktop : one - click account takeover via IPC... | beaksec</a></li>
<li><a href="https://dbu.gs/vulnerability/CVE-2026-107181">CVE-2026-107181 — Telegram Telegram Desktop | dbugs</a></li>
<li><a href="https://www.opennet.ru/opennews/art.shtml?num=66431">Уязвимость в Telegram Desktop , позволяющая отправить...</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability-disclosure`, `#telegram`, `#desktop-applications`, `#ipc`

---

<a id="item-tech-news-3"></a>
### [Oxide Computer raises $445M Series D](https://oxide.computer/blog/our-445m-series-d) ⭐️ 7.0/10

Oxide Computer announced a $445 million Series D funding round in a post on the company blog dated October 9, 2026. Oxide sells on-premises rack-scale server systems and is highly regarded in the systems, hardware, and open-source firmware communities. The announcement drew a large Hacker News discussion, with 603 points and 270 comments as captured in the submitted thread. The material available for this summary does not include the investors, valuation, or stated use of funds, so those specifics remain unconfirmed.

hackernews · ahlCVA · Oct 9, 13:12 · [Discussion](https://news.ycombinator.com/item?id=50020014)

**「Background」** Oxide Computer, a roughly seven-year-old company, builds rack-scale servers for on-premises deployment and is well regarded in the systems, hardware, and open-source firmware communities. Eclipse, which the announcement credits as a backer throughout the company&\#x27;s history, led the round, bringing Oxide&\#x27;s total raised to $742M across four rounds on record, according to funding tracker FundedIQ. That total stands well above the roughly $10M median round size FundedIQ tracks for hardware companies over the last two years, framing this Series D as an unusually large raise for the hardware sector.

**「Impact」** Organizations evaluating on-premises rack-scale hardware now have a signal that Oxide has secured substantial growth capital, but because the available announcement material does not detail how the funds will be used, buyers should confirm production capacity, lead times, and support commitments directly with the company before relying on them.

**「Community discussion」** Commentary was largely positive, with users praising Oxide&\#x27;s products and communications style, though one applicant described a months-long hiring process that ended in silence followed by a rejection. The most substantive argument came from a commenter who questioned why Oxide raised equity instead of debt or trade finance, speculating that the round might be intended to lock in supplier commitments from AMD and others beyond the current order backlog — an open question, not a confirmed fact.

<details><summary>References</summary>
<ul>
<li><a href="https://fundediq.co/oxide-computer-company-oxide-computer-funding/">Oxide Computer Company: Funding , Investors &amp; Team... | FundedIQ</a></li>
<li><a href="https://oxide.computer/blog/our-445m-series-d">Our $ 445 M Series D | Oxide Computer Company</a></li>

</ul>
</details>

**Tags**: `#hardware`, `#funding`, `#infrastructure`, `#datacenter`, `#startups`

---

<a id="item-tech-news-4"></a>
### [JetBrains Releases Open-Source Coding Model Mellum 2.1](https://blog.jetbrains.com/ai/2026/10/mellum2-1-gets-to-work-a-fast-open-model-for-coding-agents/) ⭐️ 7.0/10

JetBrains has released Mellum 2.1, an open-weights coding model distributed under the Apache 2.0 license, with weights available on Hugging Face. The model uses a 12B-parameter mixture-of-experts architecture with 2.5B active parameters and was trained through reinforcement learning in real environments. According to JetBrains, it can explore codebases, edit files, and verify changes, and is aimed at coding agents that run locally. The announcement includes no benchmark results, so its capabilities rest on the vendor&\#x27;s description rather than independent measurement.

telegram · zaihuapd · Oct 9, 07:30

**「Background」** Mixture-of-experts \(MoE\) models keep a large total parameter count but activate only a small subset per token, trading higher memory requirements for much lower per-token compute — a design that suits locally run coding agents, where fast sub-agents must perform many short code-related tasks. The &quot;Thinking&quot; designation in the released weights indicates this version adds reasoning behavior to JetBrains&\#x27; code-focused MoE line \[tool-2-1\], and the model is distributed not only as full weights but also in GGUF quantizations for serving with runtimes such as vLLM \[tool-2-2\].

**「Impact」** Developers building locally running coding agents can download the Apache 2.0-licensed weights from Hugging Face and use or fine-tune them without licensing restrictions. Because no benchmarks accompanied the release, teams should evaluate the model against their own codebases and agent workflows before adopting it.

<details><summary>References</summary>
<ul>
<li><a href="https://theopenweights.com/news/mellum2-1-12b-a2-5b-thinking-e9kt">JetBrains ships Mellum 2 . 1 , a reasoning MoE for code</a></li>
<li><a href="https://huggingface.co/JetBrains/Mellum2.1-12B-A2.5B-Thinking-GGUF">JetBrains / Mellum 2 . 1 - 12 B -A2.5B-Thinking-GGUF · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#open-source-models`, `#coding-agents`, `#JetBrains`, `#mixture-of-experts`, `#code-generation`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Software&\#x27;s centaur age may last decades](https://seangoedecke.com/softwares-centaur-age-may-last-decades/) ⭐️ 6.0/10

rss · Sean Goedecke · Oct 10, 00:00

**「Background」** In chess, human-machine &quot;centaur&quot; teams outperformed both unassisted players and computers alone for roughly twenty years. Sean Goedecke argues software engineering entered its own centaur age in 2022, making human-AI pairing the defining fact of the current era.

**「Solution」** Goedecke traces the arc from GitHub Copilot&\#x27;s autocomplete \(2022\) through chat models like GPT-4 to coding agents — Cursor&\#x27;s agent mode in 2024, Claude Code in early 2025. After Claude Opus 4.5&\#x27;s November 2025 release, he says agents are reliable enough to run unsupervised, though their errors now resemble alignment failures — over-engineering, mismatched technical values — rather than ordinary bugs. His central claim: unassisted engineers can no longer beat centaur teams, but neither can unsupervised agents, since every impressive LLM work he has seen had a competent human in control. On duration, he stacks counter-arguments: chess is simpler and more amenable to self-play, but software is far more lucrative and heavily funded; &quot;solving&quot; software may increase total work to be done; generally-capable AI could destabilize the wider economy; and knitting&\#x27;s human-plus-frame centaur age lasted two hundred years against chess&\#x27;s twenty. Nobody really knows, he concludes, but chess — attacked by the same automation forces — is the most reasonable default assumption, implying a decade or two. His advice: don&\#x27;t quit, lean into the partnership \(a financial bubble popping won&\#x27;t end AI\), and identify what human value remains — he suspects alignment has replaced technical expertise, though it&\#x27;s early days.

**「Takeaway」** His larger point: declaring either AI supremacy or apocalypse is premature — as in chess, software&\#x27;s centaur age could plausibly last decades, so engineers should stay in the field and master the partnership rather than jump ship early.

**Tags**: `#AI coding agents`, `#human-AI collaboration`, `#software engineering careers`, `#LLMs`, `#industry forecasting`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Telecom stocks plunge on Starlink threat; Humana jumps on 2027 Medicare Star Ratings](https://www.cnbc.com/2026/10/09/stocks-making-the-biggest-moves-midday-tmus-vz-t-cci-teva.html) ⭐️ 7.0/10

US telecom stocks sold off midday Friday after SpaceX moved to expand its Starlink Mobile service, with T-Mobile down 13% and AT&amp;T and Verizon each down 10%, while cellular tower operators surged, led by Crown Castle&\#x27;s 12% gain. CNBC&\#x27;s roundup also reported Humana up 12% and Alignment Healthcare down almost 14% after CMS released its 2027 Medicare Star Ratings, Apple down nearly 2% after Nikkei Asia reported October production orders for the iPhone 18 Pro and Pro Max were cut 15% from original plans, and Delta Air Lines down almost 2% after a third-quarter earnings miss prompted it to lower its full-year outlook, citing higher fuel costs.

rss · CNBC Finance · Oct 9, 18:57

**「Background」** SpaceX&\#x27;s Starlink had mostly worked alongside wireless carriers, selling them satellite coverage for dead zones, but a newly announced deal to buy low-band radio spectrum — frequencies that can reach indoors — would let it sell phone service directly in competition with AT&amp;T, T-Mobile and Verizon. Separately, the government&\#x27;s annual star ratings for Medicare Advantage plans, the private-insurance alternative to Medicare, help determine how much bonus money insurers collect, which is why rating upgrades and downgrades move those stocks sharply.

**「Impact」** US telecom investors face a sector-wide repricing as SpaceX&\#x27;s Starlink push threatens legacy carriers&\#x27; wireless business, while the 2027 Star Ratings directly shift the standing of Medicare Advantage insurers such as Humana and Alignment Healthcare, though analysts note Starlink&\#x27;s effect on tower operators remains uncertain.

<details><summary>References</summary>
<ul>
<li><a href="https://arstechnica.com/tech-policy/2026/10/starlink-spectrum-deal-boosts-musk-plan-to-beat-att-t-mobile-and-verizon/">Starlink spectrum deal boosts Musk plan to beat AT &amp; T , T - Mobile , and...</a></li>
<li><a href="https://www.phonescoop.com/articles/article.php?a=23799">SpaceX Ramps up Mobile Ambitions with Radio Spectrum Purchase</a></li>
<li><a href="https://www.statnews.com/2026/10/09/medicare-advantage-insurers-star-ratings-2027-humana-alignment/">Medicare Advantage insurers get new quality ratings , and bonuses...</a></li>
<li><a href="https://seekingalpha.com/article/4924982-crown-castle-the-pivotal-unknown">Crown Castle : The Pivotal Unknown (NYSE:CCI) | Seeking Alpha</a></li>

</ul>
</details>

**Tags**: `#telecom-stocks`, `#SpaceX-Starlink-competition`, `#Medicare-Advantage-Star-Ratings`, `#earnings`, `#midday-market-movers`

---