# Release Notes

The dates below are the tagged commits' recorded dates. These notes describe the changes in each tagged commit; the repository does not independently verify production deployment.

## v1.1.0 — 2026-06-06

**Summary**

- **Changed:** Identified the checkout service by name and an explicit placeholder service version.
- **Changed:** Updated startup output and renamed the entry point to `run`.

**Rollback target:** `v1.0.1`, if operations confirms it as the last known-good deployed release.

## v1.0.1 — 2026-06-06

**Summary**

- **Fixed:** Clarified the legacy `release_2` note to describe it as a rollback candidate. This is a documentation correction only; it does not make that legacy tag a verified rollback target.

**Rollback target:** `v1.0.0`, if operations confirms it as the last known-good deployed release.

## v1.0.0 — 2026-06-06

**Summary**

- **Added:** Initial release baseline containing the placeholder checkout service and the assignment repository's baseline documentation.

**Rollback target:** None; this is the first version in this reconstructed release sequence. Select a previous production build only after verifying its commit with operations.
