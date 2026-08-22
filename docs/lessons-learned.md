# Lessons Learned

## Orchestration products need explicit boundaries

When one SaaS product spans event creation, tasks, collaboration, directories, marketing, reporting and payment-related flows, complexity grows through interactions between modules. Clear frontend, backend, authorization and integration boundaries matter more than adding another screen quickly.

## Role-aware UX is not authorization

Conditional navigation and role-specific interfaces improve usability, but they cannot be the only access-control mechanism. Backend and data-level authorization must protect the same operations independently of the browser.

## Scheduled work is a separate operational plane

Reminders, recurring summaries and analytics refresh should not depend on someone opening the product. Scheduled automation needs its own failure, authorization and observability considerations.

## Integration code should have narrow responsibilities

Notification delivery, marketing dispatch and payment-related processing are easier to operate when they are separate responsibilities instead of being embedded in unrelated frontend flows.

## Passing builds and tests do not mean zero debt

A production build and passing unit suite are strong baseline signals, but they do not erase lint backlog, dependency advisories or the need for broader regression coverage. Recording debt explicitly is more professional than hiding it behind a green badge.

## Governance cleanup should not become an uncontrolled refactor

Repository consolidation found hundreds of pre-existing lint findings. Automatically changing them during a security/cleanup pass would have mixed governance, refactoring and behavior changes in one review. Separating those concerns reduced risk.

## Duplicate repositories need authority rules

Two repositories that look similar are not automatically safe to merge. Before consolidation, compare authoritative source state, feature branches, backend state, generated files, automation and security history.

## Security can make history preservation undesirable

When a historical workflow contains privileged access material, importing that history into a clean canonical repository adds risk without improving the current product. Preserve required implementation state, not unsafe chronology.

## Public portfolios should be built from sanitized knowledge, not private history

The strongest public case study explains architecture, engineering decisions, validation and lessons while keeping source code, client identity, provider configuration and commercial context private. A fresh Git history creates a clean technical and legal boundary.

## Clean Git is an engineering asset

Build logs, duplicate locks, temp state and tool-session files create noise. A repository should contain authoritative, reviewable material that helps engineers build, validate, operate or understand the system.
