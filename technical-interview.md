# Technical Interview Preparation

Frontend-focused technical preparation, backend fundamentals, and coding/UI review topics are consolidated here.


---

# Frontend technical interview

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

---

# Backend technical interview

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

---

# Coding, browser, JavaScript, React, and UI review

## code interview（HTML，CSS，JS）

### HTML

- How browser render html from start to end

- HML script (script , async, defer,model)
- Multilingual website (i18n,l10n)
  - how to maintain i18n
  - Something need to wary (Word Break Problem,date,time,RTL,currency)
### CSS
- CSS box model
- CSS display
- differ between block and inline element
- how a browser determines what elements match a CSS selector
  - From right to left rule
  - As flat,simple as possible to reduce complexity
- Why use translate instead of absolute position
  - Translate is faster than absolute (Translate is GPU rendering,Absolute is CPU rendering)
  - Translate 是视觉上的移动，absolute is physical move, it will repaint the whole page

  

#### JS question

> JS question lists https://github.com/greatfrontend/top-javascript-interview-questions
- JS reduce
- JS deep clone
- JS flat

## Algorithms Interviews

- Spending your limited prep time on trees, recursion, BFS, and DFS pays off more directly because the DOM itself is a tree and many UI coding problems reduce to tree traversal.

## User interface interview

- 组件化
- 尽量使用小范围状态
- 使用语义化的标签
- 不要全部使用div，点击事件请务必使用button
- 考虑a11y
## React
- 性能优化
- 状态管理（state，context，redux的具体使用场景）
- 为何list中必须要有唯一的id
- 为何函数组件只能返回一个节点

### API 设计

## Behavior question interview