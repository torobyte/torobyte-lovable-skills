---
name: torobyte-ui-standards
description: Use when designing or refining visual CRM interfaces such as dashboards, navigation, KPI cards, data tables, forms and dialogs. Focus on visual consistency and usability, not backend security audits or full responsive testing.
---
# TOROBYTE CRM — Interface design
- Preserve project branding, component library, theme tokens and typography; do not change base colors or install a second UI framework without permission.
- Design enterprise-grade, restrained, information-dense yet readable UIs: sidebar/topbar, breadcrumb, clear title/actions, tight grid, subtle border and deliberate hierarchy.
- KPI cards require label, unit/timeframe and useful context; charts require axes, units, accessible contrast and loading/empty/error presentation.
- Tables require meaningful headers, search/filter/sort/pagination when warranted, clear row actions, stable identifiers, compact spacing and confirmation for destructive actions.
- Forms use grouped fields, accessible labels, validation feedback, save progress, loading/disabled and server-error states.
- Use consistent semantic statuses, action buttons, icons, spacing and responsive tokens; avoid excessive decoration and fragile fixed sizes.
- For tasks involving device layouts or mobile app-like flows, also use torobyte-responsive-design.
- Design-only requests must not edit source; implement only on explicit authorization and scope.
- Verify with a screenshot/preview when available; do not claim the interface was viewed unless it was.
