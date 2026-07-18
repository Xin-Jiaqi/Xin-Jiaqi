# Research utility and community impact

Updated: 2026-07-18

## Decision

Research focus and community reach reinforce each other when the public promise is narrow and the internal foundation is reusable. The portfolio will not optimize every repository for stars. It will maintain two dependable foundations, promote one clear flagship first, and release application workflows only after scientific and disclosure review.

## Repository roles

| Role | Repository | What earns trust |
|---|---|---|
| Shared structure foundation | `materials-structure-core` | Correct contracts, provenance, fixtures and downstream compatibility |
| Citable symmetry reference | `group-theory-operations-toolkit` | Source-traceable data, validation and stable machine interfaces |
| First community flagship | `batch-symmetry-checker` | A five-minute batch workflow, interpretable reports and reproducible examples |
| Controlled application candidates | `extension-to-BSF`, `heterojunction` | Scientifically reviewed outputs and a recorded IP/public-disclosure decision |

The foundations should be boring, dependable and easy to reuse. The flagship should be easy to discover and explain. Applications may contain the most novel research, but novelty is not a reason to publish before validation or rights review.

## Focus–impact rules

1. **One public promise per repository.** The first screen of the README states the problem, supported input, output and limitations.
2. **Shared code moves downward.** A parser, structure contract or symmetry identifier is implemented once in a foundation after its behavior is tested.
3. **User workflows stay upward.** Batch analysis, stacking and interface construction remain independent products with their own release cadence.
4. **No speculative repository sprawl.** Multilayer, ferroelectric-state and screening ideas begin as private modules or design records. A split requires an independent user scenario and release boundary.
5. **Evidence precedes promotion.** A repository is pinned or actively promoted only after clean installation, a verified example, limitations, citation metadata and a support path are present.
6. **Publicity never bypasses IP review.** Stars cannot compensate for premature disclosure of a patent-relevant method or dataset.

## Near-term impact sequence

1. Complete review and licensing decisions for the two foundations and `batch-symmetry-checker`.
2. Publish a synthetic end-to-end example: POSCAR directory → validated structures/provenance → tolerance-aware symmetry report.
3. Add `CITATION.cff`, concise release notes and immutable artifacts to each actual release; connect the software citation to a paper or DOI when available.
4. Pin the flagship, group-theory reference and structure foundation on the profile. Do not pin unreleased application rewrites.
5. Use focused topics, consistent descriptions and a recognizable social preview after repository names stabilize.
6. Open a small number of bounded issues for documentation, new synthetic fixtures and adapters after contributor contracts are stable.
7. Share releases through research papers, reproducibility supplements, group seminars and relevant scientific communities with one reproducible example rather than generic promotion.

## Measures

Stars are a useful discovery signal but not the primary scientific objective. Review these measures quarterly:

- clean-install and five-minute-example success;
- external users, reproducible bug reports and resolved issues;
- citations, forks, downstream imports and contributed fixtures/adapters;
- release downloads and repeat users;
- scientific regressions prevented by the foundations;
- stars and profile traffic as secondary discovery measures.

A visibility task is retained only when it improves discovery for a maintained scientific outcome. A feature is retained only when it supports a foundation contract or a documented user workflow.

## GitHub implementation references

- [Repository topics](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics) improve subject-based discovery.
- A root [`CITATION.cff`](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-citation-files) exposes a machine-readable “Cite this repository” entry.
- The [community profile](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories) checks contributor-facing health files.
- [GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) bind usable artifacts and release notes to tags.
- [Profile pins](https://docs.github.com/en/account-and-profile/how-tos/profile-customization/pinning-items-to-your-profile) and [social previews](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview) make supported flagships easier to recognize.
