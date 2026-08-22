# Repository Hardening

## Why consolidation required judgment

The source project existed in two historical repositories with substantially the same implementation state. Treating repository consolidation as a blind history merge would have carried forward generated output, duplicate dependency locks, local tool state, nonessential automation and unsafe legacy deployment material.

The engineering goal was therefore **authoritative preservation**, not literal duplication.

## Consolidation rules

The retained private repository follows these principles:

- keep the canonical application source;
- keep backend migrations and serverless workflows that remain part of the product;
- keep operational scripts that are still required;
- retain safe automation after review;
- standardize dependency management on one lock path;
- remove generated build output;
- remove local/cache/temp state;
- remove stale tool-session planning artifacts;
- remove nonessential repository automation;
- do not import unsafe credential-bearing history merely to preserve chronology.

## Data-preservation verification

Before the legacy duplicate was approved for deletion, the canonical repository was verified to contain the required application and backend state, including the retained feature branch. Matching Git tree/blob identities were used where practical to verify that significant implementation state had been preserved without copying unsafe repository history.

This distinction is important: **content preservation and Git-history preservation are different decisions**.

## Security handling

A legacy deployment workflow contained privileged access material in repository history. The safe response was to exclude that workflow/history from the canonical repository, record the issue through governance, and treat provider-side invalidation as a separate security action.

No credential value, private project identifier or provider URL is reproduced in this public case study.

## Clean-repository policy

The maintained private source should not accumulate files simply because they existed historically. Files are evaluated by authority, operational value, reproducibility and security impact.

Generated logs, duplicate locks, temp state and one-off tool metadata are not evidence of a healthier repository; they create ambiguity and maintenance cost.

## Public case-study boundary

This repository was created separately with independent Git history. It intentionally contains only Markdown documentation, sanitized diagrams, OSYSTIC classification metadata and a public-safety workflow.

No private source, schema, migrations, deployment configuration, client material, provider identifiers or implementation artifacts should ever be copied here.

## Reusable lesson

A clean engineering archive answers three different questions separately:

1. **What is the authoritative product state?**
2. **What historical material is useful to retain?**
3. **What material creates unnecessary security, privacy or maintenance risk?**

Conflating those questions is how duplicate repositories become permanent technical debt.
