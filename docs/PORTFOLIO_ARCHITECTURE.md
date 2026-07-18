# Research software portfolio architecture

Updated: 2026-07-17

## 1. Design rules

The portfolio is a set of small products connected through stable contracts, not a monorepo. A new repository is justified only when it has an independent user scenario, input/output schema, test suite, release cadence, and ownership boundary.

The architecture has three coordinated layers and one deliberately separate personal domain:

1. **Foundation** — structure representation and crystallographic group-theory knowledge.
2. **Analysis and validation** — reusable symmetry analysis and scientific reports.
3. **Applications** — bilayer, multilayer, heterostructure, and ferroelectric-state workflows.
4. **Personal and web** — independent projects that share maintenance practices but no materials-code dependencies.

## 2. Repository map

| Domain | Repository | Owns | Must not own |
|---|---|---|---|
| Structure foundation | `materials-structure-core` | Structure model, POSCAR/CIF adapters, Direct/Cartesian conventions, scale factor, Selective dynamics, wrapping, validation, ordered hash, provenance, fixtures | Group tables, VASP/Slurm workflows, application-specific screening |
| Symmetry foundation | `group-theory-operations-toolkit` | Canonical operation names, matrices, multiplication tables, layer/point-group mappings and validation data | Generic file parsers or workflow orchestration |
| Analysis | `batch-symmetry-checker` | `SymmetryReport`, tolerance robustness, anomaly reporting, CLI and tabular/JSON exports | Duplicate structure parsers or private group-name tables |
| Layered application | `extension-to-BSF` → future `bilayer-stacking-workflow` | Registry enumeration, layer shift/spacing, collision checks, energy-surface workflow and run manifests | Generic POSCAR/CIF parsing or copied symmetry tables |
| Heterostructure application | `heterojunction` → future `heterostructure-builder` | Integer supercell matching, strain/angle constraints, interface registry and structure reports | Legacy Python 2 as production code, duplicated foundation logic |
| Personal and web | three existing repositories | Offline reading visualization, personal website, anonymous website template | Materials research dependencies |

## 3. Dependency contracts

- Foundation repositories never depend on analysis or applications.
- Applications do not import another application's scripts or working directories.
- Structure exchange uses a versioned `StructureRecord` and `ProvenanceManifest`.
- Symmetry exchange uses a versioned `SymmetryReport`.
- VASP, Slurm, database downloads, and institution-specific paths are optional application adapters.
- Code is not copied across repositories; shared behavior is extracted only after its scientific contract and tests are explicit.

## 4. Test-data strategy

Keep the first 8–12 small, synthetic or self-authored structures in `materials-structure-core/tests/fixtures/`. Required cases:

- equivalent Direct and Cartesian structures;
- positive and negative/non-unit POSCAR scale factors;
- Selective dynamics flags;
- cubic and hexagonal bulk cells;
- monolayer and bilayer cells with vacuum;
- species not grouped in input order;
- atoms across periodic boundaries;
- a deliberately malformed structure.

External database structures must include source, version, identifier, retrieval date, license, and checksum. When redistribution rights are unclear, store a download recipe and expected checksum instead of the file.

## 5. Repository lifecycle labels

- `validated-data`: current data passes repository checks, but a compatibility policy and stable release are not yet complete.
- `stable-data`: verified data/API with compatibility guarantees.
- `experimental`: scaffold or research implementation whose scientific contracts are still under review.
- `alpha`: usable but evolving product with automated tests.
- `legacy`: historical code not approved for new scientific conclusions.
- `personal`, `website`, `template`: outside the materials dependency graph.

## 6. Split/rename gates

Do not create separate repositories for multilayer, ferroelectric states, sliding ferroelectricity, or high-throughput screening yet. First validate them as modules in the two application repositories. Split only when a module can run independently, has stable schemas and tests, and has either two downstream consumers or an independent release need.

Rename `extension-to-BSF` and `heterojunction` only after their validated replacements pass end-to-end fixtures; GitHub redirects can then preserve links.

## 7. Public entry points

The dependency graph and the community-facing product map are intentionally different. The two foundations optimize for stable reuse, while a small number of flagships explain complete user outcomes.

- **Near-term flagship:** `batch-symmetry-checker`, because it can take a directory of structures to an auditable report without exposing unpublished application methods.
- **Citable reference asset:** `group-theory-operations-toolkit`, positioned as verified symmetry data and a machine-readable API.
- **Shared infrastructure:** `materials-structure-core`, promoted through downstream integrations and contracts rather than unrelated end-user features.
- **Controlled research applications:** bilayer and heterostructure tools remain unpromoted alphas until scientific, ownership, licensing and disclosure gates pass.

This prevents star and maintenance fragmentation: shared capability moves downward, complete user stories remain upward, and speculative research stays private until it has a tested public boundary.
