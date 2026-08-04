# Jenkins (jenkins)

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

Jenkins is the leading open source automation server that enables developers to reliably build, test, and deploy software. Jenkins exposes a machine-consumable Remote Access API for nearly every resource it manages, available in XML (with XPath filtering), JSON (with JSONP), and a Python-compatible variant, and supports HTTP Basic auth with API tokens for scripted clients.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/jenkins/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/jenkins/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Automation
- Build Server
- CI/CD
- Continuous Delivery
- Continuous Integration
- DevOps
- Open Source
- Remote Access API

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-05-19

## APIs

### Jenkins Remote Access API

Jenkins provides a machine-consumable Remote Access API to nearly every resource it exposes. The API is reached by appending /api/ to any Jenkins resource URL (top-level, jobs, builds, queue, nodes, views, etc.), is available in XML, JSON (JSONP), and Python variants, and supports authenticated requests via HTTP Basic auth with API tokens. Common operations include triggering builds, retrieving job and build information, and inspecting build queues, with depth and tree query parameters for controlling response shape.

- **Human URL:** [https://www.jenkins.io/doc/book/using/remote-access-api/](https://www.jenkins.io/doc/book/using/remote-access-api/)

#### Tags

- JSON
- Python
- Remote Access
- REST API
- XML

#### Properties

- [Documentation](https://www.jenkins.io/doc/book/using/remote-access-api/)
- [Authentication](https://www.jenkins.io/doc/book/system-administration/authenticating-scripted-clients/)
- [A P I Tokens](https://www.jenkins.io/doc/book/managing/system-configuration/#configuring-api-tokens)
- [OpenAPI](openapi/jenkins-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/jenkins.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/jenkins.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/jenkinsio)
- [Website](https://www.jenkins.io/)
- [Getting Started](https://www.jenkins.io/doc/pipeline/tour/getting-started/)
- [Documentation](https://www.jenkins.io/doc/)
- [Installation](https://www.jenkins.io/doc/book/installing/)
- [Plugins](https://plugins.jenkins.io/)
- [Tutorials](https://www.jenkins.io/doc/tutorials/)
- [Blog](https://www.jenkins.io/node/)
- [Community](https://www.jenkins.io/participate/)
- [GitHub Organization](https://github.com/jenkinsci)
- [Security Advisories](https://www.jenkins.io/security/advisories/)
- [Governance](https://www.jenkins.io/project/governance/)
- [Roadmap](https://www.jenkins.io/project/roadmap/)
- [Privacy Policy](https://www.jenkins.io/privacy/)
- [Terms of Service](https://www.jenkins.io/project/conduct/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
