---
created: "2026-06-11"
tags:
  - RDR
  - pricing
  - margin
  - finance
---

# Margin Analysis

Marginal cost-to-profit framework for RDR, prepared for finance (Arvind's margin-analysis request, like the one done for Risk Data Lake). Role split per Kirtan: product/pricing supplies the framework, unit economics, and assumptions; finance builds the model.

## Method

Unit cost is derived from the published discount waterfall so the analysis stays consistent with the rate card leadership already saw:

- `implied unit cost = unit price x (1 - gross margin)`
- `unit gross profit = unit price x gross margin = unit price - implied unit cost`

The derived per-unit figure is the **variable (marginal) cost per unit** implied by the published gross margin. It **excludes fixed overhead**. Total profit = (sum of unit gross profit across the book) - fixed cost base.

## Cost framework

- **Variable (marginal):** LLM/AI cost is the single largest variable cost, plus per-submission S3 I/O and Postgres writes and per-job EDM-import compute. These are what the implied unit cost represents.
  - **Measured AI cost (Dec'25 internal testing, incl. 25% loading): $0.92 / SoV and $0.52 / slip ($1.44 combined)**; pre-loading $0.74 / $0.42. The 25% loading is the buffer for near-term LLM price moves + external cost. Cost scales with # locations and # columns (data per cell) in a SoV. Token ref: GPT-5 ~$1.25/M in, $10/M out; Claude ~$5/M in, $25/M out. Source: `TokenConsuption_AI Cost.xlsx`; further input pending from Satya Guda. Still to add: any non-AI variable cost.
- **Fixed:** single combined annual fixed cost of **$25,000/year for all clients** (placeholder, not split slip/SoV), subtracted once at the portfolio level (`PORTFOLIO_TOTAL` row of `margin-analysis.csv`). Built from infrastructure components (values TBD from engineering): Postgres cost; S3 cost (mostly negligible but non-zero); fixed compute / API pods cost; Redis cost.

## Slip vs SoV (Kirtan's explicit question)

**Answered: yes, costs differ - measured AI cost is ~1.8x for SoV ($0.92) vs slip ($0.52), incl. loading - so treat slip and SoV as two separate cost lines.** The rate card already prices/margins them separately - accounts (slip / per-account) at 91% -> 70% gross margin vs locations (SoV / per-1k) at 94% -> 88% - so the implied unit costs differ. Caveat: these are costs implied by suggested margins, not measured COGS. If engineering confirms per-submission processing cost is identical regardless of slip vs SoV, **state that explicitly to finance and collapse to one cost line** (the "if they don't vary, say so" instruction).

## Per-band marginal cost -> profit (highlights)

Full per-band tables in the source CSVs. Unit cost/profit are derived (`price x (1 - margin)` / `price x margin`).

- **Accounts (slip / per-account):** top band <500 = $50 price / $4.50 cost / $45.50 profit (91% GM); bottom band 100k+ = $8 / $2.40 / $5.60 (70% GM). Unit profit steps down the waterfall as volume scales.
- **Locations (SoV / per-1k):** top band <1M = $35 / $2.10 / $32.90 (94% GM); bottom band 80M+ = $7 / $0.84 / $6.16 (88% GM).
- Within a band pricing is flat per unit, so the marginal profit of one more unit equals that band's unit gross profit. Across bands it steps down (intentional volume discount).
- **Waterfall cliff caveat:** each band reprices the entire volume at the lower unit price, so total revenue can dip just past a band boundary; finance should model realized blended rate from actual client volumes, not the band ceiling.

## Cohort revenue / profit logic

Three cohorts; revenue = sum of slip charge + SoV charge at each client's volume band.

- **Slip only:** accounts-waterfall(slip accounts); no locations charge.
- **SoV only:** accounts-waterfall(SoV accounts) + locations-waterfall(SoV locations).
- **Slip + SoV:** accounts-waterfall(total accounts) + locations-waterfall(SoV locations).

Mapping assumption: accounts waterfall = slip/per-account charge; locations waterfall = SoV per-1k-locations charge. Net profit (portfolio) = sum of gross profit (pre-fixed) across all clients - the single combined annual fixed cost ($25,000/year placeholder), subtracted once at the portfolio level.

## Client data - accounts-only directional pass

`margin-analysis.csv` is populated with the 21 existing AS clients (62,541 accounts total; per-client client data lives only in the source project, not the KB) across both the accounts and locations metrics. Account variable cost = $0.625/account; location variable cost = $1.25/1k. Per-client locations are now **team-supplied actuals** (65.4M total), mapped to locations bands (W.R. Berkley (2) pending a count). Variable and fixed costs are separated: per-client variable cost, then `FIXED_COST_ALL_CLIENTS_COMBINED` ($25,000/yr) and `NET_PROFIT_AFTER_FIXED` summary rows. Portfolio totals (accounts + actual locations):

| Metric | Revenue | Variable cost | Gross profit |
| --- | --- | --- | --- |
| Accounts | $1,641,178 | $39,088 | $1,602,090 |
| Locations (actual) | $1,518,745 | $81,753 | $1,436,991 |
| Total | $3,159,923 | $120,841 | $3,039,081 |

Gross margin 96.2%; net after $25k fixed = **$3,014,081**. (65.4M actual locations; W.R. Berkley (2) pending.)

Key assumptions/caveats: account variable cost = $0.625/account (midpoint of assumed $0.50-$0.75 range; detailed Dec'25 measurement is $0.92/SoV, $0.52/slip), swappable once the slip/SoV split lands; lower-inclusive band convention; "Remaining 8 Accounts" bucket is band-distorted ($156k as one row vs ~$299k if itemized); no locations (SoV) revenue yet, so SoV clients' true revenue is higher. Gross-margin-% columns removed from the CSV.

Location AI cost = **$1.25 per 1,000 locations** (working figure). Reverse-engineered from the team's measured **$0.92/SoV** over the SoV size distribution (51,244 SoVs × $0.92 = ~$47k ÷ ~27.8M implied locations ≈ $1.70/1k, set at $1.25); AI cost is mostly a fixed per-SoV overhead, so per-location is only an average. Sensitivity $1.70-$3.25/1k on the open 1,000+ band. (Earlier $0.40/1k from raw input-token cost was discarded as too low.) Per-client location revenue/cost pending `total_locations`.

## Open items

See [[Open Questions]] (Margin analysis section): fixed-cost base, measured COGS + slip-vs-SoV confirmation, client list/band mapping (pending Tathagata / Satya breakdown), and the slip<->accounts / SoV<->locations mapping. The 2027-2028 client-base forecast was deferred (out of scope this pass).

## Source references

- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-analysis.md` - framework doc.
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-accounts-unit-economics.csv` - accounts (slip) per-band unit economics.
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-locations-unit-economics.csv` - locations (SoV) per-band unit economics.
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-analysis.csv` - per-client accounts + locations margin model (values).
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-analysis.xlsx` - formula-driven version (Margin / Bands / Parameters sheets; recalculates on edit).
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/margin-clients.csv` - existing AS client list with account counts (from the Analytical Services pricing slide; source for band mapping). Contains customer data - kept in the source project, not copied into the KB.
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/TokenConsuption_AI Cost.xlsx` - LLM/AI token-consumption and per-SoV / per-slip cost workbook.
- `/Users/cherlopb/IdeaProjects/catmosai-sales-pitch/pricing-packaging-quota/Sample_SoV_AI_Tokens.csv` - per-SoV token consumption vs # locations (source for the $0.40/1k-locations cost). Contains SoV names (customer data) - not copied into KB.

## Related

- [[Pricing Packaging and Quota]]
- [[Open Questions]]
