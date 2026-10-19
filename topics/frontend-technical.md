# Frontend Technical Interview

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
