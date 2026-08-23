---
name: ui-ux-redesign
description: Analyze existing interfaces, learn from inspiration without copying, identify UX/UI problems, and produce implementation-ready redesign specifications and design systems.
---

# `ui-ux-redesign` Skill

Your responsibility is to analyze an existing interface from screenshots, optionally analyze one or more inspiration screenshots, identify UX/UI problems, create a better design direction, define the required design system and components, and produce an implementation-ready redesign.

This skill is completely standalone and usable independently.

## Core Objective

**Understand the existing product, learn from the inspiration, and create a better interface without blindly copying the reference.**

You must be able to work with any combination of existing screenshots, inspiration screenshots, and existing implementation code. Treat all screenshots as critical visual evidence.

---

## 1. Screenshot Analysis

When given an existing UI screenshot, analyze:
- **Layout:** Page structure, containers, columns, grid systems, alignment, spacing, density, visual balance.
- **Navigation:** Header, sidebar, tabs, breadcrumbs, hierarchy.
- **Components:** Identify visible components (Buttons, Cards, Forms, Tables, Modals, etc.).
- **Typography:** Font hierarchy, heading sizes, body text, weight, readability.
- **Color:** Primary/secondary colors, backgrounds, surfaces, borders, contrast, brand usage.
- **Visual Design:** Border radius, shadows, borders, icons, whitespace.
- **UX Problems:** Confusing interactions, poor hierarchy, excessive cognitive load, unclear CTAs, missing feedback, accessibility concerns.

## 2. Inspiration Screenshot Analysis

Extract the design language from inspiration screenshots. **Do NOT simply copy it.**
Analyze:
- Layout patterns, visual hierarchy, typography, color relationships, spacing.
- Component/Navigation patterns, card/button design, iconography, image treatment.
- Interaction patterns and overall visual personality.
- *Determine what makes the inspiration effective* (e.g., strong hierarchy, minimal visual noise).

## 3. Inspiration Adaptation & Multiple Inspirations

When comparing existing UI and inspiration:
`Current UI -> Problems -> Inspiration Principles -> Adaptation Strategy -> Redesign`

Distinguish between:
- **Inspiration:** Ideas that can be adapted.
- **Brand:** Elements belonging to the user's product (do not replace established brand identity).
- **Functionality:** Existing functionality that must be preserved.
- **Design:** Visual and interaction improvements.

*If multiple inspirations are provided:* Analyze common patterns and create a **unified** design direction. Do not create a random combination.

## 4. UX Redesign & Preserving Product Intent

Categorize improvements:
- **Critical:** Usability blockers.
- **High Priority:** Important UX/UI improvements.
- **Medium Priority:** Meaningful quality improvements.
- **Low Priority:** Polish and refinement.

**Preserve Product Intent:** Before redesigning, ask: Who uses the page? What are they trying to accomplish? What actions matter most? Optimizing for the user's goal is more important than visual novelty.

## 5. Creating a Design Direction

Define the visual direction before implementing:
- **Design Personality:** (e.g., Modern, premium, minimal)
- **Visual Hierarchy:** (e.g., Page title -> primary action -> secondary details)
- **Component Style:** (e.g., Soft cards, subtle borders)
- **Color, Typography, Spacing, and Interaction Styles.**

## 6. Generate a Design System & Components

- **Colors:** Primary, Secondary, Background, Surface, Text, Borders, Status (Success/Warning/Error). Use existing brand colors where appropriate.
- **Typography:** Define Display, H1-H3, Body, Caption, Label. Specify font, size, weight, line-height.
- **Spacing:** Define a consistent scale (e.g., 4, 8, 16, 24, 32).
- **Borders & Shadows:** Define radius scales and appropriate elevation levels.
- **Component Inventory:** Identify all required components (Header, Cards, Modals). Classify as NEW, MODIFY, REUSE, or REMOVE.
- **Component States:** Define Default, Hover, Focus, Disabled, Loading, Error, Empty, and Success states.

## 7. Responsive Design & Accessibility

- **Responsive:** Define layouts for Desktop (columns/grids), Tablet, and Mobile. Do not just shrink the desktop UI. Identify when components should stack, collapse, or move into bottom sheets.
- **Accessibility:** Evaluate color contrast, touch targets, keyboard navigation, focus states, and semantic hierarchy.

## 8. Before/After Design Specification & Blueprint

Produce a clear comparison:
- **Current:** Explain major problems.
- **Proposed:** Explain the redesign.
- **Why:** Explain why it is better.

**Design Blueprint Format:**
```
DESIGN BLUEPRINT
Product:
Page:
Design Personality:
Primary User Goal:
Primary CTA:
Secondary Actions:
Layout:
Navigation:
Information Hierarchy:
Color System:
Typography:
Spacing:
Components:
Component States:
Responsive Behavior:
Accessibility:
UX Improvements:
Visual Improvements:
```

## 9. Implementation Guidance

If a technology stack is provided (e.g., React, Tailwind, Next.js), provide implementation details:
- Component structure, styling approach, design tokens, and responsive behavior.
- *Do not automatically produce a huge amount of code unless implementation is requested.*
- *If source code is provided:* Analyze reusable components, simplify CSS, centralize tokens. Do not rewrite everything unless necessary.

## 10. Important Anti-Patterns to Avoid

- **Generic AI UI:** Avoid excessive glassmorphism, random purple/blue gradients, huge headings, too many cards/badges, or decorative elements without purpose.
- **Copying Inspiration:** Inspiration ≠ Copy. Adapt principles to the product, brand, and user.
- **Inconsistency:** Maintain consistency across the product (buttons, navigation, spacing).

## 11. Output Modes

The skill supports these modes (if not specified, auto-determine based on request):
- `/analyze` - Analyze the current screenshot.
- `/inspire` - Analyze the inspiration screenshot.
- `/compare` - Compare current UI with inspiration.
- `/redesign` - Create the complete redesign direction.
- `/design-system` - Create the required design system.
- `/components` - Create the component inventory and specifications.
- `/responsive` - Design responsive behavior.
- `/accessibility` - Perform accessibility analysis.
- `/implement` - Turn the redesign into implementation-ready specifications/code.

## 12. Validation Checklist

Before completing, verify:
- [ ] User goal is clear & Primary CTA is obvious.
- [ ] Information hierarchy is clear.
- [ ] Layout, typography, colors, spacing, and components are consistent.
- [ ] Important information & existing functionality preserved.
- [ ] Mobile behavior, accessibility, and UI states (loading, empty, error) considered.
- [ ] Inspiration was adapted, not copied.
- [ ] No unnecessary visual complexity introduced.

## Final Principle

**Analyze before redesigning. Learn from inspiration without copying it. Preserve the product’s purpose, improve the user’s experience, establish a coherent design system, and produce a redesign that can actually be implemented.**
