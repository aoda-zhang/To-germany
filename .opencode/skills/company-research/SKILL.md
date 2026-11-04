---
name: company-research
description: Research a company relevant to Aoda's Germany software-engineering job search, assess its business and engineering context, verify working-language and hiring signals, and prepare targeted application and interview questions.
compatibility: opencode
metadata:
  domain: germany-job-search
  language: zh-CN
---

# Company Research

## Purpose

When the user names a company, shares a company website or job link, or asks whether an employer is worth applying to, produce a concise, evidence-based company briefing in Chinese. The goal is to help Aoda decide whether to apply, tailor the CV, and prepare for recruiter or technical interviews.

This skill complements `jd-summary`:

- `jd-summary` analyzes a specific vacancy and its requirements.
- `company-research` analyzes the employer and its broader business, product, engineering, hiring, and workplace context.
- If both a company and a specific JD are supplied, use both perspectives and avoid repeating the same analysis.

Do not produce a generic company profile. Focus on what matters to a frontend-focused full-stack engineer seeking work in Germany.

## When to use

Use this skill when the user:

- Provides a company name, company website, careers page, or company profile.
- Asks what a company does, what its products are, or whether it is worth applying to.
- Wants to understand the company's engineering organization, technology environment, or working language.
- Is preparing for a recruiter call, interview, or networking conversation with the company.

## Required candidate context

Use the repository's current candidate materials when available:

- `fullStack-CV.json` — source of truth for experience, skills, dates, job titles, achievements, and language information.
- `resume-and-projects.md` — deeper project and technical context.
- `Aoda-Zhang-Full-stack-Software-Engineer.pdf` — rendered CV, when presentation or exact visible wording matters.

Default candidate positioning:

- 9+ years of software engineering experience.
- Frontend-focused full-stack engineer.
- Strongest professional evidence: React, TypeScript, JavaScript, frontend architecture, microfrontends, design systems, and complex enterprise UI.
- Backend experience: Node.js, Express.js, NestJS, and MongoDB; do not position Aoda as a backend specialist without direct supporting evidence.
- Relevant domains include financial services, e-commerce, enterprise platforms, and developer tooling.
- Germany target: frontend engineering or frontend-heavy full-stack roles.

Do not infer German or English proficiency unless explicitly documented in the CV or confirmed by the user. Do not expose private CV details that are irrelevant to the company assessment.

If the repository files are unavailable, use only the context the user has supplied and state the limitation. Do not ask the user to repeat information already available.

## Research principles

### 1. Identify the correct company

- Confirm the legal or commonly used company name, official domain, headquarters, and relevant German office/entity when possible.
- Distinguish a parent company, subsidiary, product brand, staffing agency, consultancy, and end client.
- If multiple companies share a name, use the supplied JD, URL, location, and industry to disambiguate. Ask one concise question only when identity cannot be resolved.
- Treat company-provided statements as company claims, not independent verification.

### 2. Use current, traceable sources

Prioritize sources in this order:

1. Official company website: About, Products, Customers, Locations, Careers, Engineering/Tech Blog.
2. Official job postings and official company LinkedIn page.
3. Official press releases, annual reports, investor relations, regulatory filings, and reputable public registries.
4. Reputable business and technology publications.
5. Employee-review platforms and community discussions as anecdotal signals only.

Use current sources for changing facts such as headcount, office locations, open roles, funding, financial performance, leadership, and hiring status. Include source links and publication/update dates where available.

Do not claim to have inspected a source that was not accessible. If the user provides a URL, inspect that URL first when browsing is available. If browsing is unavailable, state that the research is limited and identify what remains unverified.

For important conclusions, seek corroboration from more than one independent source. Prefer primary sources for factual company information and use independent sources to add context.

### 3. Separate facts, interpretation, and unknowns

Label conclusions clearly:

- **Verified fact** — directly supported by an accessible source.
- **Reasonable interpretation** — an evidence-based reading of multiple facts; explain the reasoning.
- **Unknown / needs confirmation** — not established by available sources.

Never invent company size, revenue, funding, customers, engineering headcount, technology stack, salary bands, hiring plans, office policy, or team language.

Do not treat a technology appearing in a job ad as proof that every engineering team at the company uses it. Distinguish company-wide technology signals from role-specific requirements.

### 4. Research the employer's business

Explain in plain Chinese:

- What the company sells or provides.
- Who its customers/users are (B2B, B2C, B2G, or mixed).
- Its main products, services, and revenue/business model, where verifiable.
- Its industry and market position, without unsupported superlatives.
- Whether the German operation appears to be headquarters, a major engineering/product hub, a sales office, or a local branch.

Explain enough business context for Aoda to understand what the company actually builds and why the role may exist.

### 5. Research engineering and technology context

Look for evidence about:

- Engineering/product organization and known German engineering locations.
- Public engineering blog posts, open-source repositories, technical talks, and architecture articles.
- Technologies explicitly associated with the company, separating:
  - **Company-level evidence** — public engineering materials or multiple role postings.
  - **Role-specific evidence** — a technology listed only in the supplied vacancy.
  - **Unverified signals** — third-party or weak evidence.
- Product engineering versus consulting/client delivery, maintenance, implementation, or internal IT.
- Engineering practices when publicly evidenced: platform engineering, microservices, cloud, CI/CD, testing, design systems, accessibility, performance, security, and developer experience.

Do not guess the internal stack from a company's industry or website. If no reliable public engineering information exists, say so.

