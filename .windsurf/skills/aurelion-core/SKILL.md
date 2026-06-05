---
name: aurelion-core
version: 1.0.0
description: The Aurelion cognitive architecture — five modules that together form a complete autonomous agentic AI system.
author: z3rosl33p
tags: [aurelion, architecture, agentic, kernel, memory, nexus, advisor, agent]
last_updated: 2026-03-22
---

# Aurelion Core Skill

## What Aurelion Is

**AURELION** — Autonomous Universal Reasoning Engine with Long-term Intelligence, Operational Memory & Neural Nexus

Aurelion is a complete cognitive architecture for personal and organizational knowledge management. It is the **agentic model** from which all z3rosl33p products derive. RELL-ECO is built on Aurelion architecture. Memoria Engine is Aurelion Nexus Premium in prototype form.

**Location:** `aurelion-eco/` — sibling project in your Personal Projects folder

---

## The Five Modules

> **March 2026 status:** KERNEL, MEMORY, AGENT, ADVISOR are now extracted as pip-installable packages under `aurelion-eco/modules/`. NEXUS (nexus-premium) has been wired to use them. Install with `install_modules.ps1`.

### 1. KERNEL (`aurelion-kernel`)
**Package:** `pip install -e ./modules/kernel`
**Import:** `from aurelion_kernel import StateManager, ConfigLoader`
**What it does:**
- `StateManager` — generic JSON-based entity store + world state (load, save, update)
- `ConfigLoader` — reads `.env` + JSON config, merges with environment variables
**Status:** Extracted and installed in nexus-premium venv ✅

---

### 2. MEMORY (`aurelion-memory`)
**Package:** `pip install -e ./modules/memory`
**Import:** `from aurelion_memory import MemoryManager`
**What it does:**
- `MemoryManager` — append-only entity journals, named snapshots, timeline logs
- Generic: entity names are arbitrary strings; no world-specific code inside
**Status:** Extracted and installed in nexus-premium venv ✅

---

### 3. AGENT (`aurelion-agent`)
**Package:** `pip install -e ./modules/agent`
**Import:** `from aurelion_agent import BaseAgent, LLMProvider`
**What it does:**
- `LLMProvider` — wired connector for OpenAI, Anthropic Claude, Ollama (local)
- `BaseAgent` — abstract base class; subclass and implement `build_system_prompt()`
- Built-in: conversation history, context injection, `chat_loop()` CLI
**Status:** Extracted and installed in nexus-premium venv. `RellAgent` now extends `BaseAgent`. ✅

---

### 4. ADVISOR (`aurelion-advisor`)
**Package:** `pip install -e ./modules/advisor`
**Import:** `from aurelion_advisor import KnowledgeRetriever, TopicAdvisor`
**What it does:**
- `KnowledgeRetriever` — keyword search over a corpus of .md/.json files; plug into `build_context()`
- `TopicAdvisor` — assembles context from multiple retrievers with character budget
**Status:** Extracted and installed in nexus-premium venv ✅

---

### 5. NEXUS (`aurelion-nexus-premium`)
**Location:** `modules/nexus/aurelion-nexus-premium/`
**What it does:** Stonecrest world simulation — uses all 4 modules above. The working AI engine.
- `RellAgent` extends `BaseAgent` from aurelion-agent
- `StateManager`/`MemoryManager` available for import from kernel/memory modules
- Entry: `python main.py cli` (with Ollama running + llama3 pulled)
**Status:** Running. Wired to module ecosystem. ✅

---

### Install into any project
```powershell
# From project root, pointing at aurelion-eco
../../install_modules.ps1 -VenvPath .venv
```
Or one at a time:
```powershell
.venv\Scripts\pip install -e ../../modules/kernel
.venv\Scripts\pip install -e ../../modules/memory
.venv\Scripts\pip install -e ../../modules/agent
.venv\Scripts\pip install -e ../../modules/advisor
```---

## The 5-Floor Architecture (Darklight Chambers)

Inspired by Rell's circular library in Stonecrest. All knowledge in the Aurelion ecosystem is organized on 5 floors:

```
Floor 5: VISION      — Long-term goals, identity, strategic direction
Floor 4: STRATEGY    — Frameworks, methodologies, decision models  
Floor 3: RELATIONS   — People, orgs, teams, stakeholders
Floor 2: OPERATIONS  — Active projects, workflows, current work
Floor 1: FOUNDATION  — Core facts, hard data, non-negotiable truths
```

Every kernel file, every audit finding, every skill — maps to a floor.

---

## System Relationships

```
KERNEL  ──defines schema──►  MEMORY  ──stores data──►  NEXUS ──routes to──►  AGENT
   ▲                                                       │
   └──────────────────── ADVISOR ────────────────────────┘
```

- **KERNEL + MEMORY** = Knowledge base
- **NEXUS + AGENT** = Autonomous action layer
- **ADVISOR** = Strategic layer connecting knowledge to decisions
- **AAI-Complete** = All five, pre-wired

---

## How Aurelion Relates to Other Projects

| Project | Aurelion Relationship |
|---|---|
| `aurelion-k-ck-instance` | CK's personal KERNEL instance |
| `memoria-engine` | NEXUS Premium prototype (Stonecrest showcase) |
| `rell-eco` | Audit product built on Aurelion architecture patterns |
| `aurelion-skills` | Context scaffolding layer for bridging Aurelion into any project |
