# Resume Walkthrough / 简历深挖

本文件的答案按**面试时可以直接说出口**的方式编写，而不是答题提示。英文答案使用第一人称，尽量自然、清楚，不把团队成果都说成个人成果。

**准确性原则：** 内容以当前简历为依据。简历没有明确写出的具体库、部署策略、测试工具、指标统计周期或精确基线，不会编造成既定事实。如果面试官追问到这些细节，应按实际项目补充；不要背诵自己无法证实的数字或实现。

## 1. Overall career story / 整体职业经历

### Q1. Could you walk me through your background?

**Answer (EN)**

Sure. I've been working in software development for over nine years. I started as a frontend engineer, mainly working with JavaScript and web technologies, and gradually developed strong experience with React and TypeScript. At Newegg, I worked on e-commerce products, including an Angular-to-React migration, seller-facing features, and React Native mobile features. I'm now at Manulife, where my role is more full-stack: I still focus strongly on frontend architecture and shared components, but I also work with Node.js technologies such as Express and NestJS. Overall, I'd describe myself as a frontend-focused full-stack engineer.

**参考回答（中文）**

当然。我有超过 9 年的软件开发经验，最初从前端开发做起，主要使用 JavaScript 和 Web 技术，之后逐渐积累了扎实的 React 和 TypeScript 经验。在 Newegg，我参与电商产品开发，包括 Angular 到 React 的迁移、面向卖家的功能以及 React Native 移动端功能。目前我在 Manulife，工作范围更偏全栈：前端架构和共享组件仍然是我的强项，同时我也使用 Express、NestJS 等 Node.js 技术参与后端开发。整体来说，我会把自己定位为以前端为核心的全栈工程师。

### Q2. What would you say is your strongest area?

**Answer (EN)**

My strongest area is frontend engineering, especially React, TypeScript, component design, and frontend architecture. I enjoy turning complex product requirements into maintainable interfaces and reusable patterns. Over time, I've also taken on more backend work, so I can contribute beyond the UI and understand how frontend features connect to APIs and services.

**参考回答（中文）**

我最强的领域是前端工程，尤其是 React、TypeScript、组件设计和前端架构。我喜欢把复杂的产品需求转化为可维护的界面和可复用的方案。随着经验增长，我也承担了更多后端工作，因此现在不只关注 UI，也能理解前端功能如何与 API 和后端服务衔接。

### Q3. Why do you describe yourself as frontend-focused full-stack rather than a general full-stack engineer?

**Answer (EN)**

Because that best reflects both my experience and my current strengths. Most of my career has been focused on frontend development, and that's where I have the deepest experience. In my current role, I've deliberately expanded into backend development with Node.js, Express, and NestJS. I can work across the stack, but I don't want to imply that my backend experience is as extensive as my frontend experience.

**参考回答（中文）**

因为这个定位最符合我的实际经历和目前的优势。我职业生涯的大部分时间都在做前端开发，这也是我经验最深的领域。在目前的工作中，我有意识地拓展了 Node.js、Express 和 NestJS 后端开发能力。我可以跨前后端工作，但不会把自己的后端经验说成和前端一样深。

### Q4. Why are you looking for a new role in Germany?

**Answer (EN)**

I'm looking for an opportunity to continue developing as an engineer in an international environment. I want to bring my frontend experience to a team building real products, while continuing to grow into broader full-stack responsibilities. I'm particularly interested in roles where frontend engineering is important and where I can also contribute to APIs, architecture, and end-to-end delivery.

**参考回答（中文）**

我希望在国际化的工作环境中继续成长。我想把自己的前端经验带到真正构建产品的团队里，同时继续拓展全栈职责。我尤其关注重视前端工程能力、同时也能参与 API、架构和端到端交付的岗位。

---

## 2. Manulife — Design tokens across five microfrontend services

**CV bullet:** Led design token implementation across 5 microfrontend services, standardizing styling and reducing frontend styling issues by at least 30%.

### Q1. What problem were you trying to solve?

**Answer (EN)**

The goal was to make styling more consistent across five microfrontend services. When separate applications evolve independently, shared design decisions can drift and similar UI elements can end up looking or behaving differently. Design tokens give the teams a common set of values to build on, making styling easier to maintain across services.

**参考回答（中文）**

这项工作的目标是统一五个微前端服务的样式。不同应用独立演进时，共同的设计规范容易逐渐偏离，类似的 UI 元素也可能出现视觉差异。Design tokens 为团队提供一套共同的设计值，让不同服务的样式更一致，也更容易维护。

### Q2. What was your contribution?

**Answer (EN)**

I led the design-token implementation across the five services. My focus was to help establish a consistent styling foundation that could be used across those applications, rather than fixing the same styling differences separately in each service. The result recorded in my CV was more consistent styling and at least a 30% reduction in frontend styling issues.

**参考回答（中文）**

我负责推动五个服务中的 design-token 实施。重点不是在每个服务里单独修复相同的样式问题，而是建立一套可以跨应用使用的一致样式基础。简历中记录的结果是样式一致性得到改善，前端样式问题至少减少了 30%。

