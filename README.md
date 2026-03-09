An implementation of [RCP 19][rcp19] (RETS Validation Expressions) from the [RESO
Transport group][transport].

[transport]: https://github.com/RESOStandards/transport
[rcp19]: https://github.com/RESOStandards/transport/blob/main/web-api-validation-expression.md

See [the docs](https://docs.rs/rets_expression) for usage.

This repo tests against the compliance tests at [https://github.com/zenlist/reso-rcp19-compliance-tests](https://github.com/zenlist/reso-rcp19-compliance-tests)

## Installation

Add to your project's `Cargo.toml` using a specific release tag (recommended):

```toml
[dependencies]
rets_expression = { git = "https://github.com/paulredmond/rets_expression", tag = "v1.0.0" }
```

Or track the latest `main` branch:

```toml
[dependencies]
rets_expression = { git = "https://github.com/paulredmond/rets_expression", branch = "main" }
```

Then run `cargo build` to fetch and compile the dependency.

## Running tests

Initialize the compliance test submodule, then run the full test suite:

```sh
git submodule update --init --recursive
cargo test
```

## Releases

Releases are automated via [release-please](https://github.com/googleapis/release-please) using conventional commits.

### Commit message format

Every commit to `main` must use the [Conventional Commits](https://www.conventionalcommits.org) format:

```
<type>: <description>

# Examples
feat: add support for negative number literals
fix: handle NULL in arithmetic expressions
chore: update winnow to 0.6.20
docs: add release workflow documentation
```

| Type | When to use | Version bump |
|------|-------------|--------------|
| `feat` | New functionality | Minor (`0.x.0`) |
| `fix` | Bug fix | Patch (`0.0.x`) |
| `chore` | Maintenance, dependency updates | None |
| `docs` | Documentation only | None |
| `refactor` | Code change with no behaviour change | None |
| `test` | Adding or updating tests | None |

To trigger a **major** version bump (`x.0.0`), add `BREAKING CHANGE:` in the commit body:

```
feat: remove deprecated bracket field syntax

BREAKING CHANGE: [FieldName] bracket syntax is no longer supported.
Use bare FieldName instead.
```

### How it works

1. Merge commits to `main` using the format above
2. release-please automatically opens a **Release PR** that bumps the version in `Cargo.toml` and updates `CHANGELOG.md`
3. Review and merge the Release PR when ready to ship
4. Merging the Release PR pushes a version tag (e.g. `v0.3.0`), which triggers the release workflow to create a GitHub Release
