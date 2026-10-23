---
name: torobyte-crm-core
description: Use when building or modifying a TOROBYTE CRM, ERP, inventory, SaaS or administration feature to preserve established architecture, shared business rules and enterprise UI consistency. Not for standalone audits, security scans or responsive-only redesigns.
---
# TOROBYTE CRM — Core
- Detect the existing React/TypeScript, backend, routing, styling, cache and data conventions before changing anything. Do not impose Supabase, Bootstrap, SWR or libraries on a different architecture.
- Keep Spanish interface copy, professional compact CRM layouts, clear navigation, meaningful KPI/data summaries and consistent project tokens. Preserve existing brand colors unless asked otherwise.
- Separate presentation, typed API/data access, hooks and domain/business rules. Centralize shared validation, status, permissions and calculations.
- Use established Query keys/mutation invalidation if TanStack Query exists; never mix with SWR. Use accurate CLP, date, number and timezone conventions when relevant.
- For existing projects make the smallest change solving the request. Preserve routes, forms, exports, filters, roles, integrations and unrelated functionality.
- Identify affected callers and contracts; test the change proportionately. Do not claim verification you could not perform.
- Analysis, review, audit and design proposal requests are READ-ONLY. Ask for explicit approval before destructive schema/data/security operations.
- Use specific companions only when relevant: torobyte-ui-standards, torobyte-responsive-design, torobyte-security, torobyte-code-audit, torobyte-debug-test.
- Return short completion report: scope, changed files, checks run, remaining risks.
