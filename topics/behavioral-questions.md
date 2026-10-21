# Behavioral Questions (BQ)

## 5. 行为面试（BQ / Behavioural）

> **Expanded practice bank:** [200 CV-tailored questions across 10 behavioural categories](./bq-question-bank.md). Use that file for category-by-category practice; use this guide for the existing STAR framework, story selection, and answer outlines.

### 5.0 先建故事库：7 个故事打天下（准备方法）

**BQ 的真相：面试官不是在考你「这道题答过没有」，而是在几个固定维度收集信号** —— 动机、主动性、模糊环境下的自主性、坚持力、冲突处理、自我认知与成长、沟通（大厂通用评分维度，德国公司同样适用，来源见第 9 节 TIH rubrics）。

所以**不要按题背答案** —— 准备一个故事库，问题来了对号入座。每个故事能服务 3–5 个问题。

**你的故事库（全部来自你简历上的真实经历）：**

| # | 故事 | 一句话版本 | 覆盖的问题类型 |
|---|---|---|---|
| 1 | 微前端迁移（Newegg） | 3 团队 Angular→React 零停机，灰度发布 + kill switch | 最难的问题、压力、跨团队协作、关键决策、复盘 |
| 2 | Design Token 体系（Manulife） | 语义化 token 共享包 + lint 卡点，推动 5 个服务迁移 | 主动性、影响力、说服他人、坚持标准 |
| 3 | PDF 重构（Manulife） | 模板层 + 异步生成，新报告开发 ↓40% | 量化结果、接手没人想碰的遗留代码 |
| 4 | 考勤系统落地（Hucai） | 技术不难，难在让用了多年手工流程的人真用起来 | 说服与同理心、落地能力、推动采纳 |
| 5 | 前端→全栈（Manulife） | 两年内有意识补后端（NestJS/MongoDB） | 快速学习、成长心态、诚实谈弱点 |
| 6 | 前端架构 + 设计系统（Design Token）（Manulife） | 主动发现 5 服务样式不一致 ↔ 语义化 token 方案 → 说服团队 → 共享包 + lint → 好反馈；也是独立完成的代表 |
| 7 | 非科班转行（新闻学 → 9 年工程师） | 真实起点 + 产出证据（开源、微前端迁移） |
| 8 | ⚠️ 已补真实案例：PDF 重构 + Design Token（上表已更新） | 主动发现问题 → approve → 独立完成 → 好反馈 |
| 9 | 跨市场企业级前端架构（Manulife / Newegg / Hucai） | 9 年企业级 + 多市场，擅长技术选型与 tradeoff |

**使用规则：**
- 一个问题 = 从库里调一个故事，按 STAR 讲 2–3 分钟（STAR 结构见 5.1）
- 全程说 **I** 不说 we —— 德国面试官一定会追问「你个人具体做了什么」
- 能带数字就带数字（第 0 节的 8 个指标）
- 结尾一定加复盘（what I'd do differently）—— 这是德国面试官最看重的部分
- 同一场面试里**不要重复用同一个故事**，面试官之间会交换笔记

**你的真实优势（直接可用的英文表达，配合故事库）：**
> I'm strongest at frontend architecture and design decisions — I've spent years on enterprise-grade projects across multiple markets, so my work isn't just using React/TypeScript; it's deciding when to build vs. buy, how to split services, and what tradeoffs are worth making. Two recent examples: I independently rebuilt our PDF module and built the system's design-token architecture from scratch — both started because I spotted the problem, got approval, and delivered end-to-end with measurable results.

**你的真实弱点（直接可用，避免「我太完美」）：**
> I'm not deep on high-concurrency backend — cache strategies, event messaging, distributed systems. That's exactly why I deliberately expanded into backend at Manulife with NestJS, but I'm honest that I'm still stronger on architecture and frontend integration than on pure backend scale.

---

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
>
> **Your real examples to adapt:** PDF/module load issue missed early? Migration rollback plan missing a stage? Design token v1 missing edge-case tokens causing a regression? Pick one — make impact real — end with mechanism change.

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

