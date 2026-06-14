# Atlassian Statuspage GraphQL Schema

## Overview

This conceptual GraphQL schema represents the Atlassian Statuspage REST API surface, which provides programmatic access to hosted status pages and incident communication. The REST API is available at `https://api.statuspage.io/v1` (management) and `https://[page-id].statuspage.io/api/v2` (public status). Authentication uses an API key passed as `OAuth <key>` in the Authorization header.

This schema is derived from the Statuspage REST API documentation at https://developer.statuspage.io/ and the public Status API v2 at https://doers.statuspage.io/api/v2/.

## Schema Source

- **Provider**: Atlassian Statuspage
- **API Base URL**: `https://api.statuspage.io/v1`
- **Public Status API**: `https://[page-id].statuspage.io/api/v2`
- **Documentation**: https://developer.statuspage.io/
- **Schema file**: statuspage-schema.graphql

## Domain Coverage

### Pages
A Page is the top-level container representing a Statuspage site. Each page has a unique ID (subdomain), a name, a public URL, and configurable settings. The `Page` type exposes metadata, branding, notification preferences, and links to components, incidents, subscribers, and metrics.

### Components
Components represent individual services or systems tracked on a status page. They carry a status (`operational`, `degraded_performance`, `partial_outage`, `major_outage`, `under_maintenance`), an optional group ID, and a sort order. Component groups (`ComponentGroup`) allow logical grouping of components. The `GroupedComponent` type represents a component nested within a group.

### Incidents
Incidents are the core communication primitive. Three variants are modeled:
- **RealTimeIncident** — ongoing or resolved unplanned disruptions
- **ScheduledIncident** (Maintenance) — planned windows of maintenance
- **BackfillIncident** — historical incidents entered retroactively

Each incident carries a status (`investigating`, `identified`, `monitoring`, `resolved` for unplanned; `scheduled`, `in_progress`, `verifying`, `completed` for maintenance) and a series of `IncidentUpdate` messages.

### Subscribers
Statuspage supports multiple subscriber delivery channels — email, SMS, webhook, Slack, Atlassian, RSS, and Atom feeds. The `Subscriber` interface is implemented by `EmailSubscriber`, `SmsSubscriber`, `WebhookSubscriber`, `AtlassianSubscriber`, and `SlackSubscriber`. RSS and Atom are passive endpoints modeled as `RssSubscriber` and `AtomSubscriber`.

### Metrics
Metrics display uptime or performance graphs on a status page. Providers include built-in (Self), Datadog, New Relic, Pingdom, and PagerDuty. Each `Metric` has associated `MetricData` points and `MetricHistory` aggregates.

### Templates
Incident templates (`Template`) allow pre-written incident messages and component impacts to be saved and reused.

### Organization and Auth
`Organization` groups multiple pages under a single account. `APIKey` and `Token` represent authentication primitives returned by the management API.

### Embedded Status Widget
`StatusEmbedded` captures the configuration for the Statuspage embed widget (JavaScript embed or iframe), including allowed origins and display options.

## Type List

| Type | Category |
|---|---|
| Page | Pages |
| PageDetails | Pages |
| PageStatus | Pages |
| PageNotifications | Pages |
| PageComponents | Pages |
| Component | Components |
| ComponentDetails | Components |
| ComponentStatus | Components |
| ComponentGroup | Components |
| GroupedComponent | Components |
| Incident | Incidents |
| IncidentDetails | Incidents |
| IncidentStatus | Incidents |
| IncidentType | Incidents |
| RealTimeIncident | Incidents |
| ScheduledIncident | Incidents |
| BackfillIncident | Incidents |
| IncidentUpdate | Incidents |
| IncidentUpdateDetails | Incidents |
| Subscriber | Subscribers |
| SubscriberType | Subscribers |
| EmailSubscriber | Subscribers |
| SmsSubscriber | Subscribers |
| WebhookSubscriber | Subscribers |
| AtlassianSubscriber | Subscribers |
| SlackSubscriber | Subscribers |
| RssSubscriber | Subscribers |
| AtomSubscriber | Subscribers |
| Metric | Metrics |
| MetricDetails | Metrics |
| MetricValue | Metrics |
| MetricProvider | Metrics |
| MetricData | Metrics |
| MetricHistory | Metrics |
| DatadogMetric | Metrics |
| NewRelicMetric | Metrics |
| PingdomMetric | Metrics |
| PagerDutyMetric | Metrics |
| MaintenanceWindow | Maintenance |
| MaintenanceDetails | Maintenance |
| Template | Templates |
| Organization | Auth/Org |
| APIKey | Auth/Org |
| Token | Auth/Org |
| StatusEmbedded | Widgets |
| Query | Root |
| Mutation | Root |
| PageInput | Inputs |
| ComponentInput | Inputs |
| ComponentGroupInput | Inputs |
| IncidentInput | Inputs |
| IncidentUpdateInput | Inputs |
| MaintenanceInput | Inputs |
| SubscriberInput | Inputs |
| MetricInput | Inputs |
| MetricDataPointInput | Inputs |
| TemplateInput | Inputs |
| PageFilter | Filters |
| IncidentFilter | Filters |
| ComponentFilter | Filters |
| SubscriberFilter | Filters |

## REST to GraphQL Mapping

| REST Endpoint | GraphQL Operation |
|---|---|
| GET /pages | Query.pages |
| GET /pages/{page_id} | Query.page(id) |
| PATCH /pages/{page_id} | Mutation.updatePage |
| GET /pages/{page_id}/components | Query.components(pageId) |
| POST /pages/{page_id}/components | Mutation.createComponent |
| PATCH /pages/{page_id}/components/{id} | Mutation.updateComponent |
| DELETE /pages/{page_id}/components/{id} | Mutation.deleteComponent |
| GET /pages/{page_id}/component-groups | Query.componentGroups(pageId) |
| POST /pages/{page_id}/component-groups | Mutation.createComponentGroup |
| GET /pages/{page_id}/incidents | Query.incidents(pageId) |
| POST /pages/{page_id}/incidents | Mutation.createIncident |
| PATCH /pages/{page_id}/incidents/{id} | Mutation.updateIncident |
| DELETE /pages/{page_id}/incidents/{id} | Mutation.deleteIncident |
| POST /pages/{page_id}/incidents/{id}/incident_updates | Mutation.postIncidentUpdate |
| GET /pages/{page_id}/subscribers | Query.subscribers(pageId) |
| POST /pages/{page_id}/subscribers | Mutation.createSubscriber |
| DELETE /pages/{page_id}/subscribers/{id} | Mutation.deleteSubscriber |
| GET /pages/{page_id}/metrics | Query.metrics(pageId) |
| POST /pages/{page_id}/metrics/{id}/data | Mutation.submitMetricData |
| GET /pages/{page_id}/incident_templates | Query.templates(pageId) |
| GET /pages/{page_id}/status | Query.pageStatus(pageId) (public v2) |
