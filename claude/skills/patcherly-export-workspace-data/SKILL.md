---
name: patcherly-export-workspace-data
description: Export Patcherly workspace data via MCP CSV tools matching dashboard exports
license: Apache-2.0
---

# Export workspace data (Patcherly MCP)

**Safety:** never paste OAuth tokens or connector keys into chat; do not dump large CSVs into chat unless the user asks; export tools need the matching `mcp:*:export` scope.

Use dedicated export tools (not list+get loops) when the user wants CSV parity with dashboard **Export** buttons:

| Tool | Scope required | Notes |
|------|------------------|-------|
| `export_targets` | `mcp:targets:export` | Same columns as Targets page CSV |
| `export_errors` | `mcp:errors:export` | Optional `status` filter; same columns as Errors page |
| `export_metrics` | `mcp:metrics:export` | KPI snapshot CSV; optional `preset` |
| `export_usage` | `mcp:usage:export` | Billing-period usage CSV |
| `export_audit` | `mcp:audit:export` | Tenant audit trail CSV |

1. Confirm the user's workspace policy includes the **Export** cap for that domain (Profile → MCP).
2. Call the export tool; result includes `content` (CSV text), `row_count`, and `format: csv`.
3. Save or summarize the CSV for the user — do not paste large exports verbatim into chat unless they ask.
4. If a tool is missing from `tools/list`, the token lacks export scope or RBAC (e.g. metrics export needs view-metrics permission).
