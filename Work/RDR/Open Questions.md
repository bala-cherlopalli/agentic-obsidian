---
created: "2026-06-08"
tags:
  - RDR
  - questions
---

# Open Questions

## Product and scope

- [ ] Finalize the GA product name for Risk Data Refinery. #task
- [ ] Confirm whether mixed slip + SoV uploads in a single batch are required for GA. #task
- [ ] Confirm whether existing preview tenants automatically upgrade to GA or opt in. #task
- [ ] Define data continuity expectations for preview-to-GA migration. #task

## API and artefacts

- [ ] Decide whether LLM Judge artefacts are in July scope. #task
- [ ] Decide whether View as Canvas artefacts are in July scope. #task
- [ ] Decide whether Parquet / EDM export is in July scope. #task
- [ ] Decide whether Excel report variants are in July scope. #task
- [ ] Confirm whether API responses remain unchanged or require rewrite and UI regression. #task

## Platform dependencies

- [ ] Decide whether Groups security adopts UDS catalog or another securable resource model. #task
- [x] License model clarified (2026-06-16): no Slips/SOVs license split — an RDR-licensed user can bring slips, SoVs, or both; usage/access governed by metering, quota, and group-based data access (group assignment). (Was: confirm runtime-only license gating vs entitlement management UI at GA.) #task
- [ ] Define quota metrics and Salesforce integration path with SML / MSP dependencies. #task
- [ ] Set concrete NFR targets for file size, volume, latency, availability, and scaling. #task (partial: submission file size cap = 100 MB (adjustable); non-submission jobs (Phase 1 = EDM import) proposed at 100/day and 10 concurrent (stretch vs AS); concurrent-user guardrail still TBD — see [[Pricing Packaging and Quota]])

## Margin analysis (finance)

See [[Margin Analysis]] for the framework. Items to validate with finance / engineering (and stakeholders Cihan, Mike Richeten):

- [ ] Provide the fixed-cost base to subtract from aggregate unit profit (finance input; not derivable from the rate card). #task
- [ ] Replace implied unit costs with measured COGS; confirm whether slip vs SoV per-submission processing cost differs — collapse to one cost line if not. #task
- [ ] Obtain actual client list + band mapping (pending Tathagata / Satya slip-only / SoV-only / both breakdown). #task
- [ ] Confirm the slip<->accounts / SoV<->locations metric mapping with product. #task
- [ ] 2027–2028 client-base forecast deferred (out of scope this pass); revisit once client breakdown lands. #task

## Jakarta 2H 2026 scope

See [[Jakarta 2H 2026 Scope]].

- [ ] Confirm Jakarta initiative success-criteria KPIs and dates (currently proposed defaults: >=30% AI-cost cut, >=60% auto-accept at >=90% confidence, >=3 pilot tenants, >=50% ERD enrichment). #task
- [ ] Resolve the Jakarta parent Jira key (2H 2026 umbrella, like Istanbul / PLAN-797) and target project. #task
- [ ] Lock OED export scope: OED version, file vs API delivery, field coverage, GA vs experimental (epic-5 Story 5.0 spike). #task
- [ ] Confirm ERD v1 attribute set and ERD API contract / entitlement check with the Model team + SML/MSP. #task
- [ ] Confirm the RDR public API namespace (placeholder `/datarefinery/v1/...`). #task
- [ ] Confirm the exact Slip submodule list for the per-submodule Retrieve APIs (Epic 6). #task
- [ ] Set the ILS spike time-box, SME, and sample offering documents (Epic 7). #task
- [ ] Decide when to push the Jakarta initiative/epics/stories to Jira. #task

## Source references

- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/July GA Scope/risk-data-refinery-ga-scope.md`
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/July GA Scope/risk-data-refinery-ga-scope-summary.md`
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/Jakarta Scope/` (initiative.md + epic-1..5)
