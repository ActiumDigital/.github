# Release Workflows

This folder documents release automation workflows.

## Files

- `release.yml` — Semantic versioning release automation.
- `changelog.yml` — Changelog generation/update on tags.

## Version Bump Rules

- `BREAKING CHANGE:` -> MAJOR
- `feat:` -> MINOR
- `fix:` -> PATCH

Add `[skip-release]` to skip release automation for a commit.
