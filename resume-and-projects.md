# Resume Walkthrough and Project Deep Dives

Use this as the canonical preparation document for explaining the CV, project decisions, ownership, trade-offs, and measurable outcomes. Keep metrics consistent with the approved CV and verify details before using them in interviews.


---

# Resume walkthrough

本文件的答案按**面试时可以直接说出口**的方式编写，而不是答题提示。英文答案使用第一人称，尽量自然、清楚，不把团队成果都说成个人成果。

**准确性原则：** 内容以当前简历为依据。简历没有明确写出的具体库、部署策略、测试工具、指标统计周期或精确基线，不会编造成既定事实。如果面试官追问到这些细节，应按实际项目补充；不要背诵自己无法证实的数字或实现。

## 1. Overall career story / 整体职业经历

### Q1. Could you walk me through your background?

**Answer (EN)**

Sure. I have over nine years of experience in software development, mainly working with React, TypeScript, and Node.js. After graduating, I joined Hucai, where I learned the software development lifecycle and worked on important internal systems with guidance from senior engineers. After five years, I wanted to step outside my comfort zone and work on more international products in an environment that placed greater emphasis on engineering quality and maintainability, so I joined Newegg. There, I contributed to the technology migration of the Newegg Marketplace and developed mobile features for sellers. I also gained experience maintaining products across multiple markets and collaborating with international teams. About a year later, the company made a strategic change and our entire mobile development team was laid off. I then joined Manulife, a Canadian global asset-management company, where my role became more full-stack. I enjoy being able to develop and maintain a product end to end, from the frontend to backend services, and to think more broadly about product needs and system architecture. I'm now planning to move to Germany for family reasons, and I'm looking for a software engineering role where I can build on my experience while continuing to learn and take on new challenges.

**参考回答（中文）**

当前，我有超过9年的软件开发工作，主要技术栈就是react typescriep nodesj

我大学毕业后，加入了hucai，在哪里里我系统性的学习了现代化软件开发的全流程，也在高级开发人员的指导下参与了很多重要的内部系统开发和维护。

在哪里工作了5年后，我开始思考我必须跳出舒适圈，我想参与更国际化的产品开发，我想在一个更重视工程质量，代码可维护性的地方去成长，于是我加入了newegg

在哪里，我主要参与了newegg market palce的技术栈迁移，以及商家端的移动端开发，见证了国际化，多市场项目的维护，也有了与多个国际化团队的工作经验

很不幸的是，1年后，公司战略调整，我们整个移动端开发团队被裁

于是我加入了上一家公司，来自加拿大的，一个做全球资产管理的国际化公司，在这里，我的角色是一名全栈开发人员，我很享受这个角色带给我的成长，因为我现在完全可以端对端开发，从0维护一个完整的产品，以前的角色可能更多关注在用户interface上，现在我关注整个产品的策略，如何设计整个系统的架构，包括前后端才可以更好的维护整个系统。

我现在为了家庭来到德国，我希望可以继续寻找一个软件开发机会，基于我过去的工作经验，同时我也保持开发心态，接收更多新的挑战

### Q2. What would you say is your strongest area?

**Answer (EN)**

My strongest area is frontend engineering, especially React, TypeScript, component design, and frontend architecture. I enjoy turning complex product requirements into maintainable interfaces and reusable patterns. Over time, I've also taken on more backend work, so I can contribute beyond the UI and understand how frontend features connect to APIs and services.

**参考回答（中文）**

我最强的领域是前端工程，尤其是 React、TypeScript、组件设计和前端架构。我喜欢把复杂的产品需求转化为可维护的界面和可复用的方案。随着经验增长，我也承担了更多后端工作，因此现在不只关注 UI，也能理解前端功能如何与 API 和后端服务衔接。

### Q3. Why do you describe yourself as frontend-focused full-stack rather than a general full-stack engineer?

**Answer (EN)**

My experience is strongest in frontend engineering, which has been the main focus of most of my career. In my current role, I have also taken on backend development, using technologies such as Node.js, Express, and NestJS. However, I have less experience with deeper backend topics such as distributed systems and cache design. So I can contribute across the stack, but I prefer to describe myself as frontend-focused rather than suggest that my frontend and backend experience are equally deep.

**参考回答（中文）**

就像我简历中写道的，我职业生涯的大部分时间都在做前端开发，这也是我经验最深的领域。在上一份工作里，我也参与了很多后端开发，但是我却少后端分布式系统，缓存设计等重后端的经验，所以我不会把自己说成真正的全栈

### Q4. Why are you looking for a new role in Germany?

**Answer (EN)**

I'm looking for an opportunity to continue developing as an engineer in an international environment. I want to bring my frontend experience to a team building real products, while continuing to grow into broader full-stack responsibilities. I'm particularly interested in roles where frontend engineering is important and where I can also contribute to APIs, architecture, and end-to-end delivery.

**参考回答（中文）**

我希望在国际化的工作环境中继续成长。我想把自己的前端经验带到真正构建产品的团队里，同时继续拓展全栈职责。我尤其关注重视前端工程能力、同时也能参与 API、架构和端到端交付的岗位。

---

## 2. Manulife — Design tokens across five microfrontend services

我们有几个微前端项目，但是由于一些架构设计问题，每个微前端都存在自己的样式管理
有时候当我们尝试修复一个样式问题，甚至颜色问题，都要花费很久时间去分析多个微前端之间的差异
当我尝试去重构我们整个系统的头部和footer部分的时候，这真的很混乱

我可以很快的按照的每个微前端的样式方式快速处理ticket，但是随着项目feature越来越多
我们的样式管理会很快遇到问题，这是我们的技术债务
我当时的想法就是，我们必须要有一个合理的可统一参考的样式，每个微服务可以采用自己的方式
但是我们必须align

于是我做了搜索，也和一些market的设计师talk，我很快发现，其实整个公司有一个很明确的design system
整个系统的primtive，like h1 h2 body,etc
so that is it，而且figma上早就有了相关标注，只是没人关注
于是我基于每个微前端的样式管理，根据这个primtive 做了实现
最终每个微前端依然可以继续使用各自的样式管理，但是相关样式内容就必须严格遵守已经写好的design-token

2:做了什么取舍
从全部重构为统一的，到保持各自的样式管理，但是底层还是用同样的内容
3:最终怎么解决的
4:遇到了哪些困难
5:下次会怎么做如果再给一次机会
如果有下次，希望尽早的参与这些架构设计，制定微前端之间共享的design token

**CV bullet:** Led design token implementation across 5 microfrontend services, standardizing styling and reducing frontend styling issues by at least 30%.

### Q1. What problem were you trying to solve?

**Answer (EN)**

We had several microfrontend applications, and each one managed its styles separately. When we needed to fix even a small styling issue, such as a color difference, we often had to spend a long time comparing the applications. This became especially confusing when I worked on refactoring the shared header and footer. Fixing each issue locally was possible in the short term, but as more features were added, the differences were becoming technical debt. I felt we needed a shared styling foundation that every microfrontend could align with, even if each application continued to manage its styles in its own way.

**参考回答（中文）**

这项工作的目标是统一五个微前端服务的样式。不同应用独立演进时，共同的设计规范容易逐渐偏离，类似的 UI 元素也可能出现视觉差异。Design tokens 为团队提供一套共同的设计值，让不同服务的样式更一致，也更容易维护。

### Q2. What was your contribution?

**Answer (EN)**

I investigated how we could establish that shared foundation and spoke with designers from different markets. I discovered that the company already had a design system defining primitives such as heading levels and body text, and the relevant specifications were documented in Figma. They simply hadn't been consistently used across the applications. I implemented the design tokens based on those existing design primitives and the styling setup of each microfrontend. This allowed each application to keep its own styling approach while requiring shared styling values to follow the agreed tokens. My CV records at least a 30% reduction in frontend styling issues.

**参考回答（中文）**

我负责推动五个服务中的 design-token 实施。重点不是在每个服务里单独修复相同的样式问题，而是建立一套可以跨应用使用的一致样式基础。简历中记录的结果是样式一致性得到改善，前端样式问题至少减少了 30%。

### Q3. Why use design tokens instead of fixing styles in each application?

**Answer (EN)**

