---
name: patcherly-triage-error
description: Triage a Patcherly error via MCP read tools before suggesting fixes
license: Apache-2.0
---

# Triage error (Patcherly MCP)

**Safety:** never paste OAuth tokens or connector keys into chat; confirm before any `confirm=true` destructive tool; prefer read tools before writes; workspace is frozen from consent.

**Data access:** Use Patcherly MCP tools for this session’s workspace data. Call `get_error` for analysis text and patch; call `get_audit_events` for audit. Do not invent other access paths or guess from ingest context alone when `get_error` is available.

1. Call `list_errors` with a small limit to find the error id (summary includes `resolution` / `resolution_path` / `ignore_reason` when set).
2. Call `get_error` for details. The payload includes nested **`analysis`**: `analysis.available`, `analysis.fix` (unified diff), `analysis.explanation`, `analysis.confidence`, `analysis.patch`, and related fields. Use those for triage. If `analysis.available` is false, analysis has not run yet (suggest `trigger_analysis` only after the user confirms quota). Disposition tips: `not_needed` → ignored + Patch not needed; `manual_*` → fixed + Manually fixed; `patch_wrong` / `analysis_wrong` / `both_wrong` → stays analyzed + Bad patch (Re-analyze); `source_changed` → analyzed + Source changed (Re-analyze / Mark fixed — not a reject choice).
3. For timeline / who-did-what, call `get_audit_events` (optional `export_audit` when the user wants CSV).
4. If analysis is stale or missing, suggest `trigger_analysis` only after user confirms quota usage.
5. Use write tools only when the user explicitly requests an action:
   - `approve_fix`
   - `retry_apply` (re-dispatch apply for approved / failed with a fix)
   - `reject_patch` with required `resolution` (`manual_suggestion` | `manual_own` | `not_needed` | `patch_wrong` | `analysis_wrong` | `both_wrong`)
   - `mark_fixed` with required `resolution` (`manual_suggestion` | `manual_own`)
   - `ignore_error` (pre-analysis hide — not a substitute for reject-patch)
