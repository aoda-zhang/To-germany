# BQ Story Bank — Five Stories Grounded in Aoda's Background

> **Purpose:** Prepare five flexible, truthful stories that can answer most behavioural interview questions for frontend-focused / frontend-heavy full-stack roles in Germany.
>
> **Source of truth:** `myCV.md`, `fullStack-CV.json`, and `topics/resume-walkthrough.md`. This file uses only experiences and outcomes already represented in those documents. Any detail marked **[CONFIRM]** must be replaced with what actually happened before using it in an interview. Do not memorise unverified implementation details.

## How to use this file

- Learn the five story arcs, not five scripts. Adapt the emphasis to the question.
- Use **I** for your own decisions and actions; use **we** only for team outcomes.
- Aim for 90–150 seconds: Situation (15s), Task (10s), Action (60–90s), Result (15s), Reflection (15s).
- The metric must keep its original meaning. For example, the PDF result is **new-report development time reduced by 40%** in the resume walkthrough, while the CV profile also says report delivery time fell by 60%. Verify the approved CV wording and measurement before quoting either number; do not combine them.
- Never invent conflict, failure, feedback, stakeholder reactions, measurement methods, or technical mechanisms. If asked for a story whose real details you cannot recall, say so honestly and explain how you would handle the situation.

## The five core stories

### Story 1 — Making design decisions consistent across five microfrontend services
**Employer:** Manulife  
**Best for:** initiative, ownership, influencing without authority, ambiguous tasks, quality, standards, explaining technical concepts, measurable improvement.

**Grounded situation:** Five microfrontend services had inconsistent styling. Your CV attributes a reduction in styling issues (at least 30% in the resume walkthrough; 40% in `myCV.md`) to implementing design tokens. **Resolve this metric discrepancy against your final CV before interviews.**

**Story spine (STAR + reflection):**
- **Situation:** As the services evolved, visual styling was not consistent across products.
- **Task:** Help establish a reusable way to keep design decisions consistent across independently maintained services.
- **Action:** Explain the actual token architecture you implemented, how consuming services used it, how you worked with other developers/designers, and what you personally owned. **[CONFIRM]** the exact token categories, package/distribution mechanism, enforcement rules, rollout sequence, and how teams agreed to adopt it; mention only what you really did.
- **Result:** State the verified reduction in styling issues and the scope of the five services. Explain the measurement source and comparison period if you know them.
- **Reflection:** Explain what you learned about adoption: a shared standard succeeds only when it is easy to consume, clearly documented, and supported by a practical migration path. Make this personal reflection your own.

**Questions this story can answer:**
- Tell me about a time you took initiative beyond your role.
- Tell me about a time you influenced people without formal authority.
- Tell me about a time you convinced others to change their approach.
- Describe a time you handled an ambiguous problem.
- Tell me about an improvement you are proud of.
- How have you improved code quality or consistency?
- How do you explain a technical concept to a non-technical stakeholder?
- Tell me about a time you had to balance consistency and team autonomy.
- What is an example of a decision with impact beyond your own feature?
- What would you do differently if you repeated the project?

**Likely follow-ups to prepare:** What was inconsistent? Why tokens rather than only shared CSS? What did you personally implement? How did the services consume tokens? How was adoption handled? How was the metric measured? What exceptions existed?

### Story 2 — Coordinating an Angular-to-React microfrontend migration
**Employer:** Newegg  
**Best for:** teamwork, leadership, complex problem, risk management, planning, disagreement, delivery under constraints, decision-making.

**Grounded situation:** You led an Angular-to-React microfrontend migration across three production teams, with zero production downtime.

**Story spine:**
- **Situation:** A migration had to happen in a live production environment while three teams were involved.
- **Task:** Lead the frontend migration while keeping production available and coordinating the work across teams.
- **Action:** Describe the actual migration boundaries, your personal technical responsibilities, how you aligned the teams, how dependencies and integration were handled, and how rollout risk was controlled. **[CONFIRM]** any specifics such as traffic percentages, kill switches, contract tests, monitoring thresholds, or rollback mechanics; use them only if they were genuinely part of the project.
- **Result:** The migration completed with zero production downtime across the three teams. Keep that claim precise: it does not automatically mean there were no defects or user-visible issues.
- **Reflection:** Discuss one real lesson about cross-team planning, integration, or observability. If earlier monitoring or clearer contracts really was a lesson, explain the actual example; otherwise use the lesson you genuinely took away.

**Questions this story can answer:**
- Tell me about the most challenging project you worked on.
- Tell me about a time you worked across teams.
- Tell me about a time you led without being a manager.
- Tell me about a difficult technical decision.
- Tell me about a time you managed risk.
- Tell me about a time you had to coordinate competing priorities.
- Tell me about a disagreement on technical direction.
- Tell me about a time you delivered a major change without disrupting users.
- How do you approach a migration from a legacy system?
- Tell me about a project that required careful planning.
- What was your role, and what did the other teams own?
- What would you change if you did it again?

