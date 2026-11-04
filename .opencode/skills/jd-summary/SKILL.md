---
name: jd-summary
description: Analyze a Germany-focused software engineering job description, explain the role and working-language requirements, extract its technical stack and keywords, and recommend evidence-based CV tailoring using the repository's CV source.
compatibility: opencode
metadata:
  domain: germany-job-search
  language: zh-CN
---

# JD Summary

## Purpose

When the user provides a job description (JD), analyze it against Aoda's current CV and return a practical application assessment in Chinese. The analysis must help answer:

1. What is this job actually responsible for, and what seniority/profile is the employer seeking?
2. What language is used in the hiring process and daily work? Is German required, preferred, optional, or not mentioned?
3. Which technical skills and domain keywords matter most?
4. How closely does the role match Aoda's actual experience?
5. Which specific CV sections and bullets should be optimized for this role?

Do not merely translate or paraphrase the JD. Interpret the hiring signals and make a recommendation.

## When to use

Use this skill whenever the user pastes, uploads, links, or asks to evaluate a job description, job advertisement, vacancy, or role. It is especially intended for software engineering jobs in Germany.

## Required repository context

Before analyzing, read the current source files from the repository root:

- `fullStack-CV.json` — primary structured source of truth for experience, dates, job titles, responsibilities, achievements, metrics, education, and skills.
- `Aoda-Zhang-Full-stack-Software-Engineer.pdf` — rendered CV; inspect it when layout, wording, ordering, or the visible one/two-page presentation matters.
- `resume-and-projects.md` — detailed project and experience context; use it to understand evidence behind CV bullets and avoid shallow keyword matching.

If a file is unavailable, say so and continue only with available evidence. Do not ask the user to paste CV details already present in these files. If the skill is run outside this repository and the files are unavailable, ask the user to provide the CV or relevant content.

Treat the CV and project guide as factual constraints. Never invent skills, responsibilities, years of experience, language proficiency, certifications, business impact, or metrics. If a detail is uncertain or inconsistent, flag it as `需要确认` instead of silently resolving it.

## Candidate positioning

Use this positioning as the default lens, while allowing the JD to change the emphasis:

- 9+ years of software engineering experience.
- Frontend-focused full-stack engineer; strongest evidence is React, TypeScript, JavaScript, frontend architecture, and complex enterprise UI.
- Current Manulife experience: React/TypeScript, Express.js, NestJS, MongoDB; design-token standardization across five microfrontend services; legacy PDF report module refactoring; component-library architecture; financial-services product work; AI-powered developer/productivity tools.
- Newegg experience: Angular-to-React microfrontend migration, React/TypeScript/Redux, React Native seller features, e-commerce marketplace workflows.
- Hucai experience: Vue/React frontend, e-commerce cart and inventory workflows, and an employee attendance platform.
- Backend experience exists, especially Node.js, Express.js, NestJS, and MongoDB, but do not position the candidate as a backend-specialist unless the supplied evidence supports it.
- PawHaven may be used as a personal/open-source project only when relevant and when its details are available in the repository/CV context. Do not present it as commercial employment.

Do not infer German proficiency or English proficiency from nationality, location, or the fact that the CV is in English. Report language levels only when explicitly documented by the CV or user.

## Analysis workflow

### 1. Understand and classify the role

Extract and explain:

- Original job title and a natural Chinese interpretation.
- Company, industry, product/domain, location, work model (onsite/hybrid/remote), and employment type when stated.
- Actual role type: frontend, frontend-heavy full-stack, balanced full-stack, backend, mobile, platform, or another category.
- Expected seniority and ownership: individual contributor/lead, architecture, mentoring, delivery ownership, stakeholder collaboration.
- Main business purpose of the role in plain Chinese.
- The 3–6 most important responsibilities, ranked by importance.

Distinguish explicit requirements from reasonable interpretation. Do not infer a technology or responsibility merely because it is common in the industry.

### 2. Determine language requirements precisely

This is a high-priority section for Germany applications. Separate the following instead of reducing everything to “English/German required”:

- **Application/interview language:** what the JD says about interviews, applications, or communication.
- **Daily working language:** the language used by the engineering team and internal collaboration.
- **Business/customer language:** whether the role deals with German-speaking customers, authorities, suppliers, or local stakeholders.
- **Required German level:** quote the exact stated level (A1/A2/B1/B2/C1/native/fluent) when present.
- **English requirement:** quote the stated level or wording when present.

Classify German as exactly one of:

- **Required** — explicit mandatory wording such as “German is required”, “fluent German”, “C1 German”, or equivalent.
- **Preferred** — wording such as “German is a plus”, “preferred”, “ideally”, or “nice to have”.
- **Not required / English-speaking environment** — explicit statement that English is the working language or German is not required.
- **Not mentioned / unclear** — no reliable statement. Do not interpret silence as “German not required”.

Give the evidence: quote the shortest relevant JD phrase and explain its practical meaning. If a level is given, distinguish a hard minimum from a preferred level. If the JD contains conflicting signals (for example, English-speaking team but German customer communication), explain the conflict.