### 6. Assess language and workplace signals for Germany

This is a priority for Aoda. Investigate separately:

- Corporate language or official language policy, if stated.
- Engineering team's likely working language.
- Language used for customer-facing work, sales, support, and local stakeholders.
- German-language requirements across relevant job postings.
- Whether the company appears international or primarily German-speaking, based on evidence rather than stereotypes.

Classify the evidence as:

- **Explicitly English-speaking** — the company or relevant team clearly states English is the working language.
- **English likely, not confirmed** — several credible signals suggest English may be used, but no explicit confirmation.
- **German required for relevant work** — official role/company evidence states German is mandatory or shows a clear operational need.
- **Mixed / team-dependent** — language appears to vary by team, customer, or location.
- **Unknown** — evidence is insufficient.

Never infer that German is unnecessary merely because the careers page or JD is in English. Never infer that German is mandatory merely because the company is based in Germany.

If a specific JD is supplied, use its exact language wording and reconcile it with company-level signals. Company-wide evidence does not override a role-specific requirement.

### 7. Evaluate relevance to Aoda's profile

Assess the company and any supplied role against Aoda's actual experience:

- **Strong alignment:** direct overlap with React/TypeScript, frontend platform/architecture, microfrontends, design systems, enterprise UI, or relevant domain experience.
- **Potential alignment:** transferable experience, but role/team details need confirmation.
- **Weak alignment:** role appears predominantly backend, infrastructure, data science, mobile, or another area without sufficient CV evidence.

Consider whether the company is likely to offer:
- Product engineering ownership versus short-term client delivery.
- Complex frontend challenges and architecture opportunities.
- A mature engineering environment and cross-functional collaboration.
- An English-capable team in Germany.

Do not assume a company has these qualities without evidence. Mark them unknown when necessary.

### 8. Identify hiring and employment signals

When reliable information is available, summarize:

- Current relevant vacancies and official careers page.
- Hiring location and onsite/hybrid/remote policy.
- Employment type and contract context.
- Publicly disclosed compensation range or benefits, if any.
- Company growth, restructuring, layoffs, financial pressure, or hiring freezes only when supported by credible, dated sources.
- Employee-review themes only when multiple reviews show a recurring pattern; identify the platform, date range, and limitations.

Avoid presenting anonymous reviews as established facts. Do not give a definitive culture verdict from a handful of reviews.

### 9. Prepare application and interview strategy

Provide practical next steps:

- Whether the company is worth prioritizing for Aoda.
- Which part of Aoda's experience should be emphasized for this employer.
- Which existing CV bullets or projects are most relevant; suggest targeted English wording only when supported by the CV.
- What to learn about the company's product/domain before an interview.
- Three to five thoughtful questions for a recruiter or engineering interviewer.

Questions should resolve real unknowns, for example:
- What is the day-to-day working language in this specific engineering team?
- Is German needed from the first day, and for which interactions?
- Is the German office a product/engineering hub or mainly a customer-facing location?
- How is the team split between frontend and backend, and who owns frontend architecture?
- Is the role focused on a core product or on projects for external clients?

Do not ask questions whose answers are already explicit in the JD or official materials.

## Required response format

Keep the briefing decision-oriented. Expand only when the company is complex or the user asks for deeper research.

# 1. 公司是什么

- **公司：** name, official website, headquarters, relevant German location.
- **一句话介绍：** what it does.
- **业务模式：** products/services, customer type, business model.
- **行业与规模：** only verified information; state the date and source.

# 2. 产品与业务

- Main products/services and target customers.
- What the company builds or delivers in Germany.
- Why this business context matters to the role.

# 3. 技术与工程环境

- Company-level technology signals.
- Relevant engineering locations and public technical evidence.
- Product engineering vs. consulting/client delivery.
- Unknowns that should not be assumed.

# 4. 语言与工作环境（重点）

| Dimension | Finding | Evidence / confidence |
|---|---|---|
| Company language | ... | ... |
| Engineering working language | ... | ... |
| German requirement | Explicitly English-speaking / English likely / German required / Mixed / Unknown | ... |
| Customer-facing language | ... | ... |
| Work model | ... | ... |

State clearly what this means for Aoda's application. Do not equate an English JD with an English-speaking team.

# 5. 与我的背景匹配度

- **匹配方向：** frontend / frontend-heavy full-stack / other.
- **Relevant experience:** cite specific CV evidence.
- **Potential gaps:** only evidence-based.
- **Overall:** High priority / Worth exploring / Low priority, with reasons.

# 6. 求职与面试建议

- Official careers page and relevant vacancy links.
- What to emphasize in the CV.
- What to understand before interview.
- Three to five high-value questions for HR or the engineering team.

# 7. Sources and confidence

List the most useful sources with:
- Page/article title.
- Publisher.
- Link.
- Publication or access date when available.
- What claim it supports.

Call out material facts that remain unverified.

## Quality checks

Before responding, verify:

- Is this the correct company and German entity/location?
- Are business claims based on sources rather than assumptions?
- Did I distinguish company-wide technology from role-specific technology?
- Did I assess engineering language separately from customer-facing language?
- Did I avoid treating an English JD as proof that German is unnecessary?
- Did I distinguish verified facts, interpretation, and unknowns?
- Are company size, hiring, salary, and culture claims dated and sourced?
- Is the relevance assessment grounded in Aoda's actual CV?
- Are recommendations useful for a Germany-based frontend-focused full-stack job search?
- Did I provide source links and avoid unsupported certainty?
