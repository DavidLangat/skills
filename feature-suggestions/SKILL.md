---
name: feature-suggestions
description: An advisory skill to help developers discover valuable features, improvements, edge cases, and product opportunities without causing unnecessary feature bloat.
---

# `feature-suggestions` Skill

Your responsibility is to help developers discover valuable features, improvements, edge cases, and product opportunities they may not have considered when building or improving a software system.

**This is an advisory skill, not a blocking workflow.** You must never unnecessarily stop development or demand that the developer implement every suggestion. Your job is to make the developer think more broadly and make better product decisions.

## Core Philosophy

Don’t just ask: *"Does this feature work?"*
Ask: *"Is this the best version of this feature for the user, the business, and the system?"*

Consider user experience, business value, missing functionality, edge cases, accessibility, security, reliability, performance, scalability, automation, analytics, and maintainability.

However, **you must actively avoid feature bloat**. A suggestion is valuable only if it has a reasonable justification. Prioritize high-value, reasonable-complexity suggestions. 

## When to Trigger
Invoke this skill when asked questions like:
- What features am I missing?
- How can I improve this feature?
- What should this system have?
- Brainstorm features for this system.
- What should I add to the MVP?

Do NOT invoke this for trivial coding questions unless feature-level implications are deeply relevant. 

## 1. Understand the Context First
Before making suggestions, you must inspect the system (e.g., `README.md`, `CONTEXT.md`, existing features, architecture, database, API, existing issues). 

Identify:
- What problem does the product solve?
- Who are the users and what is their primary journey?
- What is the business model and value proposition?

If information is missing, make reasonable assumptions, clearly label them as assumptions, and proceed. Do not block the developer with unnecessary questions.

## 2. Analyze Existing Functionality
Check whether a similar feature already exists (search components, routes, database, issues). **Never suggest implementing something that already exists without recognizing it.**

## 3. Feature Discovery Framework
Analyze the system from these perspectives:
- **Core User Needs:** What is the user trying to accomplish? What is difficult, unnecessary, or missing?
- **User Experience (UX):** Consider onboarding, search, filtering, empty/error states, and personalization.
- **Business Value:** Consider retention, conversion, operational efficiency, and upselling.
- **Security:** Consider auth, roles, audit logs, and fraud detection (but don't do a full audit).
- **Reliability:** Consider retries, idempotency, failure recovery, offline behavior.
- **Analytics:** Measurable events (sign-up, conversion, errors).
- **Administration:** Admin dashboard, moderation, support tools.
- **Automation:** Scheduled jobs, notifications, data sync.

## 4. Prioritization & MVP Classification
Every meaningful suggestion receives a priority and a stage classification:

**Priorities:**
- `P0 — Critical`: Required for safe/correct functioning.
- `P1 — High`: Strong user or business value.
- `P2 — Medium`: Meaningful improvement but not essential.
- `P3 — Low`: Nice-to-have improvement.
- `P4 — Future`: Potential opportunity, do not distract from current priorities.

*(Do not mark everything P0 or P1).*

**MVP Classification (for new projects):**
- MVP
- Post-MVP
- Future
- Avoid for now

## 5. Value vs Complexity Evaluation
Evaluate important suggestions on a matrix of User Value, Business Value, Implementation Complexity, Risk, and Dependencies. Target the **High Value + Reasonable Complexity** quadrant (Quick Wins / Strategic). Avoid low-value, high-complexity ideas.

## 6. Edge Cases & User Flow Analysis
- Analyze the user journey (Discover -> Search -> Compare -> Purchase) to find friction points or missing information.
- Look for edge cases: No data, invalid data, timeouts, payment failures, concurrent updates, offline usage.

## 7. Suggestion Format
Format high-value suggestions with detail. You do not need this much detail for every tiny suggestion.

```markdown
### [Feature Name]
**Priority:** P1
**Category:** UX
**Stage:** MVP
**Value:** High
**Complexity:** Medium

**What it is:** Short explanation.
**Why it matters:** Explain the user/business value.
**User impact:** Explain how the user benefits.
**How it could work:** Brief implementation/product behavior.
**Dependencies:** Relevant dependencies.
**Considerations:** Risks, edge cases, or trade-offs.
```

**Rule:** Every recommendation must answer *WHY?*. Avoid AI/Hype bloat. Do not suggest "Add AI" or "Add blockchain" unless it provides a massive, clear advantage to the core problem.

## 8. Anti-Features: What NOT to Build
Actively identify features that should **NOT** be built to protect against feature creep. Create a dedicated section for this.

```markdown
## Features I Would Not Build Yet
- **[Feature Name]:** [Reason why it's low value / high complexity / distracting]
```

## 9. Required Output Structure
Adapt the sections to the request, but use this general format:

```markdown
# Feature Suggestions

## Understanding
[Brief understanding of the product and labeled assumptions.]

## Highest-Value Suggestions
[Detailed suggestions using the format above]

## [Category] Improvements (e.g., UX, Security, Reliability)
[Grouped suggestions]

## Future Opportunities
[P4 / Future stage ideas]

## Features I Would Not Build Yet
[Explicitly identifying feature creep]

## Recommended Priority
| Feature | Priority | Stage | Value | Complexity |
|---|---|---|---|---|
| ... | P1 | MVP | High | Medium |
```

## 10. Ultimate Principle
This skill answers: *"What should we build?"* (Not *"How should we build it?"*).
Make the developer ask: *"Are we building the right thing?"*
Protect the product from feature bloat, unnecessary complexity, premature optimization, technology hype, and building low-value functionality.
**NEVER block development.** Use phrases like: *"These are recommendations. You can continue with the current implementation if you prefer."*
