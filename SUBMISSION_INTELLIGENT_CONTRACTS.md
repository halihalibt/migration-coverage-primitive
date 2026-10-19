# Intelligent Contracts submission draft — DO NOT SUBMIT YET

PENDING / BLOCKED. Portal form has not been inspected; these are field-ready content drafts to be matched to its actual fields.

Name: Migration Coverage Primitive

English description:

> A reusable GenLayer primitive for evidence-backed migration-guide coverage. It binds a supplied version transition, declared changes and guide snapshot to immutable owner-scoped records. Validators independently derive each finding and audit the proposed quotation and explanation. Deterministic checks reject fabricated evidence, omissions, ordering errors and request rebinding. The result records COVERED, MISSING, CONFLICT or UNKNOWN for each obligation; it does not prove software compatibility.

Source repository: https://github.com/halihalibt/migration-coverage-primitive

Canonical source: https://github.com/halihalibt/migration-coverage-primitive/blob/main/contracts/migration_coverage.py

Deployment address: PENDING. Network: intended Stable Studionet, 61999. Deployment/assessment transaction IDs: PENDING, none recorded.

Independent contract evidence URLs:

- https://github.com/halihalibt/migration-coverage-primitive/blob/main/RUNTIME_AUDIT.md
- https://github.com/halihalibt/migration-coverage-primitive/blob/main/VALIDATION.md
- https://github.com/halihalibt/migration-coverage-primitive/actions/workflows/test.yml

Usage: deploy MigrationCoverage with no constructor parameters, call assess(request_id, payload_JSON_string), then read get_record(actual_sender, request_id). Full exact input and evidence return with the canonical hash. See MANUAL_STUDIO_EXECUTION.md.

Logo: assets/patchdebt-logo.png in companion product (original shared product branding; not deployment evidence).

Before submission: supply verified real deployment/consensus evidence and complete target-runtime acceptance. Do not imply local Direct tests are chain execution. No Portal submission has occurred.