### 5.7 BQ 大题库（按类别速查）

> 40+ 题不需要每题写答案 —— 每题从 **5.0 故事库**调一个故事，再看「要点」列即可。标 ⭐ 的是出现率最高的必练题。

#### A. 冲突、分歧与反馈

德国公司极重视**直接沟通**和 disagree & commit，这类题出现率最高。

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| ⭐ Tell me about a time you disagreed with a coworker. How did you resolve it? | 冲突处理 | 5.3 已详答；核心：先确认目标一致 → 从观点移到数据/证据 → 决定后执行 |
| Tell me about a time you disagreed with your manager. | 向上管理 | 私下提出、摆数据、给替代方案；决定后公开支持，不阴阳怪气 |
| Tell me about a time you received critical feedback. | 接受反馈 | 不辩解 → 问清具体 → 有改进行动 → 说出后续结果 |
| Tell me about a time you had to give difficult feedback. | 给反馈 | Code review 的 blocking vs suggestion 分级（5.4）；或对上级说「这个排期做不到」 |
| What would you do if you think your lead's decision is wrong? | 情境题 | 先问清背景 → 小 prototype / 数据 → 决定后 follow。❌ 别答「我会服从」也别答「我会硬扛到底」 |
| Tell me about a conflict on your team and how it was resolved. | 团队冲突 | 故事 1：3 个团队对迁移契约的分歧 → 先定契约再写代码 |

#### B. 失败、错误与压力

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| ⭐ Tell me about a mistake you made. | 自我认知 | 5.2 已详答 —— ⚠️ **把真实案例填进去** |
| Tell me about a project that didn't go as planned. | 失败复盘 | 故事 1 的复盘段：observability 引入太晚；或你的真实失败案例 |
| Tell me about a time you missed a deadline. | 责任感 | 关键是**提前预警**而不是拖到最后；重点讲怎么补救 + 后来怎么预防 |
| How do you handle pressure / competing priorities? | 优先级 | 按影响面和阻塞关系排序 + 主动和 stakeholder 对齐预期，不闷头硬干 |
| ⭐ Tell me about a time you had to learn something new quickly. | 学习速度 | 故事 5：两年内从前端补齐 NestJS/MongoDB —— 真实、有产出 |
| Tell me about a time you took a risk. | 判断力 | 灰度 1% 起步 —— 讲你如何把风险变**可控**，而不是讲你胆子大 |

#### C. 主动性、影响力与领导力

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| ⭐ Tell me about a time you took initiative beyond your role. | 主动性 | 故事 2：没人要求做 token，你发现问题 → 提方案 → 建共享包 → 立规范 |
| Tell me about a time you convinced others to change direction. | 影响力 | lint 卡点让 5 个团队迁移：讲清「为什么」+ 把接入成本降到最低 |
| Tell me about a time you showed leadership without formal authority. | 影响力 | token 体系的事实 owner：文档、迁移支持、版本管理，没有头衔照样推得动 |
| Have you ever pushed back on an unrealistic deadline? | 谈判 | 给选项不硬顶：砍范围 / 分期 / 加资源，让 decision maker 选 |
| Tell me about a time you took on a task nobody wanted. | 担当 | 故事 3：PDF legacy 模块，人人躲着走的那块代码 |

#### D. 团队协作与沟通

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| Tell me about a time you worked well in a team. | 协作 | 故事 1：3 团队在没有共享代码库的情况下协同迁移 |
| Tell me about a difficult stakeholder and how you worked with them. | 同理心 | 故事 4：用了多年手工流程的人不信任新系统 → 先听抱怨、再改设计、再推广 |
| ⭐ Explain a complex technical concept to a non-technical person. | 沟通 | token → 「同一个按钮在不同产品里长得不一样，客户以为我们不专业」这种翻译方式 |
| Tell me about a time miscommunication caused a problem. | 教训 | ⚠️ 待补真实案例；重点：怎么发现的 + 后来建立了什么机制 |
| How do you keep stakeholders informed of progress and risks? | 主动性 | 说**具体机制**：定期 demo、风险提前上报；不说「我沟通能力很好」 |

