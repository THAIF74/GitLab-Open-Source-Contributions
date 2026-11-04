# GitLab CLI !4269 — avoid caching Go build files in lint job

- Upstream MR: https://gitlab.com/gitlab-org/cli/-/merge_requests/4269
- Project: `gitlab-org/cli`
- Status: **Open** at the last check.
- Latest recorded commit: `6b1040cb2c3fa28d6917acd4f406561f48b30d2`
- Pipeline: passed.

This CI change avoids persisting the Go build cache in the lint job, reducing the cost of restoring and saving a very large cache archive.

The MR still requires upstream review and approval. The exact patch will be archived after verifying the current source diff.
