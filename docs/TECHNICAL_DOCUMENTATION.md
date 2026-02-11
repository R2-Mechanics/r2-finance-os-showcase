# Technical Documentation (Public, Sanitized)

## Purpose of this document
Explain the methodology and system shape without operational secrets:
no real data, no keys, no private prompts/policies.

## Dataflow (Conceptual)
Inboxes → Review workbook → Master ledger → Updater/Bridge → Reports/History → Visualizer

## Core Concepts
### Review buffer (human‑in‑the‑loop)
Extraction is not truth. The review buffer prevents silent errors from entering the master ledger.

### Ledger as source of truth
The master workbook defines the final state (transactions, assets, history, pools, commander status).

### Deterministic pipelines
- append semantics (avoid overwriting formulas/styles in a template)
- archiving/idempotency patterns
- duplicate handling strategies

### Optional local OpenAI‑compatible LLM
Used for extraction/classification/advisor — locally, without the cloud.
The system remains usable without an LLM.

## Public schema
See: `schemas/EXCEL_MASTER_SCHEMA.md`

## Configuration (public example)
See: `templates/maus_config.example.json` (no secrets)

## Public operating guidance
- never commit `*.xlsx`, `.env`, `maus_config.json`
- run a secret scan before pushing (rg/CI)
- sign releases/tags if IP timestamping matters
