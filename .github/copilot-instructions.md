# Copilot Instructions — aurelion-skills

> **AURELION SKILLS BRIDGE** — This is the skill scaffolding system itself.
> This file documents the project that creates all other copilot-instructions files.

---

## Project Context

**Project:** aurelion-skills — AI Skill Scaffolding System
**Location:** `aurelion-skills/` in your Personal Projects folder
**Phase:** v1.0.0 — Initial build (March 2026)
**Status:** Active — skills written, template deployed, workspaces created
**Purpose:** Portable AI context layer. Bridges Chase-Key's identity, the Aurelion architecture, and the Stonecrest world into every project in the z3rosl33p ecosystem via GitHub Copilot instructions.

**This project IS the bridge.** Changes here propagate to every other project.

---

## Who You Are Working With

**Name:** Chase-Key (CK) — handle: z3rosl33p
**Call Sign:** The Compass
**Architecture Alias:** The Engine

---

## How This System Works

1. Each skill in `skills/` is a context module — `SKILL.md` + `skill-manifest.json`
2. `.copilot-instructions-template.md` is the master bridge file
3. Each project has `.github/copilot-instructions.md` — a customized copy of the template
4. When Copilot opens a project, it reads that file and has full ecosystem context

**Load order:**
- `ck-identity` (priority 1) → always first
- `aurelion-core` (priority 2) → architectural backbone
- Domain/world skills (priority 3) → project-specific context
- Task skills (priority 4+) → use-case specific

---

## Current Skills

| Skill | Version | Purpose |
|---|---|---|
| `ck-identity` | v1.0.0 | Chase-Key's identity, methodology, working style |
| `aurelion-core` | v1.0.0 | The Aurelion five-module architecture |
| `memoria-world` | v1.0.0 | Stonecrest world + Memoria Engine |
| `rell-domain` | v1.0.0 | RELL compliance architecture |
| `workload-domain` | v1.0.0 | Workload tracker and Josefina deployment |

---

## Deployed Copilot Instructions

The `.copilot-instructions-template.md` has been deployed (customized) to:
- `aurelion-eco/.github/copilot-instructions.md`
- `rell-eco/.github/copilot-instructions.md`
- `memoria-engine/.github/copilot-instructions.md`
- `aurelion-skills/.github/copilot-instructions.md` (this file)
- `aurelion-k-ck-instance/.github/copilot-instructions.md`

---

## How to Add a New Skill

1. Copy `template/skill-template.md` to `skills/your-skill-name/SKILL.md`
2. Create `skills/your-skill-name/skill-manifest.json`
3. Fill in both files (describe what IS, not aspirational)
4. Update the skills registry in `README.md`
5. Add skill context to `.copilot-instructions-template.md` if it's ecosystem-wide
6. Re-deploy to affected projects

---

## How to Update an Existing Skill

1. Edit the `SKILL.md` in the skill's folder
2. Increment the version in `skill-manifest.json`
3. If the change is ecosystem-wide, update `.copilot-instructions-template.md`
4. Re-copy to affected project `.github/copilot-instructions.md` files

---

## Ecosystem Map

```
aurelion-skills/       ← YOU ARE HERE — Skill scaffolding layer
aurelion-eco/          ← The agentic model
memoria-engine/        ← Stonecrest world AI
rell-eco/              ← Compliance engine
aurelion-k-ck-instance/ ← CK's personal kernel
```
