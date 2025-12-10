# Versioning policy

- Artifacts are stored under versioned folders (e.g., `contexts/v1.0/`) and must not be edited after release.
- Release tags follow `vX.Y.Z` and point to the same versioned folders (e.g., tag `v1.0.0` corresponds to the `v1.0/` directory).
- Add new versions by copying forward to a new folder (e.g., `v1.1/`) and updating contents there; never mutate old versions.
- Update `metadata/index.json` and `metadata/release-notes.md` with every release to capture canonical URLs and change history.
- Prefer raw GitHub URLs (or GitHub Pages if enabled) in all `@context` and schema references to keep URLs stable across implementations.
