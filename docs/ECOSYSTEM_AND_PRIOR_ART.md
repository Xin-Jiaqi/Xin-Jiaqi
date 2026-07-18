# Ecosystem and prior-art map

Selected primary sources checked on 2026-07-17. This is not an exhaustive literature or patent search and is not a patentability opinion.

## Reuse rather than reimplement

| Need | Primary ecosystem | Portfolio decision |
|---|---|---|
| Structure objects and POSCAR/CIF I/O | [pymatgen core](https://pymatgen.org/pymatgen.core.html) | Wrap a maintained backend with strict validation, provenance, and golden fixtures; do not add another handwritten parser |
| Generic structure construction | [ASE build tools](https://wiki.fysik.dtu.dk/ase/ase/build/build.html) | Reuse `stack`, `cut`, and supercell operations where contracts match; keep ASE as an adapter boundary |
| Space-group identification | [spglib](https://spglib.readthedocs.io/en/stable/) | Reuse identification/standardization; add portfolio-specific uncertainty, dimensional, and audit reporting |
| Layer-group/representation verification | [Bilbao Crystallographic Server](https://cryst.ehu.es/) | Use as an authoritative verification/citation source; verify terms before redistributing machine-extracted data |
| Coherent interface matching | [pymatgen interface analysis](https://pymatgen.org/pymatgen.analysis.interfaces.html) and [Zur–McGill (1984)](https://doi.org/10.1063/1.333084) | Treat basic lattice matching as prior art; differentiate with multilayer, state/path, and physical feasibility contracts |
| Commensurate twisted bilayers | [Twister paper](https://doi.org/10.1016/j.cpc.2021.108184) | Treat general moiré-supercell generation as prior art |
| Multilayer commensurate construction | [Nookiin](https://doi.org/10.1016/j.cpc.2025.110011), [MLM](https://arxiv.org/abs/2605.05393), and [MoireStudio](https://doi.org/10.1016/j.cpc.2026.110216) | Do not claim multilayer or arbitrary-Bravais construction by itself; benchmark atom-count, strain, periodicity and failure limits against these public implementations |
| High-throughput interface design | [InterMatch](https://doi.org/10.1038/s41467-023-43496-5) | Treat database-driven strain, charge-transfer and superlattice screening as prior art; integrate through explicit records rather than duplicating its workflow |
| Phonon-mode distortions | [phonopy settings](https://phonopy.github.io/phonopy/setting-tags.html) | Reuse modulation/irrep outputs for path proposals and independent checks |
| Ferroelectric polarization paths | [pymatgen ferroelectricity](https://pymatgen.org/pymatgen.analysis.ferroelectricity.html) | Reuse branch tracking; autonomous state/path discovery remains a separate research problem |
| High-throughput execution | [atomate2](https://materialsproject.github.io/atomate2/) | Integrate at the workflow layer instead of building another scheduler |

## Published baseline that constrains novelty

- General symmetry theory of stacking ferroelectricity across layer groups: [PRL 130, 146801 (2023)](https://doi.org/10.1103/PhysRevLett.130.146801).
- Fractional quantum ferroelectricity and candidate point groups: [Nature Communications 15, 135 (2024)](https://www.nature.com/articles/s41467-023-44453-y).
- Enhanced bilayer framework with rotational-operation selection: [PRB 111, 224102 (2025)](https://doi.org/10.1103/PhysRevB.111.224102).
- Multilayer stacking-ferroelectricity theory and C₃N/BPVE application: [PRB 113, 075310 (2026)](https://journals.aps.org/prb/abstract/10.1103/9tt5-qm26).
- C2DB-based high-throughput 2D ferroelectric screening: [npj Computational Materials (2023)](https://www.nature.com/articles/s41524-023-00999-5).
- High-throughput natural-bilayer stacking and emergent-property analysis: [Nature Communications (2024)](https://www.nature.com/articles/s41467-024-45003-w).

Substantial published baselines exist for theoretical group relations, bilayer generation, ordinary POSCAR/CIF conversion, symmetry identification, and high-throughput screening. None should be treated as a strong standalone patent concept without separately verified technical differences and effects.

## Public planning boundary

Detailed invention candidates, claim-feature combinations, objective functions, thresholds, materials, anomalous paths, and benchmark effects are intentionally absent from this public repository. They must be recorded in a private invention log, checked against literature and patent claims, and cleared for ownership/public disclosure before a public issue, roadmap item, implementation, or result is posted.

The private review should search CNIPA and PATENTSCOPE by keyword and relevant G16C/G06F classifications, then inspect claims, families, legal status, applicants, and inventors—not titles alone.

Official search entry points: [CNIPA patent search information](https://www.cnipa.gov.cn/art/2023/2/13/art_3166_182074.html), [WIPO PATENTSCOPE](https://patentscope.wipo.int/), and [WIPO IPC G16C](https://www.wipo.int/classifications/ipc/en/ITsupport/Version20230101/transformations/ipc/20230101/en/htm/G16C.htm).