### Q3. Why use design tokens instead of fixing styles in each application?

**Answer (EN)**

Fixing each application separately can solve an immediate issue, but it tends to create duplicated work and inconsistent results over time. Tokens centralize shared design decisions, so applications can use the same source of values and update them in a more controlled way. For a group of microfrontends, that shared foundation is more maintainable than relying on each team to make the same decisions independently.

**参考回答（中文）**

在每个应用里分别修复样式可以解决眼前的问题，但长期来看容易重复劳动，也可能产生不一致的结果。Tokens 可以集中管理共同的设计决策，让各个应用使用统一的值，并以更可控的方式更新。对于多个微前端来说，这比依赖每个团队独立做出相同决定更容易维护。

### Q4. How did you measure the 30% reduction?

**Answer (EN)**

The figure in my CV refers to a reduction in frontend styling issues after the token work was introduced. I want to be precise about the metric: I would use the team's actual issue records and comparison period to explain the calculation, rather than inventing a baseline or claiming that tokens alone caused every improvement. The important outcome was that styling became more consistent across the five services and fewer styling issues were reported.

**参考回答（中文）**

简历中的数字指的是引入 design tokens 后，前端样式问题数量的下降。我会根据团队实际的问题记录和对比周期解释具体计算方式，而不会编造基线，也不会声称所有改善都完全由 tokens 单独造成。核心结果是五个服务的样式更加一致，样式相关问题也减少了。

### Q5. What did you learn from this project?

**Answer (EN)**

I learned that shared frontend foundations are as much about coordination as they are about code. A solution only works if different applications can adopt it consistently and maintain it over time. I now pay more attention to naming, ownership, adoption, and how a shared decision affects teams beyond the application I'm working on.

**参考回答（中文）**

我学到，共享前端基础设施不仅是代码问题，也涉及团队协作。只有不同应用能够一致地采用并长期维护，这套方案才真正有效。因此，我现在会更关注命名、维护责任、推广方式，以及一个共享决策对其他团队的影响。

---

## 3. Manulife — Refactoring a legacy PDF report module

**CV bullet:** Refactored a legacy PDF report module with React, reducing new report development time by 40%.

### Q1. What was the challenge with the legacy module?

**Answer (EN)**

The challenge was making changes to an existing report module while keeping the behavior of reports reliable. As a reporting solution grows, adding another report can become slower if the implementation is difficult to understand or if common behavior is not organized well. The goal of the refactoring was to make the code easier to work with so that new reports could be developed more efficiently.

**参考回答（中文）**

挑战在于改造现有报告模块的同时，确保报告原有行为仍然可靠。随着报表功能不断增加，如果代码难以理解、共用逻辑组织得不好，新增报表的开发就会越来越慢。这次重构的目标是提高代码的可维护性，让新报表开发更高效。

### Q2. What did you do?

**Answer (EN)**

I refactored the legacy PDF report module with React, focusing on making the existing solution easier to extend and reuse for new reports. Rather than treating every new report as a completely separate implementation, the work aimed to reduce repeated effort in the reporting workflow. According to my CV, the result was a 40% reduction in the development time for new reports.

**参考回答（中文）**

我使用 React 重构了旧的 PDF 报告模块，重点是让现有方案更容易扩展和复用。目标是不再把每个新报表都当成完全独立的实现，而是减少报表开发流程中的重复工作。根据简历记录，新报表的开发时间缩短了 40%。

### Q3. How do you distinguish development time from report-generation time?

**Answer (EN)**

The 40% figure refers to the time needed to develop a new report, not the time it takes to generate a PDF at runtime. The refactoring made the reporting code easier to extend, which reduced the engineering effort required for new report requirements. I would keep those two measurements separate because they describe different kinds of improvement.

**参考回答（中文）**

这里的 40% 指的是开发一个新报表所需的时间，而不是 PDF 在运行时的生成耗时。重构让报表代码更容易扩展，从而减少了新增报表需求所需的工程工作量。这两种指标代表不同类型的改善，不能混为一谈。

### Q4. How did you approach risk during the refactoring?

**Answer (EN)**

For a legacy reporting module, I would not want to rewrite everything without checking the existing behavior. The important part is to understand what current reports depend on, make changes in manageable steps, and verify that existing output still meets the requirements. My priority was to improve maintainability without breaking the reporting workflow that users already relied on.

**参考回答（中文）**

对于旧的报表模块，我不会在没有确认现有行为的情况下直接全部重写。关键是先弄清楚现有报表依赖哪些行为，再分阶段修改，并验证原有输出仍然符合要求。我的优先目标是在提高可维护性的同时，不破坏用户已经依赖的报表流程。

### Q5. What was the business impact?

**Answer (EN)**

The direct impact was faster delivery of new reports. When the engineering effort for each new report is lower, the team can respond to reporting requirements more efficiently instead of spending as much time understanding and extending legacy code. The improvement recorded in my CV was a 40% reduction in new-report development time.

**参考回答（中文）**

最直接的业务影响是新报表交付更快。每个新报表所需的工程工作量降低后，团队就能更高效地响应报表需求，而不必花费那么多时间理解和扩展旧代码。简历记录的改善幅度是新报表开发时间缩短了 40%。

