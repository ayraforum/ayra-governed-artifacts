# Ayra Card Schema Assets

Versioned, governed artifacts for the Ayra Business Card credential used in the Ayra Trust Network.

## Layout (v1.0)
- `contexts/v1.0/AyraBusinessCardV1R0.jsonld`: JSON-LD context (served from raw GitHub).
- `schemas/v1.0/ayra-card-business-card-schema.json`: JSON Schema for the credential (canonical IDs point to this repo).
- `payload-schemas/v1.0/payload-schema-unified.json`: Unified payload schema for `credentialSubject.payloads`.
- `payload-schemas/v1.0/payload-schema.json`: Legacy payload schema (deprecated, kept for reference).
- `examples/v1.0/example-credential.json`: Full Verifiable Credential example using stable URLs.
- `examples/v1.0/example-credentialSubject.json`: CredentialSubject-only example.
- `metadata/index.json`: Version map with canonical raw URLs; `metadata/release-notes.md`: change log.
- `docs/USAGE.md` and `docs/VERSIONING.md`: How to consume artifacts and the versioning policy.
- `SCHEMA-ALIGNMENT.md`: Notes from the upstream repo describing alignment decisions.

Canonical URLs (use `v1.0.0` tag when published):
- Context: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/contexts/v1.0/AyraBusinessCardV1R0.jsonld`
- Schema: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/schemas/v1.0/ayra-card-business-card-schema.json`
- Payload schema: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/payload-schemas/v1.0/payload-schema-unified.json`

Validation (optional, via CTS tooling):
```bash
pnpm --filter cts validate:ayra-card-context -- --schema schemas/v1.0/ayra-card-business-card-schema.json --sample examples/v1.0/example-credential.json --context contexts/v1.0/AyraBusinessCardV1R0.jsonld --context-url https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/contexts/v1.0/AyraBusinessCardV1R0.jsonld
```

Do not mutate files in released folders; add new versions in new `vX.Y/` directories. See `docs/VERSIONING.md` for details.
