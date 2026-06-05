# Canvas LMS (canvas-lms)

Canvas is the open, AGPLv3-licensed learning management system created and maintained by Instructure, Inc. and used by more than 30 million students, teachers, and administrators across higher education, K-12, business, and government. Canvas exposes a deep REST API (190+ resource groups covering Accounts, Courses, Enrollments, Assignments, Submissions, Grades, Outcomes, Quizzes, Rubrics, Modules, Pages, Discussions, Files, Conversations, Calendar Events, SIS Import, Authentication Providers, Developer Keys, External Tools, AI Conversations, AI Experiences, Analytics, Audit Logs, and more), a GraphQL API at /api/graphql, IMS LTI 1.3 / LTI Advantage services (Names and Role Provisioning, Line Items, Score, Result, Deep Linking), a Platform Notification Service for server-to-server webhook delivery, and the Data Access Platform (DAP / Canvas Data 2) for warehouse-scale event and snapshot data export. Canvas is the same software that powers canvas.instructure.com (Free for Teacher), Canvas Cloud for institutions, and self-hosted deployments.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/canvas-lms/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/canvas-lms/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Learning Management
- Education
- EdTech
- LMS
- LTI
- Higher Education
- K-12
- Open Source
- AGPL
- Canvas

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-30

## APIs

### Canvas REST API

The canonical Canvas REST API at /api/v1. 190+ controller-driven resource groups covering Accounts, Account Calendars, Account Notifications, Account Reports, Admins, Announcements, Appointment Groups, Assignments, Assignment Groups, Assignment Extensions, Authentication Providers, Audit Logs (Authentications, Course, Grade Change), Blueprint Courses, Bookmarks, Brand Configs, Calendar Events, Collaborations, Communication Channels, Conferences, Content Exports, Content Migrations, Content Shares, Conversations, Courses, Course Pace, Course Reports, Custom Gradebook Columns, Developer Keys, Discussion Topics, Enrollments, Enrollment Terms, ePortfolios, ePub Exports, External Tools, Favorites, Feature Flags, Files, Folders, Gradebook History, Grading Periods, Grading Standards, Group Categories, Groups, JWTs, Late Policy, Live Assessments, Logins, Media Objects, Modules, New Quizzes, Notification Preferences, Outcomes, Outcome Groups, Outcome Imports, Outcome Results, Pages, Peer Reviews, Planner, Polls, Progress, Quizzes, Quiz Submissions, Roles, Rubrics, Sections, SIS Imports, Sub-Accounts, Submissions, Submission Comments, Tabs, User Observees, Users, AI Conversations, AI Experiences, and more. Authentication via OAuth2 (RFC 6749) with developer-key-issued client credentials; supports manual access tokens for testing and masquerading via the as_user_id parameter.

