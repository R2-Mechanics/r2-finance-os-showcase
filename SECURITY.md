# Security Policy

## Reporting
If you discover a security issue or a potential data‑leak risk, please contact the owner privately.

## What must never be public
- Real financial data (transactions, statements, receipts, IBANs, account numbers)
- Private configuration files (`maus_config.json`, `.env`) and API keys
- Internal prompts/policies/rules that encode core business logic beyond what is required to understand the architecture
- Inbox/Archive folders and any report exports (PDF/HTML), as they can leak sensitive information indirectly
