---
name: torobyte-crm-standards
description: >-
  Use when designing, building, reviewing or modifying TOROBYTE-style CRM,
  ERP, SaaS, dashboards, inventory, administration, or multi-tenant business
  application features in Lovable. Apply enterprise UI consistency, safe
  React/TypeScript architecture, secure backend boundaries, permission checks,
  data integrity, and regression prevention. Do not use for public marketing
  websites, landing pages, SEO content, or unrelated editorial tasks.
---

# TOROBYTE CRM Standards

## Mission and precedence

Build maintainable, polished enterprise applications, not marketing websites.
Respect the user's explicit task, existing project architecture, and verified
business behavior over generic examples in this skill. The skill is a **guide**,
not authorization to change files, tables, permissions, dependencies, or deploy.
If the user requests an audit, analysis, or design proposal only: **read-only**.

Before every task, identify the exact scope and preserve all unrelated behavior.
Do not invent project structures or claim tests were run when they were not.

## 1. Enterprise UI and design system

- Produce a professional, compact, modern CRM interface with clear hierarchy,
  balanced whitespace, predictable alignment, subtle borders/shadows and
  restrained accent colors. Prefer the project's existing brand tokens,
  components, icon set, fonts and navigation patterns; do not change its base
  colors without permission.
- Desktop: consistent sidebar/header/content hierarchy. Mobile/tablet: usable
  navigation, tables, actions, modals and forms without horizontal overflow.
- Use existing stack and patterns (often React + TypeScript + Tailwind + shadcn/ui).
  **Never install Bootstrap, Font Awesome, or another UI library just to satisfy
  a preference if the project already uses shadcn/Tailwind.** Reuse existing
  components and theme tokens instead.
- Use compact and readable KPI cards with contextual labels, time ranges and
  understandable number formatting. Charts need legends, units, tooltips,
  empty/error/loading states and accessible color contrast.
- Data grids: server-side pagination/filtering/sorting for large datasets,
  search with debounce when appropriate, useful density, stable row keys,
  clear bulk actions, state persistence only when requested, and permission-aware
  actions. Never fetch all rows solely for a table in a large CRM.
- Forms: grouped fields, explicit labels, required indicators, inline validation,
  meaningful error messages, loading/disabled states, confirm destructive
  actions, accessible dialogs and keyboard navigation.
- Support light/dark mode when requested or already supported. Use semantic
  tokens; avoid hard-coded colors that break either mode.
- Language: use Spanish in user-visible UI unless the project explicitly uses
  another locale. Preserve existing translations and date/number formats.
  Handle CLP, decimal separators, time zones and Chilean date conventions when
  applicable; never silently reinterpret currency or timestamps.

## 2. Architecture and separation of concerns

- Inspect current files, libraries, routes, data contracts and conventions first.
  Match the established architecture instead of imposing a new folder scheme.
- Separate visual components, page composition, hooks/query orchestration,
  domain rules, typed API clients, validation schemas and shared utilities.
- Prefer small focused components and low coupling; file length is an indicator,
  not a mandatory split threshold. Avoid god components, circular dependencies,
  duplicate business rules and hidden side effects.
- Use strict TypeScript where available; no unnecessary `any`, unchecked
  assertions, silent promise failures or opaque one-line conditions.
- For server state in TanStack Query projects, use existing query keys,
  hooks, loading/error states and mutation invalidation. Do not introduce SWR
  alongside TanStack Query, or replace an established state library by default.
- Do not optimize prematurely. Memoization, virtual lists, subscriptions and
  code splitting must have a concrete benefit; avoid excess abstraction.

## 3. Backend/API boundaries and security

- Detect the actual backend first: Supabase/Postgres, Lovable Cloud, custom API,
  or other. Never assume Supabase is present or migrate technology implicitly.
- Authentication is **not** authorization. Enforce tenant and role access on
  backend/database, not only by hiding frontend buttons.
- In multi-tenant apps, verify every read/write is scoped to the authorized
  organization/account; test or describe cross-tenant denial scenarios.
- With Supabase, require appropriate RLS on applicable tables and review
  SELECT/INSERT/UPDATE/DELETE policies; privileged/service keys must never
  enter the browser. Watch for recursive policies and unsafe SECURITY DEFINER
  functions. Never apply migrations/RLS changes without authorization.
