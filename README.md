# Ascend Trader Updates

Public distribution repository for Ascend Trader beta application updates.

This repository is intentionally limited to update metadata and release artifacts. It does not contain Ascend Trader source code, broker credentials, databases, logs, or beta-tester data.

## Update model

Ascend Trader checks a stable `update-manifest.json` published from the `main` branch. The manifest identifies the applicable beta release, approved cohort(s), installer URL, installer size, and SHA-256 hash.

Installers are published as versioned GitHub Release assets. Ascend Trader downloads only the installer referenced by the manifest, verifies its size and SHA-256 locally, and requires explicit user approval before installation handoff.

## Current beta validation

The first end-to-end updater validation release is planned as `0.1.1-beta` for the `BETA_A` cohort. This release is intended to validate distribution and update behavior only; it is not intended to introduce trading-strategy changes.

## Security boundary

The update repository must never contain:

- Alpaca API keys or secrets
- user databases or trading logs
- diagnostic bundles or exported user data
- application source code
- arbitrary executable payloads outside the governed release process

The manifest and release assets are part of Ascend Trader's distribution trust boundary and should only be changed as part of an approved release workflow.