I considered two options: refactor all the microfrontends into one unified styling approach, or let each application keep its existing styling setup while standardizing the underlying design values. I chose the second option. A complete styling refactor would have been much broader and more disruptive, while shared tokens could address the core inconsistency without forcing every application to use the same styling implementation. The key was to align the design values, not necessarily the styling tools or structure.

**参考回答（中文）**

在每个应用里分别修复样式可以解决眼前的问题，但长期来看容易重复劳动，也可能产生不一致的结果。Tokens 可以集中管理共同的设计决策，让各个应用使用统一的值，并以更可控的方式更新。对于多个微前端来说，这比依赖每个团队独立做出相同决定更容易维护。

### Q4. How did you measure the 30% reduction?

**Answer (EN)**

The figure in my CV refers to a reduction in frontend styling issues after the token work was introduced. I want to be precise about the metric: I would use the team's actual issue records and comparison period to explain the calculation, rather than inventing a baseline or claiming that tokens alone caused every improvement. The important outcome was that styling became more consistent across the five services and fewer styling issues were reported.

**参考回答（中文）**

简历中的数字指的是引入 design tokens 后，前端样式问题数量的下降。我会根据团队实际的问题记录和对比周期解释具体计算方式，而不会编造基线，也不会声称所有改善都完全由 tokens 单独造成。核心结果是五个服务的样式更加一致，样式相关问题也减少了。

### Q5. What did you learn from this project?

**Answer (EN)**

The main difficulty was working across microfrontends that had evolved with different styling conventions. I had to understand those differences and map the existing design-system primitives into a shared token foundation without requiring every application to be rebuilt in the same way. I learned that a shared frontend foundation needs both a clear technical standard and alignment across teams. If I did this again, I'd try to get involved earlier in the architecture discussions and establish shared design tokens before the individual microfrontends drifted so far apart.

**参考回答（中文）**

我学到，共享前端基础设施不仅是代码问题，也涉及团队协作。只有不同应用能够一致地采用并长期维护，这套方案才真正有效。因此，我现在会更关注命名、维护责任、推广方式，以及一个共享决策对其他团队的影响。

---


### Q6. What is the difference between a design token and a component?

**Answer (EN)**

A design token represents a shared design decision, such as a color or spacing value. A component uses those design decisions to implement a piece of UI. Keeping the two concepts separate helps us update the visual foundation consistently without tying every design decision to one specific component.

**参考回答（中文）**

Design token 表示一项共享的设计决策，例如颜色或间距值；组件则使用这些设计决策来实现具体 UI。把两者分开，可以统一更新视觉基础，而不必把每项设计决策都绑定到某个具体组件。

### Q7. How would you encourage multiple teams to adopt shared tokens?

**Answer (EN)**

I'd make the shared approach easier to use than maintaining local alternatives. That means clear naming, straightforward access to the tokens, examples, and a migration path that fits each application's release constraints. I'd also agree on ownership so teams know where to propose changes and how compatibility is managed.

**参考回答（中文）**

我会让使用共享方案比维护各自的实现更简单。这需要清晰的命名、方便的接入方式、示例，以及符合各应用发布约束的迁移路径。我也会明确维护责任，让团队知道如何提出变更，以及如何管理兼容性。

### Q8. What would you do if one service needed a different visual style?

**Answer (EN)**

I'd first check whether the difference is a legitimate product requirement or simply an inconsistency. If it is a real requirement, the shared system should support a deliberate variation rather than forcing every service to look identical. The aim is consistent design rules with controlled flexibility, not uniformity at any cost.

**参考回答（中文）**

我会先确认这种差异是合理的产品需求，还是无意产生的不一致。如果确实有业务需要，共享系统就应该支持有意识的变化，而不是强迫所有服务完全相同。目标是保持设计规则一致，同时允许受控的灵活性，而不是不计代价地追求统一。

### Q9. What would you do differently next time?

**Answer (EN)**

I'd make adoption and measurement part of the plan from the beginning. A shared token system needs more than an implementation; teams need a clear migration path, and the project needs a consistent way to track styling issues before and after adoption. That would make both rollout and the reported impact easier to evaluate.

**参考回答（中文）**

下次我会从一开始就把推广和效果衡量纳入计划。共享 token 系统不仅需要实现本身，团队还需要清晰的迁移路径，项目也需要一致的方式来比较采用前后的样式问题。这样可以更好地评估推广过程和最终效果。

## 3. Manulife — Refactoring a legacy PDF report module

1:当我在处理MY PDF报告的时候，我被告知可以参考目前其他markey的做法，然后我发现目前项目里存在至少3个
不同的解决方案，每一个方案都没有清晰的开发文档，而且开发人员全部都是复制大量的模版代码，在此基础上更改原声html
我的pdf报告和page中的内容有很多是相同的，但是目前的3种方案都无法共用，并且每一个方案的开发周期都至少3天
于是我开始思考，我们整个系统的技术栈是react，为什么我们不用react来尝试生成报告呢，本质上pdf也是UI interface
于是我做了一番调研和证据收集，我用了一天时间，用react做了一个PDF报告，复用了我们的公共组件，我很兴奋
我和我们的几个market的开发人员以及我们的技术经理做了简单汇报，大家都觉得这个方案很好，值得去尝试和推广
于是我便彻底完善了这个方案

我的manager给了很大的支持，我们开了一个会议，向我们其他国家的开发人员展示了我们的方案，
最终，我们所有的market采用了统一的方案，新的PDF我们统一采用这个方案，实际上，因为有了AI，在我走之前，我们团队也正在用AI把原来久的方案迁移到目前我这个新的方案上面

**CV bullet:** Refactored a legacy PDF report module with React, reducing new report development time by 40%.

### Q1. What was the challenge with the legacy module?

**Answer (EN)**

When I was working on PDF reports for my market, I was told to look at how other markets had implemented theirs. I found at least three different solutions, with no clear development documentation. Developers were copying large amounts of template code and then modifying the raw HTML. Although the PDF reports shared a lot of content with the corresponding web pages, the three approaches couldn't reuse that content effectively, and developing a new report took at least three days. Since our technology stack was React and a PDF report is also a user interface, I wondered whether we could build reports with React and reuse our shared components.

**参考回答（中文）**

挑战在于改造现有报告模块的同时，确保报告原有行为仍然可靠。随着报表功能不断增加，如果代码难以理解、共用逻辑组织得不好，新增报表的开发就会越来越慢。这次重构的目标是提高代码的可维护性，让新报表开发更高效。

### Q2. What did you do?

**Answer (EN)**

I researched the options and gathered evidence, then built a working React-based PDF report prototype in one day using our shared components. I presented it to developers from several markets and our technical manager, and they agreed it was worth exploring and rolling out. With my manager's support, I refined the solution and presented it to developers in other countries. Eventually, all markets adopted the unified approach for new PDF reports. Before I left, our team was also using AI to help migrate reports from the old implementations to the new approach. The result recorded in my CV was a 40% reduction in new-report development time.

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


### Q6. How did you decide what to refactor first?

**Answer (EN)**

I'd prioritize the parts that made new report work repetitive or difficult to extend, while keeping existing report behavior stable. The aim was not to rewrite code just to make it look newer; it was to remove friction from the workflow that engineers used whenever a new report was required.

**参考回答（中文）**

我会优先处理那些导致新增报表工作重复、难以扩展的部分，同时保持现有报表行为稳定。重构的目的不是单纯让代码看起来更新，而是减少工程师每次开发新报表时遇到的阻力。

### Q7. How would you test a refactor when the old behavior is poorly documented?

**Answer (EN)**

I'd first collect representative existing reports and use them as examples of expected behavior. Then I'd compare the output and important user-visible behavior before and after the changes, and ask the relevant stakeholders to confirm cases where the expected result isn't obvious. That gives the team a practical baseline even when the documentation is incomplete.

**参考回答（中文）**

我会先收集有代表性的现有报表，把它们作为预期行为的样例。之后对比改动前后的输出和关键用户可见行为；对于预期结果不明确的情况，再请相关人员确认。即使文档不完整，这也能为团队建立一个可操作的基线。

### Q8. How do you explain the 40% improvement to a non-technical stakeholder?

**Answer (EN)**

