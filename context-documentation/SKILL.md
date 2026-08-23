---
name: context-documentation
description: Generates and maintains a high-quality, structured CONTEXT.md file for software projects. This file serves as an engineering map of the system designed to help developers and AI agents understand the codebase quickly and safely.
---

# `context-documentation` Skill

Your responsibility is to create and maintain a high-quality `CONTEXT.md` file for software projects.

The purpose of `CONTEXT.md` is to give an AI coding agent (and human developers) a fast, accurate, structured understanding of a project before it modifies or extends the codebase. It functions as an engineering context document, not as a replacement for the `README.md`.

## Core Objective

You will be invoked to either:
1. Create `CONTEXT.md` for a project.
2. Update an existing `CONTEXT.md` based on the current codebase.

You must inspect the actual project and produce a `CONTEXT.md` that explains:
- What the system is and why it exists.
- Who uses it (Users & Actors).
- How it is structured.
- How the major components interact.
- Where important business logic lives.
- How data flows through the system.
- How authentication and authorization work.
- How external services are integrated.
- How the application is run, tested, and deployed.
- Important engineering decisions, conventions, known technical debt, and constraints.
- Crucial safe change guidelines for AI agents.

**CRITICAL RULE:** The document must be based on the ACTUAL repository. Never invent architecture, features, dependencies, APIs, or infrastructure.

## Repository Inspection

Before creating or updating `CONTEXT.md`, you MUST inspect the project. Start with high-value sources based on the technology stack:
- `README.md`
- Dependency manifests (`package.json`, `pom.xml`, `build.gradle`, `requirements.txt`, `pyproject.toml`, `composer.json`, `go.mod`, `Cargo.toml`, etc.)
- Configuration files, environment examples, and database configurations.
- Containerization/Deployment files (`Dockerfile`, `docker-compose.yml`, CI/CD config).
- Main application entry points, routing, and configuration.
- Source code in key structural directories.

Adapt your inspection to the specific technology used (e.g., Spring Boot, React, Node.js, Python, Laravel, Go, etc.). Do not blindly read every file; inspect relevant files.

## Document Structure & Generation

Generate a structured document using the following layout. **Do not force sections that are irrelevant to the project.** If a section does not apply, omit it or explicitly state that it is not applicable if that distinction is useful.

Include freshness metadata at the very top of the generated file:
```yaml
---
project: <project-name>
context_version: 1.0
last_updated: YYYY-MM-DD
generated_by: context-documentation
---
```

Use the current date and detected project information.

### General Structure:
```markdown
# Project Context
## 1. Project Overview
## 2. Purpose
## 3. Users & Actors
## 4. Core Features
## 5. System Architecture
## 6. Project Structure
## 7. Application Flow
## 8. Data Flow
## 9. Authentication & Authorization
## 10. Database & Data Model
## 11. APIs & Integrations
## 12. Important Business Logic
## 13. Key Components
## 14. Configuration & Environment
## 15. Development Workflow
## 16. Testing
## 17. Deployment
## 18. Engineering Conventions
## 19. Important Constraints
## 20. Known Technical Debt
## 21. Important Decisions
## 22. Common Pitfalls
## 23. Safe Change Guidelines
## 24. AI Development Guidance
## 25. Context Maintenance
```

### Content Guidelines for Sections:

