# Portfolio roadmap

## Now

- [x] Establish separate structure-core, group-operation, benchmark, and batch-analysis repositories.
- [x] License the four public foundation/analysis repositories and add automated tests.
- [x] Complete release-preparation fixes: installable benchmark CLI, versioned schemas, path-safe reports, and latest-stable Python CI.
- [x] Publish reviewed prereleases for the three code foundations and the benchmark integration update.

## Next

- [x] Define a deterministic public smoke split and use it in cross-repository integration tests.
- [x] Extend the smoke split into reviewed small/medium tiers and a recomputable structural-oracle layer.
- [x] Add a `StructureRecord` adapter to the batch analyzer without copying parsers.
- [x] Add generated $M_+$/$M_-$ matrices, schema, API and all-operation homomorphism tests.
- [x] Expand the group-operation registry to all 32 crystallographic point groups and add validated spatial invariant solvers for shift current, SHG, and circular injection current.
- [ ] Integrate the invariant solver into the private NLO workflow with frozen tensor conventions and open reference fixtures.
- [ ] Turn the validated Python 3 stacking and heterostructure prototypes into one public-safe, reusable application after ownership and disclosure review.
- [ ] Prepare version-frozen design, user, dependency, and test evidence for software-copyright registration candidates.

## Later

- [ ] Add multilayer, stacking-state, intercalation, and ferroelectric evidence collections only after provenance and evidence review.
- [ ] Add workflow adapters for established materials-computation ecosystems rather than a new scheduler.
- [ ] Evaluate patent candidates privately through feature-by-feature prior-art and measurable technical-effect review before public disclosure.

An item is complete only when implementation, tests, machine contract, failure behavior, rights boundary, and independent review agree.