I'd explain that the improvement was about the engineering time needed to build a new report, not about PDF generation speed. The refactored module made the development process more efficient, so new reporting requirements could be implemented with less effort. I'd then show the actual before-and-after measurement used by the team if the stakeholder wanted the calculation.

**参考回答（中文）**

我会解释，这个提升指的是开发新报表所需的工程时间，而不是 PDF 生成速度。模块重构提高了开发流程的效率，因此实现新的报表需求所需的工作量更少。如果对方希望了解计算方式，我会提供团队实际使用的前后对比数据。

### Q9. What is the risk of over-refactoring a legacy module?

**Answer (EN)**

The risk is introducing broad changes that don't create enough value to justify the regression risk. I prefer to connect each refactoring step to a concrete maintenance or delivery problem, preserve behavior that users depend on, and validate changes incrementally. That keeps the work focused on outcomes rather than code aesthetics alone.

**参考回答（中文）**

风险在于做了范围很大的改动，却没有创造足以抵消回归风险的价值。我倾向于让每一步重构都对应明确的维护或交付问题，保留用户依赖的行为，并逐步验证改动。这样可以让重构聚焦于结果，而不只是代码形式。



## 4. Manulife — Component-library architecture and AI-assisted review

story: 我们有接近100多个共享的业务组件，但是这些业务组件的很多readme文档和code已经不匹配
当其他market需要找到一个可复用的组件的时候，通常需要查找大量的code 导致很多时间我们会重复创建一些业务组件

于是我思考到，我们可以记住storybook搭建整个项目的组件库，同时创建相关skill，能够很快找到对应的组件
另外，将团队中关于组件的一些规则集成到了cicd中，所有关于公共组件的修改，必须进行对应scan，同时也要有至少2名以上同事的review


**CV bullet:** Independently designed and built the component library architecture, integrating AI-powered review and maintenance to ensure component quality.

### Q1. Why did the team need a component library?

**Answer (EN)**

We had close to 100 shared business components, but many README files no longer matched the actual code. When developers in another market needed to find a reusable component, they often had to search through a lot of code. That took time and sometimes led teams to build components that already existed. I wanted to make the available components easier to discover and the maintenance process more reliable.

**参考回答（中文）**

共享组件库可以避免不同团队反复解决相同的 UI 问题。它提供可复用的基础组件，也让常见界面模式的实现更加一致。架构上的挑战是提高复用性，同时避免组件过度抽象，导致难以理解或定制。

### Q2. What did you personally own?

**Answer (EN)**

I independently designed and built the component-library architecture. My approach was to use Storybook to organize and present the project's shared components, and to create a related skill that could help developers quickly find the right component instead of searching through the code manually. I also integrated the team's component rules into CI/CD: changes to shared components had to go through the relevant scan and receive reviews from at least two colleagues. This combined discoverability with a clearer quality-control process.

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


### Q6. How do you avoid making components too abstract?

**Answer (EN)**

I start from recurring use cases rather than trying to predict every possible future requirement. A component should have a clear purpose and a small, understandable API. If two use cases only look similar but behave differently, I would rather keep the distinction clear than force them into one component with many special-case props.

**参考回答（中文）**

我会从反复出现的真实使用场景出发，而不是试图预先覆盖所有未来需求。组件应该有明确目的和易理解的 API。如果两个场景只是看起来相似、实际行为却不同，我宁愿保留清晰的区别，也不会强行合并成带有大量特殊属性的组件。

### Q7. How should breaking changes in a component library be handled?

**Answer (EN)**

I'd make the impact explicit before releasing the change. That includes identifying affected consumers, documenting what changed, providing a migration path where possible, and coordinating the release so dependent applications can update safely. A shared library needs to treat compatibility as part of its product, not as an afterthought.

**参考回答（中文）**

发布变更前，我会明确说明它的影响范围，包括识别受影响的使用方、记录变更内容、尽可能提供迁移路径，并协调发布，让依赖应用能够安全升级。共享库应该把兼容性当作产品的一部分，而不是事后才考虑的问题。

### Q8. What should AI review check, and what should remain a human decision?

**Answer (EN)**

AI can help identify potential issues, inconsistent patterns, or places that deserve a closer look. A human still needs to judge whether a finding is correct, whether it matters in the product context, and whether the proposed change is safe. I would not let AI review replace ownership, tests, or the normal approval process.

**参考回答（中文）**

AI 可以帮助发现潜在问题、不一致的模式，或值得进一步检查的地方。但人仍然需要判断问题是否真实、在产品语境下是否重要，以及建议的修改是否安全。我不会让 AI review 取代责任归属、测试或正常的审批流程。

### Q9. How would you get developers to trust a shared component library?

**Answer (EN)**

Trust comes from predictable behavior, useful documentation, and responsive maintenance. Developers need to know what a component is designed to do, how to use it, and what to expect when it changes. I'd also treat bug reports and feedback as part of maintaining the library, rather than expecting consumers to work around problems themselves.

**参考回答（中文）**

信任来自可预期的行为、有用的文档和及时的维护响应。开发人员需要知道组件的设计目的、使用方式，以及组件变更会带来什么影响。我也会把缺陷报告和反馈视为维护库的一部分，而不是让使用方自行绕过问题。

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


### Q5. What does a good user experience mean in a financial workflow?

**Answer (EN)**

It means users can understand what action they are taking, what information is required, and what state the operation is in. Clear validation and status feedback are especially important because users need confidence that the system has handled their request correctly. I see usability and correctness as closely connected in financial products.

**参考回答（中文）**

这意味着用户能够理解自己正在执行什么操作、需要哪些信息，以及操作目前处于什么状态。清晰的校验和状态反馈尤其重要，因为用户需要确信系统正确处理了请求。在金融产品中，我认为易用性与正确性紧密相关。

### Q6. How do you work with product or domain experts?

**Answer (EN)**

I try to clarify the business meaning behind a requirement instead of translating the first description directly into code. I ask about expected outcomes, exceptions, and how the behavior should be explained to users. This is particularly important in financial products, where a small misunderstanding in a rule can lead to a misleading interface or incorrect workflow.

**参考回答（中文）**

我会先弄清需求背后的业务含义，而不是把最初的描述直接翻译成代码。我会询问预期结果、例外情况，以及应该如何向用户解释行为。这在金融产品中尤其重要，因为对规则的细微误解都可能造成误导性的界面或错误的流程。

### Q7. How do you approach errors in a transaction-related UI?

**Answer (EN)**

I want the interface to distinguish between a request that is still processing, one that succeeded, and one that failed. The user should not be left guessing whether an action went through. I would follow the backend's actual response and status model, show clear feedback, and avoid presenting an uncertain result as a confirmed success.

**参考回答（中文）**

我希望界面能够区分仍在处理中、已经成功和已经失败的请求，不能让用户猜测操作到底有没有生效。我会遵循后端实际的响应和状态模型，提供清晰反馈，避免把不确定的结果显示成已确认成功。

### Q8. What did working on a large financial platform teach you?

**Answer (EN)**

It reinforced the importance of domain understanding, careful validation, and clear responsibility across teams. In a large product, a feature rarely exists in isolation; it depends on business rules, APIs, and other parts of the platform. I learned to ask more questions about the full workflow before focusing on the implementation details.

**参考回答（中文）**

这段经历让我更加重视业务理解、谨慎校验，以及团队之间清晰的职责划分。在大型产品中，一个功能很少是孤立存在的，它依赖业务规则、API 和平台其他部分。我学会了在关注实现细节前，先多了解整个业务流程。

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


### Q5. Why not just ask engineers to write more documentation?

**Answer (EN)**

Documentation is still important, and I wouldn't replace it with AI. The challenge is that documentation can be incomplete or become outdated as a codebase changes. AI-powered exploration can help people navigate existing code and find relevant context, while engineers still need to verify the explanation and maintain authoritative documentation for important behavior.

**参考回答（中文）**

文档仍然很重要，我不会用 AI 取代文档。问题在于，随着代码库变化，文档可能不完整或逐渐过时。AI 辅助探索可以帮助人们浏览现有代码并找到相关背景，但工程师仍然需要验证解释，并为重要行为维护权威文档。

### Q6. How would you evaluate whether an AI tool actually saves time?

**Answer (EN)**

