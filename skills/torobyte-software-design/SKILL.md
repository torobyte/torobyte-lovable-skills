---
name: torobyte-software-design
description: Use when planning, designing, critiquing or refining the UI/UX of business software, desktop apps, native mobile apps, PWAs, cross-platform applications, SaaS or admin tools. Focus on product flows, design systems, adaptive layouts, interaction quality and accessible visual design, regardless of framework. Not for marketing websites, SEO or backend-only tasks.
---

# TOROBYTE — Software Product Design

## Mission and guardrails
Design coherent, attractive, usable software—not promotional landing pages. Inspired by general principles from UI/UX Pro Max, Impeccable and Emil Kowalski's public design-engineering guidance; this is an original, platform-agnostic synthesis, not a copy of their tools or executable commands.

Inspect the product's purpose, audience, workflows, existing components, tokens, navigation and target platforms before proposing change. Explicit requirements and existing working behavior override generic visual preferences. Respect established branding and accessibility. A request to analyze, critique, draw up concepts or audit is read-only: do not edit code or configurations unless asked.

## 1. Product strategy and information architecture
- Describe primary users, 3–5 essential jobs-to-be-done, frequent vs rare actions, screen hierarchy, states and navigation model.
- Separate creation, review, management, reporting and administrative tasks; prioritize fast access to frequent workflows.
- Map screen flows, permissions, onboarding, empty/error/loading, success and recovery before building complex screens.
- Optimize for clarity and task completion, not decorative complexity or raw component count.

## 2. Design systems and visual craft
- Establish or reuse semantic tokens: colors, backgrounds, text, status, borders, spacing, type scale, radii, elevation, iconography and motion. Maintain legible light/dark variants when requested.
- Apply a recognizable product visual direction appropriate to its users: precise hierarchy, excellent typographic rhythm, purposeful whitespace and consistent component states.
- Avoid indiscriminate gradients, excessive card nesting, generic hero-like compositions inside software, decoration that hides actions, and irrelevant stock graphics.
- Prefer existing established components; do not install a new component library or rewrite the theme without reason and approval.
- Use meaningful color for status and actions; don't communicate status only through color.
- Support long Spanish labels, currencies, dates, numbers, truncation/expansion and translated text.

## 3. Adaptive device and platform patterns
- Desktop: leverage width for overview/detail layouts, keyboard interaction, efficient tables, drag operations only when discoverable and accessible, persistent navigation if space allows.
- Tablet: support touch plus pointer/keyboard; collapse sidebars carefully, adapt split views and forms, respect portrait/landscape.
- Mobile web: one primary task per viewport, clear top-level navigation, touch-sized controls, sheets for filters, contained scrolling for complex data, no viewport-wide overflow.
- PWA: account for browser viewport changes, safe areas, back navigation, installability only when requested, connection/offline states and browser limitations; don't claim native functionality.
- Native iOS/Android or desktop apps: follow platform conventions, back gestures, focus/window behavior, accessibility and system status areas; don't blindly transplant web interaction patterns.
- Test representative widths (320/375/390/768/1024/1280/1440 CSS px where applicable), landscape and 400% zoom/reflow where tools permit. An untested size must remain marked unverified.
- Don't infer touch solely from width; use pointer/hover capability and real device tests when possible.

## 4. Component behavior and interaction states
- Controls need explicit purpose, actionable labels, predictable focus, disabled/loading/success/error states and feedback after confirmed operations.
- Forms need logical sections, input types, inline validation, good keyboard paths, preservation of entered data after errors and confirmations for destructive actions.
- Tables and collections need meaningful filtering, sorting, pagination, bulk actions and stable navigation. Preserve all features when adapting from desktop table to mobile cards.
- Drawers and dialogs need focus handling, escape/back behavior, scrolling, layering and clear exits; don't hide essential controls behind hover-only interactions.
- Handle realistic stress data: long names/emails, missing photos, zero and large totals, empty results, status extremes, multilingual copy and errors. Test using fixtures/staging, not production modification.

## 5. Motion and tactile quality
- Every animation must serve feedback, continuity, explanation or a rare delight moment; frequently repeated/keyboard-heavy actions should be immediate.
- Prefer lightweight CSS transitions for simple states; consider complex animation libraries only for justified gestures, springs or layout transitions.
- Favor transform/opacity for smoothness, avoid broad transition: all, expensive animated layout and gratuitous blur.
- Use short, interruptible easing for ordinary UI; preserve reduced-motion preferences and provide non-motion equivalents.
- Touch feedback should be immediate, avoid sticky hover, scrolling traps, unwanted zoom and unintended tap highlights. Verify on real mid-range devices when possible.
- Never promise 60/120 fps without measurement or profiling.

## 6. Design review and variants
- For review-only requests: report strengths, concrete issues, severity/impact, evidence and proposed remedies without editing.
- For design alternatives: produce 2–3 meaningfully different directions (not minor recolors), including navigation, density, hierarchy and interaction trade-offs; let the user choose before replacing a working screen.
- Use an iterative but bounded visual check: inspect rendered result at representative sizes, correct issues as a coherent batch and check once more when tools allow.
- Reject superficial improvements that reduce functionality, contrast, readability, performance or task speed.

## 7. Performance, accessibility and release gates
- Accessible name, label, contrast, keyboard/focus visibility and touch target sizes; do not disable zoom or accessibility settings.
- Measure/consider data density, expensive rerenders, heavy animation and image/media costs. Don't install dependencies for one effect.
- Distinguish findings verified with browser/device tools from code-based predictions. Avoid fabricated screenshots or test outcomes.
- Before marking UI work complete, report platforms/screen widths tested, key flows verified, changed files and remaining risks.

## 8. Compatibility and skill routing
- This skill is product-agnostic and can be installed as SKILL.md in Google Antigravity or imported as a workspace skill in Lovable where supported.
- Apply existing TOROBYTE CRM-specific skills only when the project is a CRM/ERP and the requested task warrants it; this skill does not replace security, authorization or backend reviews.
- Reuse external Impeccable, UI/UX Pro Max or Emil skills as references only when installed and relevant. Do not assume their CLIs, runtime commands, scripts, browser hooks or binaries are available inside Lovable or Antigravity.
- Do not bundle or run third-party installers implicitly. Ask for separate authorization for dependency installation, deployment or changes beyond the UI.
