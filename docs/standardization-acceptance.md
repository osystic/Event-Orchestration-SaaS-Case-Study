# OSYSTIC Standardization Acceptance

## Repository classification

- **Class:** public engineering showcase
- **Publisher:** OSYSTIC
- **Visibility:** public
- **Purpose:** portfolio, proposals, capability proof and technical due diligence
- **Source relationship:** sanitized documentation derived from a confidential engineering project
- **Git history:** independent from confidential implementation repositories

## Acceptance checklist

- [x] README uses OSYSTIC company-case-study positioning.
- [x] Client identity and private project/domain identifiers are excluded.
- [x] Confidential implementation source is excluded.
- [x] Database schema/migrations and backend implementation are excluded.
- [x] Credentials and provider access material are excluded.
- [x] Commercial terms and private conversations are excluded.
- [x] Architecture is documented at system level.
- [x] Product capabilities are described without exposing proprietary business rules.
- [x] Engineering decisions and lessons learned are documented.
- [x] Validation claims are limited to evidence supported by the private baseline.
- [x] Known engineering debt is acknowledged rather than hidden.
- [x] Repository-hardening and consolidation lessons are documented.
- [x] Publication/reuse boundary is defined.
- [x] SECURITY guidance is present.
- [x] Public-safety CI rejects confidential/source artifacts and likely access material.
- [x] Required diagrams and documentation are enforced by CI.
- [x] No production/live deployment claim is made by the showcase itself.

## Presentation standard

The repository is designed to read as an OSYSTIC engineering artifact rather than a client-delivery dump. It separates executive context, product capability, architecture, technical decisions, validation, security/governance and disclosure policy into reviewable documents.

## Maintenance rule

Future changes should improve the public case study without importing confidential implementation details. Any new image, document, benchmark, integration detail or operational evidence should be reviewed against `docs/disclosure-boundary.md` before merge.

## Acceptance state

**APPROVED PUBLIC SHOWCASE** once the `Public Showcase Safety` workflow passes on the publication pull request and the pull request is merged to `main`.