I'd evaluate it against a real task, such as finding the code behind an existing business rule or helping a new teammate understand a feature. I'd compare the time and effort needed with and without the tool, while also checking whether the answers are accurate enough to be useful. Faster output isn't a success if people spend the saved time correcting misleading answers.

**参考回答（中文）**

我会用真实任务来评估，例如查找某条既有业务规则对应的代码，或帮助新成员理解某项功能。我会比较使用和不使用工具时所需的时间与精力，同时检查答案是否足够准确。即使生成速度更快，如果大家还要花时间纠正误导性答案，也不能算成功。

### Q7. What information should an AI engineering tool be allowed to use?

**Answer (EN)**

It should use the project context that is appropriate for the task and follow the team's access and data-handling rules. The tool should not expose information to people who aren't authorized to see it, and it should make the source of important claims clear. Trust and access control are part of the design, not something to add after the tool works.

**参考回答（中文）**

工具应该只使用任务所需且符合团队访问与数据处理规则的项目上下文。它不能把信息暴露给没有权限的人，并且应尽可能说明重要结论的来源。信任和访问控制应当从设计阶段就考虑，而不是工具可用之后再补上。

### Q8. What is the role of an engineer when AI can explain code?

**Answer (EN)**

The engineer still needs to verify the explanation, understand the system's constraints, and make the final decision. AI can reduce the time spent searching and summarizing, but it doesn't take responsibility for correctness or consequences. I see it as a way to help engineers focus more time on judgment and implementation rather than repetitive discovery work.

**参考回答（中文）**

工程师仍然需要验证解释、理解系统约束，并做出最终决策。AI 可以减少搜索和总结所需的时间，但不会替人承担正确性和后果责任。我把它看作一种辅助方式，让工程师把更多时间投入判断和实现，而不是重复的信息搜寻。


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


### Q7. What makes a migration across several teams difficult?

**Answer (EN)**

The challenge is not only converting code; teams also need to agree on how their parts fit together and how changes are released. Without clear ownership and integration expectations, each team can make locally reasonable choices that don't work well together. I would treat communication and integration planning as core engineering work throughout the migration.

**参考回答（中文）**

难点不只是转换代码，团队还需要就各自负责的部分如何组合、变更如何发布达成一致。如果责任和集成预期不清晰，每个团队都可能做出局部合理、整体却无法很好协作的选择。我会把沟通和集成规划视为迁移过程中核心的工程工作。

### Q8. How do you decide whether to migrate or rewrite a feature?

**Answer (EN)**

I'd compare the cost and risk of keeping the existing feature, incrementally migrating it, or rewriting it. The decision depends on how much value the rewrite creates, how much working behavior would need to be recreated, and how safely the change can be delivered. For a production product, I would avoid a rewrite simply because the technology is newer.

**参考回答（中文）**

我会比较保留现有功能、逐步迁移和完全重写的成本与风险。决策取决于重写能带来多少价值、需要重新实现多少现有行为，以及变更能否安全交付。对于生产产品，我不会仅仅因为新技术更新就选择重写。

### Q9. How would you detect regressions during a migration?

**Answer (EN)**

I'd define the important user journeys and expected behavior before changing them, then validate those journeys as the migration progresses. I'd combine automated checks where they are available with focused manual verification for critical flows. The key is to discover differences early, while the change is still small enough to understand and correct.

**参考回答（中文）**

我会在改动前明确重要用户流程和预期行为，并在迁移过程中持续验证这些流程。在可行的地方结合自动化检查，对关键流程进行有针对性的手动验证。关键是尽早发现差异，让问题还处于容易理解和修复的范围内。

### Q10. What did the zero-downtime result require from the team?

**Answer (EN)**

It required the migration to be managed as a production change, not just a frontend rewrite. Compatibility, integration, testing, and release coordination all mattered because users needed the product to remain available. The result depended on the team keeping those concerns in view throughout the transition.

**参考回答（中文）**

这要求团队把迁移当作一次生产变更来管理，而不只是前端重写。兼容性、集成、测试和发布协调都很重要，因为用户需要产品持续可用。这个结果依赖团队在整个过渡期间始终关注这些问题。

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


### Q5. How would you handle a long or complex publishing form?

**Answer (EN)**

I'd break the workflow into understandable sections, make required information clear, and validate fields close to where users enter them. I would also preserve useful input when validation fails and make the next action obvious. The goal is to help sellers complete the task correctly without making them guess what the system expects.

**参考回答（中文）**

我会把复杂流程拆分成容易理解的部分，明确标出必填信息，并尽量在用户输入的位置附近进行校验。校验失败时，也应该保留有用的输入内容，并清楚提示下一步操作。目标是帮助卖家正确完成任务，而不是让他们猜系统需要什么。

### Q6. How do you balance feature delivery speed with quality?

**Answer (EN)**

I start by clarifying the core seller workflow and implementing the essential behavior first. I still account for validation, loading and error states, and regression checks because these directly affect whether sellers can finish the task. Moving quickly is useful only if the feature remains reliable in real use.

**参考回答（中文）**

我会先明确卖家的核心操作流程，优先实现必要行为。同时也会考虑校验、加载和错误状态，以及回归检查，因为这些会直接影响卖家能否完成任务。只有功能在真实使用中依然可靠，快速交付才有意义。

### Q7. What would you do if the business asked for a last-minute change?

**Answer (EN)**

I'd first clarify what problem the change is meant to solve and whether it affects the existing publishing flow. Then I'd assess the impact on implementation, testing, and release risk, and agree with the product team on what can safely fit into the current delivery. I wouldn't silently skip validation just to meet a deadline.

**参考回答（中文）**

我会先确认临时变更要解决什么问题，以及它是否会影响现有发布流程。然后评估它对实现、测试和发布风险的影响，并与产品团队确认当前交付周期内哪些内容能够安全完成。我不会为了赶进度而默默跳过验证。

### Q8. What did this work teach you about e-commerce products?

**Answer (EN)**

Seller-facing features affect both the seller's workflow and the quality of information customers see. A small usability problem can create extra work for sellers or lead to incomplete product content. I learned to think about the whole workflow and the business outcome, rather than evaluating a feature only by whether the interface is implemented.

**参考回答（中文）**

面向卖家的功能既会影响卖家自己的工作流程，也会影响消费者看到的信息质量。一个小的易用性问题就可能增加卖家的工作量，或导致商品内容不完整。我学会了从完整流程和业务结果来思考，而不只判断界面是否实现了。

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


### Q5. How do you decide what should be shared across iOS and Android?

**Answer (EN)**

I'd share business logic and UI behavior where the platforms have the same requirements, while keeping platform-specific differences explicit. Trying to force every detail into a single abstraction can make the code harder to maintain. The goal is to reuse what is genuinely common without hiding meaningful platform differences.

**参考回答（中文）**

对于两个平台需求一致的业务逻辑和 UI 行为，我会尽量复用；平台特有的差异则应明确保留。试图把所有细节都塞进同一个抽象，反而可能增加维护难度。目标是复用真正共通的部分，同时不掩盖有意义的平台差异。

### Q6. How would you investigate a slow React Native screen?

**Answer (EN)**

I'd first reproduce the problem and identify whether it comes from rendering, data loading, or an interaction with native functionality. Then I'd measure the relevant part rather than guessing, and narrow the change to the actual bottleneck. I'd also recheck the user journey after the fix to make sure the improvement doesn't introduce a regression.

**参考回答（中文）**

我会先复现问题，判断瓶颈来自渲染、数据加载，还是与原生功能的交互。然后针对相关环节进行测量，而不是凭感觉猜测，并把改动范围缩小到真正的瓶颈。修复后还会重新检查用户流程，确认没有引入回归。

### Q7. How do you handle platform-specific behavior?

**Answer (EN)**

I try to keep platform-specific behavior explicit and test it on the platforms that matter. Shared code is valuable, but it doesn't remove the need to verify differences in navigation, permissions, layout, and native integrations. I would rather isolate a small platform-specific implementation than make the shared code difficult to understand.

**参考回答（中文）**

我会明确处理平台特有行为，并在相关平台上进行验证。共享代码很有价值，但它并不意味着可以忽略导航、权限、布局和原生集成方面的差异。我宁愿隔离一小部分平台特定实现，也不愿让共享代码变得难以理解。