---

## 4. Manulife — Component-library architecture and AI-assisted review

**CV bullet:** Independently designed and built the component library architecture, integrating AI-powered review and maintenance to ensure component quality.

### Q1. Why did the team need a component library?

**Answer (EN)**

A shared component library helps teams avoid solving the same UI problems repeatedly. It provides reusable building blocks and a more consistent way to implement common interface patterns. The architectural challenge is to make components reusable without making them so generic that they become difficult to understand or customize.

**参考回答（中文）**

共享组件库可以避免不同团队反复解决相同的 UI 问题。它提供可复用的基础组件，也让常见界面模式的实现更加一致。架构上的挑战是提高复用性，同时避免组件过度抽象，导致难以理解或定制。

### Q2. What did you personally own?

**Answer (EN)**

I independently designed and built the component-library architecture. That means my contribution was not limited to implementing individual components; I also worked on how the library should be structured so that components could be maintained and reused. I would distinguish that architectural ownership from any broader team decisions or contributions made by other engineers.

**参考回答（中文）**

我独立设计并构建了组件库架构。我的贡献不只是实现单个组件，还包括思考整个库应该如何组织，才能让组件易于维护和复用。我会把自己负责的架构工作与团队其他成员的贡献、以及更大范围的团队决策区分开。

### Q3. Why add AI-powered review?

**Answer (EN)**

I see AI review as a way to support maintenance, not as a replacement for engineering judgment. It can help surface potential issues and suggest improvements, while the developer remains responsible for checking whether those suggestions are correct and appropriate for the codebase. The value is in making review more efficient without giving up human accountability for quality.

**参考回答（中文）**

我把 AI review 看作维护工作的辅助，而不是工程判断的替代品。它可以帮助发现潜在问题、提出改进建议，但开发人员仍然需要确认建议是否正确、是否适合当前代码库。它的价值在于提高审查效率，同时保留人对代码质量的责任。

### Q4. What are the risks of AI-assisted review?

**Answer (EN)**

The main risk is that an AI tool can produce a suggestion that sounds convincing but is incorrect or unsuitable for the project. That's why I wouldn't treat its output as an automatic decision. The suggestions need to be reviewed in the context of the component's behavior, the team's conventions, and the actual requirements.

**参考回答（中文）**

主要风险是 AI 可能给出听起来合理、实际上却不正确或不适合项目的建议。因此，我不会把 AI 的输出当成自动决策。建议必须结合组件行为、团队规范和真实需求进行审查。

### Q5. How would you know whether the library is successful?

**Answer (EN)**

I'd look at whether teams can adopt the components easily, whether the components are reused consistently, and whether the library reduces duplicated implementation and maintenance effort. I would also pay attention to defects and developer feedback. A library isn't successful just because it contains many components; it needs to make product development more consistent and efficient.

**参考回答（中文）**

我会关注团队是否能方便地接入组件、组件是否得到一致复用，以及它是否减少了重复实现和维护成本。我也会关注缺陷和开发者反馈。组件库的成功不能只看组件数量，而要看它是否真正让产品开发更加一致、高效。

---

## 5. Manulife — Fund-trading modules for a large financial platform

**CV bullet:** Collaborated on fund trading modules supporting 3,000+ fund managers and millions of investors.

### Q1. What was your role in the fund-trading work?

**Answer (EN)**

I collaborated on fund-trading modules used in a large financial platform. My role was to contribute to the implementation as part of the engineering team, working within the requirements of a financial product. I would be careful to distinguish the parts I personally implemented from the work owned by other engineers and the wider team.

**参考回答（中文）**

我参与了大型金融平台中的基金交易模块开发。我的职责是作为工程团队的一员，根据金融产品的需求参与实现。我会明确区分自己亲自负责的部分，以及其他工程师和整个团队负责的工作。

### Q2. What makes financial-product development different from ordinary e-commerce?

**Answer (EN)**

The biggest difference is the importance of correctness, traceability, and user trust. In financial workflows, users need to understand the status of an operation, and errors can have consequences beyond a poor user experience. That means requirements, validation, error handling, and communication with the relevant business teams all need to be treated carefully.

**参考回答（中文）**

最大的区别在于正确性、可追溯性和用户信任的重要性。在金融流程中，用户需要清楚了解操作状态，错误的影响也可能远超糟糕的用户体验。因此，需求确认、校验、错误处理以及与业务团队的沟通都必须更加谨慎。

### Q3. How do you handle unclear financial requirements?

**Answer (EN)**

I try to clarify the business rule before deciding how to implement it. I would ask what the expected behavior is, what should happen in edge cases, and how the result should be communicated to users. If a rule affects a transaction or eligibility, I wouldn't make assumptions based only on the UI; I'd confirm it with the relevant product or domain stakeholders.

**参考回答（中文）**

我会先确认业务规则，再决定如何实现。我会询问预期行为是什么、边界情况应该如何处理，以及结果应该如何反馈给用户。如果规则会影响交易或资格判断，我不会只根据 UI 自行推断，而会与相关产品或业务人员确认。

