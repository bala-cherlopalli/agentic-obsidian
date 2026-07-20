---
created: "2026-03-26"
tags:
  - work
  - hiring
  - api
---

# Interview Questions — Senior API Product Manager

> **Goal:** Assess whether the candidate has deep technical understanding of API standards and architecture, can coordinate effectively with engineering teams and product owners, and bridges the gap between business strategy and technical execution.

---

## Shortlist — Top Picks (if time is limited)

| #   | Question                                                                                                                                      | Tests                                               |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| 1   | Walk me through how you would design a new public API from scratch. What artifacts do you produce before a single line of code is written?    | API-first thinking, spec fluency, process           |
| 2   | Walk me through the flow of an API call through a tech stack you have previously worked on.                                                   | Architecture depth, tech stack awareness, real experience |
| 3   | How do you decide between REST, GraphQL, gRPC, and event-driven for a given use case?                                                         | Protocol trade-offs, pragmatism                     |
| 4   | How do you manage breaking changes? Walk me through a real deprecation/sunset example.                                                        | Governance, consumer empathy, communication         |
| 5   | You have three internal teams and two external partners all requesting different API changes. How do you prioritize?                          | Stakeholder coordination, prioritization frameworks |
| 6   | How do you translate a business requirement like "we need bulk operations" into an API spec?                                                  | Business-to-technical translation                   |
| 7   | **Scenario:** Your API has 200 consumers and you discover a design flaw requiring a breaking change on a field used by 40%. What's your plan? | Real-world judgment, migration planning             |
| 8   | How do you handle API design when the UI experience is completely different from the underlying API resources?                                | BFF patterns, API composition, pragmatism           |
| 9   | Pick a project you're most proud of. How deep was your involvement in the API lifecycle and technical implementation?                         | Depth of involvement, hands-on vs. hands-off, authenticity |
| 10  | How do you build an API-first culture in an org that has historically treated APIs as an afterthought?                                        | Leadership, influence, vision                       |

---

## Full Question Bank

---

## 1. API Design & Standards

These questions test whether the candidate can go beyond surface-level REST knowledge and reason about design trade-offs.

### Questions

1. **Walk me through how you would design a new public API from scratch.** What artifacts do you produce before a single line of code is written?
   - *Look for:* API-first design, OpenAPI/Swagger spec authorship, contract-driven development, stakeholder review of the spec, versioning strategy upfront.

2. **What is your approach to API versioning?** Compare URI versioning (`/v2/accounts`), header versioning, and query-param versioning. When would you choose one over another?
   - *Look for:* Awareness of breaking vs. non-breaking changes, deprecation policies, sunset headers, consumer migration plans.

3. **Explain idempotency in the context of API design.** Why does it matter, and how would you enforce it on a POST endpoint?
   - *Look for:* Idempotency keys, retry safety, exactly-once semantics, real-world examples (payment APIs, order creation).

4. **How do you decide between REST, GraphQL, gRPC, and event-driven (webhooks/async) for a given use case?**
   - *Look for:* Not dogmatic about one style. Can articulate trade-offs — latency, payload flexibility, streaming, tooling maturity, consumer developer experience.

5. **What makes a good error response?** Design the error payload structure you'd standardize across your API platform.
   - *Look for:* RFC 7807 (Problem Details), machine-readable error codes, human-readable messages, correlation/trace IDs, field-level validation errors.

6. **How do you handle pagination in APIs?** Compare offset-based, cursor-based, and keyset pagination.
   - *Look for:* Performance implications on large datasets, consistency during concurrent writes, consumer ergonomics, `Link` headers vs. response body metadata.

7. **What is HATEOAS and do you think it's practical?** Have you ever shipped an API that used it?
   - *Look for:* Honest assessment. Understands the theory (discoverability, self-describing APIs) and the practical challenges (client complexity, adoption friction).

---

## 2. API Architecture & Tech Stack

These questions probe whether the candidate understands the infrastructure APIs live in — not just the contract.

### Questions

1. **Walk me through the flow of an API call through a tech stack you have previously worked on.**
   - *Look for:* Can they narrate a real system — not a textbook answer. Should mention concrete components (load balancer, API gateway, auth layer, rate limiter, application service, database, caching) and name actual products they used (e.g. Kong, AWS ALB, Redis, Postgres). Bonus if they explain *why* each layer exists, not just *that* it exists.

