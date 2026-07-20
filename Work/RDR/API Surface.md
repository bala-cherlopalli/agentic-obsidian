---
created: "2026-06-08"
tags:
  - RDR
  - api
---

# API Surface

The GA scope calls for a public API surface for Risk Data Refinery. The details still need final ownership, specs, and implementation alignment.

## Planned API areas

- Upload and process API.
- Retrieve processed data API.
- Retrieve artefacts API.
- Combined export API.
- Reports API.
- API authentication and action-level permissions.
- OpenAPI spec and developer documentation.

## Retrieval and export behavior

- Processed data may be returned inline as JSON for smaller payloads.
- Larger payloads may use pre-signed S3 URLs.
- Combined export may include Exposure Batch JSON, MRI, and the original input file.
- Parquet / EDM export is listed as stretch or confirm.

## Report types in scope

- Exposure Overview report.
- Slip Overview report.
- Final Review report.
- Per-step pipeline summary report.
- Excel report variants are listed as stretch or confirm.

## Open API decisions

- Whether API content is rewritten for GA or existing API responses remain unchanged.
- Whether LLM Judge and View as Canvas artefacts are in the July scope.
- Final OpenAPI shape and endpoint naming.
- Regression cost if APIs are rewritten while preserving the UI.

## Source references

- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/July GA Scope/risk-data-refinery-ga-scope.md`
- [[Risk Data Refinery API Design]]
