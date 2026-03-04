# expectedbehaviors Helm Charts

Public umbrella repository for expectedbehaviors Helm charts, managed as Git submodules.

## Goals

- Keep each chart independently versioned in its own repository.
- Provide one high-level catalog for discovery and contribution.
- Automate submodule refreshes so this index tracks upstream chart repos.
- Enforce release-grade controls (branch protection workflow included).

## Repository layout

- `charts/<name>`: chart repository submodules.
- `.github/workflows/submodule-sync.yml`: opens PRs when submodules advance.
- `.github/workflows/enforce-branch-protection.yml`: applies protection policy to `main` on release/dispatch.

## Chart catalog

| Chart | Repository |
|---|---|
| radarr | https://github.com/expectedbehaviors/radarr |
| sonarr | https://github.com/expectedbehaviors/sonarr |
| lidarr | https://github.com/expectedbehaviors/lidarr |
| readarr | https://github.com/expectedbehaviors/readarr |
| prowlarr | https://github.com/expectedbehaviors/prowlarr |
| gotify | https://github.com/expectedbehaviors/gotify |
| mealie | https://github.com/expectedbehaviors/mealie |
| reloader | https://github.com/expectedbehaviors/reloader |
| oauth2-proxy | https://github.com/expectedbehaviors/oauth2-proxy |
| plex-autoskip | https://github.com/expectedbehaviors/plex-autoskip-helm-chart |

## Updating submodules manually

```bash
git submodule update --init --recursive
git submodule update --remote --merge
```

## Branch protection policy

- `main` requires at least one approving review for non-owner contributors.
- `jd4883` is allowed to bypass the review requirement.
- Policy is enforced by workflow and can be re-applied via manual dispatch.