2. **What role does an API gateway play, and how do you decide what logic belongs in the gateway vs. the service?**
   - *Look for:* Auth, rate limiting, request transformation, routing — gateway. Business logic — service. Awareness of gateway products (Kong, Apigee, AWS API Gateway, MuleSoft).

3. **How would you design rate limiting for a multi-tenant API platform?** What dimensions would you limit on?
   - *Look for:* Per-tenant, per-endpoint, per-IP, sliding window vs. token bucket, 429 responses with `Retry-After`, tiered plans, burst allowance.

4. **Explain OAuth 2.0 flows.** When would you use Authorization Code + PKCE vs. Client Credentials? How do you handle token refresh?
   - *Look for:* Understands the difference between user-context and service-to-service auth. Can explain scopes, token lifetimes, refresh rotation, and revocation.

5. **A downstream microservice your API depends on is experiencing high latency. How do you protect your consumers?**
   - *Look for:* Circuit breaker pattern, timeouts, retries with exponential backoff and jitter, bulkheads, graceful degradation, fallback responses, SLAs/SLOs.

6. **How do you approach API observability?** What metrics, logs, and traces would you require from your engineering team?
   - *Look for:* Latency percentiles (p50/p95/p99), error rates by status code, throughput, distributed tracing (OpenTelemetry), structured logging with correlation IDs, alerting thresholds.

7. **What's your experience with async APIs?** Describe a scenario where you chose webhooks or event streaming over synchronous request/response.
   - *Look for:* Webhook registration, retry/delivery guarantees, dead-letter queues, event schemas (CloudEvents, AsyncAPI spec), idempotent event processing.

8. **How do you handle API design when the UI experience is completely different from the underlying API resources?** For example, a single screen that pulls data from multiple domains, or a workflow that doesn't map cleanly to CRUD.
   - *Look for:* Backend-for-Frontend (BFF) pattern, API composition/orchestration layers, GraphQL as an aggregation option, experience APIs vs. system APIs (MuleSoft-style layering), awareness that forcing the UI to stitch together five REST calls is a bad developer experience. Red flag: insists the UI should always just call the resource APIs directly.

---

## 3. API Lifecycle & Governance

These questions evaluate whether the candidate can manage an API as a product over time.

### Questions

1. **How do you manage breaking changes?** Walk me through a real example where you had to deprecate or sunset an API version.
   - *Look for:* Communication plan, deprecation timeline, sunset headers, migration guides, usage analytics to identify impacted consumers, grace period.

2. **What does your API review process look like?** How do you ensure consistency across multiple teams shipping APIs?
   - *Look for:* API style guide, linting (Spectral or similar), design review board, automated CI checks on OpenAPI specs, shared schemas/components.

3. **How do you measure the success of an API?** What KPIs do you track?
   - *Look for:* Adoption (new consumers/month), usage (calls/day per endpoint), TTFV (time to first value), error rates, support ticket volume, developer NPS, revenue (if monetized).

4. **Describe how you'd build and maintain an API developer portal.**
   - *Look for:* Interactive docs (Swagger UI, Redocly, Stoplight), getting-started guides, code samples in multiple languages, sandbox/test environment, changelog, status page, authentication quickstart.

5. **Pick a project you're most proud of. How deep was your involvement in the API lifecycle and technical implementation?** Where did you start, where did you hand off, and where did you stay hands-on?
   - *Look for:* Specificity — did they write the spec, review PRs, define the data model, set up monitoring, or just write tickets? Strong candidates describe end-to-end involvement (discovery through production support). They can explain technical decisions they personally influenced, not just observed. Red flag: vague ownership ("I worked with the team on it"), can't name a single technical artifact they produced or a trade-off they drove.

6. **How do you handle API security beyond authentication?** What threats do you design for?
   - *Look for:* Input validation, injection attacks, OWASP API Top 10, CORS policies, TLS enforcement, sensitive data masking in logs, API key rotation, abuse detection.

---

## 4. Cross-Functional Coordination

These questions test the candidate's ability to work across engineering, product, and business.

### Questions

1. **You have three internal teams and two external partners all requesting different API changes. How do you prioritize?**
   - *Look for:* Framework (RICE, weighted scoring, strategic alignment), stakeholder negotiation, data-driven decisions (usage analytics, revenue impact), transparent roadmap communication.

