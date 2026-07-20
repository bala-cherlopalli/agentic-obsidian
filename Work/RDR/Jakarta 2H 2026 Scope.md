---
created: "2026-06-16"
tags:
  - RDR
  - jira
  - jakarta
---

# Jakarta 2H 2026 Scope

Risk Data Refinery 2H 2026 semester ("Jakarta") Jira scope — one initiative (PLAN-988) and eight epics, all now created in Jira with their child stories (all Ready For Review).

- Source: `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/Jakarta Scope/`
- Jira: initiative **PLAN-988** — https://rmsrisk.atlassian.net/browse/PLAN-988. All 8 epics (IRP-102, IRP-108, IRP-113, IRP-119, IRP-124, IRP-129, IRP-134, IRP-138) and their stories (IRP-103 through IRP-141) are children of PLAN-988 and set to Ready For Review. Epics mirror the IRP-102 template (Semester = Jakarta, Major, fix version Backlog); stories carry Product = RDR.
- Builds on July GA ([[Slip Stream GA Jira Initiative Draft]], [[Sov Stream GA Jira Initiative Draft]], PLAN-949).
- Authoring convention: each epic = a lean markdown doc (Summary, Business Need, Business Value/Impact, Scope as JTBDs, NFRs, Acceptance Criteria) + a companion `*-stories.md` for child stories; each story calls out its **UX** and **API** JTBDs explicitly (API JTBDs labeled `IRP_API`/`IRP-API`). In Jira, the epic body goes in Description and AC goes in the Acceptance Criteria field (ADF custom field `customfield_16495`). All 8 epics follow this lean structure, each with a companion `*-stories.md`.

## Initiative

**Risk Data Refinery: 2H 2026 Jakarta - Beyond GA: Quality, Cost and Reach Enhancements**. Enhances RDR beyond the July GA across three pillars: Quality (per-tenant custom context/rules + closed-loop feedback; Quality Intelligence via LLM Judge), Cost (token/AI cost optimization), and Reach (Enriched Risk Data enrichment; Open Exposure Data export; completing the public Retrieve APIs). Also includes an ILS offering-material discovery spike and a rolling AS-owned minor processing/quality track.

- Terminology: **ERD = Enriched Risk Data** (Moody's enriched property/building attributes; Retrieve -> Review -> Apply); **OED = Open Exposure Data** (Oasis open standard).
- GA licensing/control model (corrected): no Slips/SOVs license split — an RDR-licensed user can bring slips, SoVs, or both; usage/access governed by metering, quota, and group-based data access. See [[Architecture Notes]].
- Out of scope (dependency only): IRP app embedding (Alisha's app team). Preview-feedback minor enhancements are now **Epic 8** (AS-owned) — no longer out of scope.
- Initiative doc trimmed to core sections (Introduction, Business Need, Scope, Business Impact, Success Criteria, Out of scope); Users / Release Phases / Stakeholders / Dependencies / Risks sections removed per product owner.

## Eight epics

1. **Tenant-specific custom context, rules & closed-loop feedback** — move from GA feedback-*capture* (PP-3/SS-2) to per-tenant *adaptation*: tenant-scoped custom context, configurable rules, closed loop, strict isolation; governed by a new **Risk Data Refinery Admin** role/actions. **One of the most heavily requested asks in demos/Preview.** Jira: epic **IRP-102**; 9 JTBDs, consolidated into 5 stories — all in Jira and Ready For Review: 1.1 IRP-103, 1.2 IRP-104, 1.3 IRP-105, 1.4 IRP-106, 1.5 IRP-107.
2. **Token cost optimization** — per-submission AI cost telemetry, tiered model routing, prompt/context compression, caching, batching; eval gate holds first-pass accuracy >= 95%. Baseline AI COGS ~$0.92/SoV, ~$0.52/slip (see [[Margin Analysis]]). Jira: epic **IRP-108**; 4 stories IRP-109–112 (all Ready For Review).
3. **Quality Intelligence via LLM Judge** — LLM Judge surfaces data-quality issues in the exposure data, above all **cross-column cohesion/plausibility** (values individually valid but jointly implausible, e.g., a 50-story wood-frame building); plus confidence scoring, issue categorization, gating, reporting, and API artefact retrieval (closes GA stretch API-4). **Also requested by Preview customers.** Jira: epic **IRP-113**; 5 stories IRP-114–118 (all Ready For Review).
4. **ERD (Enriched Risk Data) enrichment — license-gated** — Retrieve -> Review -> Apply ERD attributes inside the SoV pipeline, gated on the tenant's existing ERD license, with usage metering. Jira: epic **IRP-119**; 4 stories IRP-120–123 (all Ready For Review).
5. **OED (Open Exposure Data) export — TBD** — export processed output as a valid OED package (file + API); scope locked first by a definition spike. Jira: epic **IRP-124**; 4 stories IRP-125–128 (all Ready For Review; spike = IRP-125).
6. **Pending public Retrieve APIs (per-submodule SoV & Slip)** — complete the public API surface deferred from GA: programmatic Retrieve of each SoV/Slip submodule's output + status (GA ships Upload & Process, Submissions, Export; not per-submodule Retrieve). Jira: epic **IRP-129**; 4 stories IRP-130–133 (all Ready For Review).
7. **Spike: process ILS offering material for ILS workflows** — time-boxed discovery to assess extending RDR to ILS (Insurance-Linked Securities) offering material (offering circulars/memoranda); deliverable = feasibility + go/no-go recommendation. No GA in this epic. Jira: epic **IRP-134**; 3 stories IRP-135–137 (all Ready For Review).
8. **Minor processing & quality updates from Preview & GA usage** *(AS-owned)* — rolling track of small pipeline/quality fixes (policy condition mapping, zone mapping, etc.) from Preview + GA usage, plus small enhancements (e.g., edit submission group access — GA set groups at creation only). Jira: epic **IRP-138**; 4 stories IRP-139–142 (all Ready For Review).

## Proposed success criteria (all *proposed — confirm*)

- >= 25% AI-cost reduction per submission vs July-GA baseline, accuracy >= 95% — by end Q4 2026.
- LLM Judge flags >= 90% of seeded implausible cross-column combinations; >= 60% fields/modules auto-accepted at >= 90% confidence; manual review touches down >= 40% — by end Q4 2026.
- >= 3 pilot tenants on custom context with a measurable accuracy lift (+3 pts) — by end Q4 2026.
- ERD enrichment available to all ERD-licensed tenants.
- OED export — export cleansed Slip and SoV data into OED files (TBD).

## Open items

See [[Open Questions]] (Jakarta 2H 2026 section): KPI sign-off, Jakarta parent Jira key, OED scope, ERD attribute set + entitlement, RDR API namespace (placeholder `/datarefinery/v1/...`), exact Slip submodule list (Epic 6), ILS spike time-box / SME / sample docs (Epic 7), and Jira-push timing. See [[API Surface]] / [[Risk Data Refinery API Design]].
