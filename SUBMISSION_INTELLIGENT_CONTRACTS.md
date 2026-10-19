# Intelligent Contracts submission draft — DO NOT SUBMIT YET

PENDING / BLOCKED. Portal form has not been inspected; these are field-ready content drafts to be matched to its actual fields.

Name: Migration Coverage Primitive

English description:

> A reusable GenLayer primitive for evidence-backed migration-guide coverage. It binds a supplied version transition, declared changes and guide snapshot to immutable owner-scoped records. Validators independently derive each finding and audit the proposed quotation and explanation. Deterministic checks reject fabricated evidence, omissions, ordering errors and request rebinding. The result records COVERED, MISSING, CONFLICT or UNKNOWN for each obligation; it does not prove software compatibility.

Source repository: https://github.com/halihalibt/migration-coverage-primitive

Canonical source: https://github.com/halihalibt/migration-coverage-primitive/blob/main/contracts/migration_coverage.py

Deployment and transaction IDs are now reported in the reconciled evidence below; independent verification remains PENDING.

Independent contract evidence URLs:

- https://github.com/halihalibt/migration-coverage-primitive/blob/main/RUNTIME_AUDIT.md
- https://github.com/halihalibt/migration-coverage-primitive/blob/main/VALIDATION.md
- https://github.com/halihalibt/migration-coverage-primitive/actions/workflows/test.yml

Usage: deploy MigrationCoverage with no constructor parameters, call assess(request_id, payload_JSON_string), then read get_record(actual_sender, request_id). Full exact input and evidence return with the canonical hash. See MANUAL_STUDIO_EXECUTION.md.

Logo: assets/patchdebt-logo.png in companion product (original shared product branding; not deployment evidence).

Before submission: supply verified real deployment/consensus evidence and complete target-runtime acceptance. Do not imply local Direct tests are chain execution. No Portal submission has occurred.

## Reconciled Studio evidence (supersedes earlier absence statements)

# Existing Studio evidence — user-provided, not independently verified

Reported network: Stable Studionet / 61999. Reported contract: `0x724AcFe201463a016f59aC41516D99ab789a5c34`. Actual source identity and transaction network details remain PENDING.

Deployment transaction: `0xfe07e2f31b1daa8ab577ad15ad6de2538c8ade6f782b97da31605581678d8387`.

Owner: `0x22acaa233b7b985b36ef168f2de9295334065b15`; reported get_count(owner): **2**.

| Request | Reported state | Reported items | Input SHA256 | Existing transaction |
|---|---|---|---|---|
| patchdebt-public-001 | COVERED | COVERED, COVERED | `5da5070d1fdfe0ce0e1f9c09032d6488bf47579ffc73c0327f527f2a072dbbe7` | `0xb9d04723fbfab34f971d1608cad2742207ec7691ca9f5c70a11a260db4e9a30b` |
| patchdebt-gap-001 | DEBT | COVERED, MISSING | `2f66e88c7134d6ea08b47b6199f3ab812b53192c4d5ac29923ebb34c8ac94e82` | `0x2e7a9f227f9178725bbc4f86ebcf634e6570fbc24830b547e72011e5a5108a58` |

These are user-provided Studio outcomes. No independently retrieved receipts, finality/execution evidence or vote exports are asserted. Canonical source SHA256 is `f828966372c167491fb8e2a61be0d7d639b5170b1bd784ab01fa4bce93cf4aa3`; equality with deployed code remains PENDING. Existing transactions must not be recreated. Input snapshots in examples/live/covered.json and missing.json independently hash to the reported input identities. They are not full returned onchain records.

Submission gate: deployed-source verification, independent record/receipt checks and product-wallet E2E remain PENDING. Do not submit this draft as fully verified.
