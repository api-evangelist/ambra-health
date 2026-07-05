# Ambra Health (ambra-health)

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
