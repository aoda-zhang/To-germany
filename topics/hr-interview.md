# HR Interview

# 德国面试问题库 / German Interview Question Bank


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

#### 0 [自我介绍](./self-introduction.md)
### 1.1 为什么想来德国 / Why Germany

**中文考察点：** 动机真实性。德国 HR 最怕中国候选人「拿 offer 跳板」，会追问「三个月你就走了怎么办」。

**你的真实故事（记在心里，按下面的英文口径讲）：**
- 疫情期间家里发生了很糟糕的事情 → 之后你和妻子开始认真考虑搬去国外 —— 所以这是**从疫情就开始的多年家庭决定**，不是临时起意
- 2025 年你们有了孩子 → 「把孩子一起接过去」是**最强的长期承诺信号**，直接反驳「跳板」质疑
- 妻子的大学舍友在德国生活了 10 年 → 你们聊了很多 —— 这是「为什么是德国而不是别的国家」的真实答案
- 于是你开始学德语，A1 已学完、正在学 A2 → 用行动证明决心
- 计划拿到蓝卡、安顿好后把妻子和孩子接过去 → 家庭团聚，德国人完全理解并尊重这种路径

**English question:**
> You're doing well in China — you're at a major global company. Why Germany, and why now?

**English answer outline:**
> This is not a recent idea. My wife and I started seriously planning a move abroad during the pandemic — we went through a difficult time as a family in that period, and it made us rethink where we want to build our life long-term. So we've been working toward this for years, not months.
>
> Why Germany specifically? My wife's closest friend from university has been living in Germany for ten years. We've had many long, honest conversations with her about what life in Germany is really like — the work culture, raising a child, everyday life. So we're moving with a realistic picture, not a fantasy.
>
> And I've backed the decision with action: I started learning German — I've completed A1 and I'm working through A2 now. Our child was born in 2025, and the plan is clear: once I'm settled with a Blue Card, my wife and our child will join me. This is a family relocation, not a solo career move — we're building our life there.
>
> On the professional side it also fits: I work on financial products where correctness matters, and Germany's engineering culture — structured development, real code review, testing discipline — is exactly the environment I want to grow in long-term.

⚠️ **中文备注：**
- 疫情时家里的变故**一句话带过**（"a difficult time as a family"），不要展开细节 —— 展开像在卖惨，也容易被解读成「逃离」
- ❌ 不要说「想拿欧盟身份」「国内太卷」
- ✅ 三个长期性证据按顺序讲：**疫情时就开始的多年决定 → 已在学德语（A1 完 / A2 在学）→ 孩子出生、全家搬过去**
- ✅ 「为什么是德国」就答**妻子舍友在德 10 年** —— 真实、具体、有一手信息，还顺便说明你对德国的预期是现实的
- ✅ 被问「你一个人先来吗」→ 如实说：先拿蓝卡安顿好，再办家庭团聚接妻儿过来 —— 这是德国标准流程，HR 都懂

**可能的追问：**

| 追问 | 要点 |
|---|---|
| Will your family join you? | 会。拿到蓝卡安顿好后办家庭团聚（Familiennachzug），妻子和孩子一起过来 |
| What if you don't like it after three months? | 这是多年的家庭决定，且舍友 10 年的一手信息让我们对德国的预期是真实的，不存在「三个月幻灭」 |
| Why Germany and not another country? | 舍友的一手信息让德国成为我们了解最深的国家 + 工程文化和我的方向契合 |

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

**中文考察点：** CV 里写的是 German A1。你的真实进度是 **A1 已完成、A2 在学** —— 面试口径保持一致，不要一会儿 A1 一会儿 A2。国际团队英语即可，但德语水平会被追问学习计划。

**English question:**
> Our working language is English, but German is common in the team. How is your German?

**English answer outline:**
> I've completed A1 and I'm currently working through A2 — enough for everyday situations, but not yet a professional working level. I'm learning it because we're relocating as a family, so it matters to me beyond work.
>
> My goal is B1 within the next [timeframe]. In the meantime I work comfortably in English, including in meetings, code review, and technical documentation.

⚠️ **中文备注：**
- 不隐瞒也不夸大。展示**具体计划**比嘴硬更有说服力
- 「因为全家搬过去所以在学德语」这句正好呼应 1.1 的故事，让动机显得真实
- 如果你已经考出 A2 证书，记得同步更新 `fullStack-CV.json` 和简历里的 level

---

### 1.7 反问薪资结构 / Logistics

**English question:**
> Before we talk about specifics — do you have any questions about the role or the process?

**English answer outline:**
> Yes, a couple. First, what's the biggest problem this hire is meant to solve? And second, what does the team's current tech stack and direction look like?

⚠️ **中文备注：** 第一轮不要问薪资和假期，留给 HR 轮。见第 7 节完整反问清单。

---
