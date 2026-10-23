---
name: torobyte-responsive-design
description: Use when designing, adapting or auditing CRM/ERP/SaaS interfaces for desktop, tablet, mobile browsers or mobile app-like/PWA experiences; including responsive tables, sidebars, forms, dashboards, touch navigation and device-specific layouts. Not for unrelated backend changes.
---
# TOROBYTE — Responsive enterprise design
## Intent and constraints
Create professional, compact and accessible administrative interfaces while preserving project brand, existing components, routes, business behavior and permission checks. Audit/design-only tasks are read-only. Do not switch frameworks or produce native iOS/Android code unless explicitly requested.

## Device strategy
- Desktop >=1280px: persistent/sidebar navigation when room allows; information-dense data grids, side filters, multi-column forms, split panes, KPIs and keyboard shortcuts when appropriate.
- Small desktop/tablet landscape ~1024–1279px: collapsible sidebar, balanced cards, tighter grid, keep frequent actions visible.
- Tablet portrait ~768–1023px: navigation drawer/rail; prioritize 1–2 column layouts, adaptable forms, sticky relevant actions and touch-friendly dropdowns.
- Mobile web ~320–767px: prioritize a single-column task flow, clear primary action, collapsible search/filters, readable status summaries and no page-wide horizontal overflow.
- App-like mobile/PWA: when requested, consider bottom navigation for 3–5 top-level destinations, safe-area inset padding, full-screen sheets for complex forms, pull-to-refresh only when appropriate, back-navigation behavior, offline/connection feedback and installable-PWA constraints. Do not represent a PWA as a native app.
- Treat widths as guides, not strict device detection; also verify intermediate widths, landscape and zoom.

## CRM component patterns
- Wide data tables: permit scrolling inside the table container, keep important ID/status/action columns accessible; on narrow viewports consider card/list presentation or explicit column prioritization WITHOUT losing sort, filters, pagination, bulk actions or data context.
- KPI dashboards: fluid card grids; group metrics by task; avoid tiny unreadable charts. Show periods, units, empty/error/loading states.
- Filters and search: desktop visible filter toolbar; tablet/mobile sheet or drawer with active-filter indicators, clear/apply actions and preserved query state.
- Forms: logical sections, autocomplete/input types, visible validation, large enough tap controls; prevent keyboard overlay and accidental data loss; complex forms may become a step flow only if behavior permits.
- Menus/modals: constrain to viewport, scroll within dialog when necessary, accessible focus trapping and restore, visible close/back actions, no hover-only essential controls.
- Files, charts, timelines: responsive media, viewport-aware legends/tooltips, contained scrolling for truly two-dimensional content.
- Support light and dark modes via semantic tokens; all text/buttons/icons must retain contrast.

## Measurable acceptance checks
1. Test widths 320, 375, 390, 768, 1024, 1280 and 1440 CSS px when preview tools permit, plus 400% zoom/reflow at 1280px.
2. No page-level horizontal scrolling; tables, code and diagrams may scroll inside their own labeled containers.
3. No clipped text/actions, overlapping fixed bars, blocked form fields or inaccessible navigation. Avoid arbitrary fixed widths and heights for growing content.
4. Form field text >=16px on mobile to avoid unwanted iOS zoom. Meet WCAG 2.2 AA 24x24 CSS px target-size rule (or qualifying spacing/exception); aim ~44x44 for primary touch interactions.
5. Honor virtual keyboard and safe-area insets where applicable; usable with touch, keyboard, pointer and screen-reader labels. Keep visual order aligned with DOM focus order.
6. No unannounced workflow regression across viewport modes: CRUD, search, sort, filters, bulk selection, status/actions and permissions remain available.
7. Diagnose overflow causes (min-width of flex/grid, fixed sizes, unbroken values) rather than hide all overflow on body.
8. Log verified device widths and any untested screen states; do not claim testing where no preview was performed.

## Procedure
1. Inspect existing layout, tokens, breakpoints, route shell and user workflows.
2. List responsive pain points per desktop/tablet/mobile/app-like mode and choose intended adaptations.
3. If asked to propose only, provide wireframe/layout specs without edits.
4. If implementation authorized, change only relevant UI code, preserve existing API/data behavior.
5. Validate representative widths, empty/loading/error states, keyboard/touch and dark mode when possible; report results and risks.

## Styling direction
Prefer premium enterprise software over marketing styles: disciplined hierarchy, compact spacing, reduced visual noise, contextual secondary information and obvious actions. Mobile adaptation is not 'shrink the desktop screen': restructure hierarchy while preserving capabilities.
