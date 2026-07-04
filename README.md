# Supermove (supermove)

Supermove is a cloud-based moving company operating system that manages the full job lifecycle for residential and commercial movers - sales and booking, estimating, dispatch and operations, a field crew app, storage, payments, and accounting. It is a proprietary SaaS platform sold via demo and a custom subscription quote (no self-serve signup or published price).

**Access model (read this first):** Supermove's public developer surface is intentionally narrow. There is **one** documented public API - the **Developer API "New Lead Endpoint."** It is an *inbound* webhook: each Supermove account is provisioned with a unique endpoint URL, and an upstream lead provider (or the company's own website) POSTs a lead as JSON to that URL to create a new lead/project. Possession of the account-specific URL is what scopes the payload to the account - **no API key or organization identifier is sent.** This surface is lead ingestion only; it does **not** provide documented public read/write access to jobs, moves, customers, estimates, crews, dispatch, or invoices. Those exist as product features and are exchanged with third parties through Supermove's own named integrations (QuickBooks Online, HubSpot, Stripe, Google Calendar, Zapier, Thumbtack, and other lead providers) rather than a general public REST API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/supermove/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/supermove/refs/heads/main/apis.yml)

## Tags

- Moving
- Moving Company Software
- Logistics
- Field Service
- Lead Management
- Operations
- Dispatch
- Webhooks

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

### Supermove Developer API - New Lead Endpoint

The one documented public Supermove API. Each Supermove account exposes a unique per-account webhook URL; a lead provider or the company's own website POSTs a lead as JSON to that URL to create a new lead/project. The payload follows a documented JSON schema with a `project_type` plus `client`, `billing_client`, and `jobs` objects (contacts, locations, and lead metadata); most fields are optional. Authentication is by possession of the account-specific endpoint URL - no API key is used. This surface is inbound only.

Endpoints are **modeled** in OpenAPI from the public Help Center documentation because the concrete host is a per-account URL that Supermove does not publish.

- **Human URL:** [Developer API: New Lead Endpoint](https://help.supermove.com/hc/en-us/articles/36934839868692-Developer-API-New-Lead-Endpoint)

#### Tags

- Leads
- Webhooks
- Inbound Integration
- Lead Providers

#### Properties

- [Documentation](https://help.supermove.com/hc/en-us/articles/36934839868692-Developer-API-Integration)
- [API Reference](https://help.supermove.com/hc/en-us/articles/36934839868692-Developer-API-New-Lead-Endpoint)
- [OpenAPI](openapi/supermove-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/supermoveco)
- [Website](https://www.supermove.com/)
- [Documentation](https://help.supermove.com/hc/en-us/articles/36934839868692-Developer-API-Integration)
- [Plans](plans/supermove-plans-pricing.yml)

## Pricing

Supermove does not publish standard or per-user pricing. It is sold as a custom subscription - book a demo for a personalized quote. A free trial and demo are reported by third-party review sites. The Developer API New Lead Endpoint is a platform capability with no separately published API price, quota, or usage tier. See [plans/supermove-plans-pricing.yml](plans/supermove-plans-pricing.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
