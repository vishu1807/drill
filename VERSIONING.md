# Release Versioning Convention

## Semantic versioning

Release versions use `MAJOR.MINOR.PATCH`:

- **MAJOR** increments for an incompatible change, such as `v1.4.2 -> v2.0.0` when a supported checkout API is removed or changed incompatibly.
- **MINOR** increments for backward-compatible functionality, such as `v1.4.2 -> v1.5.0` when an optional checkout capability is added.
- **PATCH** increments for a backward-compatible fix, such as `v1.4.2 -> v1.4.3` when a checkout timeout defect is corrected without changing the interface.

After a MAJOR increment, MINOR and PATCH reset to zero. After a MINOR increment, PATCH resets to zero.

## Tag format

Use the exact format `vMAJOR.MINOR.PATCH`, with a lowercase `v` prefix and non-negative integers (for example, `v1.4.2`). Do not add descriptive words to a release tag.

## Release tags

Production releases use **annotated** tags so that the tag records the release message and tagger metadata, rather than only naming a commit. Create one with:

```sh
git tag -a v1.2.3 -m "Release 1.2.3: <summary of shipped changes>" <commit>
```

Use a lightweight tag only for temporary local references, never for a production release.

## Pre-releases

Mark a candidate with a hyphenated pre-release identifier, for example `v1.5.0-rc.1` or `v1.5.0-beta.1`. Increment the numeric identifier for subsequent candidates (`v1.5.0-rc.2`). Under semantic-version precedence, pre-releases sort before the corresponding final release: `v1.5.0-rc.1 < v1.5.0`. Pre-releases are not production releases.
