# Public Release Checklist (5 minutes)

This repository is a **public showcase**. It must never contain real data, secrets, or operational logic.

## 1) Working tree sanity
- `git status` is clean (no unexpected files)
- Only these directories should change frequently:
  - `docs/`
  - `schemas/`
  - `templates/`
  - root docs files (`README.md`, `NOTICE.md`, `SECURITY.md`, `LICENSE`, `.gitignore`)

## 2) Forbidden files (must be zero)
Do **not** publish any of the following:
- Real ledgers/exports: `*.xlsx`, `*.xls`, `*.csv`, `*.pdf`, `*.html`
- Secrets/configs: `.env`, `*.env`, `maus_config.json`, tokens, API keys, certificates
- Operational artifacts: `Inbox_*`, `Archive/`, `Buchung/`, logs, screenshots of real data
- Internal policies/prompts/rules that encode core business logic

## 3) Fast secret/data scan (recommended)
Run at repo root:
- `rg -n "API_KEY|SECRET|TOKEN|PASSWORD|BEGIN PRIVATE|IBAN|ACCOUNT\\s*NO|KONTO|KONTONR|SWIFT" -S .`

If anything matches, stop and remove/redact before pushing.

## 4) Diff review
- `git diff --stat`
- Skim the actual diff for accidental copy/paste of real identifiers or values.

## 5) Release gate
Before tagging a release:
- Confirm: docs/schemas/templates only
- Confirm: no real values embedded in examples
- Confirm: `.gitignore` blocks all sensitive artifact types
