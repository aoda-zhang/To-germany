# 德国面试问题库 / German Interview Question Bank

> 基于 `fullStack-CV.json`（**唯一权威版本**）生成。
> 定位：假设一位德国公司的 **Senior HR + 技术面试官**，在看到你这份简历后可能提出的问题。
>
> **每题结构：**
> - **中文** — 问题翻译与考察意图（帮你理解为什么这么问）
> - **English question** — 面试官会怎么问（照着念）
> - **English answer outline** — ✅ **可以直接用英文说出来的答题骨架**
> - **中文备注** — 关键提醒、易踩坑

> 💡 **怎么用这份文档：** 面试是英文的，所以 **English answer outline 才是主体**。中文部分只帮你理解考察点。
> 建议：把每题的英文骨架**出声念 3 遍**，直到不用看也能说。

---

**处理方式：**
1. 以 JSON 为准，去改 `myCV.md` 和 `self-introduction.md`
2. ⚠️ JSON 里没有的数字，**面试中不要说**
3. ⚠️ 如果某个指标**确实是你做的**，把它补进 JSON，而不是删掉 —— 但要能扛住追问
4. 每个数字都要能说清**统计口径**（分母是什么、怎么统计的、多长时间）

**JSON 里的全部 8 个数字指标**（本文件已逐条覆盖对应问题）：

| # | 指标 | 出处 | 对应问题 |
|---|---|---|---|
| 1 | 5 个微前端服务 | Manulife | 2.1 |
| 2 | 样式问题 ↓≥30% | Manulife | 2.1 |
| 3 | 新报告开发时间 ↓40% | Manulife | 2.2 |
| 4 | 3000+ 基金经理 | Manulife | 2.4 |
| 5 | 卖家发布效率 ↑40% | Newegg | 2.6 |
| 6 | 12+ 移动端功能 | Newegg | 2.7 |
| 7 | 2000+ 日活 | Hucai | 2.8 |
| 8 | HR 工时 ↓60% | Hucai | 2.9 |

---

## 0.5 ⚠️ 职责边界表：每段经历你到底做了什么

**中文：** 这是最容易翻车的地方。简历上每家公司只有一行 `techStack`，它反映的是**日常主要用的技术**，不等于你参与过的所有工作。面试官会顺着简历往下钻，**吹出来的技术一定会被问穿**。

| 公司 | 职位 | 技术栈 | 你的真实定位 |
|---|---|---|---|
| **Manulife** | Full-stack Software Engineer | TypeScript, React, Express.js, NestJS, MongoDB | ⭐ **唯一可以放心讲后端的地方** —— 你是全栈岗，前后端都能深讲 |
| **Newegg** | Senior **Frontend** Software Engineer | JavaScript, TypeScript, React, React Native, Redux | **前端为主**。RN、迁移、组件都是前端话题。不要说「我们设计了微服务架构的后端」 |
| **Hucai** | **Frontend** Software Engineer | JavaScript, Vue, React, Redux, Webpack | **纯前端**。购物车/库存的**一致性方案是后端实现的**，你负责的是前端交互和状态 |

### 绝对不能说的话

| 不能说 | 为什么 | 应该怎么说 |
|---|---|---|
| 「我们用乐观锁/事务消息表/幂等解决了库存一致性」（在 Hucai） | 你是前端，没参与后端设计 | 「一致性由后端团队实现，我负责的是客户端的状态管理和接口对接」 |
| 在 Newegg/Newegg 时期讲后端架构设计 | 那是前端岗，技术栈里没有后端 | 讲前端：迁移、组件、RN、性能 |
| 把 Manulife 的后端能力说成「我以前就会」 | 时间线对不上 | 「这是我在 Manulife 这两年开始做的，是有意识地从前端往全栈扩展」 |

### 被问到不会的问题时，用这三句

> **1. 诚实划界：** "That was implemented by the backend team — my part was the client integration and the UX around it."
>
> **2. 说明现状：** "Deep backend work is something I picked up deliberately at Manulife over the last two years, with NestJS and MongoDB."
>
> **3. 反问回去：** "I'd be interested to hear how your team handles that."

⚠️ **德国面试非常看重诚实和边界感。** 说「这不是我做的，但我想知道你们怎么做」比硬装强得多 —— 后者一旦被问穿，**整场面试的可信度全部崩塌**。

---

## 1. HR 面试（HR Round）

### 1.1 为什么想来德国 / Why Germany

**中文考察点：** 动机真实性。德国 HR 最怕中国候选人「拿 offer 跳板」，会追问「三个月你就走了怎么办」。必须是**长期性**理由。

**English question:**
> You're doing well in China — you're at a major global company. Why Germany, and why now?

