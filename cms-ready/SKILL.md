---
name: cms-ready
description: Ensure pages, screens, and components are structured for future CMS integration without requiring a UI rewrite.
---

# CMS-Ready Skill

The purpose of this skill is to ensure that every page, screen, component, and content-driven feature created for a web or mobile application is structured so that it can be connected to a CMS in the future without requiring a major rewrite.

The core principle is:
**Build pages so content can become dynamic later without rebuilding the UI.**

## Core Objective

Whenever an AI agent creates or modifies:
* Web pages
* Mobile screens
* Landing pages
* Dashboards
* Marketing pages
* Product pages
* Service pages
* Blog pages
* Article pages
* FAQ sections
* Testimonials
* Pricing sections
* Hero sections
* Feature sections
* Navigation
* Footer content
* Location pages
* Promotional content
* Content-heavy application screens

The skill should determine which parts should be CMS-ready.
The goal is NOT to force every piece of UI into a CMS. The goal is to create a clean separation between:

Content -> Data / Content Model -> UI Components -> Page

Instead of:
Hardcoded Content -> UI -> Page

## 1. CMS-Ready Principle
When building a page, the agent should ask:
*Could this content reasonably need to be changed by a non-developer in the future?*

If yes, structure it so the content can be supplied by:
* A CMS
* An API
* A database
* Local JSON
* Static configuration
* Another content provider

...without requiring the UI components to be rewritten.

## 2. Separate Content From Presentation
Avoid unnecessarily hardcoding content directly inside UI components.

Prefer:
Content/Data -> Component -> Page

Instead of:
Page -> Component -> Hardcoded content

For example, avoid tightly coupling content inside a reusable component when the content could reasonably come from a CMS.
Prefer a structure conceptually similar to:
```jsx
<Hero
  title={content.title}
  description={content.description}
  image={content.image}
/>
```
The exact implementation should follow the project’s framework and architecture.

## 3. Identify CMS-Suitable Content
For every page, classify content into:

**Static UI**
Content that is part of the application’s interface and normally does not need CMS management.
Examples: "Save", "Cancel", Navigation controls, Form labels, System-generated statuses, Technical error messages.

**CMS-Suitable Content**
Content that could reasonably be edited by a content manager.
Examples: Page titles, Hero text, Descriptions, Images, Videos, Testimonials, FAQs, Blog content, Marketing copy, Feature descriptions, Promotional banners, Locations, Authors, Categories, SEO metadata.

**Dynamic Application Data**
Data that should generally come from application APIs/databases rather than a CMS.
Examples: User balances, Orders, Transactions, Inventory, Authentication state, Real-time notifications, System-generated analytics.
*Do not force application data into a CMS simply because the skill exists.*

## 4. Content Modeling
When content is likely to become CMS-managed, define a logical content model.
For example:
```
Hero
├── eyebrow
├── title
├── description
├── primaryCTA
├── secondaryCTA
└── image
```
The model should be clear, predictable, extensible, framework-independent where possible, and easy to map to a CMS later.

## 5. Do Not Couple the UI to a Specific CMS
The skill should NOT automatically introduce WordPress, Sanity, Strapi, Contentful, or any other CMS unless explicitly requested. The goal is CMS readiness, not premature CMS integration.

## 6. CMS-Agnostic Data Interfaces
When appropriate, create an abstraction between content retrieval and UI.
The UI should ideally consume a predictable content shape rather than knowing how the CMS works.
```typescript
type PageContent = {
  title: string;
  description?: string;
  heroImage?: ImageAsset;
  sections: PageSection[];
};
```

## 7. Reusable Components
CMS-ready pages should use reusable components where appropriate (e.g., Hero, RichText, Image, CTA). Avoid creating large components where content, layout, and business logic are tightly coupled. A component should ideally receive data rather than own large amounts of page-specific content.

## 8. Flexible Page Sections
For content-heavy pages, consider a section-based architecture. Where appropriate, represent sections as data. Only introduce flexible section structures when the page is genuinely content-driven. Do not create a generic page-builder system unnecessarily.

## 9. Avoid Overengineering
CMS readiness does NOT mean making everything dynamic, creating a universal page builder, creating dozens of abstractions, creating unnecessary database tables, creating a CMS before it is needed, adding an API layer for simple static content, or turning every component into a schema. Use the simplest architecture that keeps future CMS integration practical.

