# Event Orchestration SaaS — Full Case Study

## Executive summary

OSYSTIC engineered and later standardized a full-stack SaaS platform centered on event planning and operational coordination. The product combines a large role-aware React application with a Supabase backend, serverless business workflows, scheduled automation, notification paths, reporting surfaces, and payment-related integration boundaries.

The public value of this case study is the engineering pattern: how to organize a broad workflow product so that UI state, identity, permissions, backend operations, notifications, scheduled jobs and transactional integrations remain separable and governable.

This document is intentionally sanitized. It does not reproduce the confidential implementation, database schema, private provider configuration, customer identity, domains, credentials, contract terms, or private conversations.

## Problem space

Event operations rarely behave like a single CRUD workflow. A real orchestration product has to coordinate many concurrent concerns:

- users with different responsibilities and access levels;
- events moving through multiple planning states;
- tasks, comments, changes and ownership hand-offs;
- reusable templates and operational directories;
- reminders and due-soon activity;
- marketing and participant communication;
- dashboards, summaries and reporting;
- invoice/payment workflows;
- scheduled work that must continue without a browser session.

The architecture therefore needed to support a workflow system rather than a collection of disconnected pages.

## Solution architecture

### Frontend application

The retained implementation uses React and TypeScript with Vite as the application build system. The frontend is organized around routed pages, reusable component primitives, hooks, integrations and supporting libraries. Form state and validation, responsive UI primitives, charting, drag-and-drop interactions and themed presentation are implemented with established ecosystem libraries rather than one monolithic custom UI layer.

### Backend and data layer

Supabase provides authentication, PostgreSQL-backed data access, row-level authorization controls, realtime/data APIs and Edge Functions. Privileged or integration-sensitive workflows are kept on the server side instead of being delegated to browser-only logic.

### Serverless workflows

The private source contains separate backend functions for role assignment, invitation/user administration, event/task notifications, marketing dispatch and payment checkout/webhook flows. This separation improves responsibility boundaries and makes sensitive operations easier to reason about and validate.

### Scheduled automation

Repository automation includes scheduled operational workflows for recurring summaries, due-soon processing and analytics refresh. This demonstrates an important SaaS property: orchestration continues independently of interactive user sessions.

## Product capability map

The source product exposes a broad set of operational surfaces, including:

- authentication and account access;
- event creation and event management;
- event summaries and dashboards;
- team collaboration and comments;
- templates and reusable planning structures;
- project/task/change-management workflows;
- calendar and progress-oriented views;
- bookings, hospitality, entertainment and related service directories;
- notifications and invitations;
- marketing campaign operations;
- reporting and analytics;
- invoice and payment-related flows.

The public repository describes these capabilities at system level only; it does not publish proprietary UI code, data models or business rules.

## Key engineering decisions

### 1. Keep privileged actions server-side

Role assignment, administrative user operations, notifications and payment-sensitive behavior are implemented through backend functions. This reduces exposure of privileged behavior and keeps browser code focused on user interaction and approved API calls.

### 2. Treat access control as a data concern as well as a UI concern

Role-aware navigation improves usability, but data authorization cannot rely only on hidden buttons. The backend architecture therefore includes row-level authorization controls and server-side boundaries.

### 3. Separate interactive workflows from scheduled orchestration

A due-soon reminder or analytics refresh should not depend on someone opening the dashboard. Scheduled automation provides an independent operational plane for recurring tasks.

### 4. Prefer explicit integration boundaries

Payment checkout, webhook processing, notification delivery and marketing dispatch are modeled as distinct backend responsibilities. This creates clearer failure domains and reduces coupling between core planning UI and external-service behavior.

### 5. Preserve a canonical dependency path

Repository consolidation standardized the retained private source on npm with `package-lock` as the authoritative dependency lock, while duplicate package-manager lockfiles were treated as repository noise rather than evidence of product completeness.

## Validation and engineering quality

During the repository-consolidation baseline, the private source successfully completed dependency installation, production build and unit testing. The recorded test baseline contains 13 test files and 49 passing tests. Governance checks and a critical-severity dependency-audit gate also passed.

The same review explicitly documented pre-existing lint and dependency-maintenance debt rather than presenting the codebase as debt-free. This distinction matters: a credible engineering case study should show both verified strengths and known remediation work.

## Repository consolidation and security governance

Two historical repositories contained substantially the same project state. A naïve merge would have imported generated files, duplicate dependency locks, local tool state and unsafe legacy deployment history into the maintained source.

OSYSTIC instead used a significance-and-security approach:

1. identify the canonical private implementation state;
2. verify that required application, backend and feature-branch data was preserved;
3. exclude generated and duplicate repository artifacts;
4. avoid importing unsafe credential-bearing history;
5. add governance and validation controls to the retained private repository;
6. create this public case study with completely independent Git history.

This is a reusable engineering lesson for repository migrations: preserving software does not require preserving every historical artifact.

## Outcome

The result is a clearly separated portfolio model:

- **private engineering repository:** implementation, migrations, Edge Functions and operational source;
- **public case-study repository:** sanitized architecture, capability proof, engineering decisions, validation boundary and lessons learned;
- **governance layer:** records repository classification, consolidation decisions and security follow-up.

The public case study is suitable for technical due diligence, proposals and capability review without turning confidential delivery material into open source.

## Known limitations and non-claims

The private baseline includes recorded lint and dependency-maintenance debt. This repository also does not independently establish production uptime, audited compliance certification, production payment certification, or live deployment state.

Those are intentionally separated from what the evidence supports: a broad implemented SaaS architecture, passing build/tests at the standardization baseline, and a governed private/public repository boundary.