**English answer outline:**
> I've been working toward this for a while, not just recently. What draws me to Germany specifically is the engineering culture — the emphasis on structured engineering, real code review, and testing discipline. In my current role at Manulife I work on financial products where correctness matters, and I've seen how much a strong engineering culture pays off. I've also been building an open-source project in my spare time and I work with colleagues across different countries, so working in an international environment isn't new to me.
>
> It's not about escaping anything — my motivation is that I want to grow as an engineer within a different engineering culture, and I want to stay long-term, not just land a contract.

⚠️ **中文备注：**
- ❌ 不要说「想拿欧盟身份」「想逃避」「国内卷」
- ✅ 要表现成**长期决定**，不是临时起意
- ✅ 提一句你做过功课（了解德国工程文化 / 已了解该公司）

---

### 1.2 为什么选我们公司 / Why us

**中文考察点：** 是否做过功课。德国公司非常看重 `Warum Sie sich für unser Unternehmen interessieren`。

**English question:**
> What do you know about our company, and why are you interested in this role?

**English answer outline:**
> I've looked into [Company] — you [one specific thing: product/market/engineering practice]. What stood out to me is [specific: e.g. a technical blog post, a product, a recent release].
>
> On the role side, it lines up well with where I want to go. I'm frontend-heavy but I've deliberately moved into backend over the last few years — Node, Express, NestJS — because I want to own whole features end to end, not just a layer. That's exactly the trajectory this role offers.

⚠️ **中文备注：** 必须说出**该公司具体业务**，不能泛泛而谈。至少能说出：他们做什么、目标客户、公开的技术栈。

---

### 1.3 工作许可 / Visa & work permit（**必问**）

**中文考察点：** ⚠️ 你的 CV 里 `workPermit`、`blueCard`、`residenceStatus` 三个字段是空的。这在德国是硬性障碍，不是技术问题。

**English question:**
> What is your current visa and residence status in Germany?
> Would you require visa sponsorship?

**English answer outline:**
> I'm currently based in Berlin on a [type of visa — 填你的真实情况]. For this role I would need Blue Card sponsorship, and I've already started the process — specifically the [ANAB / ZAB] degree recognition.
>
> I understand the lead time and I've planned around it. From my side the notice period would be 30 days, and [my earliest possible start date].

⚠️ **中文备注：**
- **先把你的真实居留状态填清楚**，不要说错
- Blue Card 需要担保要**主动说**，别等对方问
- README 里的 **ZAB / ANAB 学历认证**是德国技术岗前置条件，尽快办

---

### 1.4 薪资期望 / Salary expectations

**中文考察点：** 德国标准流程，谈崩直接 lose offer。给区间不给单点。

**English question:**
> What are your salary expectations?

**English answer outline:**
> Could I ask what the budget range is for this role? Based on my experience and the market in [city], I'd be looking at roughly **X to Y thousand euros gross per year** — but I'm flexible depending on the overall package, including the technical scope of the role and the holiday allowance.

⚠️ **中文备注：** 先反问预算区间，再说自己的区间。最后一句留谈判空间。

---

### 1.5 离职时间 / Notice period & availability

**English question:**
> When can you start, and what's your notice period?

**English answer outline:**
> My notice period is 30 days, so if I receive an offer today I could start on [specific date]. I want to leave with a proper handover — my current employer has been good to me and I want to leave things in a clean state.

⚠️ **中文备注：** 给**确定日期**，不要说「尽快」。德国 HR 排期需要确定性。

---

### 1.6 语言 / Language

**中文考察点：** CV 里 German A1。国际团队英语即可，但**德语 A1 会被追问学习计划**。

**English question:**
> Our working language is English, but German is common in the team. How is your German?

**English answer outline:**
> My German is currently A1 — I've started learning and I can follow simple technical conversations, but I'm not there yet in a professional setting.
>
> I've started a structured course and my goal is B1 within the next [timeframe]. In the meantime I work comfortably in English, including in meetings, code review, and technical documentation.

⚠️ **中文备注：** 不隐瞒也不夸大。展示**具体计划**比嘴硬更有说服力。

---

### 1.7 反问薪资结构 / Logistics

**English question:**
> Before we talk about specifics — do you have any questions about the role or the process?

**English answer outline:**
> Yes, a couple. First, what's the biggest problem this hire is meant to solve? And second, what does the team's current tech stack and direction look like?

⚠️ **中文备注：** 第一轮不要问薪资和假期，留给 HR 轮。见第 7 节完整反问清单。

---

## 2. 简历深挖（Resume Deep Dive）

> 德国面试**几乎必问**，而且会一段一段往下钻。**每一行简历都要能展开 5 分钟。**

### 2.1 Manulife — Design Token（重点）

**English question:**
> You implemented design tokens across 5 micro-frontend services, reducing styling issues by at least 30%. How did you measure that, and what did you actually build?

