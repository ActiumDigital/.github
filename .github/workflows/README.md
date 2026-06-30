# Team Sync Workflow

This folder contains workflows under `.github/workflows`.

## Files

- `sync-teams.yml` — Synchronizes teams from `teams/teams.json`.

## What `sync-teams.yml` Does

1. Creates or updates GitHub teams.
2. Adds configured team members.
3. Creates configured repositories when missing.
4. Grants team `admin` permission to configured repositories.
5. Updates `ActiumDigital/.github-private/profile/README.md` between:
   - `<!-- TEAM_REGISTRY_START -->`
   - `<!-- TEAM_REGISTRY_END -->`

## Required Secret

- `ORG_ADMIN_TOKEN` with organization admin permissions.
