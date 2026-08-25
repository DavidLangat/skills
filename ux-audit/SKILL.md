---
name: ux-audit
description: Analyzes an existing web or mobile page to identify UX problems, evaluate user journeys, and propose or implement improvements.
---

# ux-audit

The purpose of this skill is to analyze an existing web or mobile page, identify UX problems, evaluate the user journey and interaction patterns, and propose or implement improvements that make the page easier, clearer, faster, and more intuitive to use.

The skill is UX-focused, not primarily a visual redesign skill.

Its core principle is:
**Improve how the user accomplishes their goal, not simply how the interface looks.**

The skill must work independently and must not depend on another skill.

## Input Types

The skill should work with any combination of:
* Screenshot
* Multiple screenshots
* Screen recording
* Existing frontend code
* Component code
* Page URL when accessible
* User flow description
* Product requirements
* Existing design
* Existing UI implementation

The skill should be useful even when only a screenshot is provided.

When code is available, inspect the implementation as well as the visual result.

## Understand the Page Before Critiquing It

Before identifying UX problems, determine:
- **Page purpose**: What is this page supposed to accomplish?
- **User**: Who is using the page?
- **Primary goal**: What is the most important thing the user should accomplish?
- **Secondary goals**: What other actions might the user perform?
- **Context**: Where does this page exist in the larger application?
- **Expected next step**: What should the user naturally do after interacting with the page?

Do not judge a page without understanding its purpose.

## Identify the Primary User Journey

Map the expected user journey.

For example:
Arrive
  ↓
Understand page
  ↓
Find relevant information
  ↓
Choose action
  ↓
Complete action
  ↓
Receive feedback
  ↓
Continue / Finish

Identify friction at every stage.

## UX Heuristic Analysis

Evaluate the page using established usability principles.

Analyze:
1. **Visibility of System Status**
   Does the user know: What is happening? Whether an action worked? Whether something is loading? Whether something failed? What state they are currently in?
2. **Match Between System and Real World**
   Does the interface use language and concepts users understand?
3. **User Control and Freedom**
   Can users: Go back? Cancel? Undo? Edit? Recover from mistakes?
4. **Consistency**
   Are similar interactions presented consistently?
5. **Error Prevention**
   Does the interface prevent mistakes before they happen?
6. **Recognition Over Recall**
   Does the interface show necessary information rather than requiring users to remember it?
7. **Flexibility and Efficiency**
   Does the interface support both: New users, Experienced users
8. **Minimalism**
   Does every visible element contribute to the user’s goal?
9. **Error Recovery**
   Are errors understandable and actionable?
10. **Help and Guidance**
    Does the user receive enough guidance when needed?

## Analyze Information Hierarchy

Determine:
What should the user notice first?
        ↓
What should they notice second?
        ↓
What information supports the decision?
        ↓
What information is optional?

Identify:
* Competing elements
* Weak hierarchy
* Important information buried too deeply
* Excessive visual noise
* Unnecessary content
* Missing context

## Analyze Cognitive Load

Determine whether the page asks the user to think more than necessary.

Look for:
* Too many choices
* Too many CTAs
* Complex forms
* Unclear terminology
* Excessive information
* Long instructions
* Hidden requirements
* Unnecessary steps
* Ambiguous actions

Recommend ways to reduce cognitive load.

## Analyze Navigation

Evaluate:
* Can users understand where they are?
* Can they understand where to go next?
* Is navigation predictable?
* Are important actions easy to find?
* Are breadcrumbs useful?
* Are tabs understandable?
* Are navigation labels clear?

For mobile applications, also evaluate:
* Bottom navigation
* Back navigation
* Gestures
* Navigation hierarchy
* Screen transitions

## Analyze Forms

If the page contains forms, evaluate:

**Fields**
* Are all fields necessary?
* Can fields be combined?
* Is the order logical?
* Are defaults appropriate?

**Labels**
* Are labels clear?
* Are they visible?
* Are they understandable?

**Validation**
* Is validation immediate when appropriate?
* Are errors shown near the relevant field?
* Are error messages understandable?

**Submission**
* Is the primary action obvious?
* Does the user know what will happen?
* Is duplicate submission prevented?

**Completion**
* Does the user receive clear confirmation?

## Analyze Calls to Action

For every important CTA determine:
- What does this button do?
- Why would the user click it?
- Is it the correct primary action?
- Is its label clear?
- What happens after clicking?

