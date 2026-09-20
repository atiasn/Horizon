---
layout: default
title: "Horizon Summary: 2026-09-20 (ZH)"
date: 2026-09-20
lang: zh
---

> 从 30 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [为什么你几乎不该用 AI 来写作](#item-tech-news-1) ⭐️ 7.0/10
2. [ProgramAsWeights：将英文函数描述编译为可本地运行的神经程序](#item-tech-news-2) ⭐️ 7.0/10
3. [四家 AI 巨头因呼吁放缓研发遭反垄断诉讼](#item-tech-news-3) ⭐️ 7.0/10

**科技博客**
1. [咬紧牙关发出去：会构建的人为何难发布](#item-tech-blog-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [为什么你几乎不该用 AI 来写作](https://erichgrunewald.substack.com/p/why-you-should-almost-never-use-ai) ⭐️ 7.0/10

Eric Grunewald 于 2026 年 9 月 19 日在其 Substack 发表文章，主张人们几乎不应使用 AI 来撰写面向他人阅读的文字。文章援引 Eric Schwitzgebel 的论点：“生成文本”与“边读边点头”存在巨大的认知差异——初稿一旦由 AI 产出，作者就容易被动接受“大致够用”的措辞，不再像从头写作那样主动推敲用词，而 AI 添加的内容还会埋没作者真正想表达的意思。这是一篇观点文章，并未附带新的技术测量结果，但已在 Hacker News 引发 120 条评论的实质讨论。

hackernews · erwald · 9月19日 16:35 · [社区讨论](https://news.ycombinator.com/item?id=49767937)

**「发表背景」** 这篇文章并非首次发表：作者 Erich Grunewald 早在 2026 年 8 月 6 日就已在个人网站以《Why You Should Almost Never Use AI to Write Anything Substantive》为题刊出全文，并于同日在 LessWrong 上以链接帖形式分享，此次在 Hacker News 上引发讨论的是其 Substack 版本。原标题中的 &quot;Anything Substantive&quot;（任何实质性文本）点明了论点的适用范围：作者将&quot;写作&quot;定义为亲自在页面上生成文字这一行为，其主张针对的是博客文章、研究报告、备忘录、认真撰写的邮件、小说等旨在向读者传达想法、论证或分析的文本，而非所有写作场景。

**「影响」** 对把 LLM 用于工作写作的人，评论中已出现具体的代价案例：一位评论者报告，团队用 AI“总结”一份集体白皮书后，论证的细微差别以难以察觉的方式丢失，不得不花大量时间重读和修正。讨论中对应的做法是让 LLM 充当批评者而非代笔：让它点评你的草稿，由你自己判断采纳哪些建议，并拒绝它主动给出的整篇重写。

**「社区讨论」** 评论中被引用最多的框架来自 jameshart：可以用 AI 写“给你自己读”的文字——例如总结某主题的研究、为决策整理数据报告、把会议记录整理成邮件草稿——但不要用它写给别人消费的文字。foobarbecue 的立场更激进：既然 LLM 会加入你没写的内容，直接发布提示词反而更能传达本意，除非目的只是填充篇幅。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.erichgrunewald.com/posts/why-i-think-you-should-almost-never-use-ai-to-write-anything-substantive/">Why You Should Almost Never Use AI to Write Anything Substantive</a></li>
<li><a href="https://www.greaterwrong.com/posts/kjQdL3dxaACSbjkSx/why-you-should-almost-never-use-ai-to-write-anything-1">Why You Should Almost Never Use AI to Write Anything Substantive - LessWrong 2.0 viewer</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#writing`, `#communication`, `#opinion-essay`

---

<a id="item-tech-news-2"></a>
### [ProgramAsWeights：将英文函数描述编译为可本地运行的神经程序](https://www.reddit.com/r/MachineLearning/comments/1wl13eu/programasweights_compile_english_function/) ⭐️ 7.0/10

滑铁卢大学研究员 /u/yuntiandeng 在 Reddit 上发布了开源研究项目 ProgramAsWeights（PAW）：用英文写下一句函数描述（例如“分类紧急邮件”），即可编译成一个可保存、可组合、能在本地（包括 CPU）反复调用的神经程序；编译可使用官方托管服务，或用已发布的模型权重自托管编译器（需 GPU），程序和本地运行时下载完成后，后续调用不再依赖外部 API。其标准编译器是一个微调过的 Qwen3-4B 模型，为冻结的 Qwen3-0.6B“解释器”生成 LoRA 适配器，神经程序由该适配器和一个“伪程序”（编译时生成的清理版任务描述及少量输入输出示例，放入解释器提示词）组成，编译只需数秒，处理新输入时不再需要大模型。作者在自建的 FuzzyBench 基准（按任务规格划分训练/测试集）上报告，0.6B 解释器达到 73.4% 精确匹配准确率，高于直接提示 Qwen3-32B 的 68.7%；后续工作 Compile by Training 以生成的适配器为起点，用教师模型合成数据再微调约 100 步（约一分钟），在更难的 FuzzyBench-Hard 子集上报告 83.6% 语义准确率。代码、模型权重和在线演示均已公开，但上述数字均为作者自报结果，项目目前尚无独立评测或社区采用证据。

reddit · r/MachineLearning · /u/yuntiandeng · 9月19日 23:35

**「从 Text-to-LoRA 到可复用的神经程序」** LoRA 适配器是一种只向冻结的基础模型添加少量可训练权重、从而使其适配特定任务的轻量微调技术。2025 年，Charakorn 等人提出的 Text-to-LoRA 展示了超网络可以直接依据自然语言任务描述即时生成此类任务专用适配器，该工作发表于 ICML 2025。ProgramAsWeights 沿用了这一适配器生成机制，并将其扩展为&quot;编译—推理&quot;分离的范式：生成的适配器连同编译期产出的伪程序一起，构成可保存、分发并在本地小模型上反复执行的神经程序。

**「影响：固定文本任务可一次编译、本地离线运行」** 对于规格固定、输入持续变化的文本处理任务（分类、抽取、解析、格式转换等），PAW 的实际意义在于开发者可以用一次数秒的编译替代对大模型 API 的反复调用：编译产物是绑定冻结 Qwen3-0.6B 解释器的 LoRA 适配器，下载后可在本地乃至 CPU 上离线执行，但换用其他底座模型则需要另行适配。论文摘要确认作者已公开代码、模型权重和含 1000 万样本的 FuzzyBench 数据集，而 73.4% 精确匹配、高于直接提示 Qwen3-32B 的 68.7% 属作者自报结果，目前未见独立评测，因此落地前应按其建议先手写小型验证集检验编译出的函数。GitHub 上已出现第三方基于该思路的 Claude Code 实现，说明有早期尝试，但广泛采用的证据仍然缺乏。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.deeplearning.ai/the-batch/text-to-lora-generates-task-specific-lora-adapters-directly-from-natural-language-descriptions">Text-to-LoRA Generates Task-Specific LoRA Adapters Directly From Natural Language Descriptions</a></li>
<li><a href="https://github.com/sakanaai/text-to-lora">GitHub - SakanaAI/text-to-lora: Hypernetworks that adapt LLMs for specific benchmark tasks using only textual task description as the input · GitHub</a></li>
<li><a href="https://arxiv.org/abs/2607.02512">[2607.02512] Program-as-Weights: A Programming Paradigm for ...</a></li>
<li><a href="https://github.com/kseuro/program-as-weights/tree/main">GitHub - kseuro/program-as-weights: A Claude Code ...</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#neural-program-synthesis`, `#local-inference`, `#open-source`, `#natural-language-programming`

---

<a id="item-tech-news-3"></a>
### [四家 AI 巨头因呼吁放缓研发遭反垄断诉讼](https://www.politico.com/news/2026/09/18/anthropic-openai-spacexai-google-sued-over-calls-to-pace-ai-development-01085023) ⭐️ 7.0/10

Anthropic、OpenAI、SpaceXAI 和 Google 在美国加州联邦法院遭到消费者反垄断诉讼，起诉书指控四家相互竞争的 AI 企业高管公开支持协调放缓前沿 AI 能力进展，可能构成限制竞争的非法协议，涉嫌违反美国《谢尔曼法》第 1 条。诉状称，Anthropic CEO 达里奥·阿莫迪本月发文呼吁行业协同放缓前沿 AI 能力发展步伐，随后马斯克、奥特曼和哈萨比斯相继公开表示认同。原告为订阅上述公司 AI 服务的消费者，请求法院进行集体诉讼认证并发布禁令。该案目前处于起诉初期，相关指控尚未经法庭审理，四家公司均未回应置评请求。

telegram · zaihuapd · 9月19日 02:08

**「《谢尔曼法》第一条为何适用于公开表态」** 《谢尔曼法》第一条是美国反垄断法的核心条款，禁止竞争企业之间通过合同、联合或共谋限制贸易，传统案例多涉及竞争者秘密协商定价或限产。本案的特殊之处在于，原告试图将四家相互竞争的 AI 公司高管公开表态支持&quot;协同放缓前沿 AI 发展&quot;认定为非法协调的证据，而非依赖传统的秘密协议证据。据补充报道，该诉讼已于周五提交至美国加州北区联邦地区法院，指控四家公司在放缓 AI 发展策略上存在串谋。

**「对付费用户与研发实践的影响」** 这起已提交加州北区联邦法院的诉讼直接涉及四家公司 AI 服务的付费订阅用户：诉状指控协调放缓研发降低了 ChatGPT、Claude、Gemini 和 Grok 付费订阅的价值，并请求集体诉讼认证和禁令。若原告最终胜诉，禁令可能限制这些公司公开协调放缓前沿 AI 开发的做法，并推动其研发实践更透明。不过相关指控尚未在法庭上得到证实，受影响的付费用户可保留订阅记录并跟踪案件进展，而不应将起诉书视为协调行为已成立的证明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.independent.co.uk/news/world/americas/google-anthropic-openai-spacexai-lawsuit-antitrust-laws-b3052994.html">Lawsuit accuses Anthropic , OpenAI , Google and... | The Independent</a></li>
<li><a href="https://www.politico.com/news/2026/09/18/anthropic-openai-spacexai-google-sued-over-calls-to-pace-ai-development-01085023">Anthropic , OpenAI , SpaceXAI, Google sued over call to ‘pace’ AI ...</a></li>
<li><a href="https://apnews.com/article/antitrust-lawsuit-ai-slowdown-anthropic-openai-spacexai-google-960af4308161eaf4ed13c383b0ce1c1b">Antitrust lawsuit filed against AI companies challenges ...</a></li>
<li><a href="https://techjournal.org/ai-slowdown-antitrust-lawsuit">AI Slowdown Antitrust Lawsuit Targets Anthropic, OpenAI</a></li>
<li><a href="https://enterpriseai.economictimes.indiatimes.com/news/industry/anthropic-openai-spacexai-google-face-federal-antitrust-lawsuit-over-calls-to-slowdown-ai-development/134350351">Making AI Work: Federal Antitrust Lawsuit Targets AI Giants ...</a></li>

</ul>
</details>

**标签**: `#antitrust`, `#AI industry`, `#AI safety`, `#regulation`, `#litigation`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [咬紧牙关发出去：会构建的人为何难发布](https://seangoedecke.com/grit-your-teeth-and-ship-it/) ⭐️ 7.0/10

rss · Sean Goedecke · 9月20日 00:00

**「背景」** Sean Goedecke 提出，&quot;擅长构建&quot;与&quot;擅长发布&quot;是两种独立且短期相互掣肘的技能：对优雅、正确的代码有近乎病态追求的程序员，恰恰最难交出不完美的成果。他借 Ira Glass 的&quot;品味差距&quot;解释根源——人因好品味入行，也正因好品味而对自己的作品处处不满。

**「方案」** 在编程一侧，作者观察到，天赋型程序员会把代码缺陷当作情绪上的刺痛，担心带瑕发布显得自己不够细心或不够强；但大型系统本就遍布妥协，一致性比局部正确更重要，有时正确做法就是照搬既有缺陷（只要非灾难）。这类人于是常常僵住：退到改开发环境、重构测试等能安全追求&quot;正确&quot;的小天地，或在羞愧与内疚中空转直至离职。用他的话说，差的 diff 还能靠时间改进，&quot;没有 diff 则无从改进&quot;。写作一侧，他以自述经验佐证：过半博文完稿时他都觉得不够好，仍照发不误；而且发布是可练习的技能——停更一个月后下一稿显得拿不出手，日更时反而每篇感觉良好。他自称回看旧文已分不清当初满意与否，自我评价与传播效果毫无相关：几篇他不喜欢的文章反而流行，几篇满意的却无人问津。既然无法预测读者口味，高产量就比少量精雕细琢命中率更高；好点子也不必吝惜，同一主题可以反复写——他自称已围绕&quot;发布&quot;写了约三十篇。

**「启示」** 作者的核心结论是：既然无法靠打磨单件作品来保证成功，就应&quot;基于动量而非结果&quot;行事——咬紧牙关，把连自己都不满意的东西发出去，用产量换取命中。

**标签**: `#shipping`, `#software-engineering-culture`, `#perfectionism`, `#career-advice`, `#writing`

---