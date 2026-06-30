# Teams Configuration

This folder contains the source of truth for organization team management.

## File

- `teams.json` — Teams-as-code configuration consumed by `.github/workflows/sync-teams.yml`.

## Team Schema

Each team item supports:

- `client` (string): Display name used in the README table.
- `name` (string, required): GitHub team name.
- `alias` (string): Alternate customer/team names.
- `tool` (string): Allowed values: `PBI` or `Qlik Sense`.
- `description` (string): Team description.
- `privacy` (string): `closed` or `secret`.
- `members` (array): GitHub usernames to add to the team.
- `repositories` (array): Repository names. Missing repos are created and assigned to the team with `admin` permission.

## Example

```json
{
  "teams": [
    {
      "client": "TALMA",
      "name": "TALMA",
      "alias": "Associacio Talma",
      "tool": "PBI",
      "description": "Talma apps en Power BI",
      "privacy": "closed",
      "members": ["user1", "user2"],
      "repositories": ["talma-bi-demo-ventas"]
    }
  ]
}
```
