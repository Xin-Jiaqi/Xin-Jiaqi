# Portfolio maintenance policy

1. Work in a focused branch and describe the scientific invariant being protected.
2. Add a regression fixture before changing P0/P1 scientific logic.
3. Keep foundation APIs independent of VASP, Slurm, databases, and application working directories.
4. Record input checksums, dependency versions, parameters, success/failure counts, and output schema versions.
5. Require an independent reviewer for scientific changes.
6. Do not select a code/data/asset license without confirmed ownership.
7. Apply the IP/public-disclosure gate before publishing novel algorithms or results.
