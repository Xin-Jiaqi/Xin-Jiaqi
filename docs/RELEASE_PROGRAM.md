# Research software release program

Updated: 2026-07-18

This program turns the five materials repositories into one composable research-software line. Personal and website repositories are outside its dependency graph.

## Product line

| Layer | Product | Stable responsibility | First releasable milestone |
|---|---|---|---|
| Foundation | `materials-structure-core` | Versioned structures, coordinate and unit conventions, validated I/O, hashes, provenance, fixtures | POSCAR round-trip candidate with explicit unsupported cases |
| Foundation | `group-theory-operations-toolkit` | Source-checked operation identifiers, matrices, multiplication, lookup and validation | Importable data API and schema-validated D4h/D6h release |
| Analysis | `batch-symmetry-checker` | Batch symmetry analysis, tolerance evidence and machine-readable reports | Library + CLI producing versioned JSON/CSV reports |
| Applications | `extension-to-BSF` | Bilayer registry generation and reproducible scan preparation | Python 3 bilayer MVP validated against frozen legacy fixtures |
| Applications | `heterojunction` | Constrained interface matching and auditable structure generation | Python 3 matching MVP with strain, atom-count and failure limits |

The public repositories are engineering products, not patent specifications. Unpublished scoring rules, candidate lists, technical-effect measurements and claim-oriented combinations stay in the private invention record until ownership and filing review are complete.

## Cross-repository contracts

The products communicate through small, versioned records:

1. `StructureRecord` and `ProvenanceManifest` are owned by `materials-structure-core`.
2. `SymmetryReport` is owned by `batch-symmetry-checker`; operation identifiers resolve through `group-theory-operations-toolkit`.
3. Application repositories consume foundation records and emit an application plan plus result manifest. They do not copy parsers, symmetry tables or provenance code.
4. Every serialized record carries a schema version. A consumer must reject an unsupported major version instead of guessing.
5. Optional adapters for ASE, pymatgen, spglib, VASP, CIF and schedulers stay at repository boundaries; the internal contracts do not depend on an HPC installation.

Planned application records are deliberately descriptive rather than claim-enabling:

- `StackingPlan`: input structure IDs, transform, layer assignment, spacing, validation summary and result IDs;
- `InterfaceMatch`: input structure IDs, integer supercell matrices, strain/angle/area summary, limits and result IDs;
- `RunManifest`: tool and schema versions, parameters, timestamps, checksums, warnings and failure state.

## Release gates

A repository reaches a public release candidate only when all six gates pass.

### Scientific correctness

- coordinate, lattice-vector, unit and periodic-boundary conventions are written down;
- every corrected P0/P1 behavior has a regression fixture;
- representative results are checked with an independent implementation or hand-derived reference;
- numerical tolerances are explicit and sensitivity is reported where it changes classification;
- unsupported structures fail clearly instead of being silently repaired.

### Software quality

- supported Python versions are tested in CI;
- library and CLI behavior are separated, typed and documented;
- structured errors and nonzero exit codes cover partial and complete failure;
- wheel and source distribution build and install in an isolated environment;
- duplicate parsers and tables are removed only after output-equivalence tests pass.

### Data and reproducibility

- test data are synthetic, self-authored, redistributable or represented by a download recipe;
- every external structure has source, identifier, retrieval date, rights note and checksum;
- outputs include schema version, input hash, parameters, producer version and failure manifest;
- deterministic work receives a stable content identifier, while symmetry-equivalent identity is kept as a separate concept.

### Security and operations

- no credentials, cookies, private paths, cluster hostnames or restricted datasets are committed;
- file overwrite, path traversal, unbounded enumeration and excessive atom-count cases are tested;
- external executables and HPC schedulers are optional adapters with dry-run support;
- dependency updates and Actions use reviewable, pinned policies.

### Rights and disclosure

- authorship and ownership are confirmed before choosing a license;
- code, data, documents, screenshots and logos have separate rights checks;
- third-party algorithms are cited and independently implemented where required;
- the private invention/public-disclosure gate is completed before novel technical details appear in code, issues, benchmarks or examples.

### Distribution and community use

- README includes one verified install path, a five-minute example and limitations;
- API reference, design note, changelog, citation metadata and contribution guide are present;
- a tagged release has immutable artifacts and checksums;
- PyPI/archival DOI publication occurs only after ownership, naming and license review.

