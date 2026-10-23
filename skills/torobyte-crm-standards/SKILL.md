---
name: torobyte-crm-standards
description: Legacy compatibility entry for older TOROBYTE CRM projects. Use only when an existing Lovable workspace explicitly invokes torobyte-crm-standards; prefer torobyte-crm-core and focused companion skills for new tasks.
---
# TOROBYTE CRM Standards — Legacy
This original all-in-one skill has been modularized. Do not combine this legacy entry with all six new skills in a single task.
- For general CRM architecture and maintainability, use `torobyte-crm-core`.
- For dashboards, tables and forms appearance, use `torobyte-ui-standards`.
- For responsive desktop/tablet/mobile/PWA layout, use `torobyte-responsive-design`.
- For authentication, authorization, RLS, tenant separation, APIs and secrets, use `torobyte-security`.
- For read-only technical audits, use `torobyte-code-audit`.
- For debugging and tests, use `torobyte-debug-test`.
Do not modify source for audit or design-only requests. Preserve current stack, brand, behavior and data unless explicitly authorized.
