---
layout: default
title: "Horizon Summary: 2026-09-20 (EN)"
date: 2026-09-20
lang: en
---

> From 30 items, 4 important content pieces were selected

---

**Technology News**
1. [Essay argues you should almost never use AI to write for others](#item-tech-news-1) ⭐️ 7.0/10
2. [ProgramAsWeights compiles English function descriptions into locally runnable neural programs](#item-tech-news-2) ⭐️ 7.0/10
3. [Anthropic, OpenAI, SpaceXAI, Google face antitrust suit over AI slowdown calls](#item-tech-news-3) ⭐️ 7.0/10

**Technology Blog**
1. [Grit Your Teeth and Ship It](#item-tech-blog-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Essay argues you should almost never use AI to write for others](https://erichgrunewald.substack.com/p/why-you-should-almost-never-use-ai) ⭐️ 7.0/10

Eric Grunewald published an essay arguing that AI should almost never be used to write text intended for other people to read, contending that delegating generation to a model undermines the writer&\#x27;s own thinking and buries the writer&\#x27;s meaning under plausible approximations. Citing philosopher Eric Schwitzgebel, the essay claims there is a large cognitive difference between passively reviewing generated text and actively generating prose, and that even experts cannot reliably catch what a model adds, omits, or gets subtly wrong. The piece is an argument rather than a study — its claims rest on reasoning and anecdote rather than measurement — and it drew a roughly 120-comment Hacker News debate over which LLM writing use cases, if any, are defensible.

hackernews · erwald · Sep 19, 16:35 · [Discussion](https://news.ycombinator.com/item?id=49767937)

**「Background」** The essay was originally published on Erich Grunewald&\#x27;s personal website on August 6, 2026, and circulated as a linkpost on LessWrong before the Substack version drew the wider Hacker News debate. Its argument rests on a distinction Grunewald borrows from philosopher Eric Schwitzgebel: generating prose forces effortful, active choices about wording and meaning, whereas reviewing AI output tempts writers to passively let &quot;the approximate word suffice&quot; — the premise from which the essay&\#x27;s claims about acceptable LLM writing use cases follow.

**「Practical takeaway」** For knowledge workers weighing LLM writing tools, the discussion yields a direction test: point models at text you will read — research summaries, reports on data, drafts pulled from meeting transcripts — and keep authorship of anything others will consume, or limit the model to critiquing drafts you wrote yourself. One commenter&\#x27;s report of losing substantial time re-reading and correcting an AI-generated summary of a collective white paper, in which nuance disappeared in hard-to-notice ways, illustrates the verification and rework cost the essay warns about.

**「Reader debate」** Among the most substantive comments, jameshart proposed a dividing line — use AI to write things &\#x27;for you to read,&\#x27; such as summaries of research or reports on data, but never text you produce for someone else to consume — while rectang recommended using LLMs as critics of your own drafts, warning that they &\#x27;always give you a full rewrite&\#x27; that does too much. Foobarbecue argued more bluntly that LLM prose buries the author&\#x27;s meaning under material the author never wrote, and alas44 described losing considerable time fixing an AI summary that had stripped nuance from a white paper &\#x27;in sneaky ways.&\#x27;

<details><summary>References</summary>
<ul>
<li><a href="https://www.erichgrunewald.com/posts/why-i-think-you-should-almost-never-use-ai-to-write-anything-substantive/">Why You Should Almost Never Use AI to Write Anything Substantive</a></li>
<li><a href="https://www.greaterwrong.com/posts/kjQdL3dxaACSbjkSx/why-you-should-almost-never-use-ai-to-write-anything-1">Why You Should Almost Never Use AI to Write Anything Substantive - LessWrong 2.0 viewer</a></li>

</ul>
</details>

**Tags**: `#AI`, `#LLM`, `#writing`, `#communication`, `#opinion-essay`

---

<a id="item-tech-news-2"></a>
### [ProgramAsWeights compiles English function descriptions into locally runnable neural programs](https://www.reddit.com/r/MachineLearning/comments/1wl13eu/programasweights_compile_english_function/) ⭐️ 7.0/10

ProgramAsWeights \(PAW\) is an open-source University of Waterloo research project that compiles English function descriptions into reusable neural programs that then run locally, including on a CPU. Its standard compiler, a finetuned Qwen3-4B model, generates a LoRA adapter for a frozen Qwen3-0.6B interpreter plus a compile-time pseudo-program of a cleaned-up description and example input/output pairs; compilation takes seconds, and afterward calls run on the user&\#x27;s machine without an external API. On the project&\#x27;s own FuzzyBench benchmark, the author reports the 0.6B interpreter reaches 73.4% exact-match accuracy versus 68.7% for directly prompting Qwen3-32B, and a follow-up Compile by Training mode that finetunes the generated adapter for roughly a minute reaches 83.6% semantic accuracy on the harder subset. Code, compiler weights, a self-hostable GPU-based compiler, and a web demo are released, but the figures are self-reported on a synthetic benchmark and the Reddit post shows no independent evaluation or community adoption yet.

reddit · r/MachineLearning · /u/yuntiandeng · Sep 19, 23:35

**「Background」** LoRA adapters are small sets of trained weights that specialize a frozen base model for a particular task without modifying its core parameters. In work published at ICML 2025, Sakana AI researchers including Rujikorn Charakorn introduced Text-to-LoRA, a hypernetwork that generates such task-specific adapters directly from a natural-language description of the task, allowing a separate large language model to be adapted instantly from text alone. ProgramAsWeights adopts this adapter-generation mechanism but applies it to a different goal: training a compiler that equips a small frozen interpreter model with generated adapters so the resulting functions can run locally after a one-time compilation.

**「Impact」** Developers with fixed text tasks \(classification, extraction, parsing, format conversion\) get a compile-once deployment path: the Qwen3-4B compiler runs only at compile time — seconds per specification, or roughly a minute in the finetune mode — after which the generated adapter runs on a frozen Qwen3-0.6B interpreter locally on CPU with no external API calls; self-hosting the compiler requires a GPU, or the hosted compiler can be used. Two constraints matter before production use: compiled programs target the project&\#x27;s specific frozen Qwen3-0.6B interpreter, and the reported 73.4% exact-match accuracy \(versus 68.7% for directly prompting Qwen3-32B\) comes from the authors&\#x27; own synthetic FuzzyBench, so the author-recommended practice of validating each compiled function on a small handwritten test set should be treated as a prerequisite. Third-party uptake has begun: a separate GitHub repository \(kseuro/program-as-weights\) already provides a Claude Code-based implementation of the fuzzy-function paradigm.

<details><summary>References</summary>
<ul>
<li><a href="https://www.deeplearning.ai/the-batch/text-to-lora-generates-task-specific-lora-adapters-directly-from-natural-language-descriptions">Text-to-LoRA Generates Task-Specific LoRA Adapters Directly From Natural Language Descriptions</a></li>
<li><a href="https://github.com/sakanaai/text-to-lora">GitHub - SakanaAI/text-to-lora: Hypernetworks that adapt LLMs for specific benchmark tasks using only textual task description as the input · GitHub</a></li>
<li><a href="https://github.com/kseuro/program-as-weights/tree/main">GitHub - kseuro/program-as-weights: A Claude Code ...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#neural-program-synthesis`, `#local-inference`, `#open-source`, `#natural-language-programming`

---

<a id="item-tech-news-3"></a>
### [Anthropic, OpenAI, SpaceXAI, Google face antitrust suit over AI slowdown calls](https://www.politico.com/news/2026/09/18/anthropic-openai-spacexai-google-sued-over-calls-to-pace-ai-development-01085023) ⭐️ 7.0/10

Anthropic, OpenAI, SpaceXAI, and Google are facing a consumer antitrust lawsuit in California federal court alleging that their public endorsements of slowing frontier AI development amounted to illegal coordination under Section 1 of the Sherman Act. The complaint cites an essay published this month by Anthropic CEO Dario Amodei calling for the industry to jointly slow the pace of frontier AI capability development, followed by public statements of agreement from Elon Musk, Sam Altman, and Demis Hassabis. The plaintiffs, consumers who subscribe to the four companies&\#x27; AI services, are asking the court to certify a class action and issue an injunction. None of the companies had responded to requests for comment, and the suit remains at the filing stage with no court findings.

telegram · zaihuapd · Sep 19, 02:08

**「Legal backdrop」** Section 1 of the Sherman Act, the statute invoked in the complaint, bars agreements among competitors that restrain trade, and such cases have traditionally depended on evidence of a private arrangement — secret communications, meetings, or coordinated conduct — rather than public advocacy alone. The suit instead treats the executives&\#x27; public endorsements of slowing frontier AI development, a goal long urged by AI safety advocates concerned that competitive pressure pushes labs to release risky capabilities too quickly, as itself supplying the agreement element the law requires. The case, filed Friday in the U.S. District Court for the Northern District of California, will be an early test of whether openly calling for collective restraint on safety grounds can amount to illegal collusion.

**「What it means for subscribers」** Paid subscribers of ChatGPT, Claude, Gemini, and Grok are the group the suit aims to represent: the complaint, filed Friday in the U.S. District Court for the Northern District of California, seeks class certification and an injunction over claims that a coordinated slowdown reduced the value of those subscriptions. However, the September 18, 2026 filing has not established its allegations in court and none of the four companies has responded, so subscribers should follow the case and keep subscription records rather than treating the complaint as proof of coordination.

<details><summary>References</summary>
<ul>
<li><a href="https://www.independent.co.uk/news/world/americas/google-anthropic-openai-spacexai-lawsuit-antitrust-laws-b3052994.html">Lawsuit accuses Anthropic , OpenAI , Google and... | The Independent</a></li>
<li><a href="https://www.politico.com/news/2026/09/18/anthropic-openai-spacexai-google-sued-over-calls-to-pace-ai-development-01085023">Anthropic , OpenAI , SpaceXAI, Google sued over call to ‘pace’ AI ...</a></li>
<li><a href="https://apnews.com/article/antitrust-lawsuit-ai-slowdown-anthropic-openai-spacexai-google-960af4308161eaf4ed13c383b0ce1c1b">Antitrust lawsuit filed against AI companies challenges ...</a></li>
<li><a href="https://techjournal.org/ai-slowdown-antitrust-lawsuit">AI Slowdown Antitrust Lawsuit Targets Anthropic, OpenAI</a></li>

</ul>
</details>

**Tags**: `#antitrust`, `#AI industry`, `#AI safety`, `#regulation`, `#litigation`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Grit Your Teeth and Ship It](https://seangoedecke.com/grit-your-teeth-and-ship-it/) ⭐️ 7.0/10

rss · Sean Goedecke · Sep 20, 00:00

**「Background」** The essay tackles a paradox in creative work: the perfectionism that makes programmers and writers good at their craft — the drive for elegant, correct output — is the same trait that keeps them from shipping anything flawed. Being good at building and being good at shipping, the author argues, are separate skills that, in the short term, actually countervail each other.

**「Solution」** Following Ira Glass&\#x27;s taste gap, the mechanism is that good taste outruns early ability, so flaws hurt emotionally: shipping imperfect work feels like evidence of carelessness or incompetence. In a company this turns fatal, because large codebases are inevitably covered in flaws; working in one means compromise, and since consistency matters most, the right move is sometimes to duplicate non-catastrophic flaws. The author reports watching gifted programmers freeze — retreating to safe domains like dev-environment tweaks or test refactoring, or spinning in guilt until they quit — when a bad diff can be improved with effort but no diff cannot. His writing shows the same trap: he dislikes more than half his drafts at publish time, yet rereading later he cannot tell which ones those were, and his satisfaction shows no correlation with which posts become popular. Since you cannot predict what resonates, he argues, high volume yields more than a small amount of polished work — and ideas are not wasted, because you can revisit the same theme until it lands \(he estimates he has written thirty posts about shipping\).

**「Takeaway」** Because success on any single piece lies outside your control, the author concludes, you should be momentum-based rather than outcome-based: the only cure for the taste gap is to grit your teeth and publish.

**Tags**: `#shipping`, `#software-engineering-culture`, `#perfectionism`, `#career-advice`, `#writing`

---