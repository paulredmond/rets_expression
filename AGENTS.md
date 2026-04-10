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

## Git remotes and pull requests

This repo has two remotes:

- `origin` → `paulredmond/rets_expression` (fork)
- `upstream` → `zenlist/rets_expression` (upstream)

**All branches MUST be pushed to `origin`.** When creating pull requests with `gh pr create`, always pass `--repo paulredmond/rets_expression` to ensure the PR is created on the fork. NEVER push to or create PRs against `upstream` unless explicitly instructed.
