---
name: torobyte-code-audit
description: Use ONLY when explicitly asked to audit, inspect, assess technical debt, find dead code or plan cleanup across a Lovable CRM project. Read-only by default; no automatic fixes.
---
# TOROBYTE CRM — Codebase audit
## Phase 1 — READ ONLY
- Inspect routes, components, hooks, API clients, types, schemas, functions, auth, data migrations, dependencies, styles, assets, tests and configuration available.
- Report files >300 lines as review candidates, not automatic defects; check god components, duplicated rules, naming, boundaries, dead code, function complexity, hardcoded values, performance and security.
- Examine suspected dead code against lazy imports, feature flags, runtime registration, DB triggers, webhooks, scheduled jobs, external consumers and build config. If unsure say **requires verification**.
- For every grounded finding provide ID, severity CRITICAL/HIGH/MEDIUM/LOW, exact file/line if available, evidence, consequence, proposed fix, regression risk, confidence and validation.
- Sort by real impact, not line count. Identify missing inspections and tests honestly. Group recommended cleanup into independent batches.
- Do not edit, format, rename, delete, install, migrate, deploy or run data-changing checks during audit.
## Phase 2 — ONLY BY EXPLICIT APPROVAL
- Execute only the named findings/batches explicitly approved by the user. Small diffs, preserve behavior, verify tests and report changed files.
- If requested to 'clean up' without a prior approved audit, perform phase 1 and stop.