### Q8. What does delivering more than twelve features demonstrate?

**Answer (EN)**

It shows that I contributed to a range of real mobile product functionality, rather than only building a prototype or one isolated screen. Those features supported the seller store-management experience. I would choose one or two representative features from my actual work to explain the requirements, implementation, and trade-offs in more detail.

**参考回答（中文）**

这说明我参与交付了一系列真实的移动端产品功能，而不只是做原型或单独的一个页面。这些功能共同支持卖家的店铺管理体验。面试时，我会从实际工作中挑选一到两个有代表性的功能，进一步解释需求、实现和技术取舍。

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


### Q6. Why shouldn't the frontend be the source of truth for stock?

**Answer (EN)**

The browser cannot reliably coordinate inventory across multiple users and requests. The backend needs to enforce the authoritative inventory rules, while the frontend presents the current result and guides the user through the next step. That separation prevents the UI from promising availability that the server cannot guarantee.

**参考回答（中文）**

浏览器无法可靠地协调多个用户和请求之间的库存状态。后端需要执行权威的库存规则，前端则负责呈现当前结果并引导用户进行下一步操作。这样的职责分离可以避免界面承诺服务端无法保证的库存状态。

### Q7. How do you prevent duplicate user actions from creating a confusing UI?

**Answer (EN)**

At the UI level, I'd give clear feedback when an action is being processed and avoid encouraging repeated submissions while the request is pending. I would still rely on the backend to enforce correctness for operations that must not be duplicated. The frontend can improve the interaction, but it cannot replace server-side safeguards.

**参考回答（中文）**

在 UI 层，我会在操作处理中提供清晰反馈，并避免请求尚未完成时鼓励用户重复提交。对于不能重复执行的操作，我仍然依赖后端保证正确性。前端可以改善交互，但不能替代服务端的保护机制。

### Q8. How would you test cart and inventory edge cases?

**Answer (EN)**

I'd cover the main states: adding and removing items, updating quantities, receiving an API error, and discovering that an item is no longer available. I'd verify both the displayed state and the recovery path, so users aren't left with stale information or a blocked workflow. The exact automated tests would depend on the test setup used in the project.

**参考回答（中文）**

我会覆盖主要状态，包括添加和移除商品、更新数量、收到 API 错误，以及商品变为无货的情况。我会同时验证界面显示的状态和后续恢复流程，避免用户看到过期信息或被卡在流程中。具体自动化测试会根据项目实际使用的测试环境来确定。

### Q9. How did you work with backend engineers on these features?

**Answer (EN)**

I'd align on the API contract, expected response states, and how errors should be represented to the client. That helps the frontend handle normal and exceptional cases consistently. Because inventory rules belonged to the backend, collaboration was important to ensure the UI reflected the server's actual behavior rather than making assumptions of its own.

**参考回答（中文）**

我会与后端工程师对齐 API 契约、预期响应状态，以及错误应该如何反馈给客户端。这样前端才能一致地处理正常情况和异常情况。由于库存规则由后端负责，双方协作很重要，可以确保 UI 反映服务端的真实行为，而不是自行假设。

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


### Q5. Why was automation valuable for HR?

**Answer (EN)**

Attendance administration can involve repeated collection, checking, and summarizing of employee information. Automating parts of that workflow reduces repetitive manual work and makes the process easier to manage. The platform's reported impact was an approximately 60% reduction in HR's manual workload.

**参考回答（中文）**

考勤管理可能涉及反复收集、核对和汇总员工信息。将流程中的一部分自动化，可以减少重复的人工操作，让管理更容易。这个平台记录的效果是 HR 人工工作量减少了约 60%。

### Q6. What would you do if employees reported incorrect attendance data?

**Answer (EN)**

I'd first reproduce the issue and determine whether it came from the input data, the business rules, or how the frontend displayed the result. I'd then work with the relevant owner to correct the cause and make sure the interface communicates the state clearly. For an attendance system, users need a way to understand discrepancies rather than simply seeing a number that looks wrong.

**参考回答（中文）**

我会先复现问题，判断原因来自输入数据、业务规则，还是前端展示方式。然后与对应负责人一起修正问题，并确保界面能清晰表达当前状态。对于考勤系统，用户需要理解数据差异的原因，而不只是看到一个看起来不对的数字。

### Q7. How do you design an internal tool for different user groups?

**Answer (EN)**

I'd identify the tasks each group needs to complete and make the most common actions clear for that role. Employees and HR may look at the same attendance data for different reasons, so the interface should support those workflows without overwhelming users with irrelevant information. I'd validate the design with the people who actually use the system.

**参考回答（中文）**

我会先确认不同用户群体需要完成的任务，并让每个角色最常用的操作足够清晰。员工和 HR 可能出于不同目的查看同一份考勤数据，因此界面需要支持各自的流程，避免展示过多无关信息。我也会向实际使用系统的人确认设计是否符合需求。

### Q8. What does the 1,000+ employee scale change about the design?

**Answer (EN)**

It means the workflow needs to work consistently for many people, not just for a small pilot group. Clear states, predictable behavior, and maintainable code become important because even a small usability problem can affect many users. It also makes it important to understand the operational process rather than designing the UI in isolation.

**参考回答（中文）**

这意味着流程必须能够稳定服务大量用户，而不只是一个小规模试用群体。清晰的状态、可预期的行为和可维护的代码都很重要，因为即使很小的易用性问题也可能影响很多人。同时，这也要求我们理解实际业务流程，而不是孤立地设计 UI。

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

---

# Advanced project deep dive

## 11. 高强度技术追问：四个核心项目（中英文参考答案）

> **使用说明：** 本节用于 Senior Frontend / Frontend-focused Full-stack Engineer 的技术面试深挖。英文答案是可练习的回答框架，不代表简历已经证明了所有具体实现。请把方括号中的内容替换成真实项目事实；没有亲自做过的技术决策、工具、测试或指标，不要声称自己做过。面试官通常会沿着“问题 → 约束 → 方案 → 取舍 → 验证 → 结果”继续追问。

### 11.1 Manulife — Design Tokens across five microfrontend services

#### Q1. What problem did design tokens solve that ordinary shared CSS could not?

**Question（中文）：** Design Tokens 解决了什么问题？为什么不只是共享一份 CSS？

**Model answer (EN):** The goal was to make design decisions consistent across five independently delivered microfrontend services. Shared CSS can reuse selectors, but it does not necessarily establish a clear contract for design values such as color, spacing, typography, and borders. Tokens provide named, reusable design decisions, while the consuming applications still need an agreed way to load and apply them. I would explain the exact token categories and distribution mechanism used in our project rather than imply that tokens alone solved every styling inconsistency.

**参考答案（中文）：** 目标是在五个独立交付的微前端服务之间统一设计决策。共享 CSS 可以复用选择器，但不一定能为颜色、间距、字体和边框等设计值建立清晰的约定。Tokens 为这些设计决策提供命名和复用机制，但各应用仍然需要约定如何加载和使用它们。我会进一步说明项目实际采用的 token 分类和分发方式，不会把所有样式不一致都归因于是否使用了 tokens。

#### Q2. How would you design tokens for multiple microfrontends without tightly coupling the applications?

**Question（中文）：** 如何为多个微前端设计 tokens，同时避免应用之间形成紧耦合？

**Model answer (EN):** I would separate the shared design contract from each application's implementation. The contract should define stable token names and their meaning; consuming applications should reference those names instead of copying raw values. I would also define ownership, versioning, change communication, and a deprecation process. The implementation could use CSS custom properties, generated CSS, or a package, depending on the existing build and deployment model. I would name the option we actually used and explain why it fitted our constraints.

**参考答案（中文）：** 我会把共享设计契约与各应用的具体实现分开。契约定义稳定的 token 名称及其语义，使用方引用这些名称，而不是重复维护原始值。同时需要明确维护责任、版本策略、变更通知和弃用流程。具体实现可以是 CSS 自定义属性、生成后的 CSS 或共享包，取决于现有构建和部署方式。我会明确说出项目实际采用的方案，并解释它为什么符合当时的约束。

#### Q3. What happens when one microfrontend needs a token change but the others are not ready?

