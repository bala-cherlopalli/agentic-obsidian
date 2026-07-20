---
created: "2026-04-13"
tags:
  - TIQ
  - ILS
---

# TIQ — Reference loss source and share factors

Technical concept for **ILS program configuration** in TIQ (workshop notes).

## Reference loss source

- **Reference Loss Source** — user chooses an **`analysisId`**.
- That choice defines the **reference risk source** plus **market exposures** (geography-wise **share factors**).

## Share factor sources in a program

Within a program, **share factor risk source** can come from:

1. **Existing reference loss source** + **simulationSet** + **share factor resolution**, or  
2. An **existing risk source** as the **reference risk source**, with **share factors** aligned to **market exposures** (shares by resolution).

## See also

- [[ILS Workshop Day 1]]
- [[TIQ — ILS program model (Program, IED, ILC)]]
- [[TIQ New Endpoints]]
