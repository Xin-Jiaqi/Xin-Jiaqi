# Portfolio maintenance workflow

## Roles

1. **Custodian** — defines scope and risk, assigns work, checks cross-repository boundaries, and makes the merge decision.
2. **Auditor** — performs read-only code, data, dependency, security, rights, reproducibility, and scientific-correctness review.
3. **Executor** — changes only the approved scope in a focused branch and adds regression evidence.
4. **Independent reviewer** — reruns tests and challenges the diff without relying on the executor's summary.
5. **Research/IP reviewer** — checks primary sources, prior public disclosures, ownership, and whether technical detail must remain private.

One person or agent may coordinate several roles, but the executor cannot be the only reviewer of a scientific change.

## Severity

- **P0** — security, rights, scientific correctness, or data-loss risk; blocks publication and scientific use.
- **P1** — high-probability reliability, reproducibility, or automation failure; requires near-term regression coverage.
- **P2** — maintainability, performance, usability, or longer-term product work.

## Change flow

1. Read the repository, default branch, current diff, tests, data contracts, and ownership/license status.
2. Freeze a minimal reproducer or fixture before modifying P0/P1 behavior.
3. Work in a focused branch; never mix unrelated repositories or personal working-tree changes.
4. Record scientific invariants, provenance, failure behavior, compatibility impact, and tests in the PR.
5. Compare important remote files with the reviewed local version by Git blob SHA.
6. Require CI plus independent review; use squash merge for a single-purpose maintenance PR.
7. After merge, update the persistent Desktop clone and the portfolio roadmap/status.

## Merge gate

- approved diff only;
- regression fixture or reproducible benchmark;
- no credentials, cookies, private paths, restricted data, or unlicensed assets;
- code/data/document/asset ownership status recorded;
- all applicable supported runtimes, platforms, data validators, and package artifacts verified;
- versioned input/output schemas and explicit failure reporting;
- IP/public-disclosure gate completed;
- independent reviewer records PASS.

## Repository-creation gate

A new repository needs an independent user scenario, a defined and independently testable input/output boundary with a stabilization plan, its own tests and release cadence, and an ownership reason. Stable schemas are required for a formal release, not for an explicitly experimental scaffold. Shared code is extracted after two real consumers exist; speculative empty repositories are not created.