Identify:
* Too many primary CTAs
* Weak CTA hierarchy
* Ambiguous labels
* Misleading buttons
* Actions hidden in menus
* Destructive actions without adequate warning

## Analyze Feedback

Determine whether the interface provides feedback for:
* Clicks
* Submissions
* Saves
* Deletes
* Uploads
* Errors
* Success
* Loading
* Processing
* Empty states

Every meaningful user action should have appropriate feedback.

## Analyze Empty States

For relevant components, evaluate what happens when there is no data.

A good empty state should explain:
- What happened?
- Why is it empty?
- What can the user do next?

Avoid empty screens with no guidance.

## Analyze Loading States

Evaluate whether the page handles:
* Initial loading
* Partial loading
* Slow network
* Background operations

Consider:
* Skeletons
* Progress indicators
* Disabled states
* Optimistic updates
* Preserving existing content while refreshing

Do not recommend loading animations unnecessarily.

## Analyze Error States

Evaluate:
* Error clarity
* Error location
* Recovery options
* Technical jargon
* Destructive consequences

A good error should answer:
- What went wrong?
- Why?
- What can I do now?

## Analyze Destructive Actions

For actions such as Delete, Cancel, Remove, Revoke, Reset, Disable, evaluate:
* Discoverability
* Confirmation
* Consequences
* Undo options
* Recovery

Do not use confirmation dialogs for every action. Use them when the consequence is meaningful or difficult to reverse.

## Analyze Accessibility UX

Evaluate:
* Keyboard navigation
* Focus states
* Touch target sizes
* Color dependence
* Text readability
* Labels
* Screen-reader context
* Error announcements
* Motion
* Contrast
* Interactive element clarity

Accessibility should be treated as part of UX.

## Analyze Mobile UX

If the page is mobile or responsive, evaluate:
* Touch target sizes
* Reachability
* Thumb-friendly interaction
* Bottom navigation
* Input behavior
* Keyboard interaction
* Scrolling
* Fixed elements
* Modal behavior
* Sheet/drawer behavior
* Content density
* Orientation

Do not simply treat mobile as a smaller desktop.

## Identify UX Friction

Create a friction map.

Example:
**Friction 1**: User cannot immediately understand the page.
**Friction 2**: Primary action competes with three secondary actions.
**Friction 3**: Form requires unnecessary information.
**Friction 4**: Success feedback is unclear.

For every friction point explain:
Problem ↓ Why it matters ↓ Recommended improvement

## Prioritize UX Problems

Classify findings as:
- **Critical**: The user may be unable to complete the task.
- **High**: Significant friction or confusion.
- **Medium**: Meaningful usability improvement.
- **Low**: Minor usability issue.
- **Enhancement**: Potential improvement that is not currently a problem.

## UX Improvement Recommendations

For every significant problem provide:
- **Problem**:
- **Current UX**:
- **Impact**:
- **Recommendation**:
- **Expected improvement**:
- **Priority**:

Recommendations should be practical and implementable. Avoid generic statements such as: “Make it more user-friendly.” Instead say exactly what should change.

## Redesign the User Flow

When necessary, redesign the flow rather than just individual components. The goal is to reduce unnecessary effort.

For example:
**Current**: Page ↓ 5 required fields ↓ Submit ↓ Error ↓ Fix ↓ Submit again
**Proposed**: Page ↓ Only necessary fields ↓ Inline validation ↓ Submit ↓ Success confirmation

## Before vs After

Provide a clear comparison.
- **Current UX**: Describe the current journey.
- **Improved UX**: Describe the proposed journey.
- **Why**: Explain why the new flow is better.

## UX Design Specifications

When recommending changes, specify:
- **Navigation**: Structure, Labels, Placement
- **Content**: What should be visible, What can be hidden, What should be prioritized
- **Interactions**: Click behavior, Hover behavior, Focus behavior, Mobile behavior
- **Forms**: Field order, Validation, Defaults, Submission
- **Feedback**: Loading, Success, Error, Empty

## Do Not Confuse UX With UI

The skill must distinguish:
- **UX Problem**: Users cannot easily determine what action to take.
- **UI Problem**: The button has insufficient visual contrast.

A UI change can solve a UX problem, but not every visual issue is a UX issue. Prioritize actual usability.

## Preserve Functionality

When improving UX, do not unnecessarily remove existing functionality.

Instead consider:
* Reordering
* Grouping
* Simplifying
* Progressive disclosure
* Better defaults
* Better labels
* Better feedback
* Better navigation

