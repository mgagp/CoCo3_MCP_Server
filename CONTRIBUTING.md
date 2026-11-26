# Contributing

This repository is a laboratory fork of
[`dbowlin/CoCo3_MCP_Server`](https://github.com/dbowlin/CoCo3_MCP_Server).

## Branch model

- `main` tracks the upstream `main` branch as closely as possible.
- `lab` is the integration branch for this fork.
- All work starts on a short-lived branch and lands through a pull request.
- Lab-specific work branches from `lab`.
- Candidate upstream changes branch from `upstream/main`, not from `lab`.

## Local setup

```bash
git clone https://github.com/mgagp/CoCo3_MCP_Server.git
cd CoCo3_MCP_Server
git remote add upstream https://github.com/dbowlin/CoCo3_MCP_Server.git
git fetch upstream
```

## Syncing upstream

Keep the mirror branch simple:

```bash
git switch main
git fetch upstream
git merge --ff-only upstream/main
git push origin main
```

Then integrate upstream into the laboratory branch:

```bash
git switch lab
git merge origin/main
git push origin lab
```

Do not use force-push on `main` or `lab`.

## Preparing an upstream contribution

1. Confirm the issue and expected behavior are useful to the upstream project.
2. Create a focused branch from `upstream/main`.
3. Keep project-specific paths, fixtures, or agent policy out of the patch.
4. Run the same validation as CI.
5. Open a pull request to this fork for review if useful, then propose the same
   branch directly to `dbowlin/CoCo3_MCP_Server`.

## Pull request standard

- Link an issue.
- Keep one purpose per pull request.
- Include a concise validation section.
- Add or update focused tests when behavior changes.
- Document user-visible configuration changes.
- Do not commit ROMs, generated DSK files, `.env`, logs, snapshots, personal
  credentials, or host-specific state.

## Validation

From `MCP/`:

```bash
npm ci
npm test
npm run build
```

Real MAME end-to-end tests are introduced progressively and must remain
isolated from a user's open emulator session and canonical disk images.
