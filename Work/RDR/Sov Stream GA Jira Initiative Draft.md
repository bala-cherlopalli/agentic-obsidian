https://rmsrisk.atlassian.net/browse/PLAN-950
[[sovstream]]
[[risk data refinery]]
[[catmosai]]

Initiative Text:
### Introduction

Insurers and reinsurers routinely receive exposure data in the form of Schedules of Values (SOVs) — semi-structured datasets that vary widely in format, terminology, and completeness. To prepare this data for catastrophe modeling or portfolio analysis, clients must manually cleanse, geocode, and transform it into formats compatible with IRP applications — a labor-intensive process that can take hours or days depending on schedule size.

SoV Stream is an AI-powered automation service that transforms raw SOV data into platform-ready exposure datasets. It automates cleansing, geo-enhancement, and exposure code standardization — delivering rapid, accurate risk insights with full process visibility. Currently in Preview, SoV Stream has demonstrated its ability to eliminate manual preprocessing and accelerate the path from raw exposure data to actionable analytics.

This initiative outlines the path to making "SoV Stream" features a Generally Available (GA) offering on the Intelligent Risk Platform.

### Business Need

There are several dimensions of need driving this initiative:

- **Client Pain Point:** Clients spend significant time manually cleansing, geocoding, and converting SOV data into platform-compatible formats. This creates a recurring bottleneck every time new exposure data is received — delaying modeling, accumulation, and underwriting workflows.
    
- **Competitive Pressure:** Companies in the Intelligent Document Processing (IDP) and exposure management space are offering automated SOV transformation services. Without a native solution, clients may turn to off-platform tools, fragmenting their workflow and reducing platform stickiness.
    
- **Platform Upsell Opportunity:** Offering SoV Stream as a standardized platform service — creates a natural entry point to upsell IRP applications such as UnderwriteIQ, Risk Modeler, and ExposureIQ.
    
- **Reduced Advisory Dependency:** SoV Stream reduces reliance on bespoke advisory or professional services engagements for data preparation, improving data quality and consistency while lowering the cost to serve.
    

### Scope

- **Automated Cleansing** — removal of irrelevant data for streamlined processing
    
- **Geo-Enhancements** — address parsing and geocoding accuracy improvements via IRP API integration
    
- **Model-Ready Output** — conversion of descriptive data into standardized codes compatible with IRP applications
    
- **User Flexibility** — ability to update and re-run individual modules without re-uploading files
    
- **Accuracy & Transparency** — precision with full process visibility into each transformation step
    
- Structured output generation with file downloads and direct import integration
    
- Platform APIs for programmatic ingestion and integration
    
- IRP Standardized user experience
    
- Production-grade performance, reliability, and scalability hardening
    
- Pricing and Packaging
    
- Quota definition and enforcement
    
- Telemetry
    

### Business Impact

- **Platform Adoption:** Offering SoV Stream as a GA capability strengthens IRP's position as an end-to-end platform, bringing clients onto the platform earlier in their exposure management workflow
    
- **Competitive Differentiation:** A native, AI-powered SOV transformation service positions Moody's ahead of fragmented point solutions and reduces client reliance on off-platform tools
    
- **Revenue Uplift:** SoV Stream serves as a gateway to upsell Risk Modeler, ExposureIQ, and other IRP applications by converting raw exposure data directly into model-ready formats
    
- **Client Retention:** Eliminating manual preprocessing reduces friction, increases stickiness, and improves the overall client experience
    
- **Speed & Efficiency:** Transforms hours of manual effort into rapid, automated processing — enabling clients to move from raw SOV to actionable insights significantly faster
    
- **Accuracy & Consistency:** Minimizes manual errors and ensures consistent, repeatable results across schedules — improving confidence in downstream modeling outputs