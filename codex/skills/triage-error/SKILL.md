---
name: triage-error
description: Triage a Patcherly error via MCP read tools before suggesting fixes
license: FSL-1.1-Apache-2.0
---

# Triage error (Patcherly MCP)

**Safety:** never paste OAuth tokens or connector keys into chat; confirm before any `confirm=true` destructive tool; prefer read tools before writes; workspace is frozen from consent.

1. Call `list_errors` with a small limit to find the error id.
2. Call `get_error` for details (no secrets in chat).
3. If analysis is stale, suggest `trigger_analysis` only after user confirms quota usage.
4. Use `approve_fix` / `reject_patch` / `ignore_error` only when the user explicitly requests an action.
