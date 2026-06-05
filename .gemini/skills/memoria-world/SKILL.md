---
name: memoria-world
version: 1.0.0
description: The Stonecrest world, the Darklight Chambers library, and the Memoria Engine — CK's creative universe that shapes the architecture of everything.
author: z3rosl33p
tags: [stonecrest, memoria, world-building, dnd, darklight-chambers, nexus-premium]
last_updated: 2026-03-22
---

# Memoria World Skill

## What This Is

Stonecrest is Chase-Key's D&D campaign world. It is also the **conceptual origin** of the entire Aurelion architecture. The Darklight Chambers — a 5-floor circular library inside Stonecrest — became the organizing metaphor for the AAAI knowledge engine. The Memoria Engine is the AI-powered implementation of this world as a persistent, living system.

**Location:** `memoria-engine/` — sibling project in your Personal Projects folder

---

## Stonecrest: The World

Stonecrest is an active D&D campaign world with persistent NPCs, faction dynamics, consequence tracking, and 30+ sessions of accumulated history. It is run by CK as Dungeon Master.

### The Darklight Chambers
The Darklight Chambers is a legendary circular library within Stonecrest — 5 floors of organized knowledge that serves as the real-world metaphor for CK's AAAI architecture:

```
Floor 5 — VISION VAULT       The highest floor. Long-term prophecy, destiny, world direction.
Floor 4 — STRATEGY WING      Frameworks, maps, faction plans, political models.
Floor 3 — RELATIONS ARCHIVE  NPCs, relationships, alliances, grudges.
Floor 2 — OPERATIONS LEDGER  Active quests, current events, recent sessions.
Floor 1 — FOUNDATION STONES  Immutable lore: creation myths, world laws, hard facts.
```

The 5-floor architecture used in CK's AAAI kernel is a direct translation of this structure into a professional knowledge management system.

---

## The Memoria Engine

**Memoria** is the AI-powered world engine built to manage Stonecrest.

### What It Does
- **NPC Consistency** — NPCs remember interactions across 30+ sessions
- **World Simulation** — The world evolves between sessions even when no one is playing
- **Smart Q&A** — Query the world, get in-character answers grounded in lore and session history
- **Consequence Tracking** — Player actions cascade realistically through faction dynamics
- **Memory Management** — Auto-journals character interactions, tracks relationships

### Technical Architecture
```
memoria-engine/
├── engine/           ← Core AI reasoning loop
├── agents.py         ← NPC agent behaviors
├── memory.py         ← Persistent memory storage
├── retrieval.py      ← Semantic retrieval of lore/events
├── llm_integration.py ← OpenAI integration
├── state_manager.py  ← World state persistence
├── lore_indexer.py   ← Lore ingestion and indexing
├── library_system.py ← The Darklight Chambers interface
├── characters/       ← NPC definitions
├── lore/             ← World lore documents
├── state/            ← Current world state
└── rules/            ← D&D rules as data
```

**Stack:** Python, OpenAI, ChromaDB (vector store), FastAPI, Fly.io deployment

### Relationship to Aurelion
Memoria Engine IS Aurelion Nexus Premium in prototype form. The ROADMAP for AURELION-ECO explicitly notes that `rell-engine` should "Remove AURELION-specific references (Stonecrest, Memoria, D&D world engine)" — confirming Memoria is the source from which rell-engine was extracted.

This means:
- `memoria-engine` = the showcase that proved the architecture works
- `aurelion-nexus-premium` = the productized, portable version of what memoria is doing
- `rell-engine` = the compliance-specific derivative

---

## Why This Matters for Development

When CK references "the library," "Stonecrest," "the chambers," or "Rell's world" — he is using his D&D world as **conceptual shorthand for architectural decisions**. Understanding Stonecrest helps understand why:

- Everything is organized on 5 floors (not 3, not 7 — 5)
- Knowledge is treated as a **living system** that evolves
- Memory is not just storage — it's the world's **continuity**
- The "engine" metaphor (things that run, persist, evolve) pervades all projects

---

## The talk_to_rell.py Interface

`memoria-engine/talk_to_rell.py` — This is the CLI for talking to the Stonecrest world AI. The name "Rell" here refers to a character or entity within Stonecrest, predating the RELL-ECO compliance product. The naming shares roots.

To run Memoria locally:
```bash
cd memoria-engine
python main.py cli
```
