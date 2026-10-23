# release-tagging-drill

## Assignment Overview

The Checkout service has been deployed for over a year. The engineering team inherited inconsistent, unreliable release tagging and incomplete deployment traceability. Your role is to act as the Release Engineer who audits the existing tag history, defines a consistent semantic versioning policy, and documents release-to-deployment traceability.

## Repository Story

- Multiple developers created tags using different naming styles.
- Some releases are lightweight tags, some are annotated tags.
- Some tags have meaningless names or point to unrelated commits.
- Production incidents happened with no reliable rollback target.
- Nobody can confidently identify which release corresponds to which deployment.

## What students must do

1. Audit the existing repository tags.
2. Identify tagging problems and recommend fixes.
3. Define a semantic versioning and annotated tag policy.
4. Create a release map that ties versions to commits and deployments.
5. Produce structured release notes with rollback targets.
6. Document rollback traceability and recovery commands.

## Repository Files

- `docs/deployment-history.md` — flawed deployment history examples
- `docs/incident-log.md` — incidents caused by bad tagging
- `docs/release-notes-old.md` — inconsistent old release notes
- `CHANGELOG.md` — historical changelog with mixed records
- `src/` — dummy checkout service application
- `feature/release-tagging` — branch with the student deliverables

## How to complete this assignment

1. Create a feature branch called `feature/release-tagging`.
2. Add `TAG-AUDIT.md`, `VERSIONING.md`, `RELEASE-MAP.md`, and `RELEASES.md`. Include rollback traceability in `RELEASE-MAP.md` or a separate `TRACEABILITY.md`.
3. Use annotated semantic-version tags for releases and document the policy.
4. Open a GitHub pull request from `feature/release-tagging` into `main`.
5. Record your audit findings during a short explainer video.

## Notes for instructors

This repository already contains a broken tag history. Students should audit the tags and rebuild release traceability without adding CI/CD automation.