### Q4. How do you avoid overstating your contribution?

**Answer (EN)**

My CV says I collaborated on these modules, rather than claiming that I led the entire trading system. I can explain the parts I worked on and the engineering decisions within my responsibility, but I wouldn't claim ownership of the entire platform or of backend and financial rules that were owned by other people.

**参考回答（中文）**

我的简历写的是参与这些模块的开发，而不是声称自己主导了整个交易系统。我可以详细解释自己负责的部分，以及职责范围内的工程决策，但不会把整个平台或由其他人负责的后端和金融规则说成是自己主导的。

---

## 6. Manulife — AI tools for development, onboarding, and business-logic discovery

**CV bullet:** Built AI-powered tools to accelerate development, improve team onboarding, and help BAs understand historical business logic.

### Q1. What problem were you trying to solve with these tools?

**Answer (EN)**

The goal was to reduce the effort needed to understand an existing codebase and its historical business logic. In a mature product, important knowledge can be spread across code, documentation, and the experience of existing team members. AI-powered tools can help people explore that information more quickly, especially during onboarding or when investigating unfamiliar behavior.

**参考回答（中文）**

目标是减少理解现有代码库和历史业务逻辑所需的时间。在成熟产品中，重要知识可能分散在代码、文档以及老团队成员的经验里。AI 工具可以帮助团队更快地探索这些信息，尤其是在新人入职或排查陌生行为时。

### Q2. How do you prevent AI from giving misleading explanations?

**Answer (EN)**

I treat AI-generated explanations as a starting point, not as the source of truth. The output should be checked against the actual code and available documentation, and the tool should make it possible to trace an explanation back to supporting evidence. If the evidence is incomplete, the answer should make that uncertainty clear instead of presenting a guess as a fact.

**参考回答（中文）**

我把 AI 生成的解释当作调查起点，而不是最终事实。输出需要与真实代码和现有文档核对，工具也应该尽可能让人追溯解释所依据的证据。如果证据不完整，就应该明确说明不确定性，而不是把猜测包装成事实。

### Q3. How can these tools help business analysts?

**Answer (EN)**

They can help business analysts explore how existing behavior is represented in the codebase, so they have a clearer starting point when investigating historical requirements. The tool doesn't replace conversations with engineers or product owners, but it can reduce the time spent searching for relevant context and help people ask more focused questions.

**参考回答（中文）**

这些工具可以帮助业务分析师了解既有业务行为在代码库中的体现，为调查历史需求提供更清晰的起点。它们不能取代与工程师或产品负责人的沟通，但可以减少搜索背景信息的时间，让后续问题更加聚焦。

### Q4. What is the most important lesson from building AI engineering tools?

**Answer (EN)**

The most important lesson is that usefulness depends on workflow integration and trust, not just on the model's ability to generate text. The tool needs to solve a real problem, fit into how people already work, and make it easy to verify the result. For engineering tasks, a fast but unreliable answer can create more work than it saves.

**参考回答（中文）**

最重要的经验是，工具是否有用取决于它能否融入工作流程并建立信任，而不只是模型能否生成文本。工具需要解决真实问题、适应团队现有的工作方式，并让结果容易验证。对于工程任务来说，快速但不可靠的答案可能反而增加工作量。

---

## 7. Newegg — Angular-to-React micro-frontend migration

**CV bullet:** Led an Angular-to-React micro-frontend migration with zero production downtime across three teams.

### Q1. Why did you migrate from Angular to React?

**Answer (EN)**

The project involved moving an existing frontend from Angular to React while keeping production available. The goal wasn't simply to replace one framework with another; it was to enable the product to evolve on a React-based frontend without disrupting users. Because three teams were involved, coordination and clear boundaries were just as important as the technical migration itself.

**参考回答（中文）**

这个项目是在保持线上服务可用的前提下，将现有前端从 Angular 迁移到 React。目标不只是替换框架，而是让产品能够在 React 技术体系下继续演进，同时不影响用户。由于涉及三个团队，团队协调和清晰的边界与技术迁移本身同样重要。

### Q2. What was your contribution as the migration lead?

**Answer (EN)**

I led the frontend migration across the three teams. My responsibility was to help move the work forward while keeping the transition controlled and production availability intact. The key result recorded in my CV was completing the migration with zero production downtime. I would distinguish my leadership of the migration from the implementation work contributed by the other engineers.

**参考回答（中文）**

我负责推动三个团队参与的前端迁移工作。我的职责是推进迁移，同时控制变更风险并保证线上服务持续可用。简历中记录的关键结果是迁移过程中没有出现生产环境停机。我会区分自己负责推动和协调的工作，以及其他工程师承担的具体实现。

### Q3. Why use a micro-frontend approach instead of a big-bang rewrite?

**Answer (EN)**

For a production system, replacing everything at once can concentrate too much risk into a single release. A micro-frontend approach can create clearer application boundaries and allow teams to work on parts of the product more independently. The trade-off is extra integration and governance work, so the boundaries and shared contracts need to be clear rather than introducing micro-frontends just for the sake of it.

**参考回答（中文）**

