---
created: "2026-04-13"
tags:
  - TIQ
  - ILS
---

# TIQ — ILS program lifecycle and quote states

Workshop mapping from **marketing lifecycle** to **program states** for **ILS flows in TIQ**. Some states may need **new enums** where existing names do not fit.

| Business phase | Typical duration / meaning | Program state (conceptual) |
| --- | --- | --- |
| Pre-marketing (optional) | Early | **NEW** (possible new state) |
| Marketing | ~2 weeks; rough-to-finalized package | **Quote** |
| Launched / on risk | Live | **Written** |
| Reset with year | Annual / structural reset | **New enum** — does not map cleanly to current names |

**Quote status** line in tooling should reflect this progression where TIQ surfaces program/quote workflow.

## See also

- [[ILS Workshop Day 1]]
- [[TIQ — ILS enablement (SKU, tenant, attachments, RDX)]]