Also give a **language risk assessment** for Aoda based only on documented information. If the candidate's German level is not recorded, say “CV未提供德语水平，无法判断是否达到要求” rather than guessing. Recommend asking the recruiter when the JD is ambiguous.

### 3. Extract technical stack and ATS keywords

Group keywords instead of returning one undifferentiated list:

- Core languages
- Frontend frameworks and UI
- State management and data fetching
- Backend, APIs, and runtime
- Databases and data
- Cloud, DevOps, CI/CD, and infrastructure
- Testing and quality
- Architecture and engineering practices
- Domain/business knowledge
- Collaboration, delivery, and leadership

For each keyword, label it:

- **Must-have** — explicitly required or repeatedly emphasized.
- **Preferred** — desirable or listed as a plus.
- **Contextual** — appears in responsibilities or domain context but is not a hard requirement.

Preserve the original English keywords so the user can reuse them in an English CV and ATS. Normalize obvious synonyms only when useful; do not add technologies that are absent from the JD.

### 4. Compare JD with Aoda's CV

Build a requirement-to-evidence comparison. For each major requirement, classify:

- **Strong match** — direct, explicit evidence in the CV.
- **Partial match** — adjacent experience or transferable skills, but the exact requirement is not evidenced.
- **Gap** — no evidence in the current CV.
- **Unclear** — insufficient information; ask the user only if it materially affects the recommendation.

Cite the matching employer/project and actual CV evidence in concise language. Do not mark a skill as a match merely because it is a familiar technology. Separate “used professionally”, “used in a personal project”, and “not evidenced”.

Summarize the overall fit as one of:

- Strong match
- Reasonable match
- Stretch role
- Weak match

Explain the top 2–3 reasons. This is a qualitative assessment, not a fabricated percentage score.

### 5. Recommend targeted CV optimization

Give a short, prioritized edit plan, not generic resume advice. Address only changes that improve alignment with this JD:

1. **Headline / professional summary** — whether to emphasize frontend-focused full-stack, frontend architecture, React/TypeScript, Node.js, financial services, e-commerce, or another evidenced strength.
2. **Skills section** — which existing skills to move forward, group, or de-emphasize. Never add a keyword unless supported by the CV or confirmed by the user.
3. **Experience bullets** — identify the exact company/bullet to revise, why it matters for the JD, and provide a suggested English rewrite.
4. **Project selection/order** — recommend which existing experience or project should receive more space or appear earlier.
5. **Gaps** — identify requirements that cannot honestly be fixed by wording. Suggest a learning or interview-preparation action only when useful.

For every suggested English bullet:
- Keep the underlying facts and scope unchanged.
- Preserve existing metrics exactly unless the source files explicitly resolve a discrepancy.
- Use the JD's wording naturally where it accurately describes the work.
- Do not claim hands-on experience with a tool or framework merely because the JD asks for it.
- If a metric, ownership level, or implementation detail needs verification, mark it `[需要确认]` and provide a safer alternative.

Do not rewrite the entire CV unless the user explicitly asks. Do not modify repository files or the CV automatically; provide recommendations and drafts in the response first.

### 6. Give an application recommendation

End with a direct decision:

- **建议投递** / **可以尝试，但需针对性调整** / **优先级较低**.
- Explain the decisive factors, especially German-language barriers and must-have technical gaps.
- List up to three questions to clarify with the recruiter when the JD leaves important details unanswered (for example, actual team working language, whether German is needed from day one, and whether a listed technology is mandatory).

## Required response format

Use this structure and keep it concise enough to scan. Expand only where the JD is complex.

# 1. 岗位是什么
- **职位：** original title + Chinese interpretation
- **岗位类型：** frontend / frontend-heavy full-stack / balanced full-stack / backend / other
- **级别：** ...
- **业务与团队：** ...
- **核心职责：** ranked list

# 2. 语言要求（重点）
- **英语：** ...
- **德语：** Required / Preferred / Not required / Not mentioned or unclear
- **证据：** exact JD wording + interpretation
- **对我的影响：** ...
- **需要向 HR 确认：** ... (only if needed)

# 3. 技术栈与关键词
Organize Must-have / Preferred / Contextual and group by technical area. Preserve English terms.

# 4. 与我的 CV 匹配度
A compact table: JD requirement | CV evidence | Match (Strong / Partial / Gap / Unclear).

Then state the qualitative overall fit and reasons.

# 5. CV 优化建议
Prioritized table: Priority | CV location / current experience | Recommended change | Suggested English wording.
Only include changes that are relevant and supported by evidence.

# 6. 投递建议
Give one clear recommendation and up to three recruiter questions if necessary.

## Quality checks

Before responding, verify:

- Did I distinguish “German required” from “German preferred” and “not mentioned”?
- Did I quote evidence for the language classification?
- Did I identify the real role type rather than repeat the job title?
- Are the technical keywords grouped and prioritized?
- Does every claimed CV match have actual evidence?
- Are CV edits specific to this JD and factually safe?
- Did I preserve the candidate's frontend-focused full-stack positioning instead of overstating backend depth?
- Did I avoid inventing language levels, skills, tools, responsibilities, and metrics?
- Is the final application recommendation clear?
