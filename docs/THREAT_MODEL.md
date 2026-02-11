# Threat Model (Public)

## Assets to protect
- real financial data (amounts, transactions, recipients, account details)
- identifiers (IBAN/account IDs/invoice numbers)
- secrets (API keys, tokens, `.env`)
- operational prompts/policies/rules (core IP)
- logs/exports (may leak data indirectly)

## Attack surfaces
- accidental commits (XLSX/PDF/HTML/logs)
- copy/paste into docs (screenshots, tables, “example values”)
- config leaks (`maus_config.json`, `.env`)
- “helpful” debug output checked into git

## Controls
**Public repository**
- strict `.gitignore`
- allowlist mindset: docs/schemas/templates only (sanitized)
- release checklist as a process gate

**Private repository**
- separate remotes (private origin ≠ public origin)
- CI secret scanning + file allowlists
- redacted config templates; real configs remain local

## Residual risk
Human error is the primary risk factor → process + automation + hard repo separation.
