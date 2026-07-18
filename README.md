# Jiaqi Xin — Computational Materials & Ferroelectricity

I build reproducible research software for crystallographic symmetry, layered-material structures, heterostructures, and ferroelectric-state exploration.

## Research software architecture

```mermaid
flowchart BT
  S[materials-structure-core] --> A[batch-symmetry-checker]
  G[group-theory-operations-toolkit] --> A
  S --> B[bilayer stacking workflow]
  G --> B
  A --> B
  S --> H[heterostructure builder]
  G --> H
  A --> H
  B --> F[future multilayer and ferroelectric-state workflows]
  H --> F
```

The dependency direction is always upward: foundations never import application code. Applications exchange versioned structures, symmetry reports, and provenance manifests instead of copying parsers or scripts.

## Portfolio

| Layer | Repository | Status | Purpose |
|---|---|---:|---|
| Structure foundation | [`materials-structure-core`](https://github.com/Xin-Jiaqi/materials-structure-core) | experimental | Structure contracts, coordinate transforms, validation, hashing, provenance, and regression fixtures |
| Symmetry foundation | [`group-theory-operations-toolkit`](https://github.com/Xin-Jiaqi/group-theory-operations-toolkit) | validated-data / pre-release | Machine-readable crystallographic operations, matrices, and verified multiplication tables |
| Analysis | [`batch-symmetry-checker`](https://github.com/Xin-Jiaqi/batch-symmetry-checker) | alpha | Batch symmetry analysis and tolerance-robust reporting |
| Layered-material application | [`extension-to-BSF`](https://github.com/Xin-Jiaqi/extension-to-BSF) | public legacy / alpha under review | Bilayer stacking and sliding-workflow research prototype |
| Heterostructure application | [`heterojunction`](https://github.com/Xin-Jiaqi/heterojunction) | public legacy / alpha under review | Historical prototype with a Python 3 redesign behind scientific and disclosure gates |

Personal and web projects are intentionally outside the materials-software dependency graph: [`weread-calendar`](https://github.com/Xin-Jiaqi/weread-calendar), [`Xin-Jiaqi.github.io`](https://github.com/Xin-Jiaqi/Xin-Jiaqi.github.io), and [`minimal-academic-homepage`](https://github.com/Xin-Jiaqi/minimal-academic-homepage).

## Current 90-day focus

1. Maintain `materials-structure-core` and `group-theory-operations-toolkit` as the reusable scientific foundation; application repositories consume their contracts instead of copying them.
2. Make `batch-symmetry-checker` the first community-facing flagship: one clear problem, a five-minute workflow, comparable reports, and a citable release.
3. Validate bilayer and heterostructure applications privately against synthetic and real-world structures before choosing what can be disclosed.
4. Publish fewer, stronger entry points. New repositories or public features need an independent user scenario, tests, documentation, and a maintenance owner.
5. Measure impact by reproducible use, citations, downstream adoption, issues resolved, and releases—not stars alone.

See [the portfolio architecture](docs/PORTFOLIO_ARCHITECTURE.md), [the research-utility and community-impact strategy](docs/RESEARCH_UTILITY_AND_IMPACT.md), [the release program and candidate-test matrix](docs/RELEASE_PROGRAM.md), [the executable roadmap](ROADMAP.md), [the maintenance workflow](docs/MAINTENANCE_WORKFLOW.md), [the ecosystem/prior-art map](docs/ECOSYSTEM_AND_PRIOR_ART.md), and [the IP/public-disclosure gate](docs/IP_AND_DISCLOSURE_GATE.md).

The 2026-07-18 engineering checkpoint opened independently reviewed draft PRs for the two foundations and the analysis package. The two Python 3 application candidates also passed local source/sdist/wheel, failure-injection and private real-structure smoke checks, but remain local until ownership, licensing and public-disclosure decisions are recorded; passing tests alone do not authorize publication.

## Quality principles

- Scientific invariants and provenance are part of the API.
- Every P0/P1 scientific fix requires a fixture, regression test, and independent review.
- Public visibility does not imply an open-source license; each repository states its own code, data, and asset rights.
- Unpublished algorithms, scoring functions, candidate lists, and technical-effect data stay private until ownership and patent review are complete.
