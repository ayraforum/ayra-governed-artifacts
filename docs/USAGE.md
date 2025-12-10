# Using the governed artifacts

## Canonical URLs (v1.0.0)
- Context: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/contexts/v1.0/AyraBusinessCardV1R0.jsonld`
- JSON Schema: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/schemas/v1.0/ayra-card-business-card-schema.json`
- Payload schema (unified): `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/payload-schemas/v1.0/payload-schema-unified.json`
- Examples: `https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/examples/v1.0/example-credential.json`

Use the same paths with the release tag (e.g., `v1.0.0`) instead of `main` once the tag is published for immutable URLs.

## Referencing in credentials
- Add the context URL above to the `@context` array of your Verifiable Credential.
- Set `credentialSchema.id` to the JSON Schema URL above (type: `JsonSchemaValidator2018`).
- Payload objects embedded in `credentialSubject.payloads` should validate against `payload-schema-unified.json`.

## Fetching artifacts locally
```bash
curl -sSfL https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/contexts/v1.0/AyraBusinessCardV1R0.jsonld -o AyraBusinessCardV1R0.jsonld
curl -sSfL https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/schemas/v1.0/ayra-card-business-card-schema.json -o ayra-card-business-card-schema.json
curl -sSfL https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/examples/v1.0/example-credential.json -o example-credential.json
```

## Validation (optional)
Use your preferred JSON Schema validator against the schema URL, or run the upstream CTS script if available:
```bash
pnpm --filter cts validate:ayra-card-context -- --schema schemas/v1.0/ayra-card-business-card-schema.json --sample examples/v1.0/example-credential.json --context contexts/v1.0/AyraBusinessCardV1R0.jsonld --context-url https://raw.githubusercontent.com/ayraforum/ayra-governed-artifacts/main/contexts/v1.0/AyraBusinessCardV1R0.jsonld
```
