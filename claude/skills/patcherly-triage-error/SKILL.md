---
name: patcherly-triage-error
description: Triage a Patcherly error via MCP read tools before suggesting fixes
license: Apache-2.0
---

# Triage error (Patcherly MCP)

**Safety:** never paste OAuth tokens or connector keys into chat; confirm before any `confirm=true` destructive tool; prefer read tools before writes; workspace is frozen from consent.

1. Call `list_errors` with a small limit to find the error id (summary includes `resolution` / `resolution_path` / `ignore_reason` when set).
2. Call `get_error` for details (no secrets in chat). Disposition tips: `not_needed` → ignored + Patch not needed; `manual_*` → fixed + Manually fixed.
3. If analysis is stale, suggest `trigger_analysis` only after user confirms quota usage.
4. Use write tools only when the user explicitly requests an action:
   - `approve_fix`
   - `reject_patch` with required `resolution` (`manual_suggestion` | `manual_own` | `not_needed`)
   - `mark_fixed` with required `resolution` (`manual_suggestion` | `manual_own`)
   - `ignore_error` (pre-analysis hide — not a substitute for reject-patch)
