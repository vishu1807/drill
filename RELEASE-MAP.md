# Release Map

The canonical release tags below are annotated and point to the commits listed. Dates are the commits' recorded dates; “What Shipped” describes the contents of those commits. The repository contains no authoritative production deployment record, so this map does not claim that any version is currently running in production. Confirm the deployed version with operations before using it as the live rollback point.

| Version (tag) | Commit (short hash) | Date | What Shipped |
| --- | --- | --- | --- |
| `v1.0.0` | `ff1fb9a` | 2026-06-06 | Initial exercise repository and placeholder checkout service, with the baseline documentation. Reconstructed baseline release record; actual production deployment is unverified. |
| `v1.0.1` | `86989b6` | 2026-06-06 | Corrected the legacy `release_2` note to identify it as a rollback candidate. This is a documentation-only patch; it does not validate the historical deployment claim. |
| `v1.1.0` | `82535d9` | 2026-06-06 | Updated the checkout-service placeholder's name, version constant, startup output, and entry-point function. Reconstructed release record; actual production deployment is unverified. |

## Traceable rollback

Assuming operations confirms that production is running `v1.1.0` and that `v1.0.1` is the last known-good version, use:

```sh
git tag --sort=-v:refname
git show --no-patch --format="%h %ad %s" --date=short v1.1.0
git show --no-patch --format="%h %ad %s" --date=short v1.0.1
git checkout v1.0.1
# Redeploy the checked-out commit using the team's deployment process.
```

The versioned tags sort in release order and each resolves to an immutable commit, so the team can identify and redeploy the exact last known-good source instead of interpreting names such as `latest-good` or `patch-new`. The deployment history still needs to be checked with operations: the original repository does not establish which version is live, and a tag alone is not proof of deployment.
