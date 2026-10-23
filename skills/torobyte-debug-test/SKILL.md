---
name: torobyte-debug-test
description: Use when a CRM feature has an error, broken flow, repeated fix failures, or the user explicitly requests functional tests or regression verification. Not for pure UI styling.
---
# TOROBYTE CRM — Root-cause debugging and tests
- First reproduce or precisely characterize the symptom. Inspect relevant console/build/API/Edge Function/DB logs and deployment version before modifying code; formulate a cause supported by evidence.
- Separate build, state/cache, auth/RLS, external API, configuration, timing and live-vs-preview failures. Fix root cause, not by hiding the error.
- After two failed attempts or recurring regression STOP editing; summarize attempts and their effects, inspect alternative causes, propose a new approach before proceeding.
- Never roll back code or migrations without explicit approval. A Git rollback does not restore DB state.
- Choose smallest meaningful verification: UI/interaction check for visual changes, unit/integration tests for domain rules, backend permissions tests and E2E for cross-layer core flows.
- Prioritize login, organization isolation, form validation, main CRUD paths, billing, exports, API errors and any bug just fixed.
- Use isolated test data and sandbox credentials for writes. Do not run destructive tests against production without authorization.
- Report passes, failures and untested items separately. No invented test outcomes; retain regression tests that protect real behaviors.