对于生产系统，一次性整体替换会把过多风险集中到单次发布中。微前端可以建立更清晰的应用边界，让团队相对独立地开发产品的不同部分。它的代价是增加集成和治理工作，因此必须明确应用边界和共享契约，不能只是为了使用微前端而引入它。

### Q4. How did you keep production available during the migration?

**Answer (EN)**

The key requirement was to keep the existing production experience available throughout the transition. That meant treating compatibility, integration, and release coordination as first-class concerns rather than focusing only on rewriting components. My CV records the outcome as zero production downtime. For the exact rollout and rollback steps, I would describe the process used by our team rather than claim a traffic-splitting strategy or tooling that wasn't part of the project.

**参考回答（中文）**

关键要求是在整个迁移期间保持现有生产服务可用。因此，兼容性、集成和发布协调都必须作为核心问题处理，而不能只关注组件重写。我的简历记录的结果是生产环境零停机。至于具体的灰度和回滚步骤，我会按团队当时实际采用的流程说明，不会声称使用了项目中并未采用的流量切分策略或工具。

### Q5. What was the hardest part of coordinating three teams?

**Answer (EN)**

The hardest part was keeping everyone aligned while different teams were changing different parts of the frontend. If teams make different assumptions about application boundaries or integration, problems tend to appear late. I learned that migration work needs explicit communication, clear ownership, and agreement on integration expectations—not just a technical plan.

**参考回答（中文）**

最难的是在不同团队分别修改前端不同部分的同时，确保大家保持一致。如果团队对应用边界或集成方式有不同理解，问题往往会到后期才暴露。我学到，迁移工作不仅需要技术方案，还需要明确的沟通、责任划分，以及对集成预期达成一致。

### Q6. What would you improve if you did it again?

**Answer (EN)**

I'd make the integration and validation plan explicit as early as possible. In a multi-team migration, teams can make good local decisions that still create problems when combined. I'd therefore align the boundaries, ownership, and acceptance criteria early, and make sure the end-to-end behavior is checked throughout the migration rather than only near release.

**参考回答（中文）**

如果再做一次，我会更早明确集成和验证计划。在多团队迁移中，每个团队的局部决策可能都合理，但组合起来却出现问题。因此，我会尽早对齐边界、责任和验收标准，并在整个迁移过程中持续验证端到端行为，而不是只在发布前集中检查。

---

## 8. Newegg — A+ content marketplace features

**CV bullet:** Built A+ content marketplace features, improving seller publishing efficiency by 40%.

### Q1. What was the purpose of the A+ content marketplace?

**Answer (EN)**

It supported sellers in creating and publishing richer product content. For an e-commerce platform, product content is important because it helps sellers present their products and gives customers better information when making a purchase decision. My work focused on building the frontend features that supported that seller workflow.

**参考回答（中文）**

这个功能帮助卖家创建并发布更丰富的商品内容。对于电商平台来说，商品内容很重要，因为它既帮助卖家展示产品，也能让消费者在购买前获得更充分的信息。我的工作重点是开发支持卖家这一工作流程的前端功能。

### Q2. What did you personally build?

**Answer (EN)**

I built frontend features for the A+ content marketplace. My focus was on the seller-facing workflow and making the relevant product-content tasks easier to complete. The outcome stated in my CV was a 40% improvement in seller publishing efficiency. I would explain the specific screens and interactions I implemented based on the actual features I worked on.

**参考回答（中文）**

我负责开发 A+ 内容市场的前端功能，重点是面向卖家的工作流程，让相关商品内容任务更容易完成。简历中记录的结果是卖家发布效率提升了 40%。如果面试官希望了解具体实现，我会结合自己实际开发的页面和交互逐一说明。

### Q3. What does the 40% improvement mean?

**Answer (EN)**

The 40% figure in my CV refers to improved seller publishing efficiency, not a general increase in sales. I would explain the exact operational metric using the project's actual measurement—for example, the specific task or process used to assess publishing efficiency. I wouldn't substitute a different metric or invent a measurement period that I can't verify.

**参考回答（中文）**

简历中的 40% 指的是卖家发布效率的提升，不是销售额增长。我会根据项目实际使用的衡量方式解释具体指标，例如评估发布效率时采用的任务或流程。我不会把它替换成其他指标，也不会编造无法核实的统计周期。

### Q4. How did you approach usability for seller-facing features?

**Answer (EN)**

I focused on making the workflow clear and predictable. Seller tools often involve several steps and content fields, so the interface should help users understand what is required, what has been completed, and what still needs attention. I also consider validation and error feedback important because unclear errors can make publishing slower and more frustrating.

**参考回答（中文）**

我会重点关注工作流程是否清晰、可预期。卖家工具往往涉及多个步骤和内容字段，因此界面需要让用户清楚知道哪些内容是必填的、哪些已经完成、还有哪些需要处理。我也很重视校验和错误反馈，因为模糊的错误提示会拖慢发布流程，让用户感到挫败。

---

## 9. Newegg — React Native mobile features

**CV bullet:** Delivered 12+ mobile app features enabling end-to-end store management for sellers.

### Q1. What did the mobile app help sellers do?

**Answer (EN)**

