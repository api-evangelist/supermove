# Supermove (supermove)

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
