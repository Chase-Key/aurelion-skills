# AURELION Skills

**Standalone AI Skill Scaffolding System for the z3rosl33p Ecosystem**

> The persistent cognitive layer that bridges Chase-Key, the Aurelion architecture, and every project in the ecosystem.

---

## What This Is

`aurelion-skills` is a portable, self-contained skill scaffolding system. It solves one problem: **when you open any project in this ecosystem, the AI already knows who you are, what you've built, and how you work.**

Every skill here is a structured context module. Drop one into a project and you have:
- Chase-Key's identity, methodology, and working style loaded
- The Aurelion architecture as the active cognitive framework
- The Stonecrest/Memoria world as shared creative context
- Project-specific domain knowledge (RELL, workload, etc.)

**The engine stays portable. The value is in the context.**

---

## Architecture

```
aurelion-skills/
├── skills/
│   ├── ck-identity/          ← Who Chase-Key is — personality, methodology, vision
│   ├── aurelion-core/        ← The Aurelion architecture (kernel, memory, nexus, advisor, agent)
│   ├── memoria-world/        ← The Stonecrest world, D&D campaign, Darklight Chambers
│   ├── rell-domain/          ← RELL compliance engine, audit architecture
│   └── workload-domain/      ← Workload tracker, team operations, scoring engine
├── spec/
│   └── skill-schema.md       ← What a valid skill looks like
├── template/
│   └── skill-template.md     ← Start here to create a new skill
└── .copilot-instructions-template.md   ← Drop into .github/ in any project
```

---

## Quick Start: Wire a Project

To bring the full cognitive context into any project, copy `.copilot-instructions-template.md` to that project's `.github/copilot-instructions.md` and customize the `[PROJECT]` section at the top.

```
cp .copilot-instructions-template.md  ../my-project/.github/copilot-instructions.md
```

Then open the project in VS Code. GitHub Copilot will load the context on every session.

---

## Skills Registry

| Skill | Version | Purpose |
|---|---|---|
| `ck-identity` | `v1.0.0` | Chase-Key's identity, methodology, and working principles |
| `aurelion-core` | `v1.0.0` | The Aurelion cognitive architecture |
| `memoria-world` | `v1.0.0` | Stonecrest world, Darklight Chambers, Memoria engine |
| `rell-domain` | `v1.0.0` | RELL compliance audit architecture |
| `workload-domain` | `v1.0.0` | Workload tracking and operational management |

---

## Design Principles

1. **Separable** — Each skill can be loaded independently
2. **Composable** — Stack skills to build exactly the context you need
3. **Portable** — A skill is a folder. It works anywhere
4. **Living** — Skills are updated as projects evolve; they don't go stale
5. **Honest** — Skills describe what IS, not what's aspirational (mark aspirations clearly)

---

## Relationship to the Ecosystem

```
aurelion-eco       ← The agentic model (KERNEL, MEMORY, NEXUS, ADVISOR, AGENT)
memoria-engine     ← The Stonecrest world AI — Aurelion Nexus Premium prototype
aurelion-skills    ← YOU ARE HERE — skill scaffolding layer
rell-eco           ← Compliance product built on Aurelion architecture
aurelion-k-ck-instance  ← Chase-Key's personal Aurelion kernel instance
```

`aurelion-skills` sits between the projects and the AI. It is not an agent. It is not an engine. It is context made portable.

---

*Part of the z3rosl33p / AURELION Ecosystem*
*Built so the AI always knows where it is.*