#### E. 自我认知与动机

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| ⭐ What are your strengths? | 自我认知 | 端到端 owner + 迁移经验 + 用产出说话（非科班但有 9 年证据） |
| ⭐ What is your greatest weakness? | 诚实度 | **真实的两条**：① 不擅长高并发后端（cache / event message 等）—— 这就是为什么选前端/全栈，Manulife 两年补 NestJS 但深度仍不如纯后端；② 早期习惯自己扛问题，后来学会提前暴露风险。❌ 别说「太追求完美」 |
| What's the best feedback you've received? | 成长 | 和你的失败故事呼应，两个答案要**相互一致** |
| What motivates you as an engineer? | 动机 | 把混乱理顺、做出可衡量的改进（↓40% 这类数字）；可带一句家庭长期定居德国的目标 |
| Why should we NOT hire you? | 压力测试 | 诚实：「如果你要的是 10 年经验的纯后端架构师，那我不是。但如果你要的是能把功能从数据模型做到 UI 的人，这正是我这两年的方向」 |
| What would your previous manager say about you? | 一致性 | 挑 1–2 个真实、可验证的评价点，别吹 |
| What's the project you're most proud of? | 动机 + 主动性 | **PDF 重构 + Design Token 双项目**：主动发现问题 → 拿到 approve → 独立完成 → 好反馈（设计师反馈 + 业务效率提升） |

#### F. 决策与模糊性

| 问题 | 考察点 | 用哪个故事 / 要点 |
|---|---|---|
| Tell me about a hard decision you made with incomplete information. | 决策 | 微前端 vs 全量重写：列出权衡（风险、团队独立部署、复用旧代码）→ 解释为什么这么选 |
| Tell me about a time you made a fast decision. | 果断 | 灰度阶段指标异常 → kill switch 回滚 → 修复 → 重新灰度 |
| How do you decide when to take on technical debt? | 工程判断 | 三问：影响面多大？有偿还计划吗？决策相关方知情吗？❌ 别说「永远不欠债」 |
| Tell me about an ambiguous task you were given. | 自主性 | 「把样式问题解决一下」—— 只有问题没有方案；先量化问题，再建 token 体系 |
| Speed vs quality — what trade-off have you made? | 权衡 | 灰度发布本身就是答案：用流程换速度（1% 起步 = 又快又稳） |

#### G. 德国特有 / Teamfit

| 问题 | 考察点 | 要点 |
|---|---|---|
| How do you handle direct criticism? | 文化适配 | 直接 ≠ 针对个人；「明确的负面反馈比客气的模糊更好」—— 呼应 6.1 |
| What do you do in your free time?（德企真的会问） | 真实感 + 平衡 | 开源项目 + 学德语 + 陪家人 —— 顺便印证搬家是认真的；说真实的，别背稿 |
| How do you view work-life balance? | 文化适配 | 高效产出 + 清晰边界；❌ 别表现成「随时在线」，德国不买账 |
| Have you ever said "I don't know" in a professional setting? | 诚实 | 直接用第 0 节那三句话 —— 德国面试**最吃**这套 |
| Wie arbeiten Sie im Team?（如遇德语环节） | 团队适配 | 故事 1 的协作版本，重点讲跨团队契约与沟通 |

**准备方法（Tech Interview Handbook 建议 + 本地化）：**
1. 每个故事写一张英文 STAR 卡：Situation 1 句 / Task 1 句 / Action 4–5 句 / Result 带数字 / Reflection 1 句
2. 出声练 3 遍，练到不看卡
3. 用上面的题库随机抽题 mock（找 AI 或朋友抽）—— 目标是抽到任何一题都能 30 秒内想起用哪个故事

---
