# Submission draft — final acceptance still pending

Status: PENDING; do not submit to Portal yet. Actual form not inspected; labels below are semantic drafts, not invented required form fields.

## Copyable English introduction

PatchDebt — Migration Coverage Primitive

PatchDebt is a GenLayer Intelligent Contract that audits a supplied migration guide against an explicit list of software changes. It stores ordered findings, verbatim evidence and explanations bound to the sender, request ID and canonical input hash. Independent validator review challenges the proposed findings. It identifies documentation gaps, conflicts and uncertainty without claiming software compatibility or complete change discovery.

## Field values

- Repository (VERIFIED public): https://github.com/halihalibt/migration-coverage-primitive
- Complete source (VERIFIED): https://github.com/halihalibt/migration-coverage-primitive/blob/main/contracts/migration_coverage.py
- Contract (VERIFIED): `0x724AcFe201463a016f59aC41516D99ab789a5c34`
- Network: Stable Studionet; configured chain ID 61999
- Source SHA256 (VERIFIED): `f828966372c167491fb8e2a61be0d7d639b5170b1bd784ab01fa4bce93cf4aa3`
- Evidence (VERIFIED observations): https://github.com/halihalibt/migration-coverage-primitive/blob/main/evidence/EXPLORER_VERIFICATION.md
- Validation: https://github.com/halihalibt/migration-coverage-primitive/blob/main/FINAL_READINESS_REPORT.md
- Contract runtime audit: https://github.com/halihalibt/migration-coverage-primitive/blob/main/RUNTIME_AUDIT.md
- Contract CI: https://github.com/halihalibt/migration-coverage-primitive/actions/runs/39286212477 (unchanged source ancestor)
- Logo (VERIFIED): https://raw.githubusercontent.com/halihalibt/patchdebt-genlayer/main/assets/patchdebt-logo.png — original PNG, 1024×1024, 189067 bytes

## Existing transaction evidence

- Deployment: https://explorer-studio.genlayer.com/tx/0xfe07e2f31b1daa8ab577ad15ad6de2538c8ade6f782b97da31605581678d8387
- Public assessment: https://explorer-studio.genlayer.com/tx/0xb9d04723fbfab34f971d1608cad2742207ec7691ca9f5c70a11a260db4e9a30b
- Gap assessment: https://explorer-studio.genlayer.com/tx/0x2e7a9f227f9178725bbc4f86ebcf634e6570fbc24830b547e72011e5a5108a58

## Use

Constructor has no arguments. `assess(request_id, payload)` accepts the JSON input documented in README; `get_record(owner, request_id)` and `get_count(owner)` are public views. Existing records can be queried without a wallet. The website source check precedes reads; signing additionally requires an active wallet, accepted manifest and correct network.

## Product-wallet evidence update

VERIFIED: user completed one assessment through the product; actual public website independently verified and exported a finalized transaction-bound dossier. No further signature is needed. Transaction: https://explorer-studio.genlayer.com/tx/0x50d745ee7ddfc89fcbf54c849585ab870b4215d1ca73f456511502dea7f28d82 . Final evidence: https://github.com/halihalibt/patchdebt-genlayer/blob/main/evidence/WEBSITE_WALLET_DOSSIER.json . This supplements, rather than replaces, the distinct original A/B evidence fields above.

Full local WASM execution and mobile render acceptance remain unperformed. Actual Portal fields have not been inspected; do not invent required field rules. See FINAL_READINESS_REPORT.md for the exact remaining limits. No Portal submission has occurred.
