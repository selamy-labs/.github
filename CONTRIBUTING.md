# Contributing

Org-wide defaults for Selamy Labs repositories. A repo may override any of these
with its own `CONTRIBUTING.md` when it has stricter or more specific rules.

## Workflow

- **Branch and PR, never push to the default branch.** The default branch is
  protected; all changes land through a pull request with required checks green.
- **One unit of work per PR.** Keep diffs focused and reviewable.
- **Conventional Commit PR titles.** Titles must match `type: description`
  (`feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `test:`). Releases are cut
  from these, so the type is not optional.

## Quality bar

- **Tests with the change.** New behavior ships with tests; fixes ship with a
  regression test. Public repositories hold a ≥90% coverage floor, enforced in CI.
- **Meaningful tests, not padding.** A test must be able to fail for a real reason.
- **CI must be green.** Lint, tests, and any privacy/security gates pass before merge.
- **No false claims.** Every statement in a README or doc must be demonstrably
  true — run the example before you assert it works.

## Privacy and security

- **Public repositories are privacy-clean.** No secrets, internal hostnames, or
  internal-only names. Where a privacy/secret scanner exists, it gates the merge.
- Report vulnerabilities privately — see [`SECURITY.md`](./SECURITY.md). Do not
  open a public issue for a security problem.

## Style

- Match the surrounding code: its naming, structure, and idiom.
- Prefer the smallest change that fully solves the problem.
- Name things for the practice or behavior, not for a person, brand, model, or tool.
