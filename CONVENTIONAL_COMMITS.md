# Conventional Commits Guide

This project follows the [Conventional Commits](https://www.conventionalcommits.org/) specification for clear and structured commit messages.

## Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

## Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that don't affect code meaning (formatting, semicolons, etc.)
- **refactor**: Code change that neither fixes a bug nor adds a feature
- **perf**: Code change that improves performance
- **test**: Adding or updating tests
- **chore**: Changes to build process, dependencies, or tooling
- **ci**: Changes to CI configuration files and scripts
- **revert**: Revert a previous commit

## Examples

### Simple bug fix
```
fix: Resolve authentication timeout on login page
```

### New feature with scope
```
feat(api): Add user profile endpoint
```

### Breaking change
```
feat!: Remove deprecated legacy API

BREAKING CHANGE: Legacy API endpoints have been removed in favor of the v2 API.
```

### With issue reference
```
fix(login): Correct password validation logic (#123)

Resolves the issue where special characters were not accepted in passwords.
```

### Complete example
```
feat(auth): Implement OAuth2 authentication

- Add OAuth2 provider configuration
- Support multiple auth providers
- Update user model to store provider ID

Closes #456
```

## Benefits

✅ **Automatic versioning** — Tools can auto-increment versions based on commit types  
✅ **Semantic changelog** — Automated changelog generation  
✅ **Clear history** — Easy to understand what changed and why  
✅ **Linked issues** — Track which commits close which issues  

## Tips

- Keep the subject line under 50 characters
- Use imperative mood ("add" not "added" or "adds")
- Reference issues: `Closes #123` or `Fixes #456`
- Mark breaking changes: `BREAKING CHANGE:` in footer
