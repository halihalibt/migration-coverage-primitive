# Migration Coverage Primitive — review reference

## Project description

A reusable GenLayer Intelligent Contract that checks whether a supplied migration guide gives actionable instructions for each declared software change. It stores ordered findings, verbatim evidence and explanations bound to package versions, the guide snapshot, sender and request ID. PatchDebt evaluates documentation coverage. It does not prove software compatibility, authenticate a source URL or establish that the supplied change list is complete. Semantic judgments remain model-dependent.

## Links and identity

| Field | Value |
|---|---|
| Name | PatchDebt — Migration Coverage Primitive |
| Repository | https://github.com/halihalibt/migration-coverage-primitive |
| Complete contract source | https://github.com/halihalibt/migration-coverage-primitive/blob/main/contracts/migration_coverage.py |
| Network | Stable GenLayer Studionet, chain ID 61999 |
| Contract | `0x724AcFe201463a016f59aC41516D99ab789a5c34` |
| Evidence | https://github.com/halihalibt/migration-coverage-primitive/blob/main/evidence/EXPLORER_VERIFICATION.md |
| Validation | https://github.com/halihalibt/migration-coverage-primitive/blob/main/VALIDATION.md |
| Additional information | https://github.com/halihalibt/migration-coverage-primitive/blob/main/RUNTIME_AUDIT.md |
| Logo | https://raw.githubusercontent.com/halihalibt/patchdebt-genlayer/main/assets/patchdebt-logo.png |

Canonical SHA-256: `f828966372c167491fb8e2a61be0d7d639b5170b1bd784ab01fa4bce93cf4aa3`. Logo: original PNG, 1024 × 1024, 189,067 bytes.

## Relevant transaction

Deployment: https://explorer-studio.genlayer.com/tx/0xfe07e2f31b1daa8ab577ad15ad6de2538c8ade6f782b97da31605581678d8387

## Usage

Constructor: no arguments. assess(request_id, payload) writes a request-bound assessment; get_record(owner, request_id) and get_count(owner) are public views.

[Full usage](USAGE.md) · [Deployment evidence](DEPLOYMENT_STATUS.md) · [Validation scope](VALIDATION.md#validation-boundaries).
