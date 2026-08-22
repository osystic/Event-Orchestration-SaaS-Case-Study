# Engineering Decisions

## 1. Model the product as orchestration, not isolated CRUD

Event operations span people, tasks, deadlines, directories, communication, reporting and transactional workflows. The architecture therefore treats the product as a coordinated workflow system rather than a set of unrelated database forms.

## 2. Keep privileged workflows behind backend boundaries

Administrative user operations, role assignment, invitations, notifications and payment-related server actions are separated from browser-only behavior. This creates a clearer trust boundary and keeps privileged processing subject to backend authorization.

## 3. Combine role-aware UX with backend authorization

A role-aware interface improves navigation and reduces accidental misuse, but hiding a button is not authorization. The data/backend layer therefore includes row-level access controls and server-side boundaries so access policy is not delegated to presentation logic.

## 4. Separate recurring operations from user sessions

Due-soon processing, recurring summaries and analytics refresh are scheduled independently from the browser. This keeps operational automation reliable even when nobody is actively using the application.

## 5. Isolate external integrations by responsibility

Notification delivery, marketing dispatch, checkout creation and webhook handling are separate backend responsibilities. This reduces coupling and makes it easier to reason about failures, retries, authorization and provider-specific behavior.

## 6. Preserve deterministic dependency management

The retained private repository standardizes on one canonical dependency lock path. Duplicate package-manager lockfiles were removed during repository cleanup so dependency state is unambiguous.

## 7. Do not mix governance cleanup with broad refactoring

Repository consolidation uncovered pre-existing lint and dependency-maintenance debt. Rather than auto-fixing hundreds of findings during a security/governance cleanup, the debt was documented and left for dedicated remediation with regression validation.

## 8. Prefer safe preservation over literal history merging

The source project existed in duplicate historical repositories. Because one history included unsafe deployment material, the correct consolidation action was to retain the safe implementation state without importing that history. Repository integrity is defined by authoritative source and validated behavior, not by preserving every commit from every duplicate.

## 9. Keep the public portfolio independently reproducible as documentation

The public case study has its own Git history, its own disclosure rules, its own safety CI and no runtime dependency on the confidential repository. This allows OSYSTIC to demonstrate engineering capability without weakening client confidentiality or implementation ownership boundaries.
