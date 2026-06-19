# .github

Org-wide community-health defaults for [Selamy Labs](https://github.com/selamy-labs).
GitHub applies these to any repository in the org that does not provide its own:

- [`CONTRIBUTING.md`](./CONTRIBUTING.md) — how to contribute (PR-only, Conventional
  Commit titles, tests + coverage, privacy-clean).
- [`SECURITY.md`](./SECURITY.md) — how to report a vulnerability privately.
- [`.github/PULL_REQUEST_TEMPLATE.md`](./.github/PULL_REQUEST_TEMPLATE.md) — the PR checklist.
- [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE) — bug report + feature request forms.

A repository overrides any default by adding its own copy of the file.

## Reusable workflows

This repo also hosts org-wide **reusable GitHub Actions workflows**. Define CI
once here, call it from each repo with a tiny caller workflow.

- [`.github/workflows/python-ci.yml`](./.github/workflows/python-ci.yml) —
  lint + test + coverage for Python repos.
- [`.github/workflows/secret-scan.yml`](./.github/workflows/secret-scan.yml) —
  PR-diff secret scanning (gitleaks CLI). Fails CI when a new commit introduces
  a plaintext credential; already-committed secrets do not block new PRs.

The shared gitleaks ruleset lives at [`.gitleaks.toml`](./.gitleaks.toml).

### Adopt the secret-scan gate

Add `.github/workflows/secret-scan.yml` to any repo:

```yaml
name: Secret Scan
on:
  pull_request:
  push:
    branches: [main]
permissions:
  contents: read
jobs:
  secret-scan:
    uses: selamy-labs/.github/.github/workflows/secret-scan.yml@main
```

The resulting check is `secret-scan / Scan`. Ask an admin to mark it a required
branch-protection check once it is green.
