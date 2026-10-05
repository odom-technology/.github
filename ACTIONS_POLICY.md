# GitHub Actions run policy

This policy applies to every `odom-technology` repository. It is intended to keep
development pushes and background events from consuming Actions minutes or deploying
unfinished work.

## Trigger rule

Every workflow that starts a runner must have **only** a push trigger filtered to
`main`:

```yaml
on:
  push:
    branches: [main]
```

Additional path filters may make this narrower. Do not add `dev`, wildcard branches,
pull requests, schedules, manual dispatch, tags, releases, `workflow_run`, or other
events without the repository owner's explicit approval for that exact workflow.
Reusable `workflow_call` workflows may exist only when every caller follows the same
`main`-push rule; they must not create an alternate run path.

## Deployment rule

- Deploy only the commit pushed to `main`. Do not check out `dev` or another mutable ref
  inside a workflow triggered by `main`.
- Use the minimum `GITHUB_TOKEN` permissions and only the deployment secrets needed by
  that workflow. A template never contains credentials.
- Use a concurrency group where duplicate deployments could overlap. Choose
  `cancel-in-progress` based on the deployment's rollback behavior.
- Review both the workflow's `on` block and any external hosting integration when a
  repository starts or changes deployment automation. External hosting may deploy from
  GitHub without a GitHub Actions workflow.

## Review before publishing

1. Inspect every file under `.github/workflows/` on both `dev` and `main`.
2. Confirm that each runnable workflow has only `push.branches: [main]` and that no
   deployment job can be reached from another event or branch.
3. Check recent Actions runs for event and branch to find generated or legacy jobs.
4. Merge the reviewed workflow change to `main`, then sync `dev` with `main` without
   replacing unrelated development work.

This repository contains guidance, not a central branch-filter enforcement mechanism.
Repository workflow triggers must carry the `main` filter. Organization-level Actions
event restrictions, when available, can provide an additional event guard but cannot
replace each workflow's branch filter.

GitHub-managed Dependabot and Pages workflows may also appear in Actions history outside
`.github/workflows/`. [GitHub's billing documentation](https://docs.github.com/en/billing/concepts/product-billing/github-actions)
excludes standard GitHub-hosted Dependabot and Pages runs from included Actions-minute
usage; keep Dependabot security updates enabled. External GitHub Apps such as hosting
providers can create checks on `dev` without running a GitHub Actions workflow, so
review their branch settings separately when deployment previews need restriction.
