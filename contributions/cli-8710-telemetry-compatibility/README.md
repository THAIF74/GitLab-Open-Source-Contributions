# GitLab CLI issue #8710 — telemetry compatibility

**Upstream issue:** [#8710 — telemetry properties rejected by GitLab instances older than 19.4](https://gitlab.com/gitlab-org/cli/-/work_items/8710)  
**Upstream merge request:** [!4343 — avoid unsupported telemetry properties on older GitLab instances](https://gitlab.com/gitlab-org/cli/-/merge_requests/4343)  
**Source fork:** [THAIF74/cli](https://gitlab.com/THAIF74/cli)  
**Branch:** `fix/telemetry-properties-older-gitlab-8710`  
**Latest source commit:** [`88824c9d`](https://gitlab.com/THAIF74/cli/-/commit/88824c9da2d5ae076ae4f58c5b994b85471f78b2)  
**CI pipeline:** [#3042456467](https://gitlab.com/THAIF74/cli/-/pipelines/3042456467)

## Problem

GitLab CLI versions that send `additional_properties` to `POST /api/v4/usage_data/track_event` can cause older self-managed GitLab instances to log `InvalidPropertyError` for each CLI command. The issue reports that these properties are supported starting with GitLab 19.4.

## Change submitted upstream

The branch checks the instance version through the metadata API before including the optional `additional_properties` payload.

- GitLab 19.4 and newer receive the existing CLI attribution properties.
- Older, unknown, or unparsable versions omit `additional_properties` while the base telemetry event is still attempted.
- Tests cover the 19.4 compatibility boundary and an 18.11 metadata response.

## Files in this archive

- `telemetry.go` — complete version of `cmd/glab/telemetry.go` from the contribution branch.
- `telemetry_test.go` — complete version of `cmd/glab/telemetry_test.go` from the contribution branch.
- `changes.patch` — patch against the fork's `main` branch.

The two Go files are complete upstream source files, not standalone programs. The authoritative implementation is the GitLab branch and merge request linked above; this GitHub folder is a personal backup and review copy.

## Validation status

An initial CI run caught one test-helper lint issue (missing `t.Helper()` in a wrapper). That issue has been fixed in the latest source commit. A fresh GitLab pipeline (#3042462403) is running. The previous run had passed `lint:comments`, `docs hugo_build`, `check_docs_markdown`, `check_docs_update`, `check_args`, `check_embed`, `lint_commit`, and `check_go_generated_code`. Unit tests, integration tests, coverage, and the fresh lint run are still pending. The optional `govulncheck` job is manual.

No local test run is claimed. The upstream MR remains open and awaits CI/review; it is not merged.

## Scope note

This repository records the contribution but does not itself count as an upstream GitLab contribution. Do not mark the work merged until GitLab confirms that outcome.
