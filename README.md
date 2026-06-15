# Statuspage (statuspage)

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
