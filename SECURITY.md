# Security Policy

## Reporting a vulnerability

**Do not open a public issue for a security vulnerability.**

Report it privately through GitHub's private vulnerability reporting:

1. Go to the **Security** tab of the affected repository.
2. Click **Report a vulnerability** (Private vulnerability reporting).
3. Describe the issue, the impact, and steps to reproduce.

This opens a private advisory visible only to the maintainers. We will
acknowledge the report, work a fix under embargo, and credit you on disclosure
unless you prefer to remain anonymous.

If private reporting is not enabled on a given repository, open a minimal issue
asking a maintainer to enable it — without including any vulnerability details.

## Scope

- Report anything that could compromise confidentiality, integrity, or
  availability: credential exposure, injection, privilege escalation, or
  data leakage.
- For dependency advisories, a Dependabot alert is usually sufficient; a direct
  report is only needed when you have a concrete, exploitable finding.

## Automated secret-leak prevention

Selamy Labs repos run a **PR-diff secret-scan CI gate**
([`.github/workflows/secret-scan.yml`](./.github/workflows/secret-scan.yml),
backed by [`.gitleaks.toml`](./.gitleaks.toml)). It fails CI when a pull
request introduces a plaintext credential (API keys, tokens, service-account
private keys, DB URLs with embedded passwords, etc.). It scans only the PR's
changed commit range, so pre-existing history does not block new work.

If the gate flags a real secret: rotate it immediately, remove it from the
diff, and route the value through a secret store (GSM + ExternalSecrets, repo
secrets, or `pass`) — never commit the literal. False positives are tuned in
the shared `.gitleaks.toml` allowlist.

## What to expect

- Acknowledgement that the report was received.
- An assessment and, if valid, a fix tracked in a private advisory.
- Coordinated disclosure once a fix is available.
