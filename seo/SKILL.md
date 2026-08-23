---
name: seo
description: Audit, improve, and implement technical and on-page SEO for websites and web applications.
---

# SEO Skill

The purpose of this skill is to help an AI agent audit, improve, and implement SEO for websites and web applications, with a strong focus on technical SEO, on-page SEO, structured data, crawlability, indexability, performance, internal linking, and search-engine presentation.

The skill must work independently and must not depend on any other skill.

## Core Objective

The skill should follow this principle:

Make the website easier for search engines to crawl, understand, index, and rank while maintaining an excellent user experience.

The skill should not blindly add keywords or metadata.

SEO improvements must be based on:
* Search intent
* Page purpose
* Content quality
* Technical correctness
* Search-engine discoverability
* User experience
* Website architecture
* Structured data
* Performance
* Internal linking
* Indexability

## 1. SEO Audit

When given an existing website, page, URL, screenshot, codebase, or SEO configuration, perform a structured SEO audit.

Analyze:

### Technical SEO
* Crawlability
* Indexability
* Canonical URLs
* Robots directives
* robots.txt
* XML sitemap
* HTTPS
* URL structure
* Redirects
* 404 pages
* 5xx errors
* Duplicate URLs
* Duplicate content
* Pagination
* Internal linking
* Orphan pages
* Broken links
* Hreflang where relevant

### On-Page SEO
Analyze:
* Title
* Meta description
* H1
* H2/H3 hierarchy
* Content structure
* Keyword/topic relevance
* Search intent
* Image alt text
* Internal links
* Anchor text
* URL
* Content uniqueness
* Content depth

### SERP Presentation
Evaluate:
* Title appearance
* Meta description
* Breadcrumbs
* Rich results eligibility
* Structured data
* Site name
* Open Graph
* Twitter/X metadata

## 2. Search Intent

Before optimizing a page, determine its likely search intent.

Classify it as:
* Informational
* Navigational
* Commercial investigation
* Transactional
* Local
* Mixed

The SEO strategy must match the user’s intent.

Do not optimize a transactional page like an informational article.

## 3. Keyword and Topic Strategy

When keywords are provided, use them intelligently.

When keywords are not provided, identify relevant search topics based on:
* Page purpose
* Existing content
* User intent
* Product/service
* Location
* Target audience

Avoid:
* Keyword stuffing
* Repetitive phrases
* Artificial keyword placement
* Unnatural headings
* Hidden keywords

Prioritize topic relevance and search intent over keyword density.

## 4. Title Optimization

For every important indexable page, evaluate the title.

The title should:
* Clearly describe the page
* Match search intent
* Include the primary topic naturally
* Be unique
* Be compelling
* Avoid unnecessary repetition
* Represent the actual page content

Do not create misleading titles purely for clicks.

When appropriate, provide:
Current Title:
Proposed Title:
Reason:

## 5. Meta Description

Create descriptions that:
* Accurately describe the page
* Match search intent
* Naturally include relevant terms
* Encourage qualified clicks
* Are unique across important pages

Do not treat meta descriptions as a direct ranking guarantee.

## 6. Heading Structure

Ensure that the page has a logical hierarchy:
H1
 ├── H2
 │    ├── H3
 │    └── H3
 └── H2
      └── H3

Rules:
* Use one primary H1 where appropriate.
* Do not use headings purely for styling.
* Make headings descriptive.
* Ensure headings represent the content structure.

## 7. URL Optimization

Evaluate:
* Readability
* Stability
* Relevance
* Unnecessary parameters
* Duplicate URL variations
* Trailing slash consistency
* Case sensitivity
* Slug quality

Avoid changing established URLs unnecessarily.

If URLs must change, recommend proper redirects.

## 8. Canonicalization

Evaluate canonical URLs.

Ensure that:
* Important pages have appropriate canonical URLs.
* Canonicals point to the preferred version.
* Canonicals are absolute where appropriate.
* Canonicals do not conflict with redirects.
* Canonicals do not incorrectly point unrelated pages together.

Never use canonical tags as a substitute for fixing duplicate URL architecture.

## 9. Robots.txt

Analyze and improve robots.txt.

Ensure it does not accidentally block:
* Important pages
* CSS
* JavaScript required for rendering
* Images needed for understanding content

Do not use robots.txt to solve indexation problems that require noindex or canonicalization.

## 10. XML Sitemap

Evaluate:
* Sitemap existence
* Sitemap accessibility
* Correct URLs
* Canonical URLs
* Indexable URLs
* Last modification dates where appropriate
* Sitemap size/segmentation
* Sitemap index structure

The sitemap should primarily contain URLs that are intended to be indexed.

## 11. Structured Data

Analyze whether structured data can improve search understanding and eligibility for rich results.