- **1. Project Overview & 2. Purpose:** Keep it concise. Detail project name, type, primary purpose, current state, and major architectural style/technologies.
- **3. Users & Actors:** Identify actual actors (e.g., Customer, Admin, Background Worker) and their capabilities. Do not invent actors.
- **4. Core Features:** Describe major capabilities affecting architecture and business logic.
- **5. System Architecture:** Explain major layers (Frontend, Backend, Database, Workers). Include a Mermaid diagram (`flowchart TD`) if appropriate and accurate.
- **6. Project Structure:** Explain important directories and *why* they exist. Do NOT list every file.
- **7. Application Flow & 8. Data Flow:** Explain major flows (e.g., User registration, core data movement, event queues). Prioritize authentication, major workflows, payments, and integrations.
- **9. Authentication & Authorization:** Document the actual mechanism, where it is enforced, roles, permissions, and protected routes. **NEVER expose secrets.** Use variable names (e.g., `JWT_SECRET`).
- **10. Database & Data Model:** Document technology, important entities, relationships, constraints, and data ownership. Use a Mermaid ER diagram when useful, but do not duplicate the entire schema.
- **11. APIs & Integrations:** Document important internal/external APIs, why they exist, where they are implemented, and failure considerations.
- **12. Important Business Logic:** Identify where crucial business rules (pricing, permissions, state transitions) live and their dependencies.
- **13. Key Components:** Identify only the most important modules/classes/services, their location, and responsibility.
- **14. Configuration & Environment:** Document required env vars, config files, and feature flags. **NEVER include secret values.**
- **15. Development Workflow & 16. Testing:** Detail verifiable commands for development and testing (e.g., `npm run dev`, `pytest`). Document testing frameworks and limitations.
- **17. Deployment:** Document the actual deployment architecture (Build -> CI -> Artifact -> Deployment). If unknown or not configured, state that clearly.
- **18. Engineering Conventions:** Identify ACTUAL conventions used (naming, error handling, state management). Do not impose new conventions here.
- **19. Important Constraints:** Document verified limitations (performance, DB, external APIs).
- **20. Known Technical Debt:** Identify known problems (duplicated logic, missing tests). Distinguish verified debt from potential concerns.
- **21. Important Decisions:** Document architectural decisions affecting future development.
- **22. Common Pitfalls:** (Extremely important) Document mistakes a developer/AI could easily make that silently break the system.
- **23. Safe Change Guidelines:** Provide practical guidelines on how an AI should safely modify the project (e.g., inspect existing implementation, search usages, verify contracts, run tests).
- **24. AI Development Guidance:** Explicitly state that `CONTEXT.md` is a guide, not absolute truth, and the source code is the final authority. Advise reading `CONTEXT.md`, preserving existing behavior, and updating `CONTEXT.md` when architecture changes.
- **25. Context Maintenance:** Explain when `CONTEXT.md` should be updated (e.g., architecture changes, new features) and when it should NOT be updated (e.g., simple bug fixes, trivial refactoring).

## Confidence & Unknown Information
Distinguish between Confirmed, Inferred, and Unknown information. If something cannot be determined, explicitly state it as unknown (e.g., `> **Unknown:** Deployment infrastructure could not be determined.`). Never invent missing information.

## Updating an Existing `CONTEXT.md`
If `CONTEXT.md` already exists, DO NOT blindly overwrite it.
1. Read the existing document.
2. Inspect the current codebase.
3. Compare documented architecture with reality.
4. Preserve still-valid information.
5. Update changed sections, remove obsolete information, and add newly discovered important details.
Synchronize context with reality while keeping the document concise.

## Quality & Size Guidelines
- **Accurate, concise, structured, developer/AI-friendly.**
- Free from secrets and unnecessary duplication.
- Based on evidence, not generic assumptions (e.g., avoid "This system is scalable" unless proven).
- Aim for high information density. Size guidelines: ~100–300 lines for small projects, ~200–500 for medium, ~400–800+ for large. Use your judgment.

## Validation Checklist
Before finishing, validate the generated `CONTEXT.md`:
- [ ] Project name is correct.
- [ ] Architecture is based on actual code.
- [ ] No secrets are included.
- [ ] No invented features/dependencies.
- [ ] Business logic, data flows, authentication, and integrations are documented.
- [ ] Commands/Deployment info are verified.
- [ ] Technical debt vs. assumptions is clear.
- [ ] Common pitfalls, AI guidance, and Maintenance guidance are present.
- [ ] Markdown and Mermaid diagrams are valid.

## Hierarchical Principle
When information conflicts, follow this hierarchy:
**Actual Source Code > Project Configuration > Tests > Existing Documentation > CONTEXT.md > AI Assumptions.**

Reality always wins.
