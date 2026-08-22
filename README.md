# Ambra Health (ambra-health)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Ambra Health (now part of Intelerad Medical Systems, and rebranded as InteleShare) is a cloud-based medical image management, exchange, and interoperability platform - a cloud VNA and PACS that lets healthcare providers, patients, and researchers store, view, route, and share diagnostic imaging in real time without a VPN or CD. Its imaging data is DICOM, and its v3 Services Public API (historically the DICOM Grid API) exposes programmatic control over studies, patients, users, groups, accounts, namespaces, sharing, storage/images, and webhooks. The REST API is JSON over HTTPS and is authenticated with a session id (`sid`) obtained from `POST /session/login` (supplied as a parameter or via the `X-AmbraHealth-SID` header). Intelerad acquired Ambra Health in 2021 to form a $1.7B cloud PACS and enterprise-imaging leader.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ambra-health/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ambra-health/refs/heads/main/apis.yml)

## Tags

- Medical Imaging
- DICOM
- Healthcare
- PACS
- Image Exchange
- Interoperability
- VNA
- Cloud Imaging

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

Base URL for all APIs: `https://access.dicomgrid.com/api/v3` (`access.ambrahealth.com` is an alias). All endpoint paths and verbs are confirmed from the public [v3 Services Public API reference](https://access.dicomgrid.com/api/v3/api.html); the JSON body schemas in the OpenAPI are honestly modeled (marked `x-schema-status: modeled`) because the reference documents commands and parameters but not per-field JSON Schemas.

### Ambra Health Session API

Authenticate against the v3 Services API. Log in with credentials to obtain a session id (`sid`), inspect the current user and account permissions, run the OAuth flow, generate PIN authentication, and log out.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Studies API

The core imaging surface. Add, list (with filtering, sorting, pagination), get, update, and delete DICOM studies; approve or reject pending studies; push to external destinations; download study files; add comments; and pull the per-study audit trail.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Patients API

Manage patient records that studies attach to - add, get, update, delete, and list patients, list a patient's studies, and merge duplicate patient records.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Users API

Administer platform users - add, get, update, delete, and invite users, list the namespaces a user can reach, and manage user API tokens.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Groups API

Organize users into groups (a group is a namespace that owns studies and members). Create, list, update, and delete groups and add users to them.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Accounts API

The top-level tenant. List and get accounts, update account settings and sharing configuration, and manage the users attached to an account.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Namespaces API

Namespaces (accounts and groups) are the containers that own studies and grant access. Read namespace permissions, settings, and info, and pull the namespace-level audit log.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Sharing API

Ambra's signature image-exchange capability. Share a study with users, groups, or accounts, list active shares, revoke a share, and share saved filters - enabling VPN-free, CD-free collaboration on diagnostic imaging.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Storage and Images API

The pixel-and-metadata layer. Load DICOM metadata into a study, list and get DICOM data, and create and list frame-level image annotations. The companion Storage API handles the underlying image bytes.

- **Human URL:** [https://dicomgrid.github.io/sdk-python/storage_api.html](https://dicomgrid.github.io/sdk-python/storage_api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

### Ambra Health Webhooks API

Register HTTP callbacks that Ambra invokes when platform events occur (such as study activity). List, add, update, and delete webhooks and inspect webhook events. Delivery is server-to-endpoint HTTP POST, not a WebSocket.

- **Human URL:** [https://access.dicomgrid.com/api/v3/api.html](https://access.dicomgrid.com/api/v3/api.html)
- **Base URL:** `https://access.dicomgrid.com/api/v3`

## Common Properties

- [GitHub Organization](https://github.com/dicomgrid)
- [LinkedIn](https://www.linkedin.com/company/intelerad)
- [Website](https://ambrahealth.com)
- [Documentation](https://access.dicomgrid.com/api/v3/api.html)
- [Plans](plans/ambra-health-plans-pricing.yml)
- [Rate Limits](rate-limits/ambra-health-rate-limits.yml)
- [Fin Ops](finops/ambra-health-finops.yml)

## Review

**Does Ambra Health expose a documented public WebSocket API?** No. The v3 Services Public API is request/response REST over HTTPS with `sid` auth; realtime notification is delivered via outbound HTTP webhooks, not a client-connected WebSocket. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