### Research utility and sustainable impact

- every public feature either strengthens a shared foundation contract or completes the flagship's documented user outcome;
- a new repository needs a distinct audience and release boundary; a new idea alone is not sufficient;
- the first public example is synthetic or redistributable and produces a scientifically interpretable result in under five minutes;
- visibility work follows correctness: citation metadata, focused topics, release notes, community-health files, social preview and profile pinning are completed only for supported entry points;
- impact is reviewed using reproducible installs, external scientific use, citations, downstream adoption, resolved issues and release downloads alongside stars.

## Candidate test matrix

| Repository | Mandatory candidate tests before release |
|---|---|
| `materials-structure-core` | Direct/Cartesian equivalence; positive and negative/non-unit POSCAR scale; Selective dynamics; species order; boundary wrapping; malformed/truncated input; hash and provenance golden cases |
| `group-theory-operations-toolkit` | schema validation; unique IDs; integer/orthogonal matrices as appropriate; closure, identity, inverse and associativity; source labels; D4h/D6h reference comparisons; API/CLI parity |
| `batch-symmetry-checker` | cubic/hexagonal/low-symmetry cells; tolerance sweeps; invalid structures; mixed batch success; deterministic JSON/CSV; library/CLI parity; spglib version capture |
| `extension-to-BSF` | frozen legacy examples; Direct/Cartesian and scale handling; repeated elements; shifts across boundaries; layer assignment; minimum-distance rejection; deterministic configuration IDs; no-overwrite behavior |
| `heterojunction` | identity and known commensurate matches; rectangular/hexagonal inputs; strain/angle/area limits; handedness; composition conservation; collision rejection; atom-count guard; deterministic ranking and manifest |

## Release sequence

1. Freeze schemas and fixtures in the two Foundation repositories.
2. Release the Analysis package against explicit compatible Foundation versions.
3. Validate each Application MVP against Foundation contracts and independent reference cases.
4. Run an end-to-end demonstration from input structures to structure, symmetry and application manifests.
5. Only then consider renaming application repositories, publishing stable packages, or splitting multilayer and screening modules.

The custodian records a release decision in a pull request. An executor's passing tests are necessary but not sufficient: scientific and disclosure review must be performed independently.

## 2026-07-18 candidate checkpoint

| Repository | Engineering evidence | Public action | Remaining gate |
|---|---|---|---|
| `materials-structure-core` | 49 tests, Ruff, sdist/wheel, Twine, clean-wheel and cross-package smoke; independent audit PASS | [Draft PR #2](https://github.com/Xin-Jiaqi/materials-structure-core/pull/2); Actions PASS | ownership/license decision and release review |
| `group-theory-operations-toolkit` | 29 tests, 832 D4h/D6h products, malformed-catalog checks, sdist/wheel, Twine and clean-wheel smoke; independent audit PASS | [Draft PR #3](https://github.com/Xin-Jiaqi/group-theory-operations-toolkit/pull/3); Actions PASS | source/data-rights and license decision |
| `batch-symmetry-checker` | 36 tests, Ruff, axis-invariance and output-recovery tests, sdist/wheel, Twine and clean-wheel MoS2 smoke; independent audit PASS | [Draft PR #3](https://github.com/Xin-Jiaqi/batch-symmetry-checker/pull/3); Actions PASS | ownership/license decision and alpha review |
| `extension-to-BSF` | Python 3 alpha; 15 source + 15 sdist tests; resource, alias and transactional-pair failure checks; sdist/wheel, Twine and clean-wheel CLI; 16-sample private real-structure smoke | local candidate only; **not pushed** | ownership, license and disclosure decision; independent physical benchmark before scientific release |
| `heterojunction` | Python 3 alpha; 17 source + 17 sdist tests; basis/motif invariance, candidate replay/tamper, resource and transactional-pair checks; sdist/wheel, Twine and clean-wheel search→build; 16-sample private real-structure smoke | local candidate only; **not pushed** | ownership, license and disclosure decision; independent physical benchmark before scientific release |

The first three pull requests are review vehicles, not releases. Their current heads also contain machine-readable citation metadata and a live CI badge; all three Actions runs pass. No tag or package publication is authorized by this checkpoint. Application branches remain local because pushing a branch to either existing public repository is itself a public disclosure. Their private smoke uses only aggregate results and content hashes; no research structure or material identity is added here.
