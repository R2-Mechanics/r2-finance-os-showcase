# Whitepaper — R2 Mechanics Finance OS (Offline‑First GPU Showcase)

## 1. Executive Summary
R2 Mechanics Finance OS is an **offline‑first finance orchestration system** that combines an auditable data backbone
(an Excel ledger) with deterministic automation (Python pipelines) and optional **local GPU AI**.

This is not “yet another finance app.” It is a **proof‑of‑concept showcase** that the R2 Mechanics methodology
(data sovereignty, air‑gap readiness, audit trails) applies beyond transcription/ASR:
**messy inputs → structured truth → policy‑driven orchestration → reproducible outputs**.

## 2. Problem Space
Many consumer and enterprise finance tools are:
- **cloud‑centric** (telemetry, vendor lock‑in, data exfiltration risk)
- **hard to audit** (opaque rules, implicit transformations)
- **fragile** (API dependencies, UI‑driven workflows, limited reproducibility)

For sensitive environments (high‑security organizations, forensics, strict compliance, personal sovereignty),
this is often unacceptable.

## 3. Guiding Principles (R2 Mechanics Method)
### 3.1 Data Sovereignty
Data stays local. AI is optional and local (OpenAI‑compatible endpoint inside your own network).

### 3.2 Auditability & Reproducibility
- Excel ledger as **human‑verifiable truth**
- deterministic processing steps
- history/report artifacts that support audits and reviews

### 3.3 Human‑in‑the‑Loop as a Safety Feature
A review workbook separates extraction/interpretation from the master ledger. This prevents parsers/AI from silently
changing the truth.

### 3.4 Offline‑First, Online‑Optional
Internet‑dependent features (e.g., price feeds) are isolated. The core system can run offline.

## 4. Architectural Concept
Pipeline:
1) **Inbox ingestion**
2) **Scanner/Extractor → Review**
3) **Review (human‑in‑the‑loop)**
4) **Sync → Master ledger**
5) **Updater (optional)**
6) **Commander/Bridge → orchestration + report artifacts**
7) **Visualizer → charts/PDF**

## 5. Why “Pots” (Pools) — not just categories?
Categories explain the past. Pools control the present.
The pot model is an operational steering layer:
- budgets/liquidity are modeled as explicit pools
- transfers are explicit decisions, auditable and reproducible

## 6. GPU AI: Value Without the Cloud
- Vision/LLM extraction (receipts → structured fields)
- normalization/classification (optional)
- advisor analysis based on ledger state (optional)

AI is **not** a single point of failure. The system remains usable without it.

## 7. Security & IP Boundary
This public repository is **documentation only**, not an ops dump:
- no real financial data
- no secrets/configs
- no internal prompts/policies that disclose core IP

See `docs/THREAT_MODEL.md`, `SECURITY.md`, `PUBLIC_RELEASE_CHECKLIST.md`.

## 8. Use Cases (PoC → Product Lines)
- personal finance sovereignty
- offline networks (audit/compliance environments)
- forensic‑grade accounting workflows (reproducibility + artifacts)
- infrastructure demonstrator: R2 Mechanics offline‑first GPU orchestration outside ASR

## 9. Status / Roadmap
- Public: documentation/schemas/templates
- Private: operational tools + internal policies + CI/secret scanning

Next steps (typical):
- sanitized workbook template generator
- schema validation + diff‑friendly exports
- signed releases/hashes for IP timestamping