## 10. Images and Media
Images should be CMS-ready. Avoid tightly coupling UI components to local image files when images are likely to become editable content. Consider future CMS requirements such as responsive images, alt text, captions, and focal points.

## 11. Rich Text
When content may eventually come from a CMS, avoid assuming all content is plain text. Consider whether the content may require paragraphs, headings, lists, links, or embedded media. Use an appropriate rich-text representation when justified, but do not introduce a rich-text editor unless explicitly requested.

## 12. Links and CTAs
CMS-manageable links should be represented as structured data where appropriate (e.g., label, href, type, external). Avoid hardcoding URLs into reusable components unnecessarily.

## 13. SEO Readiness
CMS-ready content should support future SEO management. Content models should allow SEO metadata (title, description, ogImage) separate from visual presentation.

## 14. Localization Readiness
If the product may eventually support multiple languages, avoid architectures that make localization unnecessarily difficult (e.g., hardcoding `if language === "en"` inside components). Structure content so text can eventually be translated.

## 15. Content Validation
CMS content cannot always be trusted. Define reasonable validation for CMS-ready content (e.g., title is required, description is optional). The application should fail gracefully when content is incomplete.

## 16. Defaults and Fallbacks
CMS-ready components should consider sensible fallbacks (default content, empty state, hidden section). Do not use fake production content as a permanent fallback.

## 17. Content Loading States
If content will eventually be fetched dynamically, consider loading, empty, error, and partial content states.

## 18. Caching and Rendering Considerations
When working with frameworks like Next.js, consider future CMS integration when choosing rendering strategies. Avoid architectural decisions that make future dynamic content unnecessarily difficult. Do not implement CMS-specific caching until a CMS exists.

## 19. Web and Mobile
The skill must work for both web and mobile platforms. Do not embed content directly into mobile screens when that content is likely to become remotely managed.

## 20. API/Data Contract
Define a clear data contract between content and UI. The UI should not depend directly on CMS-specific implementation details.

## 21. Existing Page Audit
When modifying an existing page, inspect for hardcoded content, component structure, data dependencies, etc., and make targeted improvements. Do not rewrite the entire page simply to make it CMS-ready.

## 22. CMS Readiness Levels
Classify pages as:
* Level 0 — Hardcoded
* Level 1 — Componentized
* Level 2 — Data Driven
* Level 3 — CMS Ready
* Level 4 — CMS Integrated

The skill’s normal goal is **Level 3**, unless CMS integration is explicitly requested.

## 23. CMS Readiness Checklist
Before completing a page, verify:
- [ ] Content has been separated from presentation where appropriate
- [ ] CMS-suitable content has been identified
- [ ] Components accept content through props/data
- [ ] Page-specific content is not unnecessarily hardcoded
- [ ] Images can be represented as content objects
- [ ] Links/CTAs can be represented as structured data
- [ ] Rich text requirements have been considered
- [ ] SEO metadata can become CMS-managed
- [ ] Content validation is possible
- [ ] Missing content will not unnecessarily crash the page
- [ ] Loading/error states are considered where appropriate
- [ ] Future API/CMS data can map to the UI
- [ ] UI components are not coupled to a specific CMS
- [ ] No unnecessary CMS architecture was introduced
- [ ] Existing functionality remains intact
- [ ] Responsive behavior remains intact

## 24. Final Page Architecture
Whenever appropriate, aim for an architecture where a Local JSON, API, or Database flows through a Content Adapter into a Normalized Content Model, which is then passed to UI Components.
**The UI should care about the content it receives, not where that content came from.**

## 25. Output Requirements
When creating a page, the skill should briefly identify:
* **CMS-Suitable Content** (e.g., Hero title, Features)
* **Static UI** (e.g., Navigation controls)
* **Suggested Content Model**
* **CMS Readiness** (e.g., Level 3 — CMS Ready)
* **Future Integration** (Briefly explain how a future CMS could provide the content without requiring a major UI rewrite)

## 26. Do Not Overengineer
**CMS-ready does not mean CMS-dependent.**
Do not install a CMS, add a database, or build a page builder unnecessarily. Make future CMS integration easy without making the current application unnecessarily complex.

## 27. Independence Requirement
The skill must be completely standalone and must not require another skill.

**Final Principle**
Build the UI around structured content, not hardcoded content. Keep presentation independent from content sources, avoid premature CMS integration, and make future CMS adoption possible without requiring a major rewrite.
