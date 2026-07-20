---
created: "2026-06-08"
tags:
  - RDR
  - source-map
---

# Source Map

Source project: `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch`

## High-signal files and folders

| Source | Purpose |
| --- | --- |
| `AGENTS.md` | Workspace facts, user preferences, deck map, and product positioning guidance. |
| `risk-data-refinery-deck.html` | Main Risk Data Refinery overview deck. |
| `risk-data-refinery-preview-deck/` | Self-contained 5-slide preview deck. |
| `slipstream-preview/` | 38-slide Risk Labs preview deck for Slip Stream and SoV Stream. |
| `July GA Scope/` | GA scope summary and detailed requirements. |
| `Jakarta Scope/` | RDR 2H 2026 ("Jakarta") Jira scope drafts: one initiative + five epics with JTBD/GWT stories (markdown, pre-Jira). See [[Jakarta 2H 2026 Scope]]. |
| `risk-data-refinery-announcement-email.md` | Announcement and preview positioning. |
| `risk-data-refinery-preview-clients.md` | Preview customer and tenant tracker. |
| `leadership-status-report.html` | Leadership status pack visual report. |
| `leadership-status-email.md` | Companion leadership status email. |
| `pricing-packaging-quota/` | Leadership tabular view of limits/quotas plus pricing/packaging tiers; `index.html` (themed) and `pricing-packaging-quota.md` (source). Also holds the margin analysis: `margin-analysis.md` (framework) plus `margin-accounts-unit-economics.csv`, `margin-locations-unit-economics.csv`, `margin-analysis.csv` (cohort template), and `margin-clients.csv` (AS client account counts; customer data - not copied into KB). See [[Margin Analysis]]. |
| `pricing-packaging-quota/rdr-metering-quota-storage.md` | Detailed metering/quota/storage + telemetry spec (quota strings, 5 concurrent / 100 daily non-submission jobs, no-RDR-storage, 365-day deletion). See [[RDR Metering Quota and Storage]]. |
| `Risk Data Refinery - May 26  - Pricing and Packaging Design.pdf` | Source for rate card and discount waterfalls. |
| `assets/` | Shared presentation assets. |
| `.specstory/history/` | Cursor/SpecStory chat transcripts that capture requirements, decisions, and project evolution. |

## Ignore during KB sync

- `node_modules/`
- `.history/`
- generated zips
- temporary Office lock files such as `~$*.pptx`
- large binaries unless the user asks for asset inventory

## Sync notes

- Start each sync from `AGENTS.md`, `July GA Scope/`, and the README files for the active deck folders.
- Review `.specstory/history/` selectively for relevant decisions and rationale; summarize only durable facts.
- Use source paths in KB notes when the detail may need to be traced back.
- Prefer summaries over copied slide/deck content.