**Question（中文）：** 如果一个微前端需要修改 token，但其他微前端暂时无法同步升级，你会怎么处理？

**Model answer (EN):** I would treat a token change as a compatibility change, not merely a visual edit. Before changing or removing a token, I would check its consumers and determine whether the change is additive, backward-compatible, or breaking. For a breaking change, I would prefer a transition period: introduce the replacement, migrate consumers, monitor adoption, and remove the old token only when it is safe. The exact rollout mechanism depends on how the token assets are versioned and deployed in the real system.

**参考答案（中文）：** 我会把 token 变更视为兼容性变更，而不只是视觉修改。修改或删除 token 前，先检查它的使用方，并判断变更属于新增、向后兼容还是破坏性变更。对于破坏性变更，优先采用过渡方案：先引入新 token，再迁移使用方、检查采用情况，确认安全后才移除旧 token。具体发布机制取决于真实系统如何对 token 资源进行版本管理和部署。

#### Q4. How would you prevent teams from bypassing tokens and introducing new hard-coded values?

**Question（中文）：** 如何避免团队绕过 tokens，继续写硬编码样式值？

**Model answer (EN):** I would combine enablement with lightweight enforcement. First, the token names and usage examples need to be easy to discover. Then I would use code review guidance and, if supported by the repository, lint rules or automated checks to flag prohibited raw values in agreed areas. I would avoid banning every literal indiscriminately because some values may be legitimate exceptions. The important part is to define the rule, document exceptions, and make adoption easier than bypassing the system.

**参考答案（中文）：** 我会把开发者支持和适度的自动化约束结合起来。首先，token 名称和使用示例必须容易查找；其次，通过代码评审规范，以及仓库条件允许时的 lint 规则或自动检查，识别约定范围内不应出现的硬编码值。我不会不加区分地禁止所有字面量，因为有些场景确实需要例外。关键是明确规则、记录例外，并让正确使用 tokens 比绕过系统更容易。

#### Q5. How would you investigate a visual regression after a token release?

**Question（中文）：** token 发布后出现视觉回归，你会如何排查？

**Model answer (EN):** I would first identify the affected applications, routes, components, and token values, then compare the previous and current rendered styles. I would check whether the cause was a changed token value, a missing token, different CSS loading order, selector specificity, or an application using an outdated asset. I would reproduce the issue in the smallest affected surface, fix the source of the inconsistency, and add a regression check appropriate to the project's setup. I would not assume every visual regression comes from the token value itself.

**参考答案（中文）：** 我会先确认受影响的应用、路由、组件和 token 值，再对比变更前后的实际渲染样式。重点检查 token 值变化、token 缺失、CSS 加载顺序、选择器优先级，以及应用是否仍在使用旧资源。随后在最小范围内复现问题，修复真正的不一致来源，并根据项目现有测试体系补充回归检查。我不会假设所有视觉回归都由 token 值本身导致。

#### Q6. Your CV says styling issues fell by at least 30%. How would you defend that number?

**Question（中文）：** 简历说样式问题减少至少 30%，你如何解释这个指标？

**Model answer (EN):** I would define what counted as a styling issue, the baseline period, the comparison period, and which five services were included. I would then explain the source of the data, such as a tracked issue category or another agreed measure, only if that was how it was actually calculated. I would distinguish correlation from causation and acknowledge other changes that may have contributed. If the figure was a team estimate rather than a formal dashboard metric, I would state that transparently.

**参考答案（中文）：** 我会先定义什么情况算作样式问题、基准统计周期、对比周期，以及统计覆盖的五个服务。然后说明数据来源，例如被单独标记的问题类别或项目中实际采用的其他统计方式。只有在确实如此计算的情况下，我才会声称指标来自某个系统。我也会区分相关性和因果关系，并说明可能同时产生影响的其他变化。如果这个数字是团队估算，而不是正式仪表盘指标，我会如实说明。

### 11.2 Newegg — Angular-to-React microfrontend migration with zero production downtime

#### Q1. Why migrate from Angular to React instead of rewriting the entire application at once?

**Question（中文）：** 为什么选择 Angular 迁移到 React，而不是一次性重写整个应用？

**Model answer (EN):** The key constraint in my CV is that the migration had to avoid production downtime and coordinate work across three teams. A big-bang rewrite can create a long period before users see value and makes it harder to isolate regressions. A gradual migration can reduce the size of each release and allow old and new implementations to coexist temporarily, but it adds integration complexity. I would explain the actual migration boundary and why it was appropriate for our release and team constraints.

**参考答案（中文）：** 简历中最重要的约束是迁移期间不能造成生产停机，而且需要协调三个团队。一次性重写可能导致较长时间无法交付用户价值，也更难隔离回归问题。渐进式迁移可以缩小每次发布的变更范围，并允许新旧实现暂时共存，但会增加集成复杂度。我会结合实际迁移边界，解释为什么这种方式适合当时的发布节奏和团队约束。

#### Q2. How can Angular and React coexist during a gradual migration?

**Question（中文）：** 渐进式迁移时，Angular 和 React 如何共存？

**Model answer (EN):** I would define a clear boundary between the legacy and replacement surfaces. The integration needs an agreed routing or mounting strategy, consistent authentication and navigation behavior, and explicit ownership of shared state and events. I would avoid letting both frameworks independently own the same DOM subtree or duplicate critical business state. The exact integration pattern depends on the existing microfrontend platform, so in an interview I would describe the boundary and mechanism that our project actually used.

**参考答案（中文）：** 我会先明确旧系统和新系统各自负责的界面边界。集成方案需要约定路由或挂载方式，保持认证和导航行为一致，并明确共享状态和事件的归属。我会避免让两个框架同时控制同一段 DOM，或各自维护重复的关键业务状态。具体集成模式取决于原有微前端平台，因此面试中应该描述项目真实使用的边界和机制。

#### Q3. What does “zero production downtime” mean, and how would you verify it?

**Question（中文）：** “生产环境零停机”具体是什么意思？你会如何验证？

**Model answer (EN):** I would clarify that zero downtime means the migration did not require taking the production service offline; it does not automatically mean there were no defects or no user-visible issues. Verification should combine deployment and availability evidence with critical user-journey checks and monitoring during rollout. I would identify the actual signals available in the project, such as availability records, error rates, or smoke-test results, and avoid claiming measurements we did not collect.

**参考答案（中文）：** 我会澄清，零停机是指迁移不需要让生产服务下线，并不自动意味着没有缺陷或用户可见问题。验证时应结合部署和可用性记录、关键用户流程检查，以及发布期间的监控。我会说明项目实际拥有的数据，例如可用性记录、错误率或冒烟测试结果，不会声称收集过实际上没有收集的数据。

#### Q4. How would you reduce migration risk when three teams are working in parallel?

**Question（中文）：** 三个团队并行迁移时，如何降低风险？

**Model answer (EN):** I would establish a shared migration plan with explicit ownership, interface contracts, dependencies, and acceptance criteria. Teams should agree on the integration points and communicate breaking changes before they land. I would split work into independently reviewable increments, keep a visible list of migration blockers, and define a rollback or disablement path where the platform supports it. The aim is to reduce coordination risk, not to add meetings for their own sake.

**参考答案（中文）：** 我会建立共享迁移计划，明确负责人、接口契约、依赖关系和验收标准。各团队需要提前约定集成点，并在引入破坏性变更前同步信息。我会把工作拆成可独立评审的小批次，持续维护迁移阻塞项清单，并在平台支持的情况下准备回滚或关闭新功能的路径。目标是降低协作风险，而不是为了开会而开会。

#### Q5. How would you handle differences between Angular and React in routing, forms, state, and lifecycle behavior?

**Question（中文）：** Angular 与 React 在路由、表单、状态和生命周期方面不同，迁移时如何处理？

**Model answer (EN):** I would not translate framework APIs one by one. I would first document the user-visible behavior and business rules, then reimplement those behaviors using React's component model and the conventions of the target application. I would pay particular attention to form validation, navigation, asynchronous requests, cleanup, and state ownership because superficially similar code can behave differently. Shared acceptance scenarios are more valuable than a line-by-line translation of the old implementation.

