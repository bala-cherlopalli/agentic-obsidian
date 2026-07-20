[[Guy Carpenter]]
[[2026-04-28]]

## Meeting Summary

**Purpose**

- Check progress since last sync with GC.
- Validate resolution of prior issues (PLT vs ELT).
- Discuss export workflows, performance concerns, and data structure alignment.
- Clarify exposure export, event reference data, and HD vs DLM event logic.
- Align on timelines and cadence.

**Key Outcomes**

- **PLT flag change (ELT → PLT)**
    
    - Confirmed resolved. GC successfully generated PLT parquet files and loaded them to SQL Server.
    - No blocking issues identified related to PLT.
- **Export polling inefficiency**
    
    - GC flagged “black box” polling for export readiness.
    - Bala outlined:
        - **Short‑term workaround**: use _export size estimation task_ to bucket jobs (small/medium/large) and adjust polling intervals.
        - **Long‑term direction**: webhook‑based job notifications (push instead of pull).  
            _No committed release timeline._
- **Exposure export (Parquet)**
    
    - Current exposure export format differs from RDM (legacy structure + `.crc` checksum files for backward compatibility).
    - Bala recommended an **alternate, more polished path**:
        - Use **variation‑based export** (snapshot generated when a model run occurs).
        - Faster and closer to RDM‑like structure.
    - Documented that `.crc` files are **checksums**.
    - Some parquet files appearing empty; likely data or tooling issue—needs investigation.
- **Documentation**
    
    - Export APIs are documented in the Developer Portal (Swagger available).
    - Bala shared API links in chat and agreed to send clarifying samples.
- **Event reference data**
    
    - No new versioned Events Reference API yet.
    - Still on **legacy endpoints**; conversion to a public versioned API is **lower priority**, to be evaluated in **June planning** (possible H2 work).
    - Clarified:
        - `isHD = true` is the correct filter for HD events.
        - Same event ID can legitimately exist across multiple perils (HD + DLM).
        - Separate HD tables exist for performance reasons.
- **Databricks / MCP / Marketplace data**
    
    - Data shown is primarily **Credit / Ratings**, not Insurance Solutions.
    - Not immediately applicable to current GC insurance workflows.
- **Timeline & cadence**
    
    - GC targeting **end of June / July** for rollout phases.
    - Agreed to **bi‑weekly 30‑min check‑ins**, cancel if no agenda.

---

## Action Items / Tasks

### Moody’s (Bala / Team)

- [ ] Share **sample requests/responses** for: #task
    - Export size estimation task.
    - Variation‑based export flow.
- [ ] Review **parquet files with missing/empty data** once GC shares zipped samples. #task
- [ ] Analyze **schema differences** between: #task
    - Exposure export (legacy format).
    - Variation‑based export.
- [ ] Keep GC informed on **webhook notification** initiative progress (no promise on timeline). #task
- [ ] Follow up internally on **event reference API** planning (June cycle). #task
- [ ] Clarify documentation references if GC needs additional Swagger guidance. #task

### GC (Asokan / Team)

- Try **export size estimation API** and implement polling buckets (short‑term).
- Test **variation‑based export** using existing model run variation IDs.
- Zip and share **problematic parquet outputs** (empty/missing tables) for Moody’s review.
- Continue validating **HD vs DLM event mapping** using `isHD` flag.
- Prepare internal rollout plan targeting **end‑June / July**.

### Joint

- Maintain **bi‑weekly check‑ins** (30 min).
- Use email async updates if no meeting topics.

---

If you want, I can also:

- Convert this into a **MoM email**,
- Extract just **Moody’s‑owned tasks for a JIRA checklist**, or
- Rewrite as a **client‑shareable summary**.