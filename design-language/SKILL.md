---
name: design-language
description: Analyzes an existing website, app, screenshots, or codebase to reverse-engineer its visual identity and create a structured, reusable design language.
---

# Design Language Extraction Skill

The purpose of this skill is to analyze an existing website, web application, mobile application, screenshots, or frontend codebase and reverse-engineer its **visual identity, design language, branding, UI system, typography, color system, spacing, components, interaction patterns, imagery, and overall aesthetic**.

This skill transforms an existing design into a structured, reusable design language that can be used to:
- Build new pages
- Redesign existing pages
- Maintain visual consistency
- Create new components
- Generate design specifications
- Guide developers and designers
- Create prompts for UI generation
- Evaluate whether future screens match the existing brand

## Core Principle
> **Do not merely describe what the interface looks like. Extract the underlying design rules that explain why it looks the way it does.**

This skill works independently and does not depend on another skill.

## Supported Inputs
The skill works with any combination of:
- Website URL
- Screenshots (Mobile and Desktop)
- Screen recordings
- Frontend source code
- Design files where available
- Component libraries
- CSS
- Tailwind configuration
- Theme files
- Existing design tokens

The more evidence available, the more accurate the extracted design language will become.

## 1. Analyze Before Recommending

Do not immediately redesign the interface.

First determine:
- What already exists
- What patterns repeat
- What visual rules are intentional
- What appears to be accidental
- What is consistent
- What is inconsistent
- What defines the brand
- What defines the product UI

### Categorize Findings
Clearly distinguish between the following categories in your output:

- **Observed**: Directly visible or identifiable in the source.
- **Inferred**: A design rule that can reasonably be derived from repeated patterns.
- **Recommended**: A proposed improvement that is not currently part of the design.

*Never present recommendations as existing design rules.*

## 2. Brand Identity Extraction

Analyze the overall brand identity based on the provided inputs.

Determine and document:
- Brand personality
- Brand tone
- Visual personality
- Emotional impression
- Target audience
- Perceived positioning
- Premium vs affordable
- Modern vs traditional
- Minimal vs expressive
- Corporate vs playful
- Technical vs human
- Bold vs subtle

Describe the brand using meaningful terms.

**Example format:**
```text
Brand Personality:
- Modern
- Trustworthy
- Premium
- Approachable
- Minimal
```

## 3. Design System Extraction

Extract and define the specific rules and tokens that make up the visual system.

### Color System
- Primary, secondary, and accent colors.
- Semantic colors (success, warning, error, info).
- Background and surface colors.
- Text colors (primary, secondary, disabled).
- Gradients and their applications.

### Typography
- Font families used (headings vs. body).
- Typographic scale (sizes, line heights, font weights).
- Tracking/letter-spacing rules.

### Spacing & Layout
- Grid system and container widths.
- Spacing scale (margins, paddings).
- Breakpoints and responsive behaviors.

### Shape & Elevation
- Border radius rules (sharp vs. rounded).
- Border widths and colors.
- Shadows and elevation systems.

### Component Rules
- Button styling and states (default, hover, active, disabled).
- Form inputs and controls.
- Cards, modals, and navigation elements.

### Interaction & Motion
- Hover effects and transitions.
- Animation curves and durations.
- Loading states and feedback mechanisms.

## Output Delivery
Present the extracted design language as a comprehensive, structured markdown specification that can be easily referenced by other agents or human developers/designers. Ensure the document is organized logically, starting from high-level brand identity down to specific component rules.