2. **An engineering lead pushes back on your API design proposal, arguing it's over-engineered. How do you handle it?**
   - *Look for:* Openness to feedback, ability to distinguish "nice to have" from "must have," willingness to prototype or A/B test, collaborative problem-solving — not authority-based decision-making.

3. **How do you translate a business requirement like "we need to support bulk operations" into an API spec?**
   - *Look for:* Clarifying questions (batch size limits? sync or async? partial failure handling?), technical spike, spec draft, review with eng, iteration, consumer feedback.

4. **Describe a time you had to align engineering, product, legal, and security on an API decision.**
   - *Look for:* Concrete example. Multi-stakeholder facilitation. Awareness of compliance (GDPR data residency, PII exposure in APIs), security review gates, legal API terms of service.

5. **How do you onboard a new external API consumer?** What does the developer experience look like end-to-end?
   - *Look for:* Self-service registration, API key/OAuth provisioning, sandbox environment, documentation, quickstart guide, SDKs, support channel, feedback loop.

---

## 5. Scenario-Based / Deep Dive

These are open-ended scenarios to see how the candidate thinks on their feet.

### Questions

1. **Scenario:** You're building a financial data API. A customer wants real-time streaming of market data. Another wants batch export of historical data. A third wants webhook notifications on price alerts. **Design the API strategy that serves all three.**
   - *Look for:* REST for CRUD/batch, WebSocket or SSE for streaming, webhooks for event-driven alerts. Unified auth model. Shared data schema across delivery mechanisms.

2. **Scenario:** Your API has 200 consumers. You discover a design flaw in a core endpoint that requires a breaking change. Usage analytics show 40% of consumers use the affected field. **What's your plan?**
   - *Look for:* Impact analysis, phased migration, dual-support period, direct outreach to top consumers, automated migration tooling, clear deprecation timeline, monitoring adoption of new version.

3. **Scenario:** Engineering wants to move from a monolith to microservices. You own the API layer. **How do you ensure the external API contract stays stable while the backend is re-architected?**
   - *Look for:* API gateway as facade, Backend-for-Frontend pattern, contract testing (Pact), feature flags, canary releases, consumer-driven contract tests.

4. **Scenario:** Your API platform serves both internal teams and external developers. Internal teams want rapid iteration; external developers want stability. **How do you balance these needs?**
   - *Look for:* Internal APIs on faster release cadence (alpha/beta channels), external APIs on stable versioned releases, feature flags, separate rate limits/SLAs, clear promotion path from internal to external.

---

## 6. Culture & Leadership

### Questions

1. **How do you build an API-first culture in an organization that has historically built APIs as an afterthought?**
   - *Look for:* Education, API design-first workshops, showing ROI of good APIs, championing developer experience internally, executive buy-in strategy.

2. **How do you stay current with API industry trends?** What's one emerging standard or practice you're excited about?
   - *Look for:* Genuine passion. Mentions things like AsyncAPI, OpenAPI 3.1, API governance platforms, AI-assisted API testing, or specific community involvement.

3. **Tell me about a time an API you shipped failed.** What happened, and what did you learn?
   - *Look for:* Ownership, postmortem culture, specific lessons (better testing, clearer contracts, more consumer feedback earlier), humility.

---

## Evaluation Rubric

| Dimension | Strong Signal | Red Flag |
|---|---|---|
| **Technical Depth** | Explains trade-offs unprompted, uses precise terminology, draws from real experience | Superficial answers, confuses concepts (auth vs. authz), can't go beyond definitions |
| **Design Thinking** | Asks clarifying questions, considers edge cases, thinks about the consumer | Jumps to solutions, ignores error handling and failure modes |
| **Standards Fluency** | References RFCs, OpenAPI, OAuth, HTTP semantics naturally | Doesn't know REST constraints, can't name an API spec format |
| **Cross-Functional** | Gives concrete examples of stakeholder negotiation, shows empathy for eng constraints | "I just write the requirements and hand them off" |
| **Business Acumen** | Ties API decisions to revenue, adoption, or strategic goals | Treats APIs as purely technical artifacts with no business context |
| **Leadership** | Takes ownership of failures, builds consensus, mentors others | Blames engineering, avoids accountability, territorial |