**Likely follow-ups to prepare:** Why React? Why microfrontends? How did old and new implementations coexist? What was the boundary between teams? What did you personally decide? What did zero downtime mean and how was it verified? What risks did you identify?

### Story 3 — Refactoring the legacy PDF report module
**Employer:** Manulife  
**Best for:** ownership, technical debt, initiative, problem-solving, maintainability, delivering measurable value, taking on an unattractive task.

**Grounded situation:** Your CV describes refactoring a shared PDF report-generation module and reducing the time needed to develop new reports by 40%; `myCV.md` also uses a 60% report-delivery-time claim. Verify which statement and metric definition belong in the current CV before quoting a number.

**Story spine:**
- **Situation:** The existing report module made new report work slower than desired. Describe the real source of complexity rather than assuming it was synchronous generation, duplicated templates, or repeated data fetching.
- **Task:** Improve the module so new reports could be developed more efficiently.
- **Action:** Explain the exact legacy constraints, your investigation, the refactoring you personally performed, how you avoided breaking existing reports, and how you validated the output. **[CONFIRM]** the actual architecture and tests; do not claim asynchronous processing, a template engine, batching, or specific performance tests unless you implemented them.
- **Result:** State the verified improvement using the correct metric: development time for new reports, delivery lead time, or runtime performance are different things.
- **Reflection:** Explain what you learned about improving legacy code safely and how you would make the baseline and regression checks clearer next time.

**Questions this story can answer:**
- Tell me about a time you improved an existing system.
- Tell me about a time you took ownership of a difficult or neglected task.
- Tell me about a time you reduced technical debt.
- What project are you most proud of?
- Tell me about a time you improved developer productivity.
- Tell me about a time you had to understand unfamiliar code.
- How do you measure the impact of engineering work?
- Tell me about a time you made a system easier to maintain.
- How did you protect existing functionality during a refactor?
- Tell me about a time you delivered a measurable improvement.

**Likely follow-ups to prepare:** What made the old module difficult? Which parts did you change? How did you validate PDF correctness? What was the baseline for the metric? How did you handle regressions? What was your individual contribution?

### Story 4 — Building an attendance platform for 1,000+ employees
**Employer:** Hucai  
**Best for:** user empathy, adoption, stakeholder communication, product thinking, simplifying a workflow, practical impact, working with non-technical users.

**Grounded situation:** You built a React attendance platform for more than 1,000 employees, with an approximately 60% reduction in HR's manual workload.

**Story spine:**
- **Situation:** Attendance administration involved manual HR work.
- **Task:** Build a platform that supported the attendance workflow and reduced repetitive work.
- **Action:** Describe the real workflow, user needs you gathered, frontend features you implemented, how you handled usability and edge cases, and how you worked with HR or other stakeholders. **[CONFIRM]** the actual source of user feedback, adoption challenge, rollout, and any resistance; don't claim a difficult stakeholder conflict unless it happened.
- **Result:** The platform served 1,000+ employees and reduced HR manual workload by approximately 60%, according to your CV. Be ready to explain what work was counted and how the estimate was obtained.
- **Reflection:** Explain how this experience shaped your approach to user-centered engineering: the system is useful only if it fits the actual workflow.

**Questions this story can answer:**
- Tell me about a time you put users first.
- Tell me about a time you simplified a manual process.
- Tell me about a time you worked with non-technical stakeholders.
- Tell me about a product improvement with measurable impact.
- Tell me about a time requirements came from real users.
- Tell me about a time you had to balance usability and technical constraints.
- How do you know whether a feature is successful?
- Tell me about a time you translated a business need into a technical solution.
- What kind of impact do you want your work to have?

**Likely follow-ups to prepare:** Which workflow was automated? Which features did you personally build? How was the workload reduction estimated? What feedback changed the implementation? What was the hardest edge case? What evidence showed the platform was useful?

### Story 5 — Deliberately expanding from frontend into full-stack and AI-enabled engineering
**Employer:** Manulife  
**Best for:** learning quickly, growth mindset, adapting to change, self-awareness, career motivation, handling unfamiliar work, strengths and development areas.

**Grounded situation:** You have a frontend-heavy background and have expanded into Node.js backend work with Express.js/NestJS and MongoDB at Manulife. Your CV also describes building AI tooling that converts code into business documentation, improving documentation efficiency threefold.

**Story spine:**
- **Situation:** Your strongest foundation was frontend engineering, while your role and long-term direction called for broader end-to-end understanding.
- **Task:** Build credible full-stack capability while continuing to deliver useful engineering outcomes.
- **Action:** Explain one real example of learning or applying backend technology and, separately if appropriate, the AI documentation tool. Describe what you needed to learn, how you validated your understanding, where you asked for review, and what you personally implemented. **[CONFIRM]** the timeline, learning method, exact scope, AI model/tooling, safeguards, and the basis for the 3x metric.
- **Result:** You broadened your scope into backend work; the AI documentation tool is associated with a threefold improvement in documentation efficiency according to your CV.
- **Reflection:** Be precise about your current strengths and gaps. You can say that you are frontend-focused and growing your backend depth without pretending to be a specialist in every distributed-systems topic.