The app supported sellers in managing their stores through mobile devices. I delivered more than twelve React Native features that contributed to that end-to-end store-management experience. The value was giving sellers access to relevant store-management workflows without having to rely entirely on a desktop experience.

**参考回答（中文）**

这个应用让卖家能够通过移动设备管理店铺。我使用 React Native 交付了 12 个以上的移动端功能，共同支持端到端的店铺管理体验。它的价值在于，卖家不必完全依赖桌面端，也能处理相关的店铺管理流程。

### Q2. Why use React Native?

**Answer (EN)**

React Native allows a team to share a substantial amount of application code across iOS and Android while still building a mobile experience. That can improve development efficiency when the product needs to support both platforms. At the same time, it's important to understand platform differences and use native capabilities where the application genuinely needs them.

**参考回答（中文）**

React Native 让团队能够在 iOS 和 Android 之间复用相当一部分应用代码，同时仍然提供移动端体验。当产品需要同时支持两个平台时，这有助于提高开发效率。同时，也必须理解不同平台的差异，并在确实需要时使用原生能力。

### Q3. What are the trade-offs between React Native and native development?

**Answer (EN)**

The main benefit is code reuse and the ability to deliver features across platforms with one primary development approach. The trade-off is that platform-specific behavior, native integrations, and performance-sensitive interactions can require extra work. I see React Native as a practical choice when shared product behavior is substantial, while native development may be more suitable when a feature depends heavily on platform-specific capabilities.

**参考回答（中文）**

主要优势是代码复用，并能用一套主要的开发方式向多个平台交付功能。代价是平台特有行为、原生集成以及对性能敏感的交互可能需要额外处理。如果产品在不同平台上有大量共通逻辑，React Native 是很实用的选择；如果功能高度依赖某个平台的特性，原生开发可能更合适。

### Q4. How did you think about mobile usability?

**Answer (EN)**

For seller store management, the interface needs to make important actions easy to find and complete on a smaller screen. I pay attention to clear navigation, concise information, useful feedback after an action, and handling loading or error states. The aim is to make common tasks manageable on mobile rather than simply shrinking a desktop interface.

**参考回答（中文）**

对于卖家店铺管理，界面需要让用户在较小的屏幕上也能轻松找到并完成重要操作。我会关注清晰的导航、精简的信息呈现、操作后的有效反馈，以及加载和错误状态的处理。目标是让常用任务真正适合移动端，而不是简单缩小桌面界面。

---

## 10. Hucai — E-commerce cart and inventory-management frontend

**CV bullet:** Developed core e-commerce features, including cart and inventory management, for a platform serving 2,000+ daily users.

### Q1. What was your role in the cart and inventory features?

**Answer (EN)**

I worked on the frontend for core e-commerce features, including the cart and inventory-management experience. My responsibility was on the client side: implementing the user interactions, managing the relevant UI state, and integrating with backend APIs. The backend team owned the inventory consistency rules, so I wouldn't claim that I designed the server-side inventory mechanism.

**参考回答（中文）**

我参与了电商核心功能的前端开发，包括购物车和库存管理体验。我的职责在客户端，包括实现用户交互、管理相关 UI 状态，以及对接后端 API。库存一致性规则由后端团队负责，因此我不会声称自己设计了服务端库存机制。

### Q2. What happens if an item becomes unavailable after the user adds it to the cart?

**Answer (EN)**

The frontend should not assume that an item is guaranteed to remain available just because it was added to the cart. It needs to handle the latest response from the backend, explain the situation clearly, and let the user adjust the cart before proceeding. The server remains the source of truth for inventory; the frontend's job is to represent that result correctly and make recovery understandable.

**参考回答（中文）**

商品加入购物车后，前端不能假设它就一定会持续有货。前端需要处理后端返回的最新结果，清楚地向用户解释情况，并允许用户在继续操作前调整购物车。库存的最终状态以服务端为准，前端的职责是正确呈现结果，并让用户知道如何继续处理。

### Q3. How do you keep cart UI state consistent with API responses?

**Answer (EN)**

I treat API responses as the authoritative result for server-owned data, especially inventory and checkout-related rules. The frontend can manage temporary interaction state for responsiveness, but it needs to reconcile that state with the server response and handle failures explicitly. This avoids showing users a successful state when the backend has rejected the operation.

**参考回答（中文）**

对于库存和结账规则等由服务端负责的数据，我会以 API 返回结果为准。前端可以管理临时交互状态来提升响应速度，但必须根据服务端响应校正状态，并明确处理失败情况。这样可以避免后端已经拒绝操作，界面却仍显示成功的情况。

### Q4. How did you handle errors in the shopping flow?

**Answer (EN)**

I would make sure errors are reflected in the relevant part of the interface and that users understand what they can do next. For example, if an operation fails because the latest inventory state no longer allows it, the UI should explain the issue and let the user review the item rather than showing a generic failure with no recovery path. Clear error handling is part of the shopping experience, not just an API concern.

**参考回答（中文）**

