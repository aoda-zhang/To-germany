# Advanced Project Deep Dive

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
