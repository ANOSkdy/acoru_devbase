# DESIGN.md

## Goal
Define the shared UI/UX contract for this repository.

## Device Assumption
- Primary use: desktop
- Must remain usable on mobile
- New screens must be responsive by default

## Product Style
- Simple
- Clear
- Operationally efficient
- Easy to scan
- Low training cost for business users

## Core Principles
- Prefer clarity over decoration
- Prefer consistency over novelty
- Prefer usability over dense visual design
- Keep interaction friction low
- Keep layouts readable across laptop and mobile widths

## Layout Rules
- Avoid desktop-only fixed widths
- Prefer a readable max width for content-heavy pages
- On smaller screens, stack content vertically
- Keep major actions discoverable without clutter
- Avoid squeezing dense tables into unusable mobile layouts

## Spacing Rules
- Use consistent spacing scale
- Preserve comfortable spacing between sections
- Forms should not feel cramped
- Lists and tables should maintain readable row density

## Typography Rules
- Clear hierarchy:
  - page title
  - section title
  - body text
  - helper/error text
- Avoid tiny text for important actions or status
- Keep labels and helper text readable on mobile

## Forms
- Every input must have a visible label
- Required vs optional should be clear
- Validation messages should appear near the field
- Submit actions should be obvious
- Avoid overusing modal forms unless it improves speed
- Destructive actions must be clearly distinguishable from save/submit

## Tables / Lists
- Desktop admin pages may use tables
- Mobile should degrade gracefully:
  - stacked cards
  - grouped list items
  - or horizontal scrolling only when unavoidable
- Empty states must be explicit
- Loading states must be explicit
- Sorting/filtering controls should be compact and understandable

## Buttons / Actions
- Primary action should be visually clear
- Secondary actions should not compete with the primary
- Destructive actions should require deliberate intent
- Avoid placing destructive actions too close to high-frequency actions

## State Design
Each screen should consider:
- initial state
- loading state
- empty state
- validation error state
- server error state
- success/complete state

## Accessibility
- Keyboard reachable controls
- Visible focus states
- Sufficient contrast
- Do not rely on color alone for status or errors
- Ensure touch targets remain usable on mobile

## Content Style
- Use concise labels
- Prefer plain business language
- Avoid overly technical wording in end-user UI
- Error messages should guide the user to the next step when possible

## Responsive Guidance
- Default to a one-column mobile layout
- Expand to multi-column only when readability improves
- Tables with many columns should have a deliberate mobile fallback
- Page headers should remain compact on mobile

## Reusable Screen Pattern
Most screens should follow this structure:
1. page title
2. short purpose or context if needed
3. filters/search if needed
4. main content area
5. clear primary action
6. visible success/error feedback

## Design Change Policy
If a new feature introduces a new interaction pattern:
- keep it minimal
- document it here if it becomes reusable
- prefer adapting an existing pattern before creating a new one
