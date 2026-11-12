# GitLab CLI !4395 — Numeric project IDs in repository overrides

**Status as of 2026-11-12:** Open · Draft · CI follow-up required

## Upstream links

- **Issue:** [gitlab-org/cli#8186](https://gitlab.com/gitlab-org/cli/-/work_items/8186)
- **Merge request:** [gitlab-org/cli!4395](https://gitlab.com/gitlab-org/cli/-/merge_requests/4395)
- **Source branch:** `THAIF74/cli:thaif/8186-numeric-project-id`
- **Target branch:** `gitlab-org/cli:main`
- **Submitted head commit:** `6ca0b847db6cab7b600b1010094884a3bfa8a835`

## Problem

Repository overrides in GitLab CLI accepted repository paths and URLs, but did not accept a numeric GitLab project ID.

## Work submitted

- Added parsing for positive decimal project IDs, rejecting zero, signed or non-numeric values, and integer overflow.
- Added API-based project lookup using the authenticated GitLab client.
- Converted the project's HTTP clone URL into the existing repository representation.
- Preserved the existing repository path and URL handling.
- Updated repository-override help text and generated command documentation.
- Added parser, resolver, and factory integration test coverage.

## CI and review status

The latest pipeline associated with the MR head at the time this record was checked was [pipeline #3055854893](https://gitlab.com/THAIF74/cli/-/pipelines/3055854893), and it **failed**.

- Integration tests and several documentation checks passed.
- Unit tests failed in four new project-ID resolver test cases because the API mock expectations were not being met.
- Go lint reported two `gci` import-formatting issues.
- The commit-lint job could not resolve the target-base revision in the runner's shallow checkout.

These failures still need follow-up. This contribution is not merged or approved; the merge request remains a draft for review.

## Scope of this archive

This folder documents the contribution and links to the upstream work. The actual implementation and review history remain in the [GitLab merge request](https://gitlab.com/gitlab-org/cli/-/merge_requests/4395). This archive does not copy or replace GitLab CLI source code.
