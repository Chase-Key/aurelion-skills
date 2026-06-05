---
name: workload-domain
version: 1.0.0
description: The workload tracker system — scoring engine, team operations, and the Josefina deployment context.
author: z3rosl33p
tags: [workload, tracker, scoring, team, operations, josefina, queueing]
last_updated: 2026-03-22
---

# Workload Domain Skill

## What This Is

The workload tracker is a standalone web application for tracking team workload, scoring task complexity, and surfacing overload signals before they become problems. It was built inside `rell-engine` and has since been extracted as its own deployable product.

**Locations:**
- `rell-eco/rell-engine/engine/workload_engine.py` — Core engine
- `rell-eco/rell-workload/` — Standalone deployment

---

## Josefina Context

`rell-workload/JOSEFINA_START_HERE.bat` — The workload tracker was deployed for a specific user named Josefina. She is the primary day-to-day operator. The `.bat` file exists to make startup zero-friction for a non-technical operator.

When working on workload features, always consider:
- Non-technical operator UX (Josefina model: she should click one thing and it works)
- The tracker must be honest about overload — no softening the data
- Reports should be actionable, not just informational

---

## Scoring System

The workload engine scores individual tasks and produces aggregate team load signals.

**Config:** `rell-workload/config/scoring.json`
**Team Roster:** `rell-workload/config/team-roster.json`

Scoring factors include task complexity, priority, time sensitivity, and team member current load. Outputs a normalized score per assignment and a team-level load index.

---

## Stack

```
rell-workload/
├── run_web.py          ← Start the web server
├── engine/
│   ├── workload_engine.py   ← Core scoring logic
│   └── excel_parser.py      ← Intake from Excel files
├── web/
│   ├── workload_api.py      ← REST API
│   └── workload_pdf.py      ← PDF report generation
├── config/
│   ├── scoring.json         ← Scoring weights and thresholds
│   └── team-roster.json     ← Team members and capacity
├── data/intake/             ← Drop Excel files here
├── Dockerfile               ← Container deployment
└── fly.toml                 ← Fly.io production config
```

**Run locally:**
```bash
cd rell-eco/rell-workload
python run_web.py
```

---

## Case Study Reference

The workload tracker was built as a case study for external validation of the RELL engine approach. See:
- `rell-eco/docs/case-study_workload-tracker.md`

---

## Integration with Audit Engine

The workload tracker is also embedded inside `rell-engine` where it provides:
- Team load context during audit cycles
- Scoring configuration via `data/workload/scoring_config.json`
- Profiles via `profiles/workload/workload-tracker.json` and `team-roster.json`
