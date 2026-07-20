---
created: "2026-04-13"
tags:
  - TIQ
  - ILS
---

# TIQ — ILS program model (Program, IED, ILC)

Conceptual mapping for **enabling ILS flows in TIQ**. In this model, an **ILS cat bond aligns with a program** (same abstraction at the workshop level).

## Flow

| Concept | Role |
| --- | --- |
| **Program** | Defines coverage, structure, perils, regions; may be funded by cat bonds. |
| **IED** | Exposure / portfolio data. |
| **ILC** | Loss side — analytics outputs (losses, EP curves, AAL, PML). |

```text
Program
├─ coverage, structure, perils, regions
├─ may be funded by cat bonds
IED → Exposure / portfolio
Analytics / models
ILC → Losses, EP curves, AAL, PML
```

## See also

- [[ILS Workshop Day 1]]
- [[TIQ — Reference loss source and share factors]]
- [[TIQ — ILS program lifecycle and quote states]]
