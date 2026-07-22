# Jiaqi Xin — Materials Research Software

I build reusable tools for crystal structures, symmetry, and layered-material research. The maintained public stack follows three technical layers; personal projects are kept separate.

| Layer | Responsibility | Repositories |
|---|---|---|
| Foundation | Structure contracts, symmetry knowledge, and licensed test structures | [`materials-structure-core`](https://github.com/Xin-Jiaqi/materials-structure-core), [`group-theory-operations-toolkit`](https://github.com/Xin-Jiaqi/group-theory-operations-toolkit), [`materials-structure-benchmark`](https://github.com/Xin-Jiaqi/materials-structure-benchmark) |
| Analysis | Reproducible batch symmetry reports | [`batch-symmetry-checker`](https://github.com/Xin-Jiaqi/batch-symmetry-checker) |
| Applications | Bilayer and heterostructure engineering alphas under public review; not validated releases | [`extension-to-BSF`](https://github.com/Xin-Jiaqi/extension-to-BSF), [`heterojunction`](https://github.com/Xin-Jiaqi/heterojunction) |
| Personal | Academic communication and independent utilities | [`Xin-Jiaqi.github.io`](https://github.com/Xin-Jiaqi/Xin-Jiaqi.github.io), [`minimal-academic-homepage`](https://github.com/Xin-Jiaqi/minimal-academic-homepage), [`weread-calendar`](https://github.com/Xin-Jiaqi/weread-calendar) |

The foundation and analysis repositories are public prereleases with explicit tests, provenance, and repository-level rights. Batch Symmetry Checker consumes the shared structure contract, and the benchmark provides nested regression tiers with recomputable structural invariants. Python 3 application candidates are visible as draft reviews, but they are not reusable releases until licensing and scientific-scope review are complete; unpublished research data remain private.

See the [roadmap](ROADMAP.md) and [governance rules](GOVERNANCE.md).
