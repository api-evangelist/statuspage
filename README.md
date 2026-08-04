# Statuspage (statuspage)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Statuspage by Atlassian is a hosted status page and incident communication platform that helps companies communicate real-time service status, incident updates, scheduled maintenance, and component health to customers and internal stakeholders. It supports public and private pages, audience-specific pages, subscriber notifications via email, SMS, webhooks, Slack, and Teams, and 150+ third-party component integrations. The Statuspage REST API provides programmatic access to pages, components, incidents, maintenances, metrics, subscribers, and users authenticated with an OAuth-prefixed API key.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/statuspage/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/statuspage/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Status Page
- Incident Communication
- Incident Management
- Uptime
- Reliability
- Atlassian

## Timestamps

- **Created:** 2026-05-11
- **Modified:** 2026-05-30

## APIs

### Statuspage Manage API

REST API for managing Statuspage pages, components, component groups, incidents, incident templates, scheduled maintenances, metrics, subscribers, users, and page access groups. Authentication uses an API key passed in the Authorization header with the literal "OAuth" prefix.

- **Human URL:** [https://developer.statuspage.io/](https://developer.statuspage.io/)
- **Base URL:** `https://api.statuspage.io/v1`

#### Tags

- Management
- Incidents
- Components
- Subscribers
- Metrics

#### Properties

- [Documentation](https://developer.statuspage.io/)
- [API Reference](https://developer.statuspage.io/)
- [Authentication](https://support.atlassian.com/statuspage/docs/create-and-manage-api-keys/)
- [Postman Collection](collections/statuspage.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/statuspage.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Statuspage Status API (v2)

Public, read-only REST API exposed by every Statuspage at /api/v2 that returns current status, components, incidents, maintenances, and uptime data as JSON. Useful for embedding status data in applications.

- **Human URL:** [https://doers.statuspage.io/api/v2/](https://doers.statuspage.io/api/v2/)
- **Base URL:** `https://[page-id].statuspage.io/api/v2`

#### Tags

- Status
- Public
- Read-Only

#### Properties

- [Documentation](https://doers.statuspage.io/api/v2/)
- [Postman Collection](collections/statuspage.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/statuspage.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Statuspage Webhook Notifications

Outbound webhook notifications Statuspage POSTs to subscriber endpoints for component status changes, incident lifecycle updates, and scheduled maintenance lifecycle updates. Subscribers must respond with a 2xx status code within 30 seconds.

- **Human URL:** [https://support.atlassian.com/statuspage/docs/enable-webhook-notifications/](https://support.atlassian.com/statuspage/docs/enable-webhook-notifications/)

#### Tags

- Webhooks
- Notifications
- Incidents
- Components
- Scheduled Maintenance
- Event-Driven

#### Properties

- [Documentation](https://support.atlassian.com/statuspage/docs/enable-webhook-notifications/)
- [AsyncAPI](https://raw.githubusercontent.com/api-evangelist/statuspage/refs/heads/main/asyncapi/statuspage-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/statuspage.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/statuspage.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/StatusPage)
- [LinkedIn](https://www.linkedin.com/company/statuspage)
- [Website](https://www.atlassian.com/software/statuspage)
- [Developer  Portal](https://developer.statuspage.io/)
- [Documentation](https://support.atlassian.com/statuspage/)
- [Pricing](https://www.atlassian.com/software/statuspage/pricing)
- [Sign Up](https://www.atlassian.com/software/statuspage/try)
- [Login](https://manage.statuspage.io/login)
- [Support](https://support.atlassian.com/statuspage/)
- [Integrations](https://www.atlassian.com/software/statuspage/integrations)
- [Parent  Company](https://www.atlassian.com/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
