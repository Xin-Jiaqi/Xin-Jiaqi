# Portfolio roadmap

This public roadmap contains engineering work only. Unpublished algorithms, scoring functions, candidate materials, and technical-effect data belong in a private invention record.

## Days 1–14 — contracts and fixtures

- [x] Create `materials-structure-core` with an experimental scaffold and draft `StructureRecord`/`ProvenanceManifest` v0 contracts.
- [ ] Add 8–12 synthetic/self-authored monolayer, bilayer, bulk, boundary, scale-factor, and malformed fixtures.
- [x] Assign lifecycle status and topics to every repository.
- [x] Define stable package names: `materials_structure_core`, `group_theory_operations`, `batch_symmetry_checker`.
- [x] Record license/ownership status separately for code, data, documents, images, and logos.

## Days 15–30 — structure core v0.1

- [x] Implement POSCAR read/write round trips including Direct/Cartesian, scale factor, species order, and Selective dynamics.
- [ ] Harden and freeze the v1 periodic-wrapping/content-hash contracts; add minimum-distance and collision checks.
- [ ] Add an optional CIF adapter with explicit dependency and round-trip tolerances.
- [ ] Test Python 3.10–3.12 and document numerical tolerances.
- [ ] Publish the first v0.1 release only after independent scientific review.

## Days 31–45 — symmetry chain

- [ ] Add a source-checked and tested registry for all 32 crystallographic point-group HM/Schönflies names before making the group-theory package the canonical symbol source.
- [x] Package `group-theory-operations-toolkit` behind a stable data API; define compatibility/deprecation for `group_tools.py apply-poscar` and delegate generic structure I/O to the structure core only after output-equivalence tests pass.
- [ ] Separate `batch-symmetry-checker` into importable library and CLI; migrate parsing/provenance to `StructureRecord`/`ProvenanceManifest` before removing duplicate code.
- [ ] Migrate the batch HM–Schönflies mapping only after the group-theory registry reaches complete equivalent coverage and contract tests pass.
- [x] Define versioned JSON/CSV/Excel `SymmetryReport` output.
- [ ] Add tolerance-stability scores, 2D mode, anomaly reports, and complete failure manifests.
- [ ] Add cross-repository contract tests.

## Days 46–60 — bilayer workflow

- [x] Freeze the current MATLAB output as legacy evidence; do not silently overwrite it.
- [x] Fix scale-factor, Cartesian/Direct, species mapping, overwrite, and repeated-element problems using fixtures.
- [x] Add wrapping, collision checks, unique configuration IDs, and provenance.
- [ ] Cross-check representative outputs with an independent library or hand-derived reference.
- [ ] Rename only after the validated implementation replaces the legacy path.

## Days 61–75 — heterostructure MVP

- [x] Start a Python 3 rewrite branch in `heterojunction`.
- [x] Implement an alpha integer-supercell matching path with explicit area, strain, angle, atom-count and search limits; keep it unreleased until invariant tests pass.
- [ ] Add interlayer spacing, registry/twist enumeration, collision and composition checks.
- [x] Produce POSCAR plus machine-readable JSON reports.
- [x] Archive Python 2 scripts and label them unfit for new scientific conclusions.

## Days 76–90 — releases and rights preparation

- [ ] Run an end-to-end benchmark across structure, symmetry, bilayer, and heterostructure layers.
- [ ] Create versioned releases, hashes, installation guides, design documents, and test reports.
- [ ] Prepare software-copyright evidence for `materials-structure-core` and `batch-symmetry-checker` after ownership review.
- [ ] Complete prior-art, ownership, and public-disclosure review for candidates recorded in the private invention log; do not list unpublished implementations in this public roadmap.
- [ ] Complete ownership and public-disclosure review before exposing novel methods or results.

## Community-impact track

- [ ] Make `batch-symmetry-checker` the first pinned flagship after its license and alpha gates pass; keep the two foundations visibly linked as reusable dependencies.
- [ ] Give each releasable repository one tested five-minute example, limitations, `CITATION.cff`, release notes, and a support/contribution path.
- [ ] Publish one synthetic end-to-end demonstration from POSCAR input to structure provenance and symmetry report; do not use restricted research data in the public example.
- [ ] Add focused repository topics and a consistent social-preview design only after names and release positioning are stable.
- [ ] Label small, bounded onboarding tasks only after the public API and contributor setup are stable enough that outside work will not be discarded.
- [ ] Review quarterly evidence: clean-install success, external issues resolved, forks/downstream imports, citations, release downloads, and stars. Do not optimize stars in isolation.

## Definition of done

A roadmap item is complete only when its implementation, fixture/provenance, regression test, user documentation, failure behavior, license/ownership note, and independent review are all recorded.