**参考答案（中文）：** 我不会逐个 API 地机械翻译框架代码。我会先记录用户可见行为和业务规则，再使用 React 的组件模型以及目标应用的约定重新实现这些行为。表单校验、导航、异步请求、清理逻辑和状态归属尤其需要关注，因为表面相似的代码可能有不同的运行行为。相比逐行翻译旧实现，共享的验收场景更有价值。

#### Q6. What would your migration test strategy look like?

**Question（中文）：** 你的迁移测试策略会如何设计？

**Model answer (EN):** I would start with behavior-based acceptance criteria for the highest-value user journeys, then cover the new React components at the appropriate unit or component level. I would also test integration boundaries between the two frameworks, including navigation, authentication context, error handling, and shared events where relevant. Before each rollout, I would run the project's existing regression suite and targeted smoke tests. I would name the exact tools and test coverage only after confirming what the project actually used.

**参考答案（中文）：** 我会先为高价值用户流程建立基于行为的验收标准，再根据需要对新的 React 组件进行单元或组件级测试。还需要测试两个框架之间的集成边界，例如导航、认证上下文、错误处理和相关共享事件。每次发布前，我会运行项目已有的回归测试和针对性冒烟测试。只有确认项目实际使用了哪些工具和覆盖范围后，才会在面试中给出具体名称和数字。

### 11.3 Manulife — Refactoring a legacy PDF report module with React

#### Q1. Why refactor the PDF report module instead of continuing to add features to the legacy implementation?

**Question（中文）：** 为什么要重构旧 PDF 报表模块，而不是继续在原实现上增加功能？

**Model answer (EN):** The decision should be based on the cost and risk of future changes, not on the fact that the code was old. If adding a new report repeatedly required understanding tightly coupled logic or duplicating existing behavior, that would be evidence of a delivery bottleneck. I would explain the concrete pain points we observed, the scope we chose to refactor, and why a bounded refactor was safer than either a full rewrite or continued patching.

**参考答案（中文）：** 决策依据应该是未来变更的成本和风险，而不只是代码比较旧。如果每次增加报表都需要重新理解紧耦合逻辑或重复实现已有行为，这就可能是交付瓶颈。我会说明项目中真实存在的痛点、选择重构的范围，以及为什么有边界的重构比全面重写或继续打补丁更安全。

#### Q2. How would you separate report-specific configuration from shared rendering logic?

**Question（中文）：** 如何把报表特有配置与共享渲染逻辑分离？

**Model answer (EN):** I would look for the stable parts shared by multiple reports and the parts that vary by report type. Shared concerns might include common layout primitives, formatting conventions, and repeated rendering behavior; report-specific concerns might include sections, fields, and business rules. I would model the variation explicitly rather than create a large component full of conditionals. The exact abstraction should follow the real report formats and extension points in the codebase.

**参考答案（中文）：** 我会识别多个报表之间稳定复用的部分，以及不同报表类型之间变化的部分。共享部分可能包括通用布局原语、格式规范和重复的渲染行为；特定报表的差异可能包括章节、字段和业务规则。我会显式建模这些差异，而不是创建充满条件判断的大组件。最终抽象应由代码库中真实的报表格式和扩展点决定。

#### Q3. What are the most difficult correctness risks in PDF reporting?

**Question（中文）：** PDF 报表最难处理的正确性风险是什么？

**Model answer (EN):** The important risks are not only whether a PDF can be generated. The output must preserve business values and formatting, handle long or missing content, and remain readable across page breaks and different data shapes. Depending on the product, dates, currencies, rounding, table overflow, headers and footers may also be critical. I would identify which of these risks actually occurred in our module and describe the safeguards we implemented, rather than presenting every possible edge case as a problem we encountered.

**参考答案（中文）：** 关键风险不只是能否生成 PDF。输出还必须保证业务数值和格式正确，处理过长或缺失的内容，并在分页和不同数据结构下保持可读性。根据产品情况，日期、货币、舍入、表格溢出、页眉和页脚也可能非常重要。我会指出哪些风险确实出现在项目中，并介绍实际采取的保障措施，而不是把所有可能的边界情况都说成亲身遇到过的问题。

#### Q4. How would you prevent a refactor from changing existing report output unintentionally?

**Question（中文）：** 如何避免重构意外改变现有报表输出？

**Model answer (EN):** I would establish representative baseline cases before changing the implementation. Where practical, I would compare generated outputs using stable fixtures and a suitable visual or structural comparison, while accounting for dynamic fields such as timestamps. I would also validate important business values independently instead of relying only on visual similarity. The test method should match the actual rendering pipeline and the level of determinism available in the project.

**参考答案（中文）：** 我会在修改实现前建立有代表性的基准案例。在可行的情况下，使用稳定的测试数据生成输出，并通过合适的视觉或结构化比较进行检查，同时处理时间戳等动态字段。我还会独立验证重要业务数值，而不只是依赖视觉相似度。测试方式需要与项目真实的渲染链路及其确定性相匹配。

#### Q5. How would you design the module so a new report is faster to add?

**Question（中文）：** 如何设计模块，让新增报表的开发速度更快？

**Model answer (EN):** I would make the repeated work explicit and reusable while keeping report-specific business rules easy to locate. A new report should ideally be able to supply its configuration or compose existing building blocks without copying the entire rendering pipeline. I would also document the extension path and provide a representative example. I would avoid over-generalizing before there were enough real report variants to justify the abstraction.

**参考答案（中文）：** 我会把重复工作显式地提取为可复用能力，同时确保每种报表特有的业务规则仍然容易定位。理想情况下，新增报表只需要提供配置或组合现有构建块，而不必复制整条渲染流程。我也会记录扩展方式并提供有代表性的示例。但在没有足够真实报表类型支撑之前，我不会过度泛化设计。

#### Q6. Your CV says new-report development became 40% faster. What exactly became faster?

**Question（中文）：** 简历说新报表开发时间缩短 40%，具体是什么时间变快了？

**Model answer (EN):** I would define the measured unit—for example, engineering time from an agreed starting point to a report that meets acceptance criteria—and explain how the baseline was selected. I would compare similar report requests before and after the refactor, while noting differences in complexity and other changes that may affect the result. I would distinguish elapsed calendar time from hands-on engineering time. If the 40% was an approximate team-level estimate, I would say so instead of presenting it as a precise experiment.

**参考答案（中文）：** 我会先定义衡量单位，例如从约定的起点到报表满足验收标准所需的工程时间，并解释基准值如何确定。然后对比重构前后复杂度相近的报表需求，同时说明复杂度差异及其他可能影响结果的变化。我会区分日历耗时和实际工程投入时间。如果 40% 是团队层面的近似估算，我会如实说明，而不会把它包装成精确实验结果。

### 11.4 Manulife — AI-powered engineering tools and AI-assisted component-library quality

#### Q1. What did the AI tool do, and what part remained under human control?

**Question（中文）：** AI 工具具体做什么？哪些环节仍由人控制？

**Model answer (EN):** I would start from the actual workflow rather than describe the tool as a general-purpose AI agent. The tool was intended to accelerate development, support onboarding, and help business analysts understand historical business logic. I would describe one concrete input, the output it produced, and how a developer or analyst validated that output. Human review remained important because generated explanations or code can be incomplete, outdated, or confidently wrong.

**参考答案（中文）：** 我会从实际工作流程讲起，而不是笼统地把工具描述成通用 AI Agent。工具的目标是加速开发、帮助团队成员熟悉项目，并协助业务分析师理解历史业务逻辑。我会说明一个具体输入、工具生成的输出，以及开发人员或业务分析师如何验证结果。人工审核仍然重要，因为生成的解释或代码可能不完整、过时，甚至会以很肯定的语气给出错误结论。

#### Q2. How would you ground an AI explanation of historical business logic in reliable sources?

**Question（中文）：** 如何让 AI 对历史业务逻辑的解释有可靠依据，而不是凭空生成？

**Model answer (EN):** I would make the source material visible and traceable. Depending on the actual tool, that could mean retrieving relevant code, tests, documentation, or change history and showing the references used for an answer. I would ask the model to distinguish directly supported facts from inference and to say when evidence is insufficient. I would validate the approach against real questions from analysts and measure whether it reduces investigation effort without increasing incorrect conclusions.

