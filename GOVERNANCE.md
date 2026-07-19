# Repository governance

## Change flow

1. Work in a focused branch and state the scientific or user-facing invariant being protected.
2. Add a reproducible fixture before changing scientific, security, rights, or data-loss behavior.
3. Keep foundation APIs independent of application working directories, schedulers, and unpublished datasets.
4. Record input hashes, parameters, dependency versions, output schema, success/failure counts, and compatibility impact.
5. Require CI and an independent reviewer for scientific changes; do not rely only on the implementer's summary.

## Release gate

- no credentials, private paths, restricted data, manuscript candidates, or unlicensed assets;
- code, data, documentation, and images have explicit ownership and redistribution status;
- supported runtimes, clean package installation, data validators, and failure paths pass;
- machine-readable inputs and outputs are versioned, with deprecation rules where compatibility is promised;
- novel methods or effect data pass ownership and public-disclosure review before a public issue, commit, talk, or release.

## Portfolio boundaries

A new repository needs an independent user scenario, testable input/output boundary, maintenance reason, and release cadence. Shared code is extracted only after two real consumers exist. Foundation repositories do not import application code; personal and web projects remain outside the materials dependency graph.

No standard open-source license has been selected for this profile repository. Public visibility does not grant reuse rights, and each linked project controls its own license.