我会确保错误能在相关界面中清晰呈现，并让用户知道下一步可以做什么。例如，如果最新库存状态不允许某项操作，界面应该解释原因，让用户重新检查商品，而不是只显示一个没有后续处理方式的通用错误。清晰的错误处理是购物体验的一部分，不只是 API 层的问题。

### Q5. How large was the platform, and what does that tell you?

**Answer (EN)**

The platform served more than 2,000 daily users, according to my CV. That context matters because cart and inventory features are part of a core user journey, so correctness and predictable behavior matter as much as the visual interface. I focus on making the client-side experience reliable while respecting the backend's ownership of inventory rules.

**参考回答（中文）**

根据简历，这个平台的日活用户超过 2,000 人。这个规模很重要，因为购物车和库存属于核心用户流程，正确性和可预期性与界面本身同样重要。我关注的是让客户端体验可靠，同时尊重后端对库存规则的负责范围。

---

## 11. Hucai — React attendance platform

**CV bullet:** Built a React-based attendance platform for 1,000+ employees, reducing HR manual workload by approximately 60%.

### Q1. What problem did the attendance platform solve?

**Answer (EN)**

The platform helped manage attendance for more than 1,000 employees. The main business goal was to reduce the manual effort HR needed to collect, organize, and review attendance information. By moving that workflow into a React-based platform, the team could automate parts of the process and make the information easier to manage.

**参考回答（中文）**

这个平台用于管理 1,000 多名员工的考勤。主要业务目标是减少 HR 收集、整理和核对考勤信息所需的人工工作。通过将相关流程放到基于 React 的平台中，团队能够自动化其中一部分工作，让信息管理更方便。

### Q2. What was your contribution?

**Answer (EN)**

I built the React-based frontend for the attendance platform. My focus was turning the attendance workflow into an interface employees and HR could use, while supporting the business process the system was designed for. The CV records that the platform served more than 1,000 employees and reduced HR's manual workload by approximately 60%.

**参考回答（中文）**

我负责开发这个考勤平台的 React 前端，重点是把考勤流程转化为员工和 HR 可以使用的界面，并支持系统要解决的业务流程。简历记录的平台覆盖了 1,000 多名员工，HR 的人工工作量减少了约 60%。

### Q3. How did you measure the 60% reduction?

**Answer (EN)**

The figure in my CV is an approximate reduction in HR's manual workload after the platform was introduced. To explain it precisely, I would refer to the actual before-and-after workload measure used by the business, rather than inventing exact hours or a measurement period. The key point is that the system reduced the amount of manual attendance work HR had to do.

**参考回答（中文）**

简历中的数字表示平台上线后 HR 人工工作量大约减少了 60%。如果要精确解释，我会依据业务当时实际使用的前后对比口径，而不是编造具体工时或统计周期。核心结果是系统减少了 HR 手动处理考勤的工作量。

### Q4. What did you learn from building an internal business tool?

**Answer (EN)**

An internal tool has to fit the way people actually work. It isn't enough for the interface to function technically; the workflow needs to be clear and the information needs to be useful to the people who rely on it. I learned to think about the operational process behind the UI and the practical impact the tool should have for its users.

**参考回答（中文）**

内部工具必须符合用户真实的工作方式。界面在技术上能运行还不够，流程需要清晰，信息也必须对依赖它的人有用。我学到要关注 UI 背后的实际业务流程，以及工具应该给用户带来的具体帮助。

---

## 12. Education — Transitioning from journalism to software development

### Q1. You studied journalism. How did you move into software development?

**Answer (EN)**

I studied journalism, and one of the courses introduced me to building web pages with HTML and CSS. I enjoyed seeing something I created appear and work in the browser, and that experience motivated me to learn frontend development on my own. I used structured online learning, including freeCodeCamp, and built practice projects along the way. Over time, that learning turned into a professional career, and I've now spent more than nine years working in software development.

**参考回答（中文）**

我大学学的是新闻学，其中一门课程让我接触到使用 HTML 和 CSS 制作网页。我很喜欢自己写的东西能在浏览器中真正呈现并运行的感觉，这促使我开始自学前端开发。我通过 freeCodeCamp 等结构化在线课程学习，同时不断做练习项目。后来，这些学习逐渐转化为职业道路，到现在我已经有超过 9 年的软件开发经验。

### Q2. Do you feel that not having a computer science degree is a disadvantage?

**Answer (EN)**

I understand that a computer science degree can provide a structured foundation, and my degree was in a different field. I made up for that by learning independently and building experience through real production work over many years. My approach is to be honest about what I know, keep strengthening my fundamentals, and demonstrate my ability through the quality of my engineering work.

**参考回答（中文）**

我理解计算机科学学位能够提供系统化的基础，而我的大学专业确实不同。我通过自主学习以及多年的真实生产项目经验来补足这方面的不足。我的做法是诚实面对自己的知识边界，持续加强基础，并通过实际工程工作的质量证明能力。

### Q3. Has your journalism background helped you as an engineer?

**Answer (EN)**

It has helped me value clear communication and understanding context before drawing conclusions. In software development, technical implementation is only part of the work; I also need to understand the problem, ask good questions, and explain decisions to teammates and stakeholders. My engineering skills come from years of deliberate learning and professional practice, while my earlier education is an additional perspective rather than a substitute for that experience.