**参考答案（中文）：** 我会让依据可见、可追溯。根据工具的真实实现，依据可以来自相关代码、测试、文档或变更历史，并在答案中展示所使用的引用。如果证据不足，应要求模型明确区分有直接依据的事实和推断，并承认无法确认的部分。我会使用业务分析师的真实问题验证方案，衡量它是否减少了调查成本，同时没有增加错误结论。

#### Q3. How would you evaluate whether an AI engineering tool actually improves productivity?

**Question（中文）：** 如何判断 AI 工程工具是否真的提升了效率？

**Model answer (EN):** I would define the task and baseline before measuring. Useful measures could include time to complete a representative task, time spent onboarding, review corrections, or the proportion of answers that require substantial rework. I would not use code volume as the main success metric. I would also sample output quality because a faster first draft is not a productivity gain if it creates more debugging or review work later. Any metric I report should match data the team actually collected.

**参考答案（中文）：** 我会先定义任务范围和基准，再进行衡量。可用指标可能包括完成代表性任务的时间、团队成员熟悉项目所需时间、评审修正量，或需要大量返工的回答比例。我不会把生成代码行数作为主要成功指标。还需要抽样评估输出质量，因为如果初稿更快但后续调试和评审成本更高，就不是真正的效率提升。最终报告的指标必须与团队实际收集的数据一致。

#### Q4. How would you protect proprietary code and sensitive business information when using an AI model?

**Question（中文）：** 使用 AI 模型时，如何保护专有代码和敏感业务信息？

**Model answer (EN):** I would first follow the company's approved tooling and data-handling requirements. Before sending context to a model, I would minimize the data to what the task requires and exclude secrets, credentials, personal data, and unrelated business information. I would verify the provider's data-retention and training terms through the approved security process rather than assume all tools have the same guarantees. Access control, logging, and review requirements should be part of the design, not added after deployment.

**参考答案（中文）：** 首先必须遵循公司的 AI 工具审批和数据处理要求。向模型提供上下文前，应尽量缩小到任务必需的范围，并排除密钥、凭据、个人数据和无关业务信息。模型供应商的数据保留和训练条款需要通过公司批准的安全流程核实，不能假设所有工具都提供相同保障。访问控制、日志和审核要求应从设计阶段就纳入，而不是上线后再补充。

#### Q5. How would you integrate AI-assisted review into a component library without making the pipeline unreliable?

**Question（中文）：** 如何把 AI 辅助评审集成到组件库中，同时避免流水线变得不可靠？

**Model answer (EN):** I would treat AI feedback as an additional signal, not as a replacement for deterministic checks or human review. Formatting, type checking, linting, tests, and build validation should remain the baseline wherever the repository supports them. AI review can focus on contextual concerns such as API consistency, accessibility risks, missing edge cases, or documentation gaps, but its output should be reviewable and tied to the changed code. I would also monitor false positives and avoid making an unreliable model response the sole release gate.

**参考答案（中文）：** 我会把 AI 反馈视为额外信号，而不是确定性检查或人工评审的替代品。在仓库支持的情况下，格式检查、类型检查、lint、测试和构建验证仍然是基础。AI 评审可以补充关注 API 一致性、无障碍风险、遗漏的边界情况或文档缺口，但输出必须可审核，并能对应到实际变更代码。我也会跟踪误报情况，避免让不稳定的模型响应成为唯一的发布门槛。

#### Q6. How would you keep AI-generated component-library advice aligned with the real codebase?

**Question（中文）：** 如何确保 AI 对组件库提出的建议与真实代码库保持一致？

**Model answer (EN):** I would provide the relevant source files, component conventions, and existing tests as context, and make the tool inspect the current implementation rather than rely only on generic prompts. I would prefer recommendations that cite the affected component or rule and explain the reasoning. The output should be checked against the actual API, design-system conventions, and supported React and TypeScript versions. If the model cannot find evidence in the repository, it should ask for clarification or mark the suggestion as uncertain.

**参考答案（中文）：** 我会把相关源码、组件约定和现有测试作为上下文，让工具检查当前实现，而不是只依赖通用提示词。我更倾向于要求建议指出受影响的组件或规则，并解释原因。生成结果还必须与真实 API、设计系统约定，以及项目支持的 React 和 TypeScript 版本核对。如果模型无法在仓库中找到依据，就应该请求澄清或标记不确定性。

#### Q7. What failure modes would you expect from AI-assisted code review, and how would you handle them?

**Question（中文）：** AI 辅助代码评审可能有哪些失败模式？如何处理？

**Model answer (EN):** Common failure modes include false positives, missed defects, outdated assumptions, duplicate comments, and suggestions that conflict with local conventions. I would calibrate the tool against a set of representative changes, collect reviewer feedback, and tune its scope and instructions. High-confidence deterministic findings should come from conventional tooling where possible. AI findings should be prioritized by severity and evidence, and developers should be able to reject them with a reason so the process does not become noisy or blindly trusted.

**参考答案（中文）：** 常见问题包括误报、漏报、基于过时假设、重复评论，以及与项目约定冲突的建议。我会用一组有代表性的代码变更校准工具，收集评审人员反馈，并调整检查范围和指令。能够通过传统工具可靠发现的问题，应优先交给确定性工具处理。AI 发现的问题需要按严重程度和证据排序，同时允许开发人员说明拒绝原因，避免流程变得嘈杂或被盲目信任。

#### Q8. How would you explain the business value of these AI tools to a skeptical engineering manager?

**Question（中文）：** 如果工程经理对 AI 工具持怀疑态度，你会如何解释其业务价值？

**Model answer (EN):** I would avoid selling AI as a goal in itself. I would select a repetitive, measurable workflow—such as locating relevant business logic or preparing a first-pass review—and compare the effort and quality before and after introducing the tool. I would include the cost of validation and maintenance, not just generation speed. If the tool does not improve the overall workflow or creates unacceptable risk, I would narrow its scope or stop using it. The value is better engineering outcomes, not simply using a model.

**参考答案（中文）：** 我不会把使用 AI 本身当成目标。我会选择一个重复且可衡量的流程，例如定位相关业务逻辑或进行第一轮代码评审，对比引入工具前后的投入和质量。衡量时还要包含验证和维护成本，而不只是生成速度。如果工具没有改善整体流程，或带来不可接受的风险，就应该缩小使用范围，必要时停止使用。真正的价值是改善工程结果，而不是单纯使用模型。

---

---

# Resume preparation notes and role-specific positioning

## 简历内容

- 参考截图图片 [德国简历模版](./germany-refer.png)
- [我的简历](./Aoda-Zhang-Full-stack-Software-Engineer.pdf)

## 简历制作注意点

- 布局尽量用一栏布局，多栏ATS不友好，解析会混乱
- 每个岗位都尽量选择调整简历内容，岗位的招聘title一定要在summary中包含
- 专业技能按照前后端分开去写
- 每个工作经历一定要量化，要带上具体使用的技术栈，和专业技能模块分开写
- 写在简历中的每段工作经历，都要详细，并且可以解释清楚

## 不同职位简历

### Frontend
Senior Front End Engineer
Front End Engineer with X years of experience and strong fundamentals in Front End technologies. Likes building scalable web infrastructure and making websites fast. Passionate about programming languages, compilers, and developer tooling.

Front End Engineer with six years of experience working in small and large teams to develop interactive, user-friendly, and feature-rich web applications. A self-motivated and lifelong learner familiar with modern web development and web3 technologies (blockchain, crypto, DeFi).

### Fullstack

Software Engineer with X years of full stack web development experience specializing in Ruby on Rails and PostgreSQL. Domain expert in e-commerce and payments field as a result of working at multiple e-commerce companies.

Senior Front End Engineer
Front End Engineer with X years of experience and strong fundamentals in Front End technologies. Likes building scalable web infrastructure and making websites fast. Passionate about programming languages, compilers, and developer tooling.

## 德国可英语工作的公司

https://docs.google.com/spreadsheets/d/1ugzubxiROOuLgzm-Vltl3CRNQNEVGtQ7IQzrNppyV1I/edit?gid=1178397007#gid=1178397007


## 找人看简历 adplist
## 真实面试练习 sesame
## cambly口语练习，注意找有HR经验的
## 模拟面试 pramp