If functionality should be removed, explain why.

## Avoid Dark Patterns

Never recommend UX patterns designed to manipulate users unfairly.

Avoid:
* Misleading buttons
* Hidden cancellation
* Forced continuity
* Obstruction
* Fake urgency
* Confusing opt-outs
* Disguised advertisements
* Intentionally difficult navigation

Optimize for user success and trust.

## Screenshot-Based Analysis

When a screenshot is provided, treat the screenshot as evidence of the current UX.

Analyze: Visible hierarchy, Interaction affordances, Navigation, Content, CTA placement, Forms, Feedback, Information density.

Clearly distinguish between:
- **Observed**: What can actually be seen.
- **Inferred**: What can reasonably be assumed.
- **Unknown**: What requires interaction or code inspection.

Never claim that a screenshot proves behavior that cannot be observed.

## Code-Based Analysis

When frontend code is provided, inspect: Component structure, State management, Event handlers, Forms, Validation, Navigation, Loading states, Error handling, API interactions, Accessibility, Responsive behavior.

Use the implementation to discover UX problems that may not be visible in a screenshot.

## UX Improvement Without Unnecessary Redesign

The skill should not automatically redesign the entire page. First ask: Can the UX problem be solved with a smaller change?

Prefer: Small UX improvement ↓ Better user experience ↓ No unnecessary redesign

Only recommend a major redesign when the current structure fundamentally prevents good UX.

## UX Quality Score

Provide an optional score when appropriate:
**UX Score: 7.2/10**

Break it down into: Clarity, Navigation, Efficiency, Feedback, Error Handling, Accessibility, Mobile UX, Information Architecture.

The score should be supported by actual findings. Do not create arbitrary scores without explanation.

## Final UX Audit Report

When performing a complete audit, produce:

```
UX AUDIT
Page:
Primary User:
Primary Goal:
Overall Assessment:

USER JOURNEY
1.
2.
3.

TOP UX PROBLEMS
1.
2.
3.

FRICTION POINTS
1.
2.
3.

RECOMMENDED IMPROVEMENTS
1.
2.
3.

QUICK WINS
1.
2.
3.

LARGER IMPROVEMENTS
1.
2.

ACCESSIBILITY
...

MOBILE UX
...

IMPROVED USER FLOW
...

PRIORITY ORDER
1.
2.
3.
```

## Implementation Mode

If the user asks to actually improve the UX in code, follow:
1. Analyze current UX
2. Identify problems
3. Prioritize problems
4. Define improvements
5. Inspect existing implementation
6. Implement the smallest appropriate changes
7. Preserve existing functionality
8. Verify the new flow
9. Report changes

Do not modify unrelated functionality.

## Validation Checklist

Before completing the audit/improvement:
- [ ] Page purpose is understood
- [ ] Primary user goal is clear
- [ ] User journey is mapped
- [ ] Major friction points are identified
- [ ] Information hierarchy is evaluated
- [ ] Navigation is evaluated
- [ ] CTAs are evaluated
- [ ] Forms are evaluated where applicable
- [ ] Loading states are considered
- [ ] Empty states are considered
- [ ] Error states are considered
- [ ] Success feedback is considered
- [ ] Accessibility is evaluated
- [ ] Mobile UX is evaluated
- [ ] Problems are prioritized
- [ ] Recommendations are specific
- [ ] Existing functionality is preserved
- [ ] Unnecessary redesign is avoided

## Output Modes

Support the following modes:
* `/analyze` - Analyze the UX without changing anything.
* `/audit` - Perform a complete UX audit.
* `/improve` - Identify and implement UX improvements when code is available.
* `/flow` - Analyze and redesign the user journey.
* `/mobile` - Focus specifically on mobile UX.
* `/accessibility` - Focus specifically on accessibility UX.
* `/forms` - Analyze form UX.
* `/conversion` - Analyze UX related to completing a specific business goal or conversion.

If no mode is specified, automatically choose the appropriate analysis based on the user’s request.

## Independence Requirement

The skill must be completely standalone. It must not depend on:
* UI design skills
* Visual redesign skills
* SEO skills
* Backend skills
* Refactoring skills
* Testing skills

It can recognize design and technical issues, but its primary responsibility must remain user experience.

---

**Understand the user’s goal first. Identify friction second. Improve the journey third. Change the interface only as much as necessary to make the experience clearer, faster, easier, more accessible, and more trustworthy.**
