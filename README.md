# GitLab Open Source Contributions

This repository contains my working records and supporting files for contributions submitted to GitLab projects.

It is separate from my [GitLab Contribution Guide](https://github.com/THAIF74/GitLab-Contribution-Guide), which is used only as a progress tracker.

## Contributions

| Project | Work | Upstream status |
|---|---|---|
| [GitLab Danger Review !26](https://gitlab.com/gitlab-org/components/danger-review/-/merge_requests/26) | Restore Git fetch low-speed timeout | Merged |
| [GitLab CLI !4263](https://gitlab.com/gitlab-org/cli/-/merge_requests/4263) | Fetch all issue notes when viewing comments | Open; pipeline passed at last check |
| [GitLab CLI !4268](https://gitlab.com/gitlab-org/cli/-/merge_requests/4268) | Clarify deploy-token help text | Open; documentation CI check needs follow-up |
| [GitLab CLI !4269](https://gitlab.com/gitlab-org/cli/-/merge_requests/4269) | Avoid caching Go build files in lint job | Open; pipeline passed at last check |
| [GitLab CLI !4343](https://gitlab.com/gitlab-org/cli/-/merge_requests/4343) | Avoid unsupported telemetry properties on older GitLab instances | Open; CI status needs a fresh check |
| [GitLab CLI !4395](https://gitlab.com/gitlab-org/cli/-/merge_requests/4395) | Support numeric project IDs in repository overrides | Open draft; CI follow-up required |

## Repository layout

- `contributions/` — one folder per upstream merge request, with contribution notes and supporting artifacts added as they are verified.
- `reports/` — dated progress snapshots.
- `docs/` — repository notes and contribution workflow.

## Important notes

- The GitLab merge requests above are the actual upstream contributions. This repository is a personal archive and does not replace or modify those upstream projects.
- A passing pipeline is not the same as approval or merge.
- Only mark work as merged when the upstream GitLab project confirms it.
- GitLab reward-store credits are separate from merge-request status and are not tracked or claimed here.
