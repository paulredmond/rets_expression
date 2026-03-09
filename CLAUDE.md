# Conventions for Claude Code

## Commit messages

All commits MUST use [Conventional Commits](https://www.conventionalcommits.org) format:

```
<type>: <description>
```

| Type | Use for | Version bump |
|------|---------|--------------|
| `feat` | New functionality | Minor |
| `fix` | Bug fixes | Patch |
| `chore` | Maintenance, deps, config | None |
| `docs` | Documentation only | None |
| `refactor` | Code change, no behaviour change | None |
| `test` | Adding or updating tests | None |

For breaking changes, add `BREAKING CHANGE:` in the commit body.

Never use a generic message like "update files" or "fix bug". Always use the conventional format.
