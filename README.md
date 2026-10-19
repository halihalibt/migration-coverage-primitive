# Migration Coverage Primitive

A GenLayer Intelligent Contract primitive for evidence-backed migration-guide coverage. It binds each request to a canonical input hash, requires one ordered finding per declared change, rejects fabricated quotations, and records the finalized assessment under the submitting owner and request ID.

## Repository map

- `contracts/migration_coverage.py` — canonical contract source.
- `tests/test_contract.py` — ordinary CPython harness with mocked GenLayer APIs; not a GenVM test.
- `examples/assess-input.json` — sample request payload.
- `DEPLOYMENT_STATUS.md` — explicit runtime and deployment verification boundary.
- `SOURCE_SHA256.txt` — canonical source checksum.

## Status

Source and local harness only. No live deployment, transaction, or GenVM compatibility claim is made. See `DEPLOYMENT_STATUS.md` before deployment.
