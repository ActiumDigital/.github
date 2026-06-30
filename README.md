# ActiumDigital Organization Configuration

Central repository for organization-wide GitHub configuration, templates, and workflows for ActiumDigital projects.

## 📋 What's Included

### Issue Templates
Standardized issue templates applied to all ActiumDigital repositories:
- **Bug Report** — Structured bug reporting with environment and reproduction steps
- **Feature Request** — Feature proposals with use cases and acceptance criteria
- **Documentation** — Documentation improvements and updates

See [`ISSUE_TEMPLATE/`](./ISSUE_TEMPLATE/) for details.

### Automated Workflows

#### 🚀 Release Workflow (`release.yml`)
Automatically creates semantic versioned releases based on conventional commits.

**How it works:**
1. Push commits to `main` or `master` branch
2. Workflow analyzes commit messages using Conventional Commits format
3. Automatically determines version bump (Major.Minor.Patch)
4. Creates Git tag and GitHub release
5. Comments on related issues

**Version Bumping Logic:**
- `BREAKING CHANGE:` in commit → **MAJOR** version bump (1.0.0 → 2.0.0)
- `feat:` prefix → **MINOR** version bump (1.0.0 → 1.1.0)  
- `fix:` prefix → **PATCH** version bump (1.0.0 → 1.0.1)

**Skip Release (if needed):**
Add `[skip-release]` to commit message to prevent auto-release.

#### 📝 Changelog Workflow (`changelog.yml`)
Automatically updates `CHANGELOG.md` when a release is created.

**Features:**
- Generates changelog entries from commit messages
- Links commits with hashes
- Maintains release history
- Updates automatically on every release

#### 👥 Team Sync Workflow (`sync-teams.yml`)
Manages organization teams from code and keeps this README updated.

**Source of truth:**
- `teams/teams.json`

**How it works:**
1. Add or update a team entry in `teams/teams.json`
2. Push to `main`
3. Workflow creates/updates the GitHub team
4. Users in `members` are added to the team
5. Repositories in `repositories` are assigned with **admin** permission for that team
6. This README Team Registry section is auto-updated

**Config properties per team:**
- `name`: team name (required)
- `description`: team description (optional)
- `privacy`: `closed` or `secret` (optional, defaults to `closed`)
- `members`: GitHub usernames to add to the team (optional)
- `repositories`: repository names in ActiumDigital org to grant admin permission (optional)

**Required secret:**
- `ORG_ADMIN_TOKEN`: Personal Access Token with org admin rights (used by workflow to manage teams and repo permissions)

**Example (`teams/teams.json`):**
```json
{
  "teams": [
    {
      "name": "Data Platform",
      "description": "Owns data services and pipelines",
      "privacy": "closed",
      "members": ["alice", "bob"],
      "repositories": ["data-api", "etl-jobs"]
    }
  ]
}
```

---

## 👥 Team Registry (Auto-generated)
This section is maintained automatically from `teams/teams.json`.

<!-- TEAM_REGISTRY_START -->
_No teams registered yet._
<!-- TEAM_REGISTRY_END -->

---

## 📖 Using Conventional Commits