**English answer outline:**
> The problem was that five micro-frontends had grown independently — each had its own theme, its own spacing, and hard-coded colors. The same UI element looked slightly different in every product, and it kept coming back as bugs.
>
> What I did was extract a single set of design tokens — color, spacing, typography, radius — as the source of truth. I named them **semantically** rather than by appearance, so instead of `blue-500` it's `color-text-primary`. Then I built the tokens as a shared package that each service consumes, and added lint rules so hard-coded values would fail CI.
>
> On the 30% — that's the reduction in styling-related UI defects we tracked, and I want to be precise about the denominator: it was [your real denominator: e.g. UI bugs per release over N months], measured against [comparison period].

⚠️ **中文备注：** 「30% 的分母是什么」几乎必被追问，**提前想好真实口径**。

**必答追问：**
| 追问 | 要点 |
|---|---|
| Token 怎么命名？ | 语义化 `text-primary`，不是 `blue-500` |
| 怎么保证 5 个团队都迁移？ | 强制 lint + review 卡点 + 迁移排期 + owner |
| 为什么不用 Tailwind？ | 能说出取舍（token 是设计语言，Tailwind 是工具层，可叠加） |
| Design token 和组件库的区别？ | token 是底层契约，组件库是上层实现 |

---

### 2.2 Manulife — PDF 模块重构（重点）

**English question:**
> You refactored a legacy PDF report module with React, cutting new report development time by 40%. What made it slow?

