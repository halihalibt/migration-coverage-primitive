# PatchDebt — Migration Coverage Primitive

A reusable GenLayer Intelligent Contract that checks whether a supplied migration guide gives actionable instructions for each declared software change. It stores ordered findings, verbatim evidence and explanations bound to package versions, the guide snapshot, sender and request ID.

[Live application](https://halihalibt.github.io/patchdebt-genlayer/) · [Deployment](DEPLOYMENT.md) · [Validation](VALIDATION.md) · [Usage](USAGE.md)

## How it works

1. The caller supplies package versions, 1–8 declared changes and an exact guide snapshot.
2. A Leader proposes one ordered finding per change: `COVERED`, `MISSING`, `CONFLICT` or `UNKNOWN`.
3. Validators independently assess the statuses and audit each proposed quotation and explanation. Deterministic checks reject malformed output, missing or reordered items and quotations absent from the guide.
4. The contract stores the accepted record with a canonical input SHA-256, owner and request ID.

The aggregate states are `COVERED`, `DEBT` (a missing step), `BLOCKED` (a conflict) and `REVIEW` (uncertainty). Reusing the same owner/request ID with identical input returns its existing record; different input is rejected. Each owner can store at most 64 records.

## Contract interface

Constructor: no arguments.

| Method | Access | Arguments | Result |
|---|---|---|---|
| `assess` | Write | `request_id: str`, `payload: str` | Complete JSON assessment record |
| `get_record` | View | `owner: str`, `request_id: str` | Saved JSON record, or an empty string |
| `get_count` | View | `owner: str` | Number of saved records for that owner |

See [input format and limits](USAGE.md) and [public-document examples](examples/live/PROVENANCE.md).

## Deployment and evidence

Stable GenLayer Studionet, chain ID **61999**. Contract: `0x724AcFe201463a016f59aC41516D99ab789a5c34`.

The deployed source matches [contracts/migration_coverage.py](contracts/migration_coverage.py), SHA-256 `f828966372c167491fb8e2a61be0d7d639b5170b1bd784ab01fa4bce93cf4aa3`. Deployment, two Studio assessments and a website-wallet assessment have successful finalized evidence. [Evidence index](evidence/README.md).

The [companion product repository](https://github.com/halihalibt/patchdebt-genlayer) includes the complete byte-identical source and tests.

## Development

```sh
python3 -m unittest discover -s tests -v
sha256sum -c SOURCE_SHA256.txt
pip install -r requirements-dev.txt
PYTEST_DISABLE_PLUGIN_AUTOLOAD=1 python3 -m pytest -p gltest.direct.pytest_plugin tests/direct -q
```

The 24 CPython tests use mocked SDK/host behavior; the 10 official SDK Direct Mode tests run natively with mocked host/model responses. Neither is a full local WASM execution. See [runtime compatibility](RUNTIME_AUDIT.md) for the pinned runner and validation scope.

## Scope

PatchDebt evaluates documentation coverage. It does not prove software compatibility, authenticate a source URL or establish that the supplied change list is complete. Semantic judgments remain model-dependent. Owner namespaces and quotas are not Sybil resistance. Saved records cannot be edited or deleted.

MIT licensed. [License](LICENSE).