**Questions this story can answer:**
- Tell me about a time you learned something quickly.
- Tell me about a time you stepped outside your comfort zone.
- How have you changed as an engineer over the last few years?
- What is a professional weakness you are actively improving?
- Tell me about a time you adapted to a new technology.
- What motivates you to keep learning?
- Tell me about a time you used AI to improve a workflow.
- How do you validate AI-generated output?
- What would you like to improve next?
- Why are you moving toward full-stack work?
- How do you respond when you don't know something?

**Likely follow-ups to prepare:** What did you build yourself? What did you not own? How did you validate correctness? What was the learning curve? What exactly does 3x mean? What is still a gap in your knowledge?

## Expanded BQ question bank

Use the story map below to practise answering different questions with the same evidence, while avoiding repetition in a single interview.

| Behavioural dimension | Questions to practise | Best starting story |
|---|---|---|
| Initiative and ownership | Tell me about a time you took initiative. / Tell me about a time you owned a problem end to end. / Tell me about a time you went beyond your job description. | 1 or 3 |
| Influence and leadership | Tell me about a time you influenced a team without authority. / How did you get others to adopt your approach? / Tell me about a time you led a cross-team effort. | 1 or 2 |
| Teamwork and collaboration | Tell me about a time you collaborated across teams. / What role do you play in a team? / How did you coordinate work with dependencies? | 2 |
| Conflict and disagreement | Tell me about a technical disagreement. / Tell me about a time you challenged an approach. / What would you do if your lead disagreed with you? | 2; use only a real conflict |
| Mistakes and failure | Tell me about a mistake you made. / Tell me about a project that did not go as planned. / Tell me about a time you received critical feedback. | Choose a real incident; none is asserted by this document |
| Ambiguity and decision-making | Tell me about an ambiguous task. / How did you make a decision with incomplete information? / How do you choose between a refactor and a rewrite? | 1 or 3 |
| Pressure and prioritisation | Tell me about a time you handled competing priorities. / How do you respond to a tight deadline? / Tell me about a risk you had to manage. | 2 or 3, if the pressure is real |
| Quality and technical debt | Tell me about a time you improved maintainability. / How do you prevent regressions? / Tell me about a quality-versus-speed trade-off. | 3 or 2 |
| Customer and stakeholder focus | Tell me about a time you improved a user workflow. / How did you work with a non-technical stakeholder? / Tell me about a time user feedback changed your approach. | 4 |
| Learning and adaptability | Tell me about a time you learned a new skill. / Tell me about a time you adapted to change. / What are you currently working to improve? | 5 |
| Communication | Tell me about a time you explained something complex simply. / How do you communicate project risks? / Tell me about a time communication mattered to delivery. | 1, 2, or 4; use a specific real example |
| Impact and motivation | Which project are you proudest of? / What kind of work motivates you? / How do you measure engineering impact? | 3 or 4 |
| AI and engineering judgement | Tell me about a time you used AI at work. / How do you check AI-generated content? / When would you not use AI? | 5, limited to what you actually built |
| Self-awareness | What is your greatest strength? / What is a weakness you are addressing? / What feedback has changed how you work? | 5 for growth; use a real feedback example |
| Career direction | Why frontend-focused full-stack? / Where do you want to grow in the next three to five years? / Why this role? | 5, combined with role-specific motivation |

## Questions that need a separate, real incident

The five stories provide broad coverage, but they do **not** justify inventing an answer for every question. Prepare a sixth, short example only if you can recall a real event for:
- a mistake or failure and its actual impact;
- a missed deadline or a time you had to renegotiate scope;
- critical feedback you received and what changed afterward;
- a conflict with a coworker or manager;
- a miscommunication and the mechanism you introduced to prevent recurrence;
- an occasion when you had to say “I don't know”;
- a time you changed your mind after evidence or feedback.

A credible answer can be modest. Interviewers need to understand your judgement, accountability, and learning—not a dramatic failure.

## Personal fact-check checklist before memorising

- [ ] Confirm the design-token outcome metric and its denominator; `myCV.md` and the resume walkthrough currently use different percentages.
- [ ] Confirm whether the PDF outcome is a 40% reduction in new-report development time or a 60% reduction in report delivery time, and keep the definitions separate.
- [ ] Prepare one concrete example of your own actions in each story.
- [ ] Prepare the measurement method for every metric you quote.
- [ ] Add one truthful mistake/feedback/conflict example from your own memory.
- [ ] Remove every `[CONFIRM]` detail you cannot verify.
