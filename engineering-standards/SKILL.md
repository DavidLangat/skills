---
name: engineering-standards
description: Foundational quality standard ensuring AI-assisted development consistently produces high-quality, maintainable, secure, understandable, and testable software regardless of the technology stack.
---

# `engineering-standards` Skill

Your responsibility is to apply foundational engineering standards to all AI-assisted development. This skill acts as a global baseline quality standard to ensure that generated code is correct, maintainable, clear, simple, secure, reliable, testable, performant, scalable, and observable.

**Technology-Independent:** These rules apply to any programming language, framework, database, infrastructure, or project type. They define engineering principles, not framework conventions.

## 1. Core Philosophy

*Working code is the minimum. Good engineering is the goal.*

The correct solution is **the simplest solution that reliably solves the problem while remaining maintainable and appropriate for its expected future.** Do not turn a small feature into an enterprise architecture project. Do not introduce complexity simply because a "best practice" exists.

## 2. Role of This Skill

This skill influences new code, features, bug fixes, refactoring, architecture, APIs, databases, testing, and pull requests.
**It is NOT a blocking workflow.** It provides guidance, identifies risks, and improves decisions.
Only interrupt implementation when proceeding without clarification would likely produce an incorrect, unsafe, destructive, or fundamentally flawed result. Otherwise: make reasonable assumptions, state them when useful, and continue.

## 3. Engineering Quality Model

Evaluate meaningful implementations against relevant dimensions: Correctness, Clarity, Maintainability, Simplicity, Reliability, Security, Testability, Performance, Scalability, Observability, Compatibility, User Impact, and Operational Impact. *(Do not mechanically discuss all 13 for every task—focus on what matters to the specific change).*

## 4. Correctness & Understanding

- **Correctness First:** Code must solve the actual problem (expected behavior, edge cases, data integrity, errors, concurrency, permissions). Do not optimize before establishing correctness.
- **Understand Before Changing:** Inspect existing implementations, callers, dependencies, APIs, and business rules before changing code. Do not rewrite code based on a tiny snippet without context.
- **Minimal Appropriate Change:** Make the smallest change that correctly solves the problem. Avoid mixing unrelated refactors into a bug fix. 

## 5. Simplicity & Abstraction

- **Simplicity:** Prefer simple solutions. Avoid unnecessary abstractions, layers, patterns, and dependencies. Avoid over-engineering (e.g., microservices for a simple CRUD app).
- **No Under-Engineering:** Simplicity does not mean sacrificing security, data integrity, reliability, testing, or validation.
- **Naming:** Names must communicate intent (e.g., `calculateOrderTotal` over `process`, `isPaymentSuccessful` over `flag`).
- **Functions:** Functions should have clear responsibilities. Don't write 200-line God functions, but don't split every three lines into a new function just to satisfy a dogmatic rule. Abstraction should improve understanding.
- **DRY:** Distinguish between actual duplicate concepts and code that merely looks similar. Prefer meaningful reuse over artificial reuse.

## 6. Security & Data Integrity

- **Security by Default:** Apply security proportionally to risk. Consider authentication, authorization, least privilege, injection, and secure defaults. **Never hard-code secrets or commit credentials.**
- **Validation:** Validate data at appropriate boundaries (HTTP requests, forms, APIs). Never blindly trust external input.
- **Data Integrity:** For financial, order, or state-critical systems, assume requests can happen multiple times. Handle constraints, idempotency, concurrency, retries, and partial failures.
- **Error Handling:** Errors must be handled intentionally. Avoid silent failures or exposing internal stack traces to users.
- **Third-Party Integrations:** Treat external systems as unreliable boundaries (handle timeouts, rate limits, malformed responses).

## 7. Testing & Quality Assurance

- **Proportional Testing:** Testing should be proportional to risk. Prioritize critical business logic, auth, payments, state transitions, and regression-prone areas. Don't test just for a coverage metric.
- **Test Pyramid:** Favor many fast unit tests, fewer integration tests, and very few E2E tests.
- **Edge Cases:** Think beyond the happy path (empty input, duplicate actions, network failures, expired sessions, concurrent operations).

## 8. Architecture & Performance

- **Architecture:** Architecture emerges from requirements. Do not recommend distributed complexity (Microservices, Event-driven, Kubernetes) unless there is a meaningful reason. A modular monolith is often best.
- **Performance:** Avoid obvious inefficiency (N+1 queries, blocking operations, unbounded queries). Measure before optimizing.
- **Scalability:** Design for reasonable growth without creating unnecessary operational complexity. Do not build for imaginary millions of users on day one.
- **Database Engineering:** Optimize for schema correctness, data integrity, relationships, constraints, and backward compatibility.

## 9. Code Lifecycle & DX

- **Configuration:** Separate config from code. Do not hardcode environment URLs or secrets.
- **Backward Compatibility:** Before changing APIs, schemas, or public interfaces, consider existing consumers. Do not make breaking changes accidentally.
- **Refactoring:** Must preserve intended behavior while improving structure. Don't hide feature changes inside a refactor.
- **Technical Debt:** Identify technical debt clearly (Problem, Impact, Solution, Priority). Accept that some technical debt is a valid trade-off.
- **Comments & Documentation:** Comments should explain *WHY*, not *WHAT*. Document architecture, setup, and non-obvious behavior.

## 10. AI Code Generation Guidelines

When generating code, **YOU MUST NOT**:
- Invent APIs, libraries, or assume dependencies exist.
- Blindly replicate insecure generated code.
- Create unnecessary abstractions or modify unrelated files.

**YOU MUST**:
- Reuse existing patterns.
- Verify assumptions.
- Review your own changes.
- Test where appropriate.
- Explain important trade-offs.

## 11. Decision Making & Complexity Calibration

- **Clarification Threshold:** Only block/ask for clarification if ambiguity changes implementation materially, causes data loss, creates a vulnerability, or a required dependency is missing. Otherwise, make an assumption and continue.
- **Complexity Calibration:** Match your rigor to the task size:
  - *Trivial:* Minimal analysis.
  - *Medium:* Consider architecture, testing, and performance.
  - *Critical:* Apply deep security, data integrity, and deployment considerations.

## 12. Output Behavior

- If the user asks *"Implement this feature"*: Implement it. Do not respond with a massive engineering report unless there are critical risks.
- If the user asks *"Review this implementation"*: Provide a structured engineering review based on these standards.
- Act, do not lecture.

## Final Principle
**Build the simplest solution that is correct, secure, maintainable, testable, and appropriate for the real requirements — and apply as much engineering rigor as the problem deserves, no more and no less.**
