---
name: refactoring
description: Safely improve an existing codebase by making code easier to understand, maintain, and test without changing its externally observable behavior.
---

# `refactoring` Skill

Your responsibility is to safely improve an existing codebase by making the code easier to understand, maintain, and test without unnecessarily changing its behavior. 

This skill is completely standalone and usable independently.

## 1. Purpose

**Refactoring is defined as:**
A controlled change to the internal structure of existing code intended to improve its quality while preserving its externally observable behavior.

The most important rule is: **Change the implementation, not the behavior.**
A refactoring must not silently become a feature change, bug fix, architectural rewrite, or API change.

## 2. When to Use the Skill

Use this skill to:
- Clean up existing code and simplify complexity.
- Remove duplication and reduce unnecessary complexity.
- Improve maintainability, readability, structure, and naming.
- Break large functions/classes into smaller units.
- Improve testability, type safety, and module boundaries.
- Reduce coupling.
- Remove genuinely unused (dead) code.
- Modernize implementation patterns safely.

## 3. When NOT to Use It

Do not treat these as ordinary refactoring:
- Adding new functionality.
- Changing business requirements, rules, or API contracts.
- Changing database schemas, authentication, or authorization behavior.
- Rewriting the entire application or redesigning architecture without evidence.
- Introducing a new framework or upgrading dependencies unnecessarily.
- Fixing unrelated bugs.

*If requested work includes both refactoring and behavior changes, clearly separate the two.*

## 4. Required Refactoring Workflow

### Step 1 — Understand
Before changing code:
- Inspect relevant files, surrounding code, callers, and dependencies.
- Identify inputs, outputs, side effects, existing tests, and business rules.
- Identify public APIs and external integrations.
- *Do not refactor isolated code when surrounding context is necessary to understand its behavior.*

### Step 2 — Establish the Behavior Contract
Determine what must remain unchanged:
- Inputs, outputs, return types, exceptions, and error handling.
- Validation, database behavior, API requests/responses.
- Authentication, authorization, side effects, state changes, and ordering.
- *Treat existing behavior as intentional.* If behavior appears incorrect, do not silently fix it during refactoring.

### Step 3 — Identify Problems
Look for meaningful opportunities:
- Long functions, large classes, deep nesting, duplicate code.
- Complex conditionals, poor naming, magic numbers/strings, excessive parameters.
- Tight coupling, mixed responsibilities, God objects, dead code.
- *Do not refactor code merely because it is stylistically different.*

### Step 4 — Assess Risk
Assess risk based on the change, potential behavior impact, affected dependencies, and verification available:
- **Low risk:** Naming, formatting, straightforward extraction.
- **Medium risk:** Restructuring logic while preserving semantics.
- **High risk:** Changes involving state, concurrency, persistence, APIs, auth, or complex business logic.
- *Prefer low-risk incremental changes.*

### Step 5 — Choose the Smallest Useful Refactoring
Prefer targeted changes over rewrites:
- Extract Function/Method/Component/Class.
- Rename, Simplify Conditionals, Guard Clauses.
- Remove Duplication, Replace Magic Values.
- Separate Responsibilities, Improve Type Definitions.
- *Only introduce abstractions when they make the code genuinely easier to understand or maintain.*

### Step 6 — Make the Change
Apply the smallest change that produces a meaningful improvement.
Do not unnecessarily modify: APIs, signatures, database structures, business rules, config, or unrelated files.

### Step 7 — Verify
Verify the result using available tools (Unit/Integration/E2E tests, type checking, linting, manual comparison).
*If tests do not exist, perform the strongest reasonable verification available and explicitly state the limitation.*

## 5. Behavior Preservation Rules

Protected by default:
- **Inputs & Outputs:** Should remain compatible.
- **Errors:** Do not silently change types, conditions, responses, or validation behavior.
- **Side Effects:** Preserve DB writes, API calls, events, file operations, state changes.
- **APIs & Business Logic:** Do not modify unless explicitly requested.

## 6. Distinguishing Workflows

- **Refactoring vs Bug Fix:** If you discover a bug, do not automatically fix it. Report it: *"Potential bug discovered: [description]. Why it is outside scope: [reason]. Recommended follow-up: [separate fix]"*. If asked to fix it, treat it as a separate task.
- **Refactoring vs Feature Development:** Separate the work into 1) Refactoring, 2) Feature implementation. Do not hide features inside refactoring.

## 7. Code Quality Principles
Optimize for Clarity, Simplicity, Cohesion, Separation of Concerns, Low Duplication, Appropriate Abstraction, Maintainability, and Testability.

## 8. Important Anti-Patterns to Avoid
- **Refactoring for the sake of refactoring:** Don't change code just because it is old.
- **Over-abstraction:** Don't create `Interface -> AbstractFactory -> Provider -> Manager -> Service` when a simple function suffices.
- **Rewrite disguised as refactoring:** Don't replace working subsystems for preference.
- **Scope creep / Style wars / Unverified deletion:** Do not modify unrelated code, change purely for style, or delete code without verifying usage.

## 9. Refactoring Decision Framework
For every proposed refactoring, ask:
1. Does this improve the code? AND
2. Can the existing behavior be preserved? AND
3. Is the change worth the risk? AND
4. Can the result be verified?
*If the answer is no, reconsider the change.*

## 10. Expected Output
When performing a refactoring, provide a concise summary containing:
- **What Changed:** Structural improvements.
- **Why:** The problem addressed.
- **Behavior Preserved:** What was intentionally kept unchanged.
- **Verification:** Tests/checks performed.
- **Risks:** Remaining uncertainty.
- **Follow-ups:** Improvements deliberately left out of scope.
*(Do not overwhelm the user with unnecessary explanations).*

## Final Principle

**Refactor deliberately. Improve the structure. Preserve the behavior. Make the smallest safe change that leaves the code meaningfully better.**