Consider appropriate schemas such as:
* WebSite
* Organization
* LocalBusiness
* Person
* Product
* Offer
* Review
* AggregateRating
* Article
* BlogPosting
* BreadcrumbList
* Event
* FAQPage where appropriate
* JobPosting
* Recipe
* Other schema.org types relevant to the content

Do not add structured data simply to increase the amount of schema.

Structured data must accurately represent visible page content.

Never fabricate:
* Reviews
* Ratings
* Prices
* Events
* Organizations
* Locations
* Other structured data properties

## 12. Schema Validation

When implementing structured data:
* Use valid JSON-LD.
* Match schema types to the page.
* Avoid unsupported properties.
* Avoid misleading markup.
* Keep structured data synchronized with visible content.
* Recommend validation/testing when possible.

## 13. Internal Linking

Analyze internal links.

Identify:
* Important pages with too few links
* Orphan pages
* Excessive links
* Weak anchor text
* Missing contextual links
* Poor navigation hierarchy

Recommend descriptive, natural anchor text.

Build internal links around topical relationships rather than arbitrary keyword insertion.

## 14. Site Architecture

Analyze the website hierarchy.

For example:
Home
├── Services
│   ├── Service A
│   ├── Service B
│   └── Service C
├── Locations
│   ├── Nairobi
│   ├── Kiambu
│   └── Limuru
├── Blog
└── About

Determine whether important content is:
* Discoverable
* Logically grouped
* Close enough to the main navigation
* Supported by internal links

Avoid unnecessary URL depth.

## 15. Local SEO

When the website targets a geographic location, analyze:
* Business name
* Address
* Phone
* Opening hours
* Location pages
* LocalBusiness schema
* Google Business Profile considerations
* Local keywords
* Location-specific content
* NAP consistency
* Local internal linking
* Maps/location information

Do not create low-quality doorway pages for every location.

Location pages should provide genuinely useful, unique information.

## 16. Image SEO

Analyze:
* Alt text
* File names
* Image dimensions
* Compression
* Lazy loading
* Responsive images
* Image formats
* Relevant captions
* Decorative images

Alt text should describe meaningful images.

Do not stuff keywords into alt attributes.

## 17. Performance and Core Web Vitals

When performance information or code is available, evaluate:
* LCP
* INP
* CLS
* TTFB
* Image loading
* JavaScript execution
* CSS delivery
* Font loading
* Third-party scripts
* Caching
* Server response time

Identify SEO-relevant performance problems.

Do not blindly optimize metrics at the expense of functionality or usability.

## 18. JavaScript SEO

For JavaScript-heavy applications such as:
* Next.js
* React
* Vue
* Angular
* SPA applications

evaluate:
* Server-side rendering
* Static generation
* Dynamic rendering where relevant
* Metadata generation
* Crawlable links
* Client-only content
* Loading states
* URL accessibility
* Rendering-dependent content

Important SEO content should not depend unnecessarily on client-side JavaScript.

## 19. Next.js SEO

When the project uses Next.js, specifically evaluate:
* Metadata API
* generateMetadata
* Static metadata
* Canonicals
* Open Graph
* Twitter/X metadata
* robots.ts
* sitemap.ts
* JSON-LD
* Dynamic routes
* generateStaticParams
* Server Components
* Rendering strategy
* Image optimization
* URL structure

Use the approach appropriate to the project’s Next.js version and architecture.

Do not introduce outdated Next.js patterns when the project uses modern APIs.

## 20. Social Metadata

Evaluate:
* Open Graph title
* Open Graph description
* Open Graph image
* Open Graph URL
* Twitter/X card
* Social image dimensions

Social metadata is not a substitute for SEO metadata, but it should provide a good sharing experience.

## 21. Indexation Strategy

For every important page, determine:
Should this page be indexed?
        ↓
YES → Optimize it
        ↓
NO → Determine why

Potential reasons for noindex may include:
* Internal utility pages
* Duplicate pages
* Search results
* Temporary pages
* Private/user-specific pages
* Thin pages with no independent search value

Do not recommend noindex simply because a page is difficult to optimize.

## 22. Content Quality

Evaluate content based on:
* Usefulness
* Originality
* Relevance
* Accuracy
* Search intent
* Depth
* Clarity
* Experience/expertise signals where relevant
* Trustworthiness
* User satisfaction

Do not generate filler content solely to increase word count.

## 23. SEO for Programmatic Pages

If the website generates many pages dynamically:

Evaluate:
* Unique content
* Page usefulness
* URL patterns
* Indexation control
* Internal linking
* Canonicalization
* Duplicate content
* Thin content
* Sitemap generation

Do not recommend mass-generating pages without meaningful value.

## 24. SEO Audit Severity

Classify findings as:

Critical
Issues that can significantly prevent crawling/indexing or cause major SEO problems.

High
Issues that significantly affect important pages.

Medium
Meaningful optimization opportunities.

Low
Minor improvements or polish.

Opportunity
Potential improvements that are not errors.

Example:
CRITICAL
Important pages are blocked by robots.txt.
HIGH
Product pages have duplicate titles.
MEDIUM
Important pages have weak internal linking.
LOW
Some images have non-descriptive filenames.
OPPORTUNITY
Add BreadcrumbList structured data.

## 25. Prioritization

Prioritize SEO work using:
Impact × Confidence ÷ Effort

Focus first on improvements that:
* Affect many pages
* Affect important pages
* Block crawling/indexing
* Improve search understanding
* Have low implementation risk
* Provide measurable value

Do not spend time optimizing tiny details while major technical problems remain unresolved.

## 26. SEO Implementation

When asked to implement SEO, inspect the existing project first.

Do not blindly create new files.

Identify:
* Framework
* Routing
* Existing metadata
* Existing SEO utilities
* Existing schema
* Sitemap
* Robots configuration
* Existing canonical handling
* Existing components
* Existing content architecture

Then make the smallest appropriate implementation.

## 27. SEO Change Safety

Do not unnecessarily change:
* URLs
* Content
* Navigation
* Branding
* Page functionality
* Business logic

If changing URLs is necessary:
Old URL
↓
301 Redirect
↓
New URL

Update:
* Internal links
* Canonicals
* Sitemap
* Structured data
* Metadata

## 28. SEO Verification

After implementation, verify:
[ ] Important pages are indexable
[ ] Canonicals are correct
[ ] Titles are unique
[ ] Meta descriptions are appropriate
[ ] H1 hierarchy is correct
[ ] Robots directives are correct
[ ] robots.txt is correct
[ ] Sitemap works
[ ] Internal links work
[ ] No important pages are orphaned
[ ] Structured data is valid
[ ] URLs are correct
[ ] Images have appropriate alt text
[ ] Open Graph metadata exists where appropriate
[ ] Mobile experience is good
[ ] Performance issues are understood
[ ] No accidental noindex directives exist
[ ] No accidental robots blocks exist

## 29. SEO Reporting

When performing an audit, provide a concise but actionable report.

Use:
SEO SCORE
[Overall assessment]
CRITICAL ISSUES
1. ...
HIGH PRIORITY
1. ...
MEDIUM PRIORITY
1. ...
OPPORTUNITIES
1. ...
RECOMMENDED ORDER
1. ...
2. ...
3. ...
IMPLEMENTATION PLAN
...

For each issue include:
Problem:
Impact:
Evidence:
Recommendation:
Priority:
Effort:

## 30. Screenshot-Based SEO Analysis

If a screenshot is provided, use it to identify visible SEO-related problems such as:
* Missing/poor content hierarchy
* Weak headings
* Poor content discoverability
* Missing contextual links
* Thin content
* Poor information architecture
* Poor mobile UX
* Weak page purpose

However, clearly distinguish what can be determined from a screenshot from what requires inspecting the actual HTML/code.

Never claim that a screenshot proves:
* Indexability
* Canonical configuration
* robots directives
* Sitemap configuration
* Structured data
* HTTP status
* Server rendering

Those require technical inspection.

## 31. SEO and UX Balance

SEO must never be treated as separate from user experience.

Do not:
* Stuff keywords
* Add unnecessary paragraphs
* Hide content
* Create spammy location pages
* Add irrelevant schema
* Create excessive internal links
* Make titles misleading
* Add intrusive content purely for search engines

The best optimization should improve both:
Search Engine Understanding
+
User Experience

## 32. Search Engine Claims

Do not make absolute claims such as:
“This guarantees a #1 ranking.”

SEO results depend on many external factors.

Use evidence-based language such as:
* “This should improve crawlability.”
* “This makes the page easier for search engines to understand.”
* “This may improve eligibility for rich results.”
* “This removes a technical barrier to indexing.”

## 33. Web Research

When current search-engine behavior, official documentation, schema requirements, or framework-specific SEO behavior is uncertain or likely to have changed, research authoritative current sources before making a recommendation.

Prefer:
* Official search-engine documentation
* Official framework documentation
* Official schema documentation

Avoid relying on outdated SEO advice.

## 34. Standalone Requirement

The skill must be completely self-contained.

It must not require another skill for:
* Web development
* Content writing
* Technical audits
* Design
* Performance
* Testing
* Documentation

It can work with existing project standards when available, but must remain fully functional on its own.

## Final Principle

Optimize for discoverability, understanding, relevance, and user value. Fix technical barriers first, improve the content and structure second, and never sacrifice the user’s experience for SEO.