**参考回答（中文）**

它让我更重视清晰沟通，以及在得出结论前先理解背景。在软件开发中，技术实现只是工作的一部分；我还需要理解问题、提出恰当的问题，并向队友和相关人员解释技术决策。我的工程能力来自多年的持续学习和职业实践，而之前的教育背景提供的是额外视角，并不能替代这些经验。

---

## 13. Skills — React, TypeScript, and backend experience

### Q1. How would you describe your level in React and TypeScript?

**Answer (EN)**

React and TypeScript are among my strongest skills. I've used them in production projects and worked on larger concerns such as shared components and frontend architecture, not just individual UI features. I still expect to learn in every codebase, but I'm comfortable taking responsibility for frontend implementation and discussing the trade-offs behind design decisions.

**参考回答（中文）**

React 和 TypeScript 是我最强的技术之一。我不仅用它们开发过生产项目中的 UI 功能，也参与过共享组件和前端架构等更大范围的工作。我仍然会在每个新代码库中持续学习，但我有信心负责前端实现，并解释设计决策背后的取舍。

### Q2. How strong is your backend experience?

**Answer (EN)**

My background is stronger in frontend engineering, but I've deliberately expanded into backend development in my current role. I've worked with Node.js, Express, and NestJS, and I understand how to build and integrate APIs as part of a full-stack feature. I would describe my backend experience as practical and growing, rather than claiming that it is as deep as my frontend experience.

**参考回答（中文）**

我的前端经验更深，但在目前的工作中，我有意识地拓展了后端开发能力。我使用过 Node.js、Express 和 NestJS，也理解如何将 API 的开发与集成纳入一个全栈功能中。我会把自己的后端经验描述为有实际项目基础、仍在持续成长，而不是声称它已经和前端一样深入。

### Q3. Your CV lists skill levels as “Intermediate.” How does that fit with your experience?

**Answer (EN)**

The labels don't fully communicate the difference between my skills. My strongest experience is in React, TypeScript, and frontend engineering, while my backend experience is more recent and still developing. I'd rather explain that distinction clearly than describe every technology at the same level. My practical experience and the scope of work I've taken on provide a more useful picture than one label.

**参考回答（中文）**

这些等级标签并不能完整表达不同技术之间的差异。我最有经验的是 React、TypeScript 和前端工程，而后端经验相对较新，还在持续拓展。我更愿意把这种差异讲清楚，而不是把所有技术都描述成同一个水平。实际项目经验和承担过的工作范围，比单一标签更能说明我的能力。

---

## 14. Metrics and ownership — follow-up answers

### Q1. Are all the results on your CV solely your achievement?

**Answer (EN)**

No. I distinguish between work I personally led or implemented and outcomes delivered by the wider team. For example, my CV explicitly says I led the design-token implementation and the Angular-to-React migration, while I describe the fund-trading work as a collaboration. I take responsibility for explaining my own contribution clearly, and I don't claim that every team outcome came from me alone.

**参考回答（中文）**

不是所有结果都完全由我个人完成。我会区分自己主导或亲自实现的工作，以及整个团队共同交付的成果。例如，简历明确写了我推动 design-token 实施和 Angular 到 React 的迁移，而基金交易模块则写的是参与协作。我会清楚解释自己的贡献，不会把团队所有成果都归功于个人。

### Q2. What if you can't remember the exact calculation behind a metric?

**Answer (EN)**

I wouldn't guess. I'd explain what the metric represents and what changed, then be transparent if I can't recall the exact baseline or measurement window from memory. I think it's more important to be accurate about what I know than to give a precise-sounding number that I can't substantiate.

**参考回答（中文）**

我不会猜测。我会先解释这个指标代表什么、发生了什么变化；如果当下记不清具体基线或统计周期，我会坦诚说明。我认为准确表达自己确实知道的内容，比给出一个听起来精确但无法证实的数字更重要。

### Q3. What would you say if asked about a backend implementation you didn't own?

**Answer (EN)**

That part was implemented by the backend team, so I don't want to present it as my own work. My responsibility was on the frontend side, including integrating with the API and making sure the UI handled the returned states correctly. I can explain the interface between the frontend and backend, but I'd rather be clear about the boundary of my ownership.

**参考回答（中文）**

那部分是后端团队实现的，所以我不会把它说成是自己的工作。我的职责在前端，包括对接 API，并确保 UI 正确处理返回状态。我可以解释前后端之间的接口和协作方式，但会明确说明自己的职责边界。

---

## Practice notes / 练习说明

- 先练习每个项目的第一个回答，目标是自然讲清楚背景、自己的职责和结果。
- 后续问题用于追问练习。回答时优先使用真实做过的实现细节，不要把通用技术知识说成项目事实。
- 对于 30%、40%、60% 等指标，准备好真实的统计口径；如果暂时无法确认，不要编造精确基线、小时数或统计周期。
- 对于团队项目，始终区分 **I led / I implemented / I contributed / the team delivered**。
- 口头回答不需要逐字背诵。记住事实和逻辑，用自然的英语表达即可。
