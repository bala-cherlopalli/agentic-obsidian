---
created: "2026-06-08"
tags:
  - RDR
  - knowledge-base
---

# Implementation Overview

Risk Data Refinery is framed as a unified IRP app for AI-powered risk data preparation. It brings Slip Stream and SoV Stream into one experience for ingesting policy slips and SOVs, detecting file type, routing to the right pipeline, reviewing AI output, and importing model-ready data into IRP workflows.

Source project: `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch`

## Product shape

- One unified IRP app; an RDR-licensed user can bring slips, SOVs, or both (no per-type license split). Usage and access are governed by metering, quota, and group-based data access controls.
- Slip Stream transforms policy slip documents into structured policy exposure data.
- SoV Stream transforms SOV data into enriched, model-ready exposure data.
- The target experience is upload, detect, process, review, export/import.
- GA target from source docs is July / early Q3 2026.

## Current source materials

- `risk-data-refinery-preview-deck/README.md` — 5-slide preview deck narrative.
- `slipstream-preview/README.md` — 38-slide Risk Labs preview deck covering Slip Stream and SoV Stream workflows.
- `July GA Scope/risk-data-refinery-ga-scope-summary.md` — GA scope summary and dependencies.
- `July GA Scope/risk-data-refinery-ga-scope.md` — detailed GA requirements.
- `risk-data-refinery-announcement-email.md` — announcement narrative and preview status.
- `risk-data-refinery-preview-clients.md` — preview client tracker.

## Durable facts

- Risk Data Refinery is the AI-powered data input and preparation foundation for IRP.
- Slip Stream is available for preview before SoV Stream in the source material.
- The preview story emphasizes >95% first-pass extraction accuracy and human-in-the-loop review.
- The GA scope intentionally defers embedded agents in UIQ, Risk Modeler, and ExposureIQ to a later phase.

## Related notes

- [[Architecture Notes]]
- [[API Surface]]
- [[Source Map]]
- [[Open Questions]]
