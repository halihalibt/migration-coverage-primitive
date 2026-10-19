# Migration Coverage Primitive

A GenLayer Intelligent Contract that binds a supplied software version transition, 1–8 declared breaking changes and a migration-guide snapshot to an immutable, evidence-backed coverage map. It checks documentation coverage, not software compatibility or completeness of the change list.

## Verification status

**Candidate source; not submission-ready.** 24 CPython tests and 10 official SDK Direct Mode tests pass locally. Official linter/SDK validation passes. Full WASM GenVM execution and real Studionet consensus have NOT been run. A Studio deployment and two outcomes are now reported by the user; see DEPLOYMENT_STATUS.md. They are not yet independently verified receipts. [Verification](VALIDATION.md) · [Runtime API audit](RUNTIME_AUDIT.md) · [Manual Studio package](MANUAL_STUDIO_EXECUTION.md).

## Consensus and deterministic checks

The Leader proposes ordered COVERED / MISSING / CONFLICT / UNKNOWN findings. Each Validator independently derives each status AND audits the Leader's actual quote and reason. A matching status with an irrelevant quote or false explanation is rejected. Audit booleans must be literal `true`; omissions, reordering, malformed JSON, duplicate JSON keys and fabricated quotations fail closed. Quotes must be verbatim guide substrings; COVERED and CONFLICT require evidence, MISSING requires an empty quote.

Evidence validity remains a model-dependent semantic judgment. Tests cover injected model outputs, not universal real-model accuracy or injection immunity. Consensus does not authenticate a caller-supplied guide or URL. Source URLs are references; the contract does not fetch them.

## API

Constructor: **no arguments**.

| Method | Type | Arguments / result |
|---|---|---|
| `assess` | write | `request_id: str`, `payload: str` → complete JSON record |
| `get_record` | view | `owner: str`, `request_id: str` → JSON or empty string |
| `get_count` | view | `owner: str` → integer |

Payload: complete JSON from [example](examples/assess-input.json). Fields are exactly package, from_version, to_version, changes, guide, source_url. Package/version 1–100 characters; different versions; 1–8 unique changes of 8–500 characters; guide 1–10,000; HTTPS reference 9–500; full payload 20–18,000 characters. Blank fields and lone surrogates reject. Request IDs: 1–64 ASCII letters, digits, hyphen or underscore.

Actual sender namespaces records. A successful request token is immutable: same canonical input returns the existing record before model calls; changed input rejects. New tokens permit deliberate reassessment, capped at 64 accepted records per address. This is not Sybil resistance. Records cannot be edited/deleted. State writes occur after the consensus boundary; real VM atomicity is not proven by the unit harness.

## Run tests

```sh
python3 -m unittest discover -s tests -v
pip install -r requirements-dev.txt
PYTEST_DISABLE_PLUGIN_AUTOLOAD=1 python3 -m pytest -p gltest.direct.pytest_plugin tests/direct -q
genvm-lint check contracts/migration_coverage.py --json
sha256sum -c SOURCE_SHA256.txt
```

Direct Mode loads the pinned SDK from official GenVM v0.2.16 artifacts; it executes natively with mocked host/model responses, not inside WASM. The first run may download ~207 MiB. It explicitly invokes captured production validators and serializes closures, which ordinary Direct Mode otherwise skips. Do not mix the CPython mock harness and Direct tests in one pytest process.

[Companion PatchDebt product](https://github.com/halihalibt/patchdebt-genlayer) includes the complete identical source. All work belongs to `halihalibt`. No unrelated account or project is part of this release.

MIT License.

## Current final acceptance

Deployed source identity and both finalized website readbacks are VERIFIED; all three existing transactions display FINALIZED/SUCCESS/Normal in official Explorer. See [current matrix](FINAL_READINESS_REPORT.md) and [independent evidence](evidence/EXPLORER_VERIFICATION.md). Earlier user-reported-only deployment statements are historical. Product-wallet E2E remains BLOCKED without a browser wallet. Full local WASM execution is not claimed. No Portal submission.