All projects should follow [Conventional Commits](https://www.conventionalcommits.org/) format for consistent versioning and changelog generation.

### Commit Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types

| Type | Purpose | Version Impact |
|------|---------|-----------------|
| `feat` | New feature | Minor bump ↑ |
| `fix` | Bug fix | Patch bump ↑ |
| `docs` | Documentation changes | No version bump |
| `style` | Code formatting | No version bump |
| `refactor` | Code refactoring | No version bump |
| `perf` | Performance improvements | Patch bump ↑ |
| `test` | Test additions/changes | No version bump |
| `chore` | Build/dependency updates | No version bump |
| `ci` | CI/CD changes | No version bump |
| `revert` | Revert previous commit | Depends on reverted commit |

### Examples

**Bug Fix:**
```
fix: Resolve authentication timeout on login page
```

**New Feature:**
```
feat(api): Add user profile endpoint
```

**Breaking Change:**
```
feat!: Remove deprecated legacy API

BREAKING CHANGE: Legacy endpoints removed in favor of v2 API.
```

**With Issue Reference:**
```
fix(login): Correct password validation logic

- Allow special characters in passwords
- Add unit tests for edge cases

Closes #123
```

**Detailed Example:**
```
feat(auth): Implement OAuth2 authentication

Add OAuth2 support with multiple provider configuration:
- Google OAuth2 integration
- GitHub OAuth2 integration  
- User model updated to store provider ID

Closes #456, Relates to #789
```

### Tips
✅ Use imperative mood ("add", not "added" or "adds")  
✅ Keep subject under 50 characters  
✅ Reference issues with "Closes #123" or "Fixes #456"  
✅ Mark breaking changes with `BREAKING CHANGE:` in footer  
✅ Prefix scope in parentheses for clarity

---

## 🏗️ Setup in Your Projects

### 1. Copy CHANGELOG Template
Each repository should have its own `CHANGELOG.md`:

```bash
curl https://raw.githubusercontent.com/ActiumDigital/.github/main/CHANGELOG_TEMPLATE.md > CHANGELOG.md
```

Or manually copy [`CHANGELOG_TEMPLATE.md`](./CHANGELOG_TEMPLATE.md).

### 2. Enable Workflows
The workflows are automatically applied to all repositories via this `.github` repository. Nothing extra needed!

### 3. Start Using Conventional Commits
All team members should follow the [Conventional Commits guide](./CONVENTIONAL_COMMITS.md) when creating commits and pull requests.

---

## 📊 Workflow Examples

### Example Release Cycle

**Step 1: Create PR with feature**
```bash
git checkout -b feat/user-dashboard
# ... make changes ...
git commit -m "feat(ui): Add user dashboard component"
git push origin feat/user-dashboard
# Create PR
```

**Step 2: Merge to main**
```
PR merged to main
```

**Step 3: Automatic Release** ✨
```
release.yml triggers automatically
→ Detects "feat:" prefix
→ Bumps version 1.0.0 → 1.1.0
→ Creates tag v1.1.0
→ Creates GitHub Release
→ Comments on related issues
```

**Step 4: Changelog Updated** 📝
```
changelog.yml triggers on tag
→ Updates CHANGELOG.md
→ Commits changelog update
→ Release notes are complete
```

### Example Bug Fix

```bash
git checkout -b fix/auth-timeout
# Fix the bug
git commit -m "fix: Resolve authentication timeout

The auth token was not being refreshed properly on long sessions.
Added automatic token refresh mechanism.

Fixes #789"

git push && create PR
# PR approved and merged to main
# → release.yml auto-creates v1.0.1 release
# → changelog.yml updates CHANGELOG.md
```

---

## 🚫 Avoiding Unintended Releases

**Skip a release** by adding `[skip-release]` to commit message:
```bash
git commit -m "chore: Update dependencies [skip-release]"
```

---

## 📚 Documentation References

- [**Conventional Commits Guide**](./CONVENTIONAL_COMMITS.md) — Detailed commit message guide
- [**Changelog Template**](./CHANGELOG_TEMPLATE.md) — CHANGELOG.md format
- [**Issue Templates**](./ISSUE_TEMPLATE/) — Structured issue reporting

---

## 🔗 Useful Links

- [Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)
- [GitHub Actions](https://github.com/features/actions)

---

## ✅ Quick Checklist for Teams

- [ ] Copy `CHANGELOG_TEMPLATE.md` as `CHANGELOG.md` in each repo
- [ ] Review [Conventional Commits Guide](./CONVENTIONAL_COMMITS.md)
- [ ] Train team on commit message format
- [ ] Enable branch protection to require conventional commits in PRs (optional)
- [ ] Set up status checks if desired
- [ ] Start using the workflows!

---

**Last Updated:** 2026-06-30  
**Maintainer:** ActiumDigital
