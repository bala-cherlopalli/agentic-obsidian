---
created: "2026-06-16"
tags:
  - RDR
  - metering
  - quota
  - storage
  - telemetry
---

# RDR Metering, Quota and Storage

Detailed metering/quota/storage spec (product/engineering). Source: `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/rdr-metering-quota-storage.md`.

> Note: this spec is newer/more detailed than the leadership report and intentionally differs from it — max non-submission concurrency is **5** (report says 10) and retention is **365 days when there is no platform storage** (report says 2 years proposed). The report files were left as-is per user choice. See [[Pricing Packaging and Quota]].

## Principle

RDR meters every run and rerun via quota strings. Because all usage is counted/metered, **submission processing has no concurrency or daily limits**. Guardrails apply only to **non-submission jobs** (platform data import). RDR ships with **no storage of its own**.

## Submission size

- Max submission size: 100 MB — elastic, can be bumped to 200 MB after Phase 1.

## Submission metering (quota strings)

- New run, Slips + SoVs: `{ rdrAccountsCount: 1, rdrProcessedLocationsCount: <count> }`
- New run, SoVs: `{ rdrAccountsCount: 1, rdrProcessedLocationsCount: <count> }`
- New run, Slips: `{ rdrAccountsCount: 1 }`
- Rerun, Slips: `{ rdrAccountsCount: 1 }`
- Rerun, SoVs: `{ rdrProcessedLocationsCount: <count> }`

Rerun row-counting (depends on submodule rerun is triggered from): SoV cleansing and address cleansing count only updated rows; schema cleansing counts all rows.

## Non-submission jobs (platform data import)

- Per-job quota string: `{ concurrentRdrNonSubmissionJobs: 1, dailyRdrNonSubmissionJobs: 1 }`.
- Limits: max concurrent = 5 at any time; max daily = 100/day.
- Users can work around these limits by combining IRP app resource groups.

## Storage and retention

- RDR ships with no storage.
- Clients with IRP app licenses: use platform Exposure Storage + Other storage; raw uploads + processed data count against Other storage.
- Clients without IRP app licenses: must purchase "IC-IRP-Storage" (working name).
- Expansion: Risk Data Vault (Exposure + Submission data) or Data Bridge (Exposure).
- Retention: with no platform storage, submission + processed data is queued for deletion after 365 days.

## Telemetry model

- Common (every event): `userId` (hashed/abstracted), `tenantId`, `timeStamp`.
- Submission jobs (runs + reruns): `rdrAccountsCount`, `rdrProcessedLocationsCount`, `rdrSubmittedLocationsCount`, `rdrSubmittedSheetsCount`, `isRdrRerun`, `jobId`, `submissionId`, `OtherStorageUsed`, `submissionExpiresAt` (empty | currentDate + 365 days), `resourceGroupId`. File-level: `fileUuid`, `fileSize`, `fileType` (SoV|Slip|Unknown), `isIncluded`.
- Reruns only (additional): `rerunSubModuleName`, `rdrEditedColumns`.
- Non-submission jobs: `concurrentRdrNonSubmissionJobs`, `dailyRdrNonSubmissionJobs`, `jobType`, `resourceGroupId`.

## Related

- [[Pricing Packaging and Quota]]
- [[Architecture Notes]]
