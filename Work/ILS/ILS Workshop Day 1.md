[[ILS]]

[[2026-04-13]]

## Knowledge base (TIQ / ILS)

- [[TIQ — ILS program model (Program, IED, ILC)]]
- [[TIQ — 144A cat bonds]]
- [[TIQ — ILS program lifecycle and quote states]]
- [[TIQ — ILS enablement (SKU, tenant, attachments, RDX)]]
- [[TIQ — Reference loss source and share factors]]



![[Work/ILS/assets/Pasted image 20260413093453.png]]


==ILS Cat Bond is same as a program==

IED --> Portfolio 
ILC --> Loss / analysis


## Conceptual Mapping: Program, Cat Bond,LC

### Risk & Analytics Flow

Program 

├─ Defines coverage, structure, perils, regions 

├─ May be funded by Cat Bonds 

│ 

IED 

├─ Exposure / Portfolio data 

│ 

Analytics / Models 

│ 

ILC 

└─ Losses, EP curves, AAL, PML



Cat bonds that Moody’s works with are often **144A**-structured On Risk (private placement to QIBs).

### 144A risk cat bonds (brief)

- **Rule 144A** — U.S. rule that lets issuers sell certain securities (including cat bonds) in **private placements** to **qualified institutional buyers (QIBs)** without full SEC registration. Common format for institutional ILS in the U.S. market.
- **Cat bonds** — **catastrophe bonds**: insurance-linked securities that move natural-catastrophe risk from insurers/reinsurers to capital-market investors (principal at risk if triggers hit, coupon in return).
- Together, **144A cat bonds** are cat bond issues offered under Rule 144A. “144A risk” in workshop shorthand usually means the **risk transfer** sits in that **144A private-placement** layer (structure, investor base, and documentation typical of 144A ILS deals).



==New SKU for ILS clients >> uses TIQ app== : We need to test TIQ only tenant

Need a way to attach pdfs, spreadsheets, docs which are reports or other details to a program





**Quote Status:**

Pre-marketing (optional) ---> probably ==NEW== state in program
marketing state (Roughly 2 weeks) --> sort of finalized package --> ==Quote== state in program
Launched / On Risk State --> ==Written== state in program
Reset State with year --> does not fit into existing names --> ==new enum== 

New enhancement required - ==Risk Data Exchange should support importing the program into an existing programSet==


**Concept to note:**

Reference Loss Source --> choose an analysisId: this becomes reference risk source + Market Exposures (this is geography wise share factors)

In program,
we can add share factor risk source from:
existing reference loss source + simulationSet + sharefactor resolution
or choose an existing risksource as reference risk source + share factors similar to that of  (shares by resolution) market exposures






