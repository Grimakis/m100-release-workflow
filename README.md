# m100-release-workflow

Reusable GitHub Actions workflow that builds Model 100 artifacts via `@m100/cli`, uploads them, and attaches them to a GitHub Release.

## Usage
```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  release:
    uses: Grimakis/m100-release-workflow/.github/workflows/release.yml@v1
    with:
      source: src/EQUITY.DO
      ascii-name: EQUITY.DO
      tokenized-name: EQUITY.BA
```

## Inputs
- `source` (required): Source `.DO` file to build.
- `version-var` (optional): BASIC variable name for version. Default: `VE$`. Set empty to skip.
- `version-regex` (optional): Semver regex. Default: `X.Y.Z` pattern.
- `out-dir` (optional): Output directory. Default: `dist`.
- `artifact-name` (optional): Artifact name. Default: `model100-game-build`.
- `cli-package` (optional): NPM package to install. Default: `@m100/cli`.
