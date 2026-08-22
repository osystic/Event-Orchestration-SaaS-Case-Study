# Security Policy

## Repository scope

This repository is a **sanitized public case study**, not the production application or confidential implementation repository.

## Do not publish

Do not commit any of the following here:

- application or backend implementation source;
- database schemas, migrations or generated database types;
- environment files or deployment configuration;
- credentials, tokens, passwords, signing material or provider access details;
- customer/user/event exports;
- private screenshots, domains or project identifiers;
- private operational scripts;
- commercial documents or private conversations;
- confidential Git-history exports or delivery archives.

## Historical security note

During private repository consolidation, unsafe legacy deployment material was intentionally excluded from the maintained source rather than propagated into the canonical repository. Provider-side invalidation/rotation is handled through private governance and is not documented with sensitive values here.

## Reporting

If you identify confidential implementation material, access material or private customer/project information in this public repository, report it privately to OSYSTIC through an established business contact channel. Do not open a public issue containing the sensitive material.

## Public-safety automation

The repository includes a `Public Showcase Safety` workflow that validates required case-study structure and rejects common implementation, deployment, archive and secret-bearing artifact classes. Automated checks support review; they do not replace human disclosure judgment.
