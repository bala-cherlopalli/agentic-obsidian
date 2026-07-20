https://rmsrisk.atlassian.net/browse/PLAN-949
[[slipstream]]
[[risk data refinery]]
[[catmosai]]

Initiative Text:
### Introduction

Primary insurers — the second institution in the risk transfer chain after brokers or MGAs — frequently receive coverage submissions as unstructured policy slip documents. To prepare this data for catastrophe modeling or account underwriting, these insurers must manually convert it into formats compatible with EDM or MRI schemas — a time-consuming and error-prone process.

SlipStream uses AI/ML to extract and normalize policy information from unstructured slips, producing structured outputs aligned to IRP exposure. Currently in Preview, SlipStream has demonstrated its value as a digital ingestion asset that eliminates off-platform preprocessing and enables faster downstream modeling and analytics.

This initiative outlines the path to making “SlipStream” features a Generally Available (GA) offering on the Intelligent Risk Platform.

### Business Need

There are several dimensions of need driving this initiative:

- **Client Pain Point:** Insurers today spend significant manual effort converting unstructured policy slips into platform-compatible formats. This creates a bottleneck at the very start of the modeling workflow.
    
- **Competitive Pressure:** Companies such as DeepOpinion, Insurants, FurtherAI, and a growing number of startups in the Intelligent Document Processing (IDP) space are solely focused on providing this data transformation service. Without a native solution, we risk losing clients to off-platform alternatives.
    
- **Platform Upsell Opportunity:** Offering SlipStream as a standardized platform service — creates a natural entry point to upsell IRP applications such as UnderwriteIQ, Risk Modeler and ExposureIQ
    
- **Reduced Advisory Dependency:** SlipStream reduces reliance on bespoke advisory workflows, improving data quality and consistency while lowering the cost to serve
    
- **Accuracy & Consistency:** Minimizes manual errors and ensures consistent, repeatable results across submissions — improving confidence in downstream modeling outputs
    

### Scope

- AI/ML-powered extraction and normalization of policy slip documents with feedback loop mechanism
    
- Full visibility into extraction and normalization results, enabling users to review and validate AI-interpreted outputs
    
- Structured output generation aligned to IRP Exposure with file downloads and direct import integration
    
- Platform APIs for programmatic ingestion and integration
    
- IRP Standardized user experience
    
- Production-grade performance, reliability, and scalability hardening
    
- Pricing and Packaging
    
- Quota definition and enforcement
    
- Telemetry
    

### Business Impact

- **Platform Adoption:** Offering SlipStream as a GA capability strengthens IRP's position as an end-to-end platform, driving adoption across the insurance value chain
    
- **Competitive Differentiation:** A native, AI-powered slip processing service directly counters the growing IDP startup landscape and positions Moody's ahead of fragmented point solutions
    
- **Revenue Uplift:** SlipStream serves as a gateway to upsell Risk Modeler, ExposureIQ, and other IRP applications by bringing clients onto the platform earlier in their workflow
    
- **Client Retention:** Eliminating off-platform preprocessing reduces friction, increases stickiness, and improves the overall client experience