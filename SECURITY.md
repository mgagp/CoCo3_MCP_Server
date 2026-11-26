# Security policy

## Supported branch

Security fixes are developed against `lab`. Generic fixes may also be proposed
to the upstream repository after validation.

## Reporting

Do not open a public issue containing credentials, exploit details, personal
data, or a working secret.

Use GitHub's private vulnerability reporting for the repository when it is
available. Otherwise contact the repository owner through GitHub privately and
include:

- affected version or commit;
- reproduction steps;
- impact;
- proposed mitigation, if known.

## Repository safeguards

- Secret scanning and push protection must remain enabled.
- Dependabot vulnerability alerts and security updates must remain enabled.
- GitHub Actions use least-privilege token permissions.
- ROMs, writable disk images, `.env`, snapshots, logs, and credentials are not
  committed.

## Dependency response

Security-only updates should be evaluated in small pull requests. If a major
dependency upgrade is necessary, compatibility, tests, and build output must be
verified before merging.
