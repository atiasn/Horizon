---
layout: default
title: "Horizon Summary: 2026-10-05 (EN)"
date: 2026-10-05
lang: en
---

> From 25 items, 7 important content pieces were selected

---

**Technology News**
1. [Strata runs 125B Qwen 3.8 Flash Next on an RTX 4090 at ~124 tok/s](#item-tech-news-1) ⭐️ 7.0/10
2. [Improper redaction exposes Google data center&\#x27;s water and electricity use in Lincoln](#item-tech-news-2) ⭐️ 7.0/10
3. [Why Developers Still Prefer Frameworks Over the Web Platform](#item-tech-news-3) ⭐️ 7.0/10
4. [Nonobench: open-source benchmark tests 49 LLMs on nonogram puzzles](#item-tech-news-4) ⭐️ 7.0/10
5. [White House Creates AI Task Force for 120-Day Risk Review](#item-tech-news-5) ⭐️ 7.0/10
6. [Peripheral System Breaches Hit Shinhan, Kookmin, Hana and BNK Busan Bank](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [Gen Z Sports Betting Surge Draws Expert Warnings](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Strata runs 125B Qwen 3.8 Flash Next on an RTX 4090 at ~124 tok/s](https://github.com/Niko1221/Strata) ⭐️ 7.0/10

Strata, an open-source project on GitHub, demonstrates local inference of Qwen 3.8 Flash Next, a 125B-parameter model, on a single consumer RTX 4090; submitter snehesht reports 124 tokens/sec on a machine with 128GB DDR5 and a Ryzen 7950x3d, with weights published on Hugging Face as Qwen/Qwen3.8-Flash-Next. These throughput figures are author-reported: the supplied material includes no implementation details and no independent benchmark confirming them. Fitting 125B parameters onto a 24GB card requires heavy quantization, an approach some commenters warn can significantly degrade model quality at low bit-rates.

hackernews · snehesht · Oct 4, 12:51 · [Discussion](https://news.ycombinator.com/item?id=49953495)

**「Background」** Local large-language-model inference is normally constrained by GPU memory: a 125-billion-parameter model like Qwen 3.8 Flash Next requires far more memory than a consumer card such as the RTX 4090 can hold, so practitioners compress weights through quantization and offload storage to system RAM. The original poster&\#x27;s setup reflects this, pairing the 4090 with 128 GB of DDR5, and the high throughput depends on aggressive compression of the model&\#x27;s weights. Because quality degradation at very low bit widths \(below 4-bit quantization\) is a known risk in the community, whether such compression preserves accuracy is the central open question surrounding claims like these.

**「Promising but unverified for local-LLM users」** If Strata&\#x27;s reported throughput holds, developers could run a 125B model at usable speed on a single consumer GPU, but anyone adopting it should benchmark their own workloads first: in a 50-image object-localization test posted by commenter Jackson\_\_, Strata produced a median coordinate error of 154.8 pixels versus 46.5 for llama.cpp running the same model and vision adapter weights.

**「Strong personal results, quality skepticism」** AntiRush reports a Q4 quant on an RTX 6000 Pro Workstation Edition reaching 1,251 tok/s prefill and roughly 199-255 tok/s decode, including four concurrent streams above 400 tok/s, while a11r is skeptical of sub-4-bit quantization quality — preferring rented 4-bit inference on an RTX Pro 6000 for coding work — and jacquesm cautions that Strata hype is outpacing evidence. These are individual, unverified reports rather than established benchmarks.

**Tags**: `#LLM inference`, `#Quantization`, `#Consumer hardware`, `#Qwen`, `#Open source`

---

<a id="item-tech-news-2"></a>
### [Improper redaction exposes Google data center&\#x27;s water and electricity use in Lincoln](https://www.1011now.com/2026/09/30/more-questions-than-answers-about-lincolns-google-data-center-water-electricity-usage/) ⭐️ 7.0/10

An improperly redacted public record revealed the water and electricity consumption of Google&\#x27;s data center in Lincoln, Nebraska, figures that had otherwise been withheld from local disclosure. Numbers cited from the report put the Lincoln facility&\#x27;s water use at roughly 13 million gallons, compared with more than 500 million gallons reported for another Nebraska data center in the same article. The exposure has prompted debate over why data-center utility records are redacted in the first place and how widely water consumption varies between facilities.

hackernews · sensanaty · Oct 4, 19:37 · [Discussion](https://news.ycombinator.com/item?id=49957068)

**「Nebraska&\#x27;s data-center usage reports」** Data centers in Nebraska submit annual reports on their resource consumption to the state, as reflected in the 2026 annual filing that surfaced these figures. Usage details in such filings are normally withheld from public view, which is why the numbers remained obscure until a flawed redaction on Google&\#x27;s Lincoln facility left its water and electricity figures exposed.

**「Exposed figures may not represent other facilities」** The redaction failure matters as much for what it does not show: commenters on the report noted that the roughly 13 million gallons of water attributed to Google&\#x27;s Lincoln facility sits at the low end, with another Nebraska data center reportedly consuming more than 500 million gallons, so the exposed numbers cannot be read as representative of data-center demand generally. Because disclosure rules can still keep actual usage figures sealed, residents and city officials weighing future data-center approvals may need to require direct, itemized water and power reporting up front rather than relying on redacted filings.

**「Community discussion」** In the Hacker News thread, a commenter who said they had worked at a rural Google data center argued that local fears about data-center water and power use are often exaggerated, while others countered that the Lincoln site may be among the state&\#x27;s lightest water users because consumption can differ by orders of magnitude depending on cooling design — and disclosure rules make the full picture impossible to verify. Another commenter argued that water and energy use are poor proxies for opposing AI data centers, and one redirected readers to the Flatwater Free Press for broader statewide comparisons.

<details><summary>References</summary>
<ul>
<li><a href="https://pasqualepillitteri.it/en/news/20708/google-lincoln-data-center-botched-redaction-reveals-usage">Botched Redaction Reveals Water and Power Use at...</a></li>
<li><a href="https://metro.newschannelnebraska.com/story/364065664/update-improper-redaction-reveals-lincolns-google-data-center-water-and-electricity-usage">UPDATE: Improper redaction reveals Lincoln ’s Google Data Center ...</a></li>

</ul>
</details>

**Tags**: `#Data Centers`, `#Infrastructure`, `#Water Usage`, `#Energy Consumption`

---

<a id="item-tech-news-3"></a>
### [Why Developers Still Prefer Frameworks Over the Web Platform](https://nolanlawson.com/2026/10/03/why-dont-more-developers-use-the-platform/) ⭐️ 7.0/10

Nolan Lawson’s essay examines why many web developers choose frameworks such as React instead of relying directly on browser APIs and Web Components. It argues that the issue is less about developers disliking native technology than about the platform’s uneven ergonomics, difficult APIs, and inconsistent browser behavior. The piece is an analysis essay, not a new platform release or independently measured performance study.

hackernews · vinhnx · Oct 4, 04:10 · [Discussion](https://news.ycombinator.com/item?id=49950554)

**「Background」** &quot;Use the platform&quot; is a recurring position in frontend development that urges developers to build with native browser APIs—such as Web Components and standard HTML elements—rather than layering JavaScript frameworks like React on top. As Lawson&\#x27;s essay notes, the historical root of this divide is that for a long time browsers were playing catch-up with the ecosystem built on top of them, which is how frameworks became the default rather than the platform&\#x27;s own APIs. The debate keeps resurfacing because, years later, many developers still judge platform features as harder to use than the framework abstractions that filled those early gaps.

**「Practical trade-offs」** Teams choosing native APIs may still need libraries such as Lit or framework-level abstractions to make Web Components easier to build and maintain, while native features such as &lt;datalist&gt; may require testing across browsers before they can replace a custom implementation.

**「Community debate」** Several commenters argued that Web Components are difficult to use without wrappers such as Lit, while React offers a more consistent developer experience. Others challenged the assumption that native browser features are reliably faster or better, citing the poor usability of &lt;datalist&gt; implementations and the resulting need for custom solutions.

<details><summary>References</summary>
<ul>
<li><a href="https://nolanlawson.com/2026/10/03/why-dont-more-developers-use-the-platform/">Why don ’ t more developers “ use the platform ”? | Read the Tea...</a></li>

</ul>
</details>

**Tags**: `#web-development`, `#frontend-frameworks`, `#web-components`, `#react`, `#browser-apis`

---

<a id="item-tech-news-4"></a>
### [Nonobench: open-source benchmark tests 49 LLMs on nonogram puzzles](https://www.reddit.com/r/MachineLearning/comments/1wxa2bs/nonobench_an_open_benchmark_of_49_llms_on/) ⭐️ 7.0/10

Nonobench is a new public benchmark, with MIT-licensed code and a hosted site, that evaluates 49 LLMs on nonogram \(picross\) puzzles: each model receives the row and column clues once and must return the complete grid, with no tools and one attempt per puzzle. In Standard mode \(30 puzzles from 5x5 to 15x15, drawn from the Moyà-Alcover Nonograms dataset under CC BY 4.0\), solve rates fall from 85% on 5x5 to 46% on 10x10 and 20% on 15x15, with each model scored at its best reasoning-effort level; GPT-6 Astra solved all 30 Standard puzzles, while on Hard mode — ten random 20x20 puzzles each verified to have a single solution — Claude Opus 5.5 solved 8 of 10 and 11 of 15 models solved none. The suite covers 130 model variants across reasoning-effort levels, run through OpenRouter and pinned to each lab&\#x27;s own endpoint where possible. Because each puzzle is attempted only once, individual results are noisy \(95% intervals are shown\), so the model comparisons should be treated as preliminary.

reddit · r/MachineLearning · /u/mauricekleine · Oct 4, 07:57

**「What is a nonogram?」** A nonogram \(picross\) is a grid logic puzzle in which numeric clues for each row and column specify the lengths of consecutive filled-cell runs, and the solver must reconstruct the entire grid; the standard human technique, &quot;line logic,&quot; derives cells from one row&\#x27;s or column&\#x27;s constraints at a time, and puzzles beyond a certain difficulty cannot be finished with it alone. Because both the clues and the expected answer are plain text, the task hinges on counting run lengths, tracking constraints across a partially filled grid, and emitting an exactly formatted result rather than on retrieving knowledge. Nonobench packages this task as a documented suite for evaluating LLM reasoning on nonogram solving across different grid sizes, with results published at nonobench.com.

**「Impact」** Developers and researchers can reproduce or extend the evaluation themselves via the public site \(nonobench.com\) and the MIT-licensed GitHub repository, though the one-attempt design means per-puzzle results carry wide uncertainty. The benchmark&\#x27;s own format change is a practical takeaway: when 20x20 answers were requested as a single ~400-character string, most models lost count before the logic got hard, so Hard mode switched to an array of 20 row strings — evidence that output-structure choices can dominate measured reasoning performance.

<details><summary>References</summary>
<ul>
<li><a href="https://mcpservers.org/servers/mauricekleine/nonobench">Nonobench MCP Server | Awesome MCP Servers</a></li>

</ul>
</details>

**Tags**: `#LLM Evaluation`, `#Reasoning Benchmarks`, `#Open Source`, `#Machine Learning`, `#Model Reliability`

---

<a id="item-tech-news-5"></a>
### [White House Creates AI Task Force for 120-Day Risk Review](https://www.wsj.com/tech/ai/new-ai-task-force-to-report-on-risks-of-technology-after-public-and-industry-concerns-b6308bef) ⭐️ 7.0/10

According to the reported Wall Street Journal account, the White House has created a task force called the “Super Intelligence Force” to assess AI risks and the federal government’s responsibilities, with a report due within 120 days. National Intelligence Director Jay Clayton is leading the group and described its mandate as keeping the United States ahead in superintelligence while protecting American interests. The initiative is a planned assessment, not evidence that new AI regulations or binding safety requirements have been adopted; the report provides few details about the group’s membership or authority.

telegram · zaihuapd · Oct 4, 02:37

**「Background」** The task force builds on a US posture that, according to the WSJ report, relies on voluntary measures rather than binding rules: despite rising public and industry concern about AI safety risks, President Trump has refused to introduce new regulation, prioritizing keeping America ahead of China and backing a voluntary framework that includes external safety audits and stronger internal corporate controls. Within that setup, the new body adds a coordinating point inside the government without creating enforceable requirements — a senior White House official described the Director of National Intelligence&\#x27;s new role as effectively making him the administration&\#x27;s &\#x27;AI czar.&\#x27;

**Tags**: `#AI治理`, `#人工智能安全`, `#科技政策`, `#国家AI战略`

---

<a id="item-tech-news-6"></a>
### [Peripheral System Breaches Hit Shinhan, Kookmin, Hana and BNK Busan Bank](https://www.thelec.net/news/articleView.html?idxno=14402) ⭐️ 7.0/10

Peripheral or partner-facing systems at four South Korean banks — Shinhan, KB Kookmin, Hana, and BNK Busan Bank — have suffered a string of data breaches. Shinhan Bank&\#x27;s loan-agency inquiry system was under attack for three days, exposing data on 25,729 customers, while KB Kookmin and Hana reported 119 and 89 affected customers respectively, and Busan Bank leaked the personal information of 11 outsourced developers. In response, the country&\#x27;s financial regulator is extending planned IT inspections of the financial sector beyond core banking to employee business systems and external partners, and is requiring institutions to check externally exposed systems for vulnerabilities, strengthen authentication and access controls, and share attack IPs and techniques.

telegram · zaihuapd · Oct 4, 09:02

**「What banks&\#x27; peripheral systems are」** Large banks operate &\#x27;peripheral&\#x27; systems alongside their core banking platforms — such as loan-agency inquiry tools, employee business applications, and systems involving outsourced developers or external partners — which still hold customer or staff personal data but sit at the edge of the IT estate where outside parties connect. Because these edge systems are externally exposed and often maintained by vendors or business units rather than the core banking team, they are a recognized weak point, and the regulatory response described here follows the standard pattern of extending inspections beyond core systems to externally exposed assets, authentication, and access control.

**「Third-Party and Edge Systems Face New Scrutiny」** Korean financial institutions now face regulatory review of employee-facing and third-party systems, an area often outside standard core-banking security audits. Organizations that operate externally exposed or contractor-connected systems for these banks should verify their own vulnerability exposure and tighten identity verification and access controls before inspections reach them.

**Tags**: `#网络安全`, `#数据泄露`, `#金融科技`, `#第三方风险`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Gen Z Sports Betting Surge Draws Expert Warnings](https://www.cnbc.com/2026/10/04/gen-z-sports-betting-financial-and-mental-health-risks.html) ⭐️ 7.0/10

Sports betting has become routine for many young Americans: an August Betterment survey found 66% of Gen Z investors bet on sports, and the Bank of America Institute reported Gen Z made up nearly half of all online betting activity in July 2026, during the FIFA World Cup. Financial and mental health experts warn that many in this generation treat wagering like investing, even though the typical sportsbook and prediction-market user loses money.

rss · CNBC Finance · Oct 4, 12:57

**「Background」** Sports betting expanded after a 2018 U.S. Supreme Court ruling allowed state-authorized sportsbooks, now live in 30 states, and starting in early 2025 prediction markets such as Kalshi and Polymarket added sports event contracts they classify as financial derivatives rather than wagers, reaching states without legal sportsbooks and users under 21. Because those contracts sit in a gray zone between federal oversight and state gambling regulation, the platforms are in active legal disputes with at least twelve states.

**「Impact」** The habit appears to strain young bettors&\#x27; finances: 52% of Gen Z investors in Betterment&\#x27;s survey said they moved money meant for investing into betting, and Bank of America found betting households&\#x27; median deposit balances were just 59% of those of non-betting households. Counselors add that even occasional wagering can hurt college students&\#x27; academics, while heavy losses raise the risk of gambling addiction.

<details><summary>References</summary>
<ul>
<li><a href="https://polycop.ai/blog/polymarket-kalshi-legal-states">Are Polymarket &amp; Kalshi Legal by State ? | PolyCop</a></li>
<li><a href="https://crypto.news/kalshi-polymarket-state-war-prediction-markets/">Kalshi and Polymarket are fighting a 50- state war</a></li>

</ul>
</details>

**Tags**: `#sports betting`, `#Gen Z`, `#prediction markets`, `#personal finance`, `#gambling addiction`

---