- Keep API keys, OAuth secrets and integration tokens server-side in supported
  secrets management. Never embed them in client code, URLs, logs or examples.
- Validate and normalize untrusted inputs at backend boundaries and, where
  useful, at the UI with shared schemas. Use parameterized queries and escaping
  appropriate to output contexts. Guard file uploads by type, size, access,
  path and signed URLs as applicable.
- For external API calls, handle timeouts, non-2xx status, pagination,
  transient failures, provider rate limits, retry/backoff when safe, and redact
  sensitive logs. Do not automatically retry non-idempotent operations.
- Webhooks: verify authenticity where provider supports it, deduplicate events,
  guard against replay, and make side effects idempotent.
- Rate limiting must be enforced with concurrency-safe implementation; never
  treat a naive read-then-write counter as production-safe.

## 4. Data integrity and business rules

- Use a single source of truth for roles, statuses, business validations and
  financial calculations; avoid inconsistent reimplementations in the UI.
- Protect writes with appropriate constraints, foreign keys, transactions and
  concurrency handling where applicable. Preserve existing data and audit
  history. Consider idempotency and rollback for integrations and scheduled jobs.
- Use explicit UTC storage/timezone conversion patterns already defined by the
  project; do not compare locale strings as dates.
- Prefer soft delete/archive only when aligned with business requirements;
  never silently change deletion semantics.
- Ensure changes account for loading, empty, error, offline/retry (if relevant),
  and unauthorized states; never show a success before the backend confirms it,
  except intentional optimistic UI with rollback.

## 5. Safe change process (mandatory for existing projects)

1. **Inspect:** Read affected files, callers, data contracts, role checks and
   current UI conventions. Identify actual behavior before proposing edits.
2. **Scope:** State what will change and what will explicitly remain untouched.
   If the request is ambiguous and the decision could destroy data or change
   security, request approval before proceeding.
3. **Plan:** Choose the smallest cohesive diff. Flag dependencies, migration
   risk, user-visible changes, backward-compatibility and tests.
4. **Implement:** Only when authorized. Preserve routes, public APIs, columns,
   permissions, existing forms, filters, exports, reports and interactions.
5. **Verify:** Run available read-only checks and appropriate tests where
   permitted (TypeScript, lint, affected interactions, auth/roles, tenant
   isolation, API failures, responsive UI). Never fabricate results.
6. **Report:** Summarize changed files, verified behavior, untested risks and
   any manual validation needed. Do not report completion of actions not done.

For database changes, plan a backwards-compatible migration: add -> backfill
-> switch -> remove later. Explicitly disclose any destructive SQL and seek
approval before execution.

## 6. Audit-only mode

When asked to audit, inspect or evaluate, make **zero** code/data/config changes.
Report each grounded finding with: ID, severity (CRITICAL/HIGH/MEDIUM/LOW),
file + line if available, concise evidence, consequence, proposed fix,
regression risk, and verification method. Separate confirmed findings from
suspicions and unavailable checks; prioritize critical security and data-loss
risks, then broken workflows, then maintainability. Avoid treating line count
as a bug by itself.

## 7. Skill routing / compatibility

Combine with relevant workspace skills when present, especially:
- `refactor-safe-diff` for surgical existing-code edits.
- `supabase-rls-and-auth` and `multi-tenant-backend` only when that stack applies.
- `tanstack-query-alternative` and `tanstack-mutations-and-invalidation` only
  when the project uses TanStack Query.
- `server-input-validation`, `api-error-handling`, `edge-functions-and-webhooks`
  for secure API/backend tasks.
- `shadcn-patterns`, `dashboard-charts-recharts`, `error-states-and-empty-ui`,
  `dark-mode-and-theming` for compatible UI work.
- `migration-playbook` only for approved schema work.
- `lovable-ship-checklist` only for release readiness.
Do not apply every skill to every task or import incompatible frameworks.

## Definition of done

A change is done when it fulfills the explicit request, preserves unrelated
behaviors, respects existing architecture and security boundaries, and has
an honest account of validation and remaining risks. **Do not redesign the
whole app or refactor unrelated modules as a side effect.**