**English answer outline:**
> The module had been built up over years and every new report meant someone had to reverse-engineer how an existing one worked, then copy and adapt it.
>
> On the technical side the main issues were [pick only the ones you actually hit — do not list things you didn't do]:
> - synchronous generation blocking the request thread
> - repeated font and image loading per report
> - data fetching during report assembly
>
> I refactored it into [your real approach: a shared template layer, async generation with a notification on completion, batch data prefetching]. The 40% is about **development time for new reports** — meaning how long it takes to stand up a new report from scratch.

⚠️ **中文备注：**
- 「测量方式」比「结论」更重要 —— 准备 p95 耗时这类证据
- ⚠️ 权威口径是**开发时间 ↓40%**，不是交付时间
- ⚠️ Manulife 是全栈岗，讲后端细节没问题，但**只讲你真正做过的部分**

---

### 2.3 Manulife — 组件库 + AI Review

**English question:**
> You independently designed the component library architecture and integrated AI-powered review. Walk me through it.

**English answer outline:**
> The component library is built in layers — foundations (tokens), then primitives, then composed components. The key decision was that tokens are the contract: any component consumes tokens, never raw values, so a brand change happens in one place.
>
> On the AI review part — to be clear about what it is and isn't: we use it to **assist**, not to decide. It generates a first-pass review and suggests improvements, but a human always reviews and approves, and nothing merges automatically. I've seen it produce confidently wrong suggestions, which is exactly why the human gate matters.

⚠️ **中文备注：** ⚠️ **不要**说「50+ 组件、交付时间 ↓35%」—— 权威 JSON 里没有。如果这确实是你做的，**先补进 JSON**。

**必答追问：**
| 追问 | 要点 |
|---|---|
| `What happens when the AI is wrong?` | 有人类把关 + 有 fallback + 不自动合并 |
| 组件库怎么衡量成功？ | 覆盖率、复用率、UI 缺陷下降、新功能交付速度 |
| 版本策略？ | semver、changelog、migration guide |
| 怎么让别的团队愿意用？ | 降低接入成本 + 文档 + 有人响应支持 |

---

### 2.4 Manulife — 基金交易模块（3000+ 基金经理）

**中文考察点：** 简历用词是 "Collaborated" —— 面试官会确认你到底做了什么。金融业务必须懂。

**English question:**
> You contributed to fund trading modules supporting 3,000+ fund managers. What was your exact scope, and what was technically the hardest part?

**English answer outline:**
> My focus was on [your real scope — be explicit about what you owned vs what the team owned]. On the business side, that meant working with the fund operations team to understand the domain — subscription and redemption flows, trading windows, and how a fund manager's eligibility is determined before they can transact.
>
> Technically, the hard part was [your real answer]. In financial systems the requirement is asymmetric — a wrong trade can't just be rolled back, everything has to be traceable and auditable. That shaped how we designed the error handling and logging.

⚠️ **中文备注：**
- ⚠️ **简历原文是 "Collaborated on"，不是 "Led"** —— 讲的时候保持一致，被问到要能说清边界
- ⚠️ 明确边界，不要含糊，也不要升级成「我主导的」
- 提前准备金融概念：申购/赎回、交易时段、净值、KYC/适当性管理
- 高频追问：**"金融系统和普通电商最大的区别？"** → 出错代价不对称，可追溯/可回滚/可审计
- ✅ Manulife 是全栈岗，**这里可以放心讲后端**，但仍需说清哪部分是你做的

---

### 2.5 Newegg — Angular → React 迁移（**最可能被问**）

**中文考察点：** ⭐ 这是你简历里技术含量最高的一条，几乎必被深挖。

**English question:**
> You led an Angular-to-React micro-frontend migration with zero production downtime across three teams. That's one of the hardest types of project there is. Tell me about it.

**English answer outline:**
> The context was that we had an Angular monolith that three teams were all working in — which meant releases were blocking each other constantly.
>
> We chose micro-frontends over a rewrite for two reasons: teams could deploy independently, and we didn't have to throw away working Angular code, which kept the risk manageable.
>
> For the migration itself, the critical part was **progressive rollout** — routing-level traffic splitting, starting at 1%, then 10%, 50%, 100%, with a kill switch to roll back instantly at any point. We defined the contract between applications up front: module boundaries, how they communicate, and which shared dependencies were version-locked.
>
> Across three teams the thing that mattered most was agreeing on the contract before anyone wrote code — otherwise each team made slightly different assumptions and integration became painful.
>
> Looking back, I'd bring the observability in earlier. We monitored rollout metrics per stage, and doing that from day one would have been better than retrofitting.

⚠️ **中文备注：**

**必答追问：**
| 追问 | 要点 |
|---|---|
| 微前端之间怎么通信？ | 事件/接口；**不要直接 import**，避免耦合和版本冲突 |
| 共享依赖怎么管？ | 单独 package + 版本锁定，避免各应用各自升级 |
| 怎么保证团队不互相破坏？ | 契约测试、集成测试、发布流程卡点 |
| 灰度比例怎么定的？ | 1% → 10% → 50% → 100%，每档观察指标 |
| 双运行时的问题？ | 依赖重复、包体积、跨应用状态共享 |
| 如果重做？ | 更早定契约、更早做监控 |

---

### 2.6 Newegg — A+ 内容市场（效率提升 40%）

**English question:**
> Your A+ content marketplace improved seller publishing efficiency by 40%. What exactly was measured, and how did you improve it?

**English answer outline:**
> Sellers were spending a lot of time building these rich product listings, and the process was repetitive and error-prone.
>
> What I built was [your real solution: templating, a proper editor, image reuse, better preview performance]. The 40% refers to [your real metric — e.g. average time to publish a listing], comparing [period] against [baseline].

⚠️ **中文备注：** ⚠️ 面试官大概率追问 **"40% 的分母是什么？统计了多长时间？"** —— 提前备好真实口径。

---

### 2.7 Newegg — React Native（12+ 功能）

**English question:**
> You delivered 12+ mobile features with React Native. What are the trade-offs of RN versus native development?

**English answer outline:**
> The main advantage is cross-platform reuse — one codebase, and you can iterate and release to both platforms without waiting on two separate native pipelines. That matters a lot when you need to ship features fast.
>
> The trade-off is that you hit a performance ceiling. List rendering, animations, and anything touching native APIs directly get harder. The usual pattern is to use RN for the product surface and drop to native modules when you need the performance.
>
> There are also non-technical costs — native module dependencies slow down upgrades, and hiring becomes harder because you need people who can bridge both worlds.

⚠️ **中文备注：** 准备 1–2 个**具体的 RN 功能案例**，证明你真做过，不只是知道概念。

---

### 2.8 Hucai — 购物车/库存前端（2000+ 日活）

⚠️ **重要：这是你的前端岗位（`JavaScript, Vue, React, Redux, Webpack`），没有后端栈。**

**中文考察点：** 你负责的是**前端这一层**：状态管理、接口对接、交互与异常处理。库存一致性的**方案是后端定的**，不是你实现的。

**English question:**
> You worked on cart and inventory features for an e-commerce platform with 2,000+ daily users. What was your part in that?

**English answer outline:**
> My role there was frontend — I owned the cart and inventory experience in the client: state management, integrating with the inventory APIs, and how it behaved when things went wrong.
>
> The consistency rules themselves were implemented on the backend by the other team. My job was to make sure the UI represented them correctly — for example, reflecting that stock is only deducted at checkout and not when you add to cart, and surfacing limits clearly so users didn't hit an error at the last step.
>
> What I did own was the client-side experience around edge cases: what the user sees when an item sells out mid-session, how we handled the error responses coming back, and keeping that logic testable.

⚠️ **中文备注：**
- ❌ **绝对不要说**「我们用乐观锁」「事务消息表」「幂等」—— 那是后端的事，你没参与
- ✅ 正确姿势：**说清边界**，然后讲你真正做的（前端状态、接口对接、边界体验）
- ✅ **面试官问后端细节时，诚实回答**：「That was implemented by the backend team — my part was the client integration.」这比硬装更有说服力
- ✅ 可以补充：你现在在 Manulife 已经**开始做后端**（NestJS/MongoDB），说明是有意识地在扩展 —— 这正好呼应你「以前端为主的全栈」定位

---

### 2.9 Hucai — 考勤平台（HR 工时 ↓60%）

**English question:**
> Your attendance platform served 1,000+ employees and cut HR manual workload by ~60%. How was that measured?

**English answer outline:**
> The measurement is the manual hours HR spent each month aggregating attendance data — that went from roughly [X] hours to about [Y] after the system was in place, so around 60%.
>
> Technically the flow was: collect clock-in data, calculate automatically, flag exceptions, and generate reports. The data accuracy question was the interesting part — you have to handle missing punches, late corrections, and proxy punching.
>
> But honestly the hard part wasn't technical. The system is only worth anything if employees actually use it, and that took convincing people who'd been doing it manually for years. Adoption was the real project.

⚠️ **中文备注：** 「内部工具怎么落地」是加分项 —— 能讲出推广过程，说明你懂落地而不是只会写代码。

---

### 2.10 教育背景（**必问，且会问很久**）

**中文考察点：** ⚠️ **德国面试官对非科班背景特别关注。** 答不好会被怀疑「基础不牢」。**必须真诚 + 有作品佐证。**

**English question:**
> I noticed you studied Journalism. How did you transition into software development?

**English answer outline:**
> I first came into contact with programming [at university / through a personal project] — [your real origin story, one or two sentences, concrete].
>
> What made it stick was [the moment it clicked for you — the process of understanding how something works and then building it]. That's what made me want to do it professionally.
>
> I then deliberately filled the gaps: [your self-taught path — courses, books, projects]. The strongest evidence is my work — I've been doing this for [9+] years, most recently leading a micro-frontend migration across three production teams and building a component library at Manulife. I also maintain an open-source project, which I work on independently.
>
> I'd be honest that I didn't start with a computer science degree. But I've spent years building the fundamentals and the professional track record speaks for itself.

⚠️ **中文备注：**
- ❌ 不要贬低新闻专业（"新闻没前途"）
- ❌ 不要只说"自学了" —— 要给**产出证据**（开源项目、GitHub、真实工作成果）
- ✅ 强调持续性：9 年 + 现在还在做开源

**追问：**
| 追问 | 要点 |
|---|---|
| 计算机基础比科班弱吗？ | 不回避：承认差距，说明补齐了什么，给证据 |
| 怎么系统学的？ | 具体课程/书/项目，不要空谈 |
| 为什么公司要招非科班的？ | 用产出来证明，不用辩解 |

---

### 2.11 技能自评都是 Intermediate？

**中文考察点：** 自我认知一致性。CV 里所有技能都标了 intermediate，但职位是 Senior。

**English question:**
> I noticed all your skills are listed as "Intermediate", but you're a Senior engineer. Is that accurate?

**English answer outline:**
> That's an artifact of the CV tool — it only offers a fixed set of levels. If I'm honest about where I actually am: [React and TypeScript — strong, I've built component libraries and led a migration], [backend with Node/NestJS — solid working knowledge, I own features end to end], [infrastructure — working knowledge].
>
> I'd rather give you an honest picture than a uniform label.

⚠️ **中文备注：** **分技术栈诚实自评**，表现出对自己能力边界的清晰认知 —— 这比「全都很强」可信得多。

---

## 3. 技术面试 — 前端（Technical — Frontend）

### 3.1 React 渲染机制 / React rendering

**English question:**
> Explain React's rendering. Why do function components re-execute on every render?

**English answer outline:**
> React is declarative — components don't re-run because you call them, they re-render because their inputs changed: state, props, or context. React then reconciles the output against the previous render and only updates the actual DOM nodes that changed.
>
> That's the key distinction: re-running a component is cheap, touching the DOM is what's expensive. React's job is to minimise the second one. Fiber and concurrent features like `useTransition` are about prioritising which work is urgent.

**追问：**
| 问题 | 要点 |
|---|---|
| `useMemo` / `useCallback` 何时用？ | 传给 memo 化的子组件、依赖稳定的回调；不要滥用 |
| `useEffect` 正确用法？ | 依赖数组、异步清理、不要在 effect 里同步 setState |
| `key` 的作用？ | 列表 diff 的身份标识；用 index 会出 bug |
| React 18 变化？ | 并发渲染、自动批处理、`useTransition`、Suspense |

---

### 3.2 TypeScript

**English question:**
> When would you use `any`? What's the real value of advanced TypeScript types?

**English answer outline:**
> In business logic I avoid `any` — I use `unknown` and narrow it, because `any` silently disables the type checking that's the whole point.
>
> I use `any` at boundaries where I genuinely don't know yet — a third-party library without types, or during an incremental migration where the old code was JS.
>
> The value of types isn't clever syntax, it's that you find bugs at compile time instead of in production, and it documents what a function expects. I only reach for advanced generics when they make the call sites clearer — if my teammates can't read it, it's a net negative.

---

### 3.3 微前端 / Micro-frontends

**English question:**
> When would you choose micro-frontends, and what do they cost you?

**English answer outline:**
> They make sense when you have multiple teams working independently, when you have legacy systems you can't afford to rewrite, and when business boundaries are reasonably clear.
>
> They don't make sense for a small team or a simple product — the operational cost is real.
>
> The costs are: you give up a single runtime, so you need isolation between apps; deployment and monitoring become more complex; cross-application state is genuinely hard; and debugging across boundaries is harder. In my migration the thing that saved us was defining the contracts between applications before anyone wrote code, and having a rollback switch at every rollout stage.

---

### 3.4 Design System / Design Token

**English question:**
> How do you build a design system that stays maintainable rather than becoming a dumping ground?

**English answer outline:**
> Three layers: primitives (raw values) → semantic tokens → components. The semantic layer is the important one — it's what lets a brand change happen in one place.
>
> For maintainability: consistent component APIs, real documentation with usage examples, a migration guide when something changes, and someone owning it. A design system without an owner degrades — people fork it, work around it, and you end up with three button components again.

**追问：** 如何度量成功？→ 覆盖率、复用率、UI 缺陷变化、新功能交付速度

---

### 3.5 性能优化 / Performance

**English question:**
> Walk me through a performance optimisation you actually did.

**English answer outline:**
> I always start by measuring, otherwise you're just guessing — Lighthouse, the Performance panel, and ideally real user monitoring.
>
> [Pick one real example. Structure it as:] the symptom was [what users or metrics showed], I measured [how], the cause turned out to be [root cause], I changed [specific fix], and the result was [before → after numbers].
>
> Common levers depending on the problem: code splitting and lazy loading for the initial bundle, avoiding unnecessary re-renders, virtualising long lists, and image format and loading strategy for LCP.

⚠️ **中文备注：** 每个优化都要有**前后数据对比**。没有数据的优化说出来等于没做。

---

### 3.6 CSS 与浏览器 / CSS and the browser

**English question:**
> Flexbox versus Grid — when would you use each?

**English answer outline:**
> Flexbox is one-dimensional — it lays out along a single axis and is content-driven. Grid is two-dimensional, handling rows and columns together, and it's container-driven.
>
> In practice: Grid for overall page or component layout where you want both axes; Flexbox inside a component for aligning things in a row or column.

**追问：**
| 问题 | 要点 |
|---|---|
| BFC 是什么？ | 块级格式化上下文，影响浮动/外边距折叠 |
| 重排/重绘/回流区别？ | 重排最贵（layout），重绘次之（paint），合成最便宜 |
| 如何减少重排？ | 批量读写、避免逐个改几何属性、用 transform |

---

## 4. 技术面试 — 后端（Technical — Backend）

### 4.1 Node.js 事件循环 / Event loop

**English question:**
> Explain the Node.js event loop. What's the order of `setTimeout(fn, 0)` vs `setImmediate`?

**English answer outline:**
> The loop has distinct phases — timers, pending callbacks, poll, check, close. `setImmediate` runs in the check phase, `setTimeout` in the timers phase, so the order between them is non-deterministic when both are scheduled from the top level — that's a classic interview gotcha.
>
> The practical implication is that you must never block the main thread. Anything CPU-intensive belongs in worker threads or a separate process, otherwise your whole server stalls.

**追问：** `process.nextTick` 优先级高于 Promise microtask。

---

### 4.2 NestJS 架构 / Why NestJS

**English question:**
> Why NestJS instead of plain Express?

**English answer outline:**
> Express is minimal and gives you total control — good for small services and for exactly the middleware you need. Nest is a structured layer on top: modules, dependency injection, decorators, and conventions around controllers, services, and modules.
>
> I chose Nest when I moved to backend work because the structure scales with the team. When several people work on a service, conventions mean a new developer knows where things are without reading everything. With plain Express, structure tends to diverge per developer and eventually becomes the thing you're complaining about.

**追问：** DI 怎么理解？循环依赖怎么处理？Guard / Pipe / Interceptor 区别？

---

### 4.3 MongoDB

**English question:**
> How did you model your data, and when would you *not* use MongoDB?

**English answer outline:**
> I design the schema around the access patterns — the queries the application actually runs — and index for those. Embedded vs referenced depends on data size and whether it's always read together: embed when it's small and co-accessed, reference when it grows or is shared.
>
> I wouldn't use it when I need strong transactional consistency or complex relational querying — at that point a relational database is the honest choice. Mongo is the right tool when the document shape fits naturally and you value flexibility.

**追问：** 索引失效场景？`ObjectId` 是什么？如何做分页？

---

### 4.4 REST API 设计

**English question:**
> How do you design a REST API, and how do you handle versioning?

**English answer outline:**
> Resources are nouns, the HTTP verb expresses the action. Status codes carry meaning — 200, 201 for created, 204 for no content, 400 bad request, 401 unauthenticated, 403 authenticated but not allowed, 404, 409 conflict, 500.
>
> For versioning I use a path prefix like `/api/v1/`, which is explicit and obvious in logs. Breaking changes get a new version; non-breaking additions go into the existing one.
>
> Paging, filtering and sorting need to be part of the contract from the start, because retrofitting them later means breaking every existing client.

---

### 4.5 安全 / Security

**English question:**
> What backend security concerns have you considered?

**English answer outline:**
> Injection — always use parameterised queries or a proper ORM, never string-concatenate SQL.
>
> Authentication and authorisation are separate concerns. For tokens, I'd avoid `localStorage` because it's exposed to XSS; httpOnly cookies are safer, and you need refresh and expiry handled properly.
>
> Also: never log sensitive data, keep dependencies patched, and validate input at the boundary regardless of what the frontend already did — the client is never trusted.

---

### 4.6 系统设计 / System design（**必考**）

**English question (typical for your background):**
> Design a system where sellers can publish rich product content, with preview and moderation before it goes live.

**English answer outline (follow this structure):**
1. **Clarify first** — "Before I design, let me ask a few questions: expected traffic? Read/write ratio? Does every submission need review? How fast does content need to appear?"
2. **Estimate scale** — number of sellers, listings, storage and bandwidth
3. **API design** — endpoints, payloads
4. **Data model** — listing, version, media, moderation status
5. **Architecture** — storage, cache, queue for async processing, CDN
6. **Scalability & reliability** — what happens if the queue backs up; what if the CDN fails
7. **Observability** — what do you monitor and alert on

⚠️ **中文备注：**
- ⭐ **最重要的是先澄清需求再动手** —— 这一步就能拉开差距
- 练习：Pramp 上找 mock，或用 https://github.com/donnemartin/system-design-primer 过一遍

---

## 5. 行为面试（BQ / Behavioural）

### 5.1 最难的技术问题 / Hardest problem

**English question:**
> Tell me about the hardest technical problem you've solved.

**答题结构 STAR（英文顺序：Situation → Task → Action → Result → Reflection）：**
> **Situation:** [context — scale, constraints]
> **Task:** [what specifically you had to solve]
> **Action:** [what *you* did — your judgement, not "we"]
> **Result:** [outcome with the number from your CV]
> **Reflection:** [what you'd do differently — this is what German interviewers value most]

⚠️ **中文备注：** 用你的**微前端迁移**或 **PDF 重构**。最后一段「复盘」是加分项，很多候选人不说。

---

### 5.2 犯过的错误 / A mistake you made

**English question:**
> Tell me about a mistake you made.

**English answer outline:**
> [Pick a real but non-fatal mistake. Structure:] what happened, what the impact was — and I want to be honest about the impact — what I did about it, and what I changed so it wouldn't happen again.
>
> The lasting change was [process/tool/convention], not just "I was more careful".

⚠️ **中文备注：**
- ⚠️ 不要选无关痛痒的，也不要「我太追求完美」这种假答案
- ⚠️ **不甩锅**给"团队原因"
- 关键是最后那句「机制上的改变」

---

### 5.3 技术分歧 / Technical disagreement

**English question:**
> How do you handle technical disagreements with colleagues?

**English answer outline:**
> First I try to make sure we're arguing about the same thing — usually we actually agree on the goal and disagree about the path.
>
> After that, I try to move the debate off opinion and onto evidence: a small prototype, a benchmark, or data from production. "I think X is faster" is much weaker than "I profiled it and here's the number".
>
> Once a decision is made I follow it even if I'd have chosen differently — and then we revisit it with real data. Disagreeing with the decision isn't the same as undermining the person who made it.

⚠️ **中文备注：** 德国公司重视**建设性冲突**和**直接沟通**。这个回答正好展示了「对事不对人」。

---

### 5.4 Code Review

**English question:**
> How do you do code review?

**English answer outline:**
> I separate blocking issues from suggestions. Blocking is bugs, security, and correctness — that has to be fixed. Everything else is a suggestion, and I mark it as such so people can judge.
>
> I try to explain *why*, not just what. A comment that says "this could cause a stale closure here" teaches something; a comment that says "fix this" doesn't.

---

### 5.5 为什么招你 / Why us

**English question:**
> Why should we hire you?

**English answer outline (three concrete pillars from your CV):**
> **First, end-to-end ownership.** I'm frontend-heavy, but I deliberately moved into backend with Node and NestJS so I can own a feature from data model to UI without waiting on someone else.
>
> **Second, I've done the hard migrations.** Leading an Angular-to-React micro-frontend migration across three teams with zero downtime is not a theoretical skill — I've done it. Same with building a component library and design tokens at Manulife.
>
> **Third, I work across cultures already.** The migration project meant coordinating across three teams, and I maintain an open-source project independently. Working in a distributed, international setting isn't new to me.

⚠️ **中文备注：** 用**具体项目**支撑，不要空喊形容词。

---

### 5.6 职业规划 / Career plans

**中文考察点：** ⭐ 德国公司很看重**稳定性预期**。

**English question:**
> Where do you see yourself in three to five years?

**English answer outline:**
> I'd like to go deeper on architecture and stay hands-on technically. I don't want to move entirely into management, but I'd like to be the person who shapes how the frontend and backend fit together — and I'd like to do that long-term, in Germany, rather than bouncing between countries.

⚠️ **中文备注：** ❌ 不要说「想创业」「想做管理」（除非投管理岗）。✅ 强调长期留在德国。

---

## 6. 德国求职特定问题（Germany-specific）

### 6.1 德国职场文化 / Working in Germany

**English question:**
> What do you know about working in Germany?

**English answer outline:**
> A few things I've read about and think I'd adapt to well. Communication is quite direct — people tell you when something is wrong rather than softening it, and I actually prefer that over guessing.
>
> Punctuality is treated as basic respect, meetings start and end on time. And there's a clearer separation between work and private time than I'm used to.
>
> Documentation is more thorough, and decisions tend to be recorded — which for me is a positive, because I'd rather build on what was already decided than re-litigate it.

⚠️ **中文备注：** 提前看你 README 里那条 `海外面试特点` 链接，别只答表面。

---

### 6.2 跨文化协作 / Cross-cultural work

**English question:**
> Have you worked across cultures or with distributed teams?

**English answer outline:**
> Yes — the micro-frontend migration at Newegg was across three separate teams, and coordinating them without a shared codebase was the main challenge. I also work with people in different countries on my open-source project.
>
> Working in English throughout that project is what I'm doing right now in this interview, so it's familiar territory.

---

### 6.3 试用期 / Probation

**中文考察点：** 不要主动问太多细节，让 HR 讲。

**English question:**
> Our probation period is six months. Does that work for you?

**English answer outline:**
> That works fine for me. I understand the probation period is there for both sides, and I tend to ask for feedback early rather than waiting until the end.

⚠️ **中文备注：** 表现出**主动要反馈**的意愿 —— 德国公司很吃这一套。

---

## 7. 你的反问（Questions to ask them）

**中文考察点：** ⭐ **不问 = 不感兴趣。** 德国面试官重视主动性。准备 4–5 个。

**English questions to have ready:**
1. What's the biggest problem this hire is meant to solve?
2. What does the team's current tech stack look like, and where is it heading?
3. What does success look like in the first three months?
4. How does the team work — Scrum, Kanban, something else?
5. What does code review and testing look like in practice?

⚠️ **中文备注：**
- ❌ **第一轮不要问**薪资和假期，留给 HR 轮
- ✅ 问「这个岗位最需要解决的问题」是最高质量的开场

---

## 8. 面试当天 Checklist

- [ ] **统一简历数字**（第 0 节）—— 其他文档改成和 `fullStack-CV.json` 一致
- [ ] **通读职责边界表（第 0.5 节）** —— 确认每段经历只讲自己真做过的
- [ ] **准备好签证/Blue Card 的英文回答**（1.3 必被问）
- [ ] **3 段经历各准备一个 5 分钟英文深讲**（design token / 微前端迁移 / PDF 重构）
- [ ] **准备 2 个失败案例**（真实、不致命、有复盘）
- [ ] **准备 4–5 个反问**
- [ ] 提前看公司官网 + 近期新闻 + 产品
- [ ] **把每题的 English answer outline 出声念 3 遍** —— 这是关键
- [ ] 测试线上会议（摄像头、网络、噪音、背景）
- [ ] 准备纸质简历（德国仍然常用）

---

## 9. 练习资源

| 资源 | 用途 |
|---|---|
| [Pramp](https://www.pramp.com) | 免费 mock，优先找欧洲岗位练习 |
| [Sesame](https://www.sesame.com) | 真实面试练习（README 已列） |
| [Cambly](https://www.cambly.com) | 口语练习，找有 HR 经验的老师 |
| 系统设计导论 | https://github.com/donnemartin/system-design-primer |
| MDN | https://developer.mozilla.org |
| EU Blue Card 官方信息 | https://make-it-in-germany.com |

---

## 相关文档

- [简历制作注意点](./resume.md)
- [自我介绍](./self-introduction.md)
- [英语准备](./English.md)
- [简历 Review](./review.md)
- 权威简历数据：[fullStack-CV.json](./fullStack-CV.json)