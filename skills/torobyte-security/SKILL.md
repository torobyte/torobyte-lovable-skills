---
name: torobyte-security
description: Use when CRM work touches login, sessions, permissions, multi-tenant data, sensitive records, API credentials, Edge Functions, webhooks, uploads or payment/data security. Not for cosmetic UI-only changes.
---
# TOROBYTE CRM — Security
- Determine actual backend and identity provider; authentication is not authorization. Frontend UI restrictions never substitute for backend enforcement.
- Enforce organization/account scopes for every read/write and role checks for every action; test cross-tenant denial with distinct accounts when authorized.
- For Supabase inspect relevant SELECT/INSERT/UPDATE/DELETE RLS policies and SECURITY DEFINER search_path/privileges; never use service-role keys client-side. Do not create policies or migrate tables without authorization.
- Store external API tokens, OAuth secrets and webhook signing secrets server-side; redact credentials from errors, logs, screenshots and audit output.
- Validate all untrusted inputs at backend boundaries; parameterize queries; apply context-appropriate output encoding; guard file uploads by type, size, path and access control.
- Verify webhook signatures when supported; handle replay, duplicates and idempotent side effects. Timeout and retry external requests safely; never blindly retry non-idempotent writes.
- Apply atomic/concurrency-safe rate limiting where needed, not read-modify-write counters.
- For security review only: read-only findings with confidence, evidence, impact and remediation; do not alter production data or access controls.
