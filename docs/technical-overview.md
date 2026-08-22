# Technical Overview

## Architecture profile

The system follows a browser application, managed backend and serverless workflow model.

```text
React / TypeScript application
        |
        +-- routing and role-aware UX
        +-- forms and validation
        +-- dashboards and charts
        +-- event and task operations
        +-- collaboration and directory surfaces
        |
        v
Managed backend
        |
        +-- authentication
        +-- PostgreSQL persistence
        +-- row-level authorization
        +-- realtime/data services
        +-- serverless functions
                |
                +-- user and role workflows
                +-- invitations
                +-- event and task notifications
                +-- marketing dispatch
                +-- checkout and webhook processing

Scheduled automation
        +-- due-soon processing
        +-- recurring marketing summary
        +-- analytics refresh
```

## Frontend stack

The private source uses React 18, TypeScript and Vite. The UI ecosystem includes Tailwind CSS, Radix-based component primitives, React Router, React Hook Form, Zod, Recharts and drag-and-drop utilities.

The architectural emphasis is separation between routed application pages, reusable components, hooks, integration clients and shared helpers so a broad operational product does not collapse into one tightly coupled component tree.

## Backend stack

Supabase provides the managed backend layer. The confidential engineering repository retains the database evolution and serverless workflow implementation; those artifacts are deliberately excluded from this public case study.

Backend responsibilities include identity/session management, PostgreSQL persistence, row-level authorization controls, realtime/data access, privileged role/invitation workflows, notification and marketing actions, plus server-side checkout and webhook responsibilities.

## Validation stack

The retained engineering repository uses npm for deterministic dependency installation, Vite for production builds, Vitest for unit testing, ESLint for static-analysis visibility and GitHub Actions for repository/build/test/security governance.

At the repository-standardization baseline, dependency installation, production build and 49 unit tests passed. Existing lint debt was recorded separately rather than hidden.

## Security architecture principles

1. Browser code is not the trust boundary; privileged operations belong behind backend authorization.
2. Data access must be constrained server-side; role-aware UI does not replace row-level controls.
3. Access material must stay out of maintained source and be managed through provider/environment controls.
4. Payment-sensitive actions remain server-side.
5. Scheduled work runs independently from interactive UI state.
6. Public portfolio material uses independent Git history rather than exposing confidential source history.

## Public technical boundary

This repository contains no application implementation, database migration source, backend function source, environment configuration, deployment configuration, private screenshots or exported customer data. Architecture and engineering decisions are described at a level that demonstrates capability without reconstructing the confidential product.
