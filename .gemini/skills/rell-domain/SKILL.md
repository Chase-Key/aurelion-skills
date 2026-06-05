---
name: rell-domain
version: 1.0.0
description: The RELL compliance audit engine — architecture, philosophy, active modules, and development status.
author: z3rosl33p
tags: [rell, compliance, audit, governance, gdpr, ccpa, hipaa, architecture]
last_updated: 2026-03-22
---

# RELL Domain Skill

## What RELL Is

**RELL** — Regulatory Enforcement & Governance Layer with Live-monitoring

RELL is a compliance and data governance product line built on Aurelion architecture. It is **not an Aurelion module** — it is a separate, standalone product that derives architectural patterns from Aurelion.

**Location:** `rell-eco/` — sibling project in your Personal Projects folder

> "You have a compliance officer who sleeps. Rell doesn't."

---

## Architecture Philosophy

**Lean core. Value in the profiles.**

The RELL engine (`rell-engine`) is domain-agnostic. It doesn't care about GDPR or HIPAA. You bring the compliance profile. The engine runs the checks.

```
rell-engine     ← The open core (MIT). Anyone can run this.
rell-profiles   ← The curated ruleset registry (BSL). This is the product.
rell-gov        ← Commercial: GDPR, CCPA, ISO 27001
rell-health     ← Healthcare: HIPAA, HL7, FHIR
rell-econ       ← Economic: IMF, World Bank, sovereign indicators
rell-infra      ← Infrastructure: NERC CIP, CMMC, ICS compliance
rell-esg        ← ESG: GRI, TCFD, SEC climate disclosure
```

---

## Active Components (as of March 2026)

### rell-engine (Phase 1 — In Progress)
The portable audit core. Extracted from AURELION Nexus Premium. All AURELION-specific references (Stonecrest, Memoria, D&D world engine) are being removed.

**Capabilities:**
- Flat file ingestion and anomaly detection
- Workload tracker scoring and load analysis
- SQL schema ingestion, versioning, and drift detection
- Live database auditing (read-only, credential-validated)
- Audit cycle management with persistent finding memory
- Structured report generation (Markdown + JSON)

**Run the engine:**
```bash
cd rell-eco
python run_audit.py --scan-file path/to/data.txt
python run_web.py   # Web interface
```

**Key files:**
- `rell-engine/engine/audit_engine.py` — Core audit loop
- `rell-engine/engine/audit_agent.py` — Agent orchestration
- `rell-engine/engine/workload_engine.py` — Workload tracker
- `rell-engine/engine/llm_integration.py` — LLM interface
- `rell-engine/web/api.py` — REST API

### rell-workload (Standalone deployment)
The workload tracker has been productized as a standalone module with its own Dockerfile, Fly.io deployment config, and user-facing web UI.

**Location:** `rell-eco/rell-workload/`
**Entry:** `JOSEFINA_START_HERE.bat` — named for a specific user (Josefina) who is the primary operator

### Active Profiles
- `governance/ccpa-ca.json` — California Consumer Privacy Act
- `governance/gdpr-eu.json` — EU General Data Protection Regulation

### Audit Data
- Cycles: `rell-engine/data/audit/memory/cycle_logs/`
- Reports: `rell-engine/data/audit/memory/reports/`
- Findings: `rell-engine/data/audit/memory/finding_logs/`
- State: `rell-engine/data/audit/state/audit_state.json`

---

## Development Phases

| Phase | Target | Status |
|---|---|---|
| 1 | `rell-engine` standalone, installable | In Progress |
| 2 | `rell-profiles` with GDPR-EU as first profile | Planned |
| 3 | `rell-gov` — GDPR/CCPA commercial instance | Planned |
| 4 | `rell-health` — HIPAA, HL7, FHIR | Planned |
| 5+ | `rell-econ`, `rell-infra`, `rell-esg` | Roadmap |

**Phase 1 exit criteria:** Someone with zero Aurelion context can clone `rell-engine`, install it, drop a flat file in the intake folder, and get an audit report.

---

## License Structure

| Component | License | Rationale |
|---|---|---|
| `rell-engine` | MIT | Open core drives adoption and trust |
| `rell-profiles` | BSL | Curated, conflict-resolved rulesets |
| Domain instances | BSL | Bundled for specific markets |

---

## How RELL Relates to Aurelion

RELL extracted its audit engine from Aurelion Nexus Premium. Now they are separate:
- Aurelion = cognitive framework (memory, reasoning, planning, collaboration)
- RELL = compliance product (watch data, report violations)

They share **design philosophy**, not code. Same architect, different buyers.