- **Human URL:** [https://canvas.instructure.com/doc/api/](https://canvas.instructure.com/doc/api/)
- **Base URL:** `https://<canvas-install-url>/api/v1`

#### Tags

- REST
- Courses
- Users
- Assignments
- Grades
- Enrollments
- LMS

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/)
- [Documentation](https://canvas.instructure.com/doc/api/all_resources.html)
- [OpenAPI](openapi/canvas-lms-rest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/canvas-lms-course-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/canvas-lms-assignment-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/canvas-lms-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Authentication](https://canvas.instructure.com/doc/api/file.oauth.html)
- [Authentication](https://canvas.instructure.com/doc/api/file.oauth_endpoints.html)
- [Authentication](https://canvas.instructure.com/doc/api/file.developer_keys.html)
- [Pagination](https://canvas.instructure.com/doc/api/file.pagination.html)
- [Rate Limits](https://canvas.instructure.com/doc/api/file.throttling.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.file_uploads.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.masquerading.html)
- [Changelog](https://canvas.instructure.com/doc/api/file.changelog.html)

### Canvas GraphQL API

GraphQL endpoint exposing the Canvas object graph (courses, users, enrollments, assignments, submissions, modules, discussion topics, outcomes, account hierarchies, etc.). Permissions mirror the REST API. Includes a hosted GraphiQL explorer at /graphiql for query development. Authentication uses the same OAuth2 bearer tokens as the REST API.

- **Human URL:** [https://canvas.instructure.com/doc/api/file.graphql.html](https://canvas.instructure.com/doc/api/file.graphql.html)
- **Base URL:** `https://<canvas-install-url>/api/graphql`

#### Tags

- GraphQL
- Query
- LMS

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/file.graphql.html)
- [Sandbox](https://<canvas-install-url>/graphiql)
- [Authentication](https://canvas.instructure.com/doc/api/file.oauth.html)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Canvas LTI Advantage Services

1EdTech (IMS Global) LTI 1.3 / LTI Advantage implementation. Includes Deep Linking 2.0, Names and Role Provisioning Services (NRPS), Assignment and Grade Services (Line Items, Score, Result), Dynamic Registration, Platform Notification Service, and JWK-based key exchange. Authentication uses JWT client assertions per the IMS Security Framework.

- **Human URL:** [https://canvas.instructure.com/doc/api/file.tools_intro.html](https://canvas.instructure.com/doc/api/file.tools_intro.html)

#### Tags

- LTI
- LTI Advantage
- IMS Global
- 1EdTech
- Interoperability
- Standards

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/file.tools_intro.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.lti_launch_overview.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.lti_dev_key_config.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.content_item.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.assignment_tools.html)
- [Documentation](https://canvas.instructure.com/doc/api/names_and_role.html)
- [Documentation](https://canvas.instructure.com/doc/api/line_items.html)
- [Documentation](https://canvas.instructure.com/doc/api/score.html)
- [Documentation](https://canvas.instructure.com/doc/api/result.html)
- [Documentation](https://canvas.instructure.com/doc/api/public_jwk.html)
- [Documentation](https://canvas.instructure.com/doc/api/lti_registrations.html)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Canvas Platform Notification Service

Platform Notification Service (PNS) enables server-to-server communication by allowing Canvas to send Notices (webhook deliveries) to LTI tools outside the scope of an active user session. Tools register notice handlers for specific event types and receive signed deliveries that integrate with the IMS LTI 1.3 security model.

- **Human URL:** [https://canvas.instructure.com/doc/api/file.pns.html](https://canvas.instructure.com/doc/api/file.pns.html)

#### Tags

- Webhooks
- Notifications
- Events
- LTI
- Server to Server

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/file.pns.html)
- [Documentation](https://canvas.instructure.com/doc/api/notice_handlers.html)
- [Documentation](https://canvas.instructure.com/doc/api/webhooks_subscriptions_for_plagiarism_platform.html)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Canvas Live Events

Canvas Live Events stream lifecycle events emitted by Canvas (course, enrollment, assignment, submission, grade change, discussion, module, outcome, file/attachment, SIS batch, conversation, quiz, wiki page, LTI resource link, login, asset access, and more) to subscribed destinations. Customers subscribe via Canvas Data Services and choose a delivery method — AWS SQS (standard queue named beginning with `canvas-live-events`, granted to Canvas AWS account 636161780776, optional IAM key/secret/region) or an HTTPS webhook (POSTs the event JSON, or a signed JWT whose signing keys rotate monthly and are advertised at the Canvas JWKS endpoint). Two payload formats are supported — Canvas JSON and Caliper IMS. Failed HTTPS deliveries are retried up to three times with exponential backoff over ~10–20 minutes; sustained failure deactivates the subscription. Live Events are designed for analytics and data collection workflows, not for use cases requiring strictly up-to-date data.

- **Human URL:** [https://canvas.instructure.com/doc/api/file.live_events.html](https://canvas.instructure.com/doc/api/file.live_events.html)

#### Tags

- Live Events
- Webhooks
- Events
- Streaming
- AsyncAPI
- SQS
- HTTPS
- JWT
- Caliper
- Analytics

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/file.live_events.html)
- [Documentation](https://github.com/instructure/canvas-lms/tree/master/doc/api/data_services)
- [Documentation](https://github.com/instructure/canvas-lms/tree/master/doc/api/data_services/json/canvas/event-types)
- [Documentation](https://github.com/instructure/canvas-lms/tree/master/doc/api/data_services/json/caliper)
- [Documentation](https://community.canvaslms.com/t5/Admin-Guide/How-do-I-subscribe-to-Live-Events-using-Canvas-Data-Services/ta-p/227)
- [Documentation](https://community.canvaslms.com/t5/Admin-Guide/How-do-I-configure-and-test-Canvas-Live-Events-using-HTTPS/ta-p/151)
- [Documentation](https://community.canvaslms.com/t5/Admin-Guide/How-do-I-create-an-SQS-queue-in-Amazon-Web-Services-to-receive/ta-p/170)
- [Authentication](https://8axpcl50e4.execute-api.us-east-1.amazonaws.com/main/jwks)
- [AsyncAPI](openapi/canvas-lms-live-events-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Canvas Data Access Platform

Data Access Platform (DAP) is the warehouse-scale data export API for Canvas Data 2 — the successor to Canvas Data 1 / Canvas Data CLI. DAP exposes Canvas tables and Caliper-derived event streams as snapshot and incremental queries against the canvas and catalog namespaces, intended for bulk download into a customer's data lake or warehouse.

- **Human URL:** [https://data-access-platform-api.s3.amazonaws.com/index.html](https://data-access-platform-api.s3.amazonaws.com/index.html)
- **Base URL:** `https://api-gateway.instructure.com/dap`

#### Tags

- Canvas Data
- DAP
- Data Warehouse
- Analytics
- Snapshots
- Events

#### Properties

- [Documentation](https://data-access-platform-api.s3.amazonaws.com/index.html)
- [SDK](https://github.com/instructure/dap-client-py)
- [Tool](https://github.com/instructure/canvas-data-loader)
- [Code Examples](https://github.com/instructure/canvas-hosted-data-examples)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Canvas SIS Import API

The SIS Import API ingests Canvas's canonical SIS CSV format (and ZIP archives of those CSVs) to provision accounts, terms, courses, sections, users, enrollments, groups, group memberships, cross-listings, user observers, logins, admins, change-sis-id mappings, and admin differentiation tags. Supports diffing imports against the previous import, batch mode, and asynchronous progress polling.

- **Human URL:** [https://canvas.instructure.com/doc/api/sis_imports.html](https://canvas.instructure.com/doc/api/sis_imports.html)

#### Tags

- SIS
- Student Information System
- Provisioning
- Bulk Import
- CSV

#### Properties

- [Documentation](https://canvas.instructure.com/doc/api/sis_imports.html)
- [Documentation](https://canvas.instructure.com/doc/api/sis_import_errors.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.sis_csv.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.object_ids.html)
- [Documentation](https://canvas.instructure.com/doc/api/sis_integration.html)
- [Postman Collection](collections/canvas-lms-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/canvas-lms-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://www.instructure.com)
- [Portal](https://www.instructure.com/canvas)
- [Sign Up](https://canvas.instructure.com/)
- [Documentation](https://canvas.instructure.com/doc/api/)
- [Documentation](https://canvas.instructure.com/doc/api/all_resources.html)
- [Changelog](https://canvas.instructure.com/doc/api/file.changelog.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.graphql.html)
- [Authentication](https://canvas.instructure.com/doc/api/file.oauth.html)
- [Rate Limits](https://canvas.instructure.com/doc/api/file.throttling.html)
- [Pagination](https://canvas.instructure.com/doc/api/file.pagination.html)
- [Documentation](https://canvas.instructure.com/doc/api/file.tools_intro.html)
- [Terms of Service](https://www.instructure.com/policies/api-policy)
- [Privacy Policy](https://www.instructure.com/policies)
- [Privacy Policy](https://www.instructure.com/policies/product-privacy-notice)
- [Status Page](https://status.instructure.com/)
- [Forum](https://community.canvaslms.com/)
- [Forum](https://community.canvaslms.com/t5/Canvas-Developers-Group/gh-p/canvas-developers)
- [Blog](https://www.instructure.com/blog)
- [Portal](https://www.instructure.com/canvas/canvas-credentials)
- [Portal](https://www.instructure.com/canvas/canvas-studio)
- [Portal](https://www.instructure.com/canvas/canvas-catalog)
- [GitHub Organization](https://github.com/instructure)
- [Source Code](https://github.com/instructure/canvas-lms)
- [Documentation](https://github.com/instructure/canvas-lms/wiki)
- [Getting Started](https://github.com/instructure/canvas-lms/wiki/Quick-Start)
- [Getting Started](https://github.com/instructure/canvas-lms/wiki/Production-Start)
- [Tool](https://github.com/instructure/canvas-self-hosted)
- [Source Code](https://github.com/instructure/canvas-ios)
- [Source Code](https://github.com/instructure/canvas-android)
- [SDK](https://github.com/instructure/CanvasAPI)
- [SDK](https://github.com/instructure/pandarus)
- [SDK](https://github.com/instructure/canvas_oauth_engine)
- [SDK](https://github.com/instructure/dap-client-py)
- [Tool](https://github.com/instructure/canvas-data-loader)
- [Tool](https://github.com/instructure/canvas-data-cli)
- [Code Examples](https://github.com/instructure/canvas-studio-api-examples)
- [Source Code](https://github.com/instructure/canvas-rce-api)
- [Code Examples](https://github.com/instructure/canvas-hosted-data-examples)
- [Code Examples](https://github.com/instructure/lti_example)
- [Code Examples](https://github.com/instructure/lti1_tool_provider_example)
- [Code Examples](https://github.com/instructure/lti_tool_provider_example)
- [SDK](https://github.com/instructure/ims-lti)
- [SDK](https://github.com/instructure/basiclti-util-java)
- [Tool](https://github.com/instructure/qti)
- [Tool](https://github.com/instructure/QTIMigrationTool)
- [Tool](https://github.com/instructure/moodle2cc)
- [Tool](https://github.com/instructure/common-cartridge-viewer)
- [Tool](https://github.com/instructure/analytics)
- [Tool](https://github.com/instructure/instructure-ui)
- [Code Examples](https://github.com/instructure/canvas-alexa-lambda)
- [Tool](https://github.com/instructure/canvas_connect)
- [Marketplace](https://www.instructure.com/canvas/partners)
- [Marketplace](https://www.eduappcenter.com/)
- [Portal](https://www.instructure.com/canvas/higher-education)
- [Portal](https://www.instructure.com/canvas/k-12)
- [Portal](https://www.instructure.com/canvas/business)
- [Portal](https://www.instructure.com/canvas/government)
- [Plans](plans/canvas-lms-plans-pricing.yml)
- [Rate Limits](rate-limits/canvas-lms-rate-limits.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
