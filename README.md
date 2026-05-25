# Canvas LMS (canvas-lms)

Canvas is the open, AGPLv3-licensed learning management system created and maintained by Instructure, Inc. and used by more than 30 million students, teachers, and administrators across higher education, K-12, business, and government. Canvas exposes a deep REST API (190+ resource groups), a GraphQL API, full IMS LTI 1.3 / LTI Advantage services, a Platform Notification Service for server-to-server webhooks, the Data Access Platform (DAP / Canvas Data 2) for warehouse-scale data export, and the SIS Import API for bulk provisioning.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/canvas-lms/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Learning Management, Education, EdTech, LMS, LTI, Higher Education, K-12, Open Source, AGPL, Canvas

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Deployment Options

| Mode | Hosting | Licensing | Source |
|---|---|---|---|
| Canvas Free for Teacher | canvas.instructure.com (Instructure-hosted) | Free, individual teacher accounts | Closed (same Canvas binary) |
| Canvas Cloud (Institutional) | Instructure-hosted, per-tenant | Contract-priced per FTE / learner | Closed (same Canvas binary) |
| Canvas Self-Hosted | Customer infrastructure | AGPL-3.0-or-later, no license fee | [instructure/canvas-lms](https://github.com/instructure/canvas-lms) |

## APIs

### Canvas REST API
The canonical Canvas REST API at `/api/v1`. 190+ controller-driven resource groups covering Accounts, Courses, Enrollments, Users, Assignments, Submissions, Modules, Discussion Topics, Files, Outcomes, Quizzes, Rubrics, SIS Imports, Developer Keys, External Tools, AI Conversations, AI Experiences, Audit Logs, and more. OAuth2 (RFC 6749) authentication; pagination via RFC 5988 Link headers.

**Human URL:** [https://canvas.instructure.com/doc/api/](https://canvas.instructure.com/doc/api/)

- [Documentation — All Resources Reference](https://canvas.instructure.com/doc/api/all_resources.html)
- [OpenAPI](openapi/canvas-lms-rest-api-openapi.yml)
- [JSON Schema — Course](json-schema/canvas-lms-course-schema.json)
- [JSON Schema — Assignment](json-schema/canvas-lms-assignment-schema.json)
- [JSON-LD Context](json-ld/canvas-lms-context.jsonld)
- [Naftiko Capability — Courses](capabilities/rest-api-courses.yaml)
- [Naftiko Capability — Assignments](capabilities/rest-api-assignments.yaml)
- [OAuth2 Overview](https://canvas.instructure.com/doc/api/file.oauth.html)
- [Throttling](https://canvas.instructure.com/doc/api/file.throttling.html)
- [Pagination](https://canvas.instructure.com/doc/api/file.pagination.html)
- [Change Log](https://canvas.instructure.com/doc/api/file.changelog.html)

### Canvas GraphQL API
GraphQL endpoint at `/api/graphql` exposing the Canvas object graph with the same authentication and permissions model as the REST API. Hosted GraphiQL explorer at `/graphiql`.

**Human URL:** [https://canvas.instructure.com/doc/api/file.graphql.html](https://canvas.instructure.com/doc/api/file.graphql.html)

### Canvas LTI Advantage Services
1EdTech (IMS Global) LTI 1.3 / LTI Advantage implementation: Deep Linking 2.0, Names and Role Provisioning (NRPS), Assignment & Grade Services (Line Items, Score, Result), Dynamic Registration, Platform Notification Service, and JWK-based key exchange. JWT client-assertion authentication per the IMS Security Framework.

**Human URL:** [https://canvas.instructure.com/doc/api/file.tools_intro.html](https://canvas.instructure.com/doc/api/file.tools_intro.html)

### Canvas Platform Notification Service
Server-to-server webhook delivery to LTI tools outside the scope of an active user session. Tools register notice handlers for specific event types and receive signed deliveries that integrate with the IMS LTI 1.3 security model.

**Human URL:** [https://canvas.instructure.com/doc/api/file.pns.html](https://canvas.instructure.com/doc/api/file.pns.html)

### Canvas Data Access Platform (DAP)
Warehouse-scale data export API for Canvas Data 2 — the successor to Canvas Data 1 / Canvas Data CLI. Exposes Canvas tables and Caliper-derived event streams as snapshot and incremental queries against the `canvas` and `catalog` namespaces.

**Human URL:** [https://data-access-platform-api.s3.amazonaws.com/index.html](https://data-access-platform-api.s3.amazonaws.com/index.html)

- [DAP Client (Python)](https://github.com/instructure/dap-client-py)
- [Canvas Data Loader (Rust)](https://github.com/instructure/canvas-data-loader)
- [Canvas Hosted Data Examples](https://github.com/instructure/canvas-hosted-data-examples)

### Canvas SIS Import API
Ingests Canvas's canonical SIS CSV format (and ZIP archives of those CSVs) to provision accounts, terms, courses, sections, users, enrollments, groups, group memberships, cross-listings, user observers, logins, admins, change-sis-id mappings, and admin differentiation tags. Supports diffing, batch mode, and asynchronous progress polling.

**Human URL:** [https://canvas.instructure.com/doc/api/sis_imports.html](https://canvas.instructure.com/doc/api/sis_imports.html)

## Open Source Projects

| Repo | Language | Purpose |
|---|---|---|
| [instructure/canvas-lms](https://github.com/instructure/canvas-lms) | Ruby | Canvas LMS core source (6,600+ stars) |
| [instructure/canvas-ios](https://github.com/instructure/canvas-ios) | Swift | Canvas iOS apps (Student, Teacher, Parent) |
| [instructure/canvas-android](https://github.com/instructure/canvas-android) | Kotlin | Canvas Android apps |
| [instructure/canvas-rce-api](https://github.com/instructure/canvas-rce-api) | JavaScript | Canvas Rich Content Editor API |
| [instructure/canvas-self-hosted](https://github.com/instructure/canvas-self-hosted) | Shell | Dockerized self-hosted starter |
| [instructure/dap-client-py](https://github.com/instructure/dap-client-py) | Python | DAP / Canvas Data 2 client |
| [instructure/pandarus](https://github.com/instructure/pandarus) | Ruby | Ruby Canvas API client + code generator |
| [instructure/canvas_oauth_engine](https://github.com/instructure/canvas_oauth_engine) | Ruby | Mountable Rails engine for Canvas OAuth |
| [instructure/ims-lti](https://github.com/instructure/ims-lti) | Ruby | IMS LTI library for Ruby |
| [instructure/basiclti-util-java](https://github.com/instructure/basiclti-util-java) | Java | Basic LTI utilities for Java |
| [instructure/instructure-ui](https://github.com/instructure/instructure-ui) | TypeScript | Canvas UI component library |
| [instructure/qti](https://github.com/instructure/qti) | Ruby | QTI quiz format library |
| [instructure/QTIMigrationTool](https://github.com/instructure/QTIMigrationTool) | Python | QTI 1.x → 2.0 converter |
| [instructure/moodle2cc](https://github.com/instructure/moodle2cc) | Ruby | Moodle → Common Cartridge converter |
| [instructure/common-cartridge-viewer](https://github.com/instructure/common-cartridge-viewer) | JavaScript | Common Cartridge browser viewer |
| [instructure/analytics](https://github.com/instructure/analytics) | Ruby | Canvas Analytics plugin |
| [instructure/canvas_connect](https://github.com/instructure/canvas_connect) | Ruby | Adobe Connect plugin for Canvas |
| [instructure/canvas-studio-api-examples](https://github.com/instructure/canvas-studio-api-examples) | Python | Canvas Studio API examples |

## Authentication

The Canvas REST API uses OAuth2 (RFC 6749) with the authorization-code grant:

```
GET  https://<canvas-install-url>/login/oauth2/auth?client_id=...&response_type=code&state=...&redirect_uri=...
POST https://<canvas-install-url>/login/oauth2/token
```

Clients must be registered as a **Developer Key** in the target Canvas account. Manual personal access tokens may be generated from a user's profile **for testing only** — using them in production violates the [Canvas API Policy](https://www.instructure.com/policies/api-policy). Admin users may impersonate other users on read endpoints by appending `as_user_id={id}` (Masquerading).

LTI 1.3 services use JWT client-assertion authentication per the IMS Security Framework.

## Rate Limits

Canvas applies per-user-per-host leaky-bucket throttling. Each response includes `X-Request-Cost` (units consumed) and `X-Rate-Limit-Remaining` (room left in the bucket). When the bucket fills, requests return **HTTP 403** with body `403 Forbidden (Rate Limit Exceeded)`. Default Canvas Cloud sizing is roughly a 700-unit bucket with a 5-unit/second drain; operators can tune these per install.

See [rate-limits/canvas-lms-rate-limits.yml](rate-limits/canvas-lms-rate-limits.yml) and the [Throttling docs](https://canvas.instructure.com/doc/api/file.throttling.html).

## Plans & Pricing

Instructure does not publish per-seat list pricing. Canvas is sold in three modes:

- **Canvas Free for Teacher** — Free hosted tenant at canvas.instructure.com for individual teachers; limited storage and no SIS / DAP / SLA.
- **Canvas Cloud (Institutional)** — Per-FTE contract, quoted by Instructure sales; includes SIS Import API, DAP, PNS, SSO, 99.9% SLA, and account administration.
- **Canvas Self-Hosted** — AGPL-3.0 source from `instructure/canvas-lms`, run on customer infrastructure; no license fee, no commercial support, no DAP.

Add-on products: **Canvas Studio** (video), **Canvas Catalog** (course discovery + commerce), **Canvas Credentials** (Open Badges 3.0 / Verifiable Credentials).

See [plans/canvas-lms-plans-pricing.yml](plans/canvas-lms-plans-pricing.yml).

## Common

- [Instructure](https://www.instructure.com) — Portal
- [Canvas LMS Product Page](https://www.instructure.com/canvas) — Portal
- [Free for Teacher](https://canvas.instructure.com/) — SignUp
- [Canvas REST API Documentation](https://canvas.instructure.com/doc/api/) — Documentation
- [All Resources Reference](https://canvas.instructure.com/doc/api/all_resources.html) — Documentation
- [Canvas API Change Log](https://canvas.instructure.com/doc/api/file.changelog.html) — ChangeLog
- [Canvas GraphQL](https://canvas.instructure.com/doc/api/file.graphql.html) — Documentation
- [OAuth2 Overview](https://canvas.instructure.com/doc/api/file.oauth.html) — Authentication
- [API Throttling](https://canvas.instructure.com/doc/api/file.throttling.html) — RateLimits
- [Pagination](https://canvas.instructure.com/doc/api/file.pagination.html) — Pagination
- [LTI Tools Introduction](https://canvas.instructure.com/doc/api/file.tools_intro.html) — Documentation
- [Canvas API Policy](https://www.instructure.com/policies/api-policy) — TermsOfService
- [Instructure Status](https://status.instructure.com/) — StatusPage
- [Canvas Community](https://community.canvaslms.com/) — Forum
- [Canvas Developers Group](https://community.canvaslms.com/t5/Canvas-Developers-Group/gh-p/canvas-developers) — Forum
- [Instructure on GitHub](https://github.com/instructure) — GitHubOrganization
- [Canvas LMS Source](https://github.com/instructure/canvas-lms) — SourceCode
- [Canvas LMS Wiki](https://github.com/instructure/canvas-lms/wiki) — Documentation
- [Canvas Self-Hosted Docker](https://github.com/instructure/canvas-self-hosted) — Tool
- [Edu App Center](https://www.eduappcenter.com/) — Marketplace

## Maintainers

- **Kin Lane** — info@apievangelist.com — [apievangelist.com](https://apievangelist.com)
