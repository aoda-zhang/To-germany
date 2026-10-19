# Backend Technical Interview

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
