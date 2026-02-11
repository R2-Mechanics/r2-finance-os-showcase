# Architecture (Public)

## System Picture
**Ingestion → Review → Ledger → Orchestration → Reporting/Visualization**

This design deliberately separates:
- **extraction/interpretation** (error‑prone; optionally AI‑assisted)
- from the **truth** (master ledger)
- and from **orchestration** (policies, transfers, report artifacts)

## Logical Components
1. **Inbox Layer** — dedicated inboxes by input type  
2. **Review Layer** — a review workbook as “quarantine” (human‑in‑the‑loop)  
3. **Ledger Layer** — the master Excel ledger as source of truth  
4. **Orchestration Layer** — pools/pots, transfers, commander states, artifact generation  
5. **Visualization Layer** — history → charts/PDF (read‑only)

## Offline‑First Mechanics
- Core workflows operate offline.
- Internet‑based features (e.g., price feeds) are optional and isolated.

## Boundary (Public vs Private)
Public: architecture/schema/philosophy.  
Private: tools, configuration, internal policies, logs, and any real data.
