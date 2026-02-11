# R2 Mechanics — Finance OS (Offline‑First GPU Showcase)

## Mission
An **offline‑first Finance Operating System** that demonstrates how R2 Mechanics implements **data sovereignty** in practice:

- **Auditable ledger** (Excel as a human‑verifiable source of truth)
- **Deterministic automation** (repeatable Python pipelines instead of black‑box apps)
- **Optional local GPU AI** (Vision/LLM via an OpenAI‑compatible endpoint — no cloud requirement)

> This repository is a **proprietary public showcase** (documentation/schemas/templates only).  
> It contains **no real financial data**, no secrets, and no operational configuration.

---

## Why Excel?
Excel is not “just UI” here — it is a deliberate design choice:

- **Readable & auditable** (works without a server)
- **Template‑versionable** (sanitized master structure)
- **Compatible** with classic audit/compliance workflows

---

## System Overview (High Level)
**Ingestion → Review → Ledger → Orchestration → Reporting/Visualization**

- **Inbox ingestion:** receipts/statements enter dedicated inboxes.
- **Review buffer:** extraction results go into a review workbook (human‑in‑the‑loop).
- **Master ledger:** confirmed entries are synced into the master workbook.
- **Updater/Bridge:** prices, pools (“pots”), transfers, report artifacts.
- **Chronos:** history → charts/PDF.

---

## Offline‑First vs Online‑Optional
The core workflows are designed to operate **fully offline**.  
Internet‑dependent components (e.g., market price feeds) are **optional** and clearly separated.

---

## What is intentionally NOT included
- real `*.xlsx` ledgers, receipts, bank statements
- `maus_config.json`, `.env`, API keys
- inbox/archive folders, reports/exports
- internal prompts/policies/rules that would disclose core IP

See: `SECURITY.md` and `PUBLIC_RELEASE_CHECKLIST.md`.

---

## Repository Structure
- `docs/WHITEPAPER.md` — product vision, philosophy, positioning
- `docs/ARCHITECTURE.md` — public architecture view
- `docs/TECHNICAL_DOCUMENTATION.md` — public technical view (sanitized)
- `docs/THREAT_MODEL.md` — leak/abuse risks + controls
- `schemas/EXCEL_MASTER_SCHEMA.md` — tab/column semantics (no real values)
- `templates/maus_config.example.json` — example only, no secrets

---

## IP / License
**All rights reserved.**  
This project is **proprietary** and may contain trade secrets. Use/redistribution only with prior written permission.

---

## Contact
R2 Mechanics — Offline‑first GPU systems for high‑sensitivity processing
