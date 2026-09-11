---
layout: default
title: "Horizon Summary: 2026-09-11 (EN)"
date: 2026-09-11
lang: en
---

> From 40 items, 12 important content pieces were selected

---

**Technology News**
1. [Rust is tier-1 language at Microsoft](#item-tech-news-1) ⭐️ 9.0/10
2. [Shopify moves its mobile apps from React Native back to native Swift and Kotlin](#item-tech-news-2) ⭐️ 8.0/10
3. [Forgejo 16.0.4 Fixes Critical RCE in Template-Based Repository Creation](#item-tech-news-3) ⭐️ 8.0/10
4. [More questions about whether researchers can trust OpenAI with unpublished math](#item-tech-news-4) ⭐️ 7.0/10
5. [Cognition Launches SWE-2 Coding Model, Sparking Hacker News Skepticism](#item-tech-news-5) ⭐️ 7.0/10
6. [PlanetScale Launches Neki, a Sharded Postgres Offering](#item-tech-news-6) ⭐️ 7.0/10
7. [trynix.dev: Boot Any Nix Package in Your Browser via WebAssembly](#item-tech-news-7) ⭐️ 7.0/10
8. [SemiAnalysis Examines Why Behind-The-Meter Power Is Hard for Datacenters](#item-tech-news-8) ⭐️ 7.0/10
9. [I tried to make a real fly connectome learn to play Pong. It didn&\#x27;t — and auditing why turned out to be way more interesting than if it had worked \[p\]](#item-tech-news-9) ⭐️ 7.0/10
10. [DeepSeek releases V4.1 Flash: 552B-parameter multimodal model with new API pricing](#item-tech-news-10) ⭐️ 7.0/10
11. [Chinese AI chipmakers raise prices as HBM shortage bites](#item-tech-news-11) ⭐️ 7.0/10
12. [腾讯混元开源音频编辑模型 AuK 并推出更快的 AuK-Flash](#item-tech-news-12) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Rust is tier-1 language at Microsoft](https://rustfoundation.org/media/guest-post-rust-is-tier-1-language-at-microsoft/) ⭐️ 9.0/10

The Rust Foundation confirms Microsoft has elevated Rust to a tier-1 language, marking a major endorsement of Rust for systems programming alongside C and C++.

hackernews · mmastrac · Sep 10, 13:39 · [Discussion](https://news.ycombinator.com/item?id=49643546)

**Tags**: `#rust`, `#microsoft`, `#systems-programming`, `#memory-safety`, `#language-adoption`

---

<a id="item-tech-news-2"></a>
### [Shopify moves its mobile apps from React Native back to native Swift and Kotlin](https://shopify.engineering/back-to-native) ⭐️ 8.0/10

Shopify has announced on its engineering blog that it is moving its mobile apps away from React Native and back to fully native development with Swift for iOS and Kotlin for Android. This is a notable reversal because Shopify was one of the most prominent large-scale adopters of React Native, so the decision carries weight as a signal about cross-platform frameworks. The announcement sparked extensive debate on Hacker News \(over 500 comments\), much of it centered on whether AI-assisted coding tools are changing the native-versus-cross-platform cost calculus: if LLMs make writing platform-specific code much cheaper, the main advantage of a shared codebase shrinks. Commenters reported that AI tools can now port a React Native app to native iOS and Android codebases remarkably quickly, while others argued such migrations were feasible before LLMs and cautioned that reading and manually testing code remain costly regardless of AI. The full technical details of Shopify&\#x27;s migration timeline and approach are not available in the supplied material.

hackernews · fnthawar2 · Sep 10, 14:09 · [Discussion](https://news.ycombinator.com/item?id=49643982)

**「Background」** React Native is a cross-platform framework that lets teams build iOS and Android apps from a single JavaScript/React codebase, and Shopify was one of its most prominent large-scale adopters, having previously migrated its mobile apps to React Native around 2020. Shopify&\#x27;s Shop app has now completed a migration back to native Swift and Kotlin, going from proof-of-concept to publication in 12 weeks, with the company arguing that AI coding agents changed the economics so that building twice natively can be cheaper than maintaining one shared codebase. This makes the announcement a notable signal for the broader native-versus-cross-platform debate in mobile development.

**「Impact」** Shopify&\#x27;s return to native Swift and Kotlin is a high-profile setback for React Native adoption among large enterprises, likely prompting other companies to reevaluate cross-platform frameworks for their own mobile apps \[tool-2-1\]. React Native developers and vendors may face increased pressure to demonstrate the framework&\#x27;s viability at scale, while native iOS and Android engineers could see renewed demand from organizations following this move.

**「Community Discussion」** Commenters broadly welcomed the move, with several sharing their own experiences of using AI tools like Codex to port React Native apps to native Swift and Kotlin in days, and one iOS engineer describing the decision as validating a long-running argument against shared codebases. Skeptics pushed back on attributing the shift to AI, noting comparable migrations succeeded without LLM assistance, and one commenter observed that AI reduces the cost of writing code but not of reading or manually testing it, so the long-term native-versus-cross-platform balance remains uncertain.

<details><summary>References</summary>
<ul>
<li><a href="https://shopify.engineering/back-to-native">Native is now the future of mobile at Shopify (2026) - Shopify</a></li>
<li><a href="https://shopify.engineering/shop-app-migration">Migrating Shop app from React Native to native (2026) - Shopify</a></li>
<li><a href="https://dev.to/jamilxt/shopify-is-moving-its-mobile-apps-back-to-native-coding-agents-made-it-cheaper-to-build-twice-than-4bf9">Shopify Is Moving Its Mobile Apps Back to Native. Coding Agents Made It Cheaper to Build Twice Than to Share One Codebase. - DEV Community</a></li>
<li><a href="https://vultrade.com/saas-devsecops/shopify-moves-back-to-native-from-react-native/">Shopify Moves Back To Native From React Native - Vultrade</a></li>

</ul>
</details>

**Tags**: `#react-native`, `#mobile-development`, `#swift`, `#kotlin`, `#shopify`

---

<a id="item-tech-news-3"></a>
### [Forgejo 16.0.4 Fixes Critical RCE in Template-Based Repository Creation](https://codeberg.org/forgejo/forgejo/src/branch/forgejo/release-notes-published/16.0.4.md) ⭐️ 8.0/10

Forgejo released version 16.0.4, which patches a critical remote code execution \(RCE\) vulnerability affecting releases up to and including 16.0.3. The flaw lies in the workflow for generating a new repository from a template repository: Forgejo clones the template, removes the .git folder, performs variable template expansion on files listed in .forgejo/template, and then initializes a new git repository, and during this process template expansion could interfere with git repository initialization, enabling code execution. The fix is delivered via a pull request described as &\#x27;Critical: fix: prevent template expansion from interfering with git repo initialization&\#x27;. Administrators running affected versions should upgrade to 16.0.4. Note that the official release notes page was temporarily hard to read due to Codeberg rate limits, but community comments quoted the relevant fix descriptions.

hackernews · weierstass · Sep 10, 15:57 · [Discussion](https://news.ycombinator.com/item?id=49645907)

**「Background」** Forgejo is a self-hosted, open-source software forge for Git repositories that follows semantic versioning, with a stable release line receiving bug and security fixes for three months and a long-term support release receiving critical and security fixes for a longer period. One of its features is template repositories: when a new repository is created from a template, Forgejo clones the template, removes the .git folder, performs variable template expansion on files listed in the .forgejo/template directory, and initializes a fresh git repository. Forgejo originated as a fork of the similar Gitea project, which is why the two platforms share much of their codebase and are often compared when vulnerabilities are disclosed.

**「Impact」** Operators of self-hosted Forgejo instances on version 16.0.3 or earlier are exposed to a critical remote code execution risk when the template-based repository creation feature is used, so prompt upgrading to 16.0.4 is the concrete mitigation. Gitea, the related codebase, is confirmed by a Gitea project leader to be protected against these issues.

**「Community Discussion」** Commenters supplied the technical details of the fix and a working alternative link after the release notes became unreadable under Codeberg rate limits, and a Gitea maintainer confirmed Gitea is unaffected while urging that no one be shamed for reporting security incidents. One commenter speculated that Forgejo&\#x27;s disallowance of LLM contributions might leave it at a disadvantage against attackers who do use AI, though this was offered as personal conjecture rather than established fact.

<details><summary>References</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-89094">CVE-2026-89094 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://forgejo.org/docs/latest/admin/upgrade/">Upgrade guide | Forgejo – Beyond coding. We forge. Forgejo v15.0 is available — Forgejo Forgejo v16.0 documentation | Forgejo – Beyond coding. We forge. CVE Crowd | Crowd Intelligence on CVEs CVEs and Security Vulnerabilities - OpenCVE</a></li>

</ul>
</details>

**Tags**: `#security`, `#rce`, `#forgejo`, `#open-source`, `#git`

---

<a id="item-tech-news-4"></a>
### [More questions about whether researchers can trust OpenAI with unpublished math](https://mathstodon.xyz/@andreasthom/117240535270608201) ⭐️ 7.0/10

A widely discussed Hacker News thread examines whether OpenAI can be trusted with unpublished mathematical problems after concerns arose that the company published results connected to researchers&\#x27; confidential model interactions without attribution.

hackernews · pred\_ · Sep 10, 06:49 · [Discussion](https://news.ycombinator.com/item?id=49639408)

**Tags**: `#openai`, `#research-ethics`, `#machine-learning`, `#mathematics`, `#ai-industry`

---

<a id="item-tech-news-5"></a>
### [Cognition Launches SWE-2 Coding Model, Sparking Hacker News Skepticism](https://cognition.com/blog/swe-2) ⭐️ 7.0/10

Cognition announced SWE-2, a new AI coding model it claims rivals Fable 5.1 and GPT-Astra, and the launch drew substantial attention on Hacker News \(351 points, 142 comments\). Community discussion quickly surfaced several caveats: commenters noted that SWE-2 is post-trained from Kimi K3 rather than built from scratch, and pointed to a large gap between the model&\#x27;s reported Terminal Bench 2.1 score of 92.8% and its 27.3% on the newer Terminal Bench 4 \(released a few weeks prior\), which one commenter interpreted as a possible sign of benchmark overfitting rather than strong generalization. Skeptics also invoked Cognition&\#x27;s past controversy, in which a demoed coding bot supposedly completing Upwork tasks autonomously was shown to go off track, arguing vendor performance claims should be treated cautiously. Other commenters criticized the lack of published model statistics and questioned the value of another closed-weight provider, with some saying they would prefer open-weight alternatives like DeepSeek Flash 4.1. Because no source content from the announcement itself is available here, the model&\#x27;s full specifications and officially claimed numbers could not be independently verified from the supplied material.

hackernews · seelos · Sep 10, 15:29 · [Discussion](https://news.ycombinator.com/item?id=49645443)

**「Background」** SWE-2 is a coding-agent model from Cognition, the company behind the Devin coding agent, and it was not built from scratch: it is post-trained from Moonshot AI&\#x27;s Kimi K3, a 2.8-trillion-parameter open-weight model that had already undergone extensive reinforcement learning for agentic coding. Cognition states that its additional reinforcement learning added 5-6 points across many benchmarks and shifted K3&\#x27;s cost-performance frontier, positioning SWE-2 as a competitive, lower-cost coding model. Understanding the surrounding debate requires knowing that agentic coding models are commonly evaluated on benchmarks such as Terminal Bench and SWE-bench-style suites, and that &\#x27;benchmark overfitting&\#x27; \(colloquially, &\#x27;benchmaxxing&\#x27;\) refers to models scoring highly on benchmarks they were effectively tuned against while generalizing poorly to newer, unseen problem sets.

**「Impact」** Developers evaluating AI coding assistants gain another closed-weights option, but the reported gap between SWE-2&\#x27;s 92.8% on Terminal Bench 2.1 and 27.3% on the newer Terminal Bench 4 gives prospective adopters a concrete reason to validate the model on their own tasks before trusting its headline benchmark claims. With open-weight models like DeepSeek and Kimi having closed much of the capability gap with closed frontier models, teams that want self-hosting or independent verification may see little reason to add another closed provider.

**「Community Reaction」** Hacker News commenters were largely skeptical. The dominant criticism centered on the 65-point drop between Terminal Bench 2.1 \(92.8%\) and Terminal Bench 4 \(27.3%\) scores as evidence of possible benchmark overfitting, alongside distrust rooted in Cognition&\#x27;s earlier Devin demo controversy. Some commenters acknowledged that RL-training Kimi K3 to competitive capability is itself a meaningful demonstration, while others dismissed the launch outright, citing poor personal experience with Devin and frustration with yet another closed-weight model.

<details><summary>References</summary>
<ul>
<li><a href="https://www.orcarouter.ai/blog/cognition-swe-2-release">Cognition SWE - 2 : Frontier Coding at 64% Off, Plus a Trap</a></li>
<li><a href="https://cognition.com/blog/swe-2">Introducing SWE - 2 : Pushing the Pareto Frontier | Cognition</a></li>
<li><a href="https://genztech.blog/p/cognition-swe-2-coding-model-launch/">Cognition &#x27;s SWE - 2 Nearly Matches GPT-6 Astra for a Quarter</a></li>
<li><a href="https://axiomstudio.ai/blog/open-weight-models-deepseek-kimi-open-vs-closed">Open-Weight Models 2026: DeepSeek, Kimi, Open vs Closed ...</a></li>

</ul>
</details>

**Tags**: `#AI models`, `#code generation`, `#benchmarks`, `#machine learning`, `#software engineering`

---

<a id="item-tech-news-6"></a>
### [PlanetScale Launches Neki, a Sharded Postgres Offering](https://planetscale.com/blog/introducing-neki) ⭐️ 7.0/10

PlanetScale has launched Neki, a sharded Postgres product, extending its database platform beyond the MySQL-based Vitess technology the company was originally built on. According to the launch analysis, Neki provides sharding for Postgres, addressing the problem that a single Postgres instance becomes a bottleneck at large scale, and describes technical components intended to let users run and deploy a horizontally scaled Postgres deployment. The launch matters because PlanetScale is a well-known player in the database infrastructure market, and its entry brings commercial competition to the emerging sharded Postgres space, where open source alternatives such as Multigres are also being developed. However, the announcement drew criticism on Hacker News for unclear communication: commenters noted that the launch post explained the problem and the technical components without clearly stating early on what Neki actually is or what it is for. Neki is a closed-source, commercial product, which contrasts with PlanetScale&\#x27;s history of building its company on the open source Vitess project that originated at Google.

hackernews · simon\_weber · Sep 10, 15:43 · [Discussion](https://news.ycombinator.com/item?id=49645686)

**「Sharding and PlanetScale&\#x27;s Vitess roots」** Sharding—splitting a database&\#x27;s data horizontally across multiple servers—is the standard way to scale a database beyond a single machine, and Postgres lacks robust built-in support for it, which is why third-party sharding layers exist. PlanetScale built its original business on Vitess, the open-source MySQL sharding technology that originated at YouTube, and after extending its platform to Postgres it announced Neki on August 11, 2025 as its horizontal sharding solution for Postgres. The relevant comparison point is Multigres, an open-source Postgres sharding project that commenters describe as a Vitess-style equivalent, which frames the criticism that Neki itself is closed source.

**「Why It Matters」** Engineering teams evaluating distributed Postgres options now have a major commercial, closed-source alternative alongside open source efforts like Multigres, though the community response suggests buyers may demand clearer documentation of Neki&\#x27;s architecture and consistency guarantees before adopting it.

**「Community Reaction」** Hacker News discussion \(107 comments\) centered on three themes: criticism that the launch post failed to clearly state what Neki is or its purpose, questions about whether Neki provides strong consistency rather than eventual consistency given CAP theorem tradeoffs for HA distributed deployments, and unease about the closed-source strategy, with several commenters pointing out the irony that PlanetScale built its business on open source Vitess \(originally from Google\) while releasing a proprietary Vitess-like equivalent for Postgres. Commenters also contrasted Neki with Supabase&\#x27;s open source Multigres project and criticized the PlanetScale CEO for publicly positioning Neki as superior while keeping it closed source.

<details><summary>References</summary>
<ul>
<li><a href="https://planetscale.com/docs/postgres/sharding">Horizontal sharding for Postgres - PlanetScale</a></li>
<li><a href="https://planetscale.com/blog/announcing-neki">Announcing Neki — PlanetScale</a></li>
<li><a href="https://www.infoq.com/news/2025/10/planetscale-metal-postgres/">PlanetScale Extends Database Platform to PostgreSQL - InfoQ</a></li>

</ul>
</details>

**Tags**: `#postgresql`, `#sharding`, `#distributed-systems`, `#planetscale`, `#databases`

---

<a id="item-tech-news-7"></a>
### [trynix.dev: Boot Any Nix Package in Your Browser via WebAssembly](https://simonwillison.net/2026/Sep/10/trynix/) ⭐️ 7.0/10

Farid Zakaria has launched trynix.dev, which he calls his &quot;magnum opus&quot; of Nix work: a service that runs an x86\_64 Linux virtual machine entirely in the browser using qemu-wasm, a QEMU build compiled to WebAssembly. The VM can boot any Nix package from the past 13 years, and each package is URL addressable — for example, visiting https://trynix.dev/?pkg=python3%403.6.2 and clicking &quot;Load&quot; opens an interactive shell inside a virtual machine running Python 3.6.2 from 2017. This demonstrates a practical combination of in-browser virtualization with Nix&\#x27;s reproducible package model, requiring no servers or local installation. Zakaria is extending the concept, most notably with trynix-preview, a GitHub Action that comments a link on a pull request so reviewers can boot the PR&\#x27;s build directly in the browser, described as requiring &quot;no servers, just browsers.&quot; The tool highlights how WebAssembly-based VMs and Nix&\#x27;s historical package archive can together make software environments instantly shareable and inspectable.

rss · Simon Willison · Sep 10, 23:44

**「Background」** Nix is a package manager whose reproducible build system allows exact historical package versions to be rebuilt and shared years later, which is what makes a 13-year archive of bootable packages possible. qemu-wasm is a port of the QEMU virtual machine emulator to WebAssembly, enabling a full x86\_64 Linux system to run client-side inside a standard browser tab.

**「Impact」** Nix developers and code reviewers can now reproduce and test any package from the past 13 years, or boot a pull request&\#x27;s build directly from a GitHub comment, without installing Nix or any local tooling — trynix-preview does this with no servers, only browsers. This lowers the barrier to verifying reproducible builds and reviewing changes, though the underlying qemu-wasm technology is still early-stage with known performance and compilation-overhead limitations.

<details><summary>References</summary>
<ul>
<li><a href="https://patchew.org/QEMU/cover.1744032780.git.ktokunaga.mail@gmail.com/">[PATCH 00/10] Enable QEMU to run on browsers</a></li>
<li><a href="https://github.com/ktock/qemu-wasm">GitHub - ktock/qemu-wasm: QEMU on browser · GitHub</a></li>

</ul>
</details>

**Tags**: `#nix`, `#webassembly`, `#virtualization`, `#developer-tools`, `#reproducible-builds`

---

<a id="item-tech-news-8"></a>
### [SemiAnalysis Examines Why Behind-The-Meter Power Is Hard for Datacenters](https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the) ⭐️ 7.0/10

SemiAnalysis has published the first part of a deep-dive series, &\#x27;What is So Hard About Behind-The-Meter Power For Datacenters?&\#x27;, examining the technical and economic challenges of powering datacenters with behind-the-meter electricity, which is power generated on-site rather than drawn from the public grid. The piece arrives amid surging AI-driven energy demand that is straining grid capacity and forcing hyperscalers and datacenter operators to explore alternatives to traditional utility interconnection, where multi-year wait times for grid connections have become a major bottleneck. The article&\#x27;s framing contrasts &\#x27;dumb science experiments&\#x27; with &\#x27;money printing machines,&\#x27; suggesting it evaluates which behind-the-meter approaches are economically viable versus technically flawed, though the available source excerpt is limited to this subtitle. Because the full article content was not supplied, specific technical findings, cost figures, and vendor assessments from the piece cannot be reliably summarized here, and readers should consult the original SemiAnalysis article for the detailed analysis.

rss · Semianalysis · Sep 10, 14:28

**「What Behind-The-Meter Power Means」** Behind-the-meter \(BTM\) power refers to electricity generation located on the customer&\#x27;s side of the utility meter, allowing a datacenter to generate power on-site rather than relying solely on grid deliveries, and it spans a spectrum of grid relationships between primary and backup power, including configurations that are marketed as microgrids but may not truly qualify as such. The concept matters now because AI-driven datacenter buildouts are outpacing grid interconnection timelines, pushing operators to consider on-site generation despite higher costs: datacenter-scale behind-the-meter gas generation currently runs roughly $80-120/MWh versus $40-60/MWh for grid power in most US regions, making the premium effectively a price paid for speed of deployment.

**「Impact」** As AI-driven load growth collides with grid interconnection delays and congestion, datacenter operators and developers are increasingly pushed toward behind-the-meter solutions—on-site gas generation, fuel cells, microgrids, and eventually small modular reactors—reshaping how sites are selected, designed, and powered. The depth of these technical and economic challenges means that organizations able to solve behind-the-meter power can build capacity on faster timelines, while those relying solely on grid connections face slower deployments.

<details><summary>References</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/what-is-so-hard-about-behind-the">What is So Hard About Behind - The - Meter Power For Datacenters ?</a></li>
<li><a href="https://gentic.news/article/semianalysis-us-behind-the-meter">SemiAnalysis: US behind - the - meter datacenter … | gentic.news</a></li>
<li><a href="https://www.youtube.com/watch?v=CVfxSDNW3G4">Big Power Needed Now! How Behind - the - Meter ... - YouTube</a></li>
<li><a href="https://radiant.co/blog/what-is-behind-the-meter-power">Demystifying Behind - the - Meter : What It Actually Means... | Radiant Blog</a></li>
<li><a href="https://www.rvninc.com/post/the-future-of-behind-the-meter-power-in-the-ai-and-data-center-era">The Future of Behind - the - Meter Power in the AI and Data Center Era</a></li>

</ul>
</details>

**Tags**: `#datacenters`, `#power-infrastructure`, `#ai-infrastructure`, `#energy`, `#hardware`

---

<a id="item-tech-news-9"></a>
### [I tried to make a real fly connectome learn to play Pong. It didn&\#x27;t — and auditing why turned out to be way more interesting than if it had worked \[p\]](https://www.reddit.com/r/MachineLearning/comments/1wc67ci/i_tried_to_make_a_real_fly_connectome_learn_to/) ⭐️ 7.0/10

An ML practitioner describes attempting dopamine-style plasticity learning on a real 166k-neuron fly connectome subgraph in Pong, and explains how auditing the failure—finding a neuPrint regex bug and connectivity issues—yielded more insight than success would have.

reddit · r/MachineLearning · /u/oPeraza2007 · Sep 10, 02:28

**Tags**: `#machine learning`, `#connectomics`, `#neuroscience`, `#negative results`, `#plasticity`

---

<a id="item-tech-news-10"></a>
### [DeepSeek releases V4.1 Flash: 552B-parameter multimodal model with new API pricing](https://mp.weixin.qq.com/s/qg0NU3NNUbp1co2PdkAPAg) ⭐️ 7.0/10

DeepSeek has officially released V4.1 Flash, described as the smallest model in its new model-architecture series. It uses a 552B-parameter Causal-Encoder-Decoder structure with 8B input activations and 16B output activations, and it natively supports multimodal visual understanding. The model is now available through the DeepSeek API under the model name deepseek-flash, with new pricing taking effect at 12:00 on September 10, 2026. DeepSeek also stated that after 12:00 on September 14, requests to deepseek-v4-pro will be routed to V4.1 Flash and billed at its prices. The announcement, circulated via a Telegram channel aggregation, does not include benchmark results or independent verification of the model&\#x27;s performance claims.

telegram · zaihuapd · Sep 10, 05:54

**「Background」** DeepSeek is a Chinese AI lab known for releasing large open models with cost-efficient serving, and its recent releases have emphasized architectures that lower inference cost relative to traditional decoder-only transformers. The Causal-Encoder-Decoder design behind V4.1 Flash is a new architecture family that separates encoding and decoding to reduce per-token computation and KV cache size, while Mixture-of-Experts \(MoE\) sparsity means only a small fraction of the total parameters is active for each token. External listings describe V4.1 Flash as a 552B-parameter MoE model with roughly 8B active parameters during prefill and 16B during decode, support for contexts of up to one million tokens, and a position as the smallest model in this new architecture series rather than an incremental point release.

**「Why it matters」** Developers using deepseek-v4-pro via the DeepSeek API will be automatically migrated to V4.1 Flash after September 14, 2026, and should expect its pricing and behavior instead. Because the figures come from a channel announcement rather than primary documentation, exact rates and technical specifications should be confirmed against official DeepSeek sources.

<details><summary>References</summary>
<ul>
<li><a href="https://deepinfra.com/deepseek-ai/DeepSeek-V4.1-Flash">DeepSeek V 4 . 1 Flash API - Demo - DeepInfra</a></li>
<li><a href="https://zenmux.ai/deepseek/deepseek-v4.1-flash">deepseek / deepseek - v 4 . 1 - flash - ZenMux</a></li>
<li><a href="https://www.orcarouter.ai/blog/deepseek-v4-1-new-base-model">DeepSeek V 4 . 1 Flash : New Base Model, Not a Point Release</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#large language models`, `#model release`, `#multimodal AI`, `#API pricing`

---

<a id="item-tech-news-11"></a>
### [Chinese AI chipmakers raise prices as HBM shortage bites](https://www.reuters.com/world/asia-pacific/chinas-ai-chipmakers-raise-prices-high-bandwidth-memory-shortage-bites-2026-09-10/) ⭐️ 7.0/10

Chinese AI chipmakers Huawei and Cambricon have begun raising prices as a global shortage of high-bandwidth memory \(HBM\) tightens supply, according to a Reuters report relayed via a Telegram channel. Huawei&\#x27;s Ascend 950DT chip is now quoted roughly 20–50% higher than two months earlier, with some older chips up about 30%, while Cambricon&\#x27;s next-generation Siyuan 690 is expected to rise around 20–30%. HBM, the stacked memory critical to AI accelerator performance, is supplied almost entirely by SK Hynix, Samsung, and Micron, and US export restrictions further constrain its availability to Chinese buyers. As domestic AI compute demand grows, the HBM shortage is emerging as a key bottleneck limiting the expansion of China&\#x27;s homegrown AI chip output. The specific price figures originate from the aggregated report and could not be independently verified from the item alone.

telegram · zaihuapd · Sep 10, 09:29

**「Why HBM Matters for AI Chips」** High Bandwidth Memory \(HBM\) is stacked memory that sits alongside or atop AI processors and provides the massive data throughput that training and running large models requires, which is why every modern AI accelerator depends on it. The global HBM supply is concentrated in just three vendors — SK Hynix, Samsung, and Micron — and US export controls restrict Chinese companies&\#x27; access to advanced chips and components, pushing firms like Huawei and Cambricon toward domestic processors while simultaneously limiting their ability to source cutting-edge parts.

**「Higher costs for China&\#x27;s AI compute buildout」** Chinese organizations procuring domestic AI accelerators face sharply higher acquisition costs and tighter availability, raising the expense of scaling China&\#x27;s AI compute capacity. Because the reported figures are unverified, the actual magnitude of the increases remains uncertain.

<details><summary>References</summary>
<ul>
<li><a href="https://economictimes.indiatimes.com/tech/artificial-intelligence/chinas-ai-chipmakers-raise-prices-as-high-bandwidth-memory-shortage-bites/articleshow/134010412.cms">China&#x27;s AI chipmakers raise prices as high-bandwidth memory...</a></li>
<li><a href="https://slguardian.org/chinas-ai-chip-ambition-hits-a-memory-bottleneck/">China’s AI Chip Ambition Hits a Memory Bottleneck – Sri Lanka...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#HBM memory`, `#semiconductor supply chain`, `#Huawei`, `#export controls`

---

<a id="item-tech-news-12"></a>
### [腾讯混元开源音频编辑模型 AuK 并推出更快的 AuK-Flash](https://x.com/TencentHunyuan/status/2097996926876795197) ⭐️ 7.0/10

腾讯混元宣布正式发布 AuK，一款开源音频编辑模型，可通过自然语言指令结合参考音频统一完成语音生成与编辑。该模型支持零样本文本转语音，以及音色、风格和情绪编辑，还包括去口音和多人语音分离等功能。与之同步推出的是 AuK-Flash，一个采用 4 步推理的精简版本，在匹配条件下速度提升约 4.5 倍。代码、模型权重和在线演示均已上线。该公告缺乏详细的技术文档和全面的基准测试，因此此处引用的性能数据仅基于官方说法。

telegram · zaihuapd · Sep 10, 11:56

**「Background」** Unified speech models combine text-to-speech generation with editing tasks—such as changing voice timbre, style, or emotion, removing accents, and separating overlapping speakers—into a single system controlled by natural language instructions and a reference audio clip, rather than requiring separate specialized models per task. Tencent Hunyuan is the AI division of Tencent, which has previously released other open-source foundation models; AuK follows this pattern, shipping its code and weights on GitHub and Hugging Face under the AuK Technical Report, with AuK-Flash as a distilled variant that uses 4-step inference to reduce generation latency for faster deployment.

**「Impact」** Developers and speech-AI practitioners gain free \(MIT-licensed, per third-party coverage\) access to a compact 1.5B open-weight model that unifies zero-shot TTS, voice/style/emotion editing, accent removal, enhancement, and multi-speaker separation under one natural-language interface, with weights downloadable from ModelScope and code on GitHub. For teams previously reliant on closed APIs for these tasks, AuK—especially the 4-step AuK-Flash variant with roughly 4.5x faster inference—lowers the cost of building voice applications, though the announcement omits detailed benchmarks needed to verify quality against established alternatives.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/Tencent-Hunyuan/AuK">Tencent - Hunyuan / AuK : AuK : An Open - Source Foundational Model ...</a></li>
<li><a href="https://huggingface.co/tencent/AuK-Flash">tencent / AuK - Flash · Hugging Face</a></li>
<li><a href="https://github.com/Tencent-Hunyuan/AuK">Tencent - Hunyuan / AuK : AuK : An Open - Source Foundational Model ...</a></li>
<li><a href="https://auk-project.github.io/">AuK — An Open - Source Foundational Model for Speech Generation ...</a></li>
<li><a href="https://www.orcarouter.ai/blog/auk-open-weights-speech-explained">AuK : Tencent &#x27;s Quiet Open -Weight 1.5B Speech Editor</a></li>

</ul>
</details>

**Tags**: `#open source`, `#audio editing`, `#text-to-speech`, `#Tencent Hunyuan`, `#speech AI`

---