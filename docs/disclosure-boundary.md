# Disclosure Boundary

## Purpose

This repository is a public OSYSTIC engineering case study. Its job is to demonstrate architecture, engineering judgment, validation discipline and repository governance without exposing confidential delivery material.

## Allowed public content

The repository may contain:

- sanitized system architecture;
- technology categories;
- high-level product capability descriptions;
- engineering decisions and lessons learned;
- non-sensitive validation summaries;
- repository-governance and hardening principles;
- public-safe diagrams;
- OSYSTIC publication and reuse notices.

## Excluded content

The following must remain outside this repository:

- client or customer identity;
- private company/domain/project identifiers;
- confidential application source;
- database schemas, migration scripts or generated database types;
- backend function implementation;
- environment or deployment configuration;
- private provider references;
- credentials or access material;
- private screenshots containing customer/project information;
- exported customer/event/user data;
- contracts, invoices, payment terms or private conversations;
- private Git history or internal delivery archives;
- internal incident values or exact access-material fingerprints.

## Claims boundary

The case study may state that the retained private baseline passed dependency installation, production build and its unit-test suite at the recorded standardization point. It may also state that repository governance and a critical dependency-audit gate passed at that baseline.

It must not convert those facts into unsupported claims of audited compliance, guaranteed uptime, penetration-test certification, production payment certification, zero technical debt or universal end-to-end coverage.

## Source relationship

The confidential engineering repository and this public repository have separate purposes and histories. This repository must never become a mirror, fork or partial source export of the private implementation.

## Review rule

When a potential public artifact is ambiguous, default to exclusion until it can be shown that the material is both necessary for the showcase and safe to disclose.
