# Skill Schema

Every skill in the `aurelion-skills` system follows this structure.

---

## Required Files

```
skills/your-skill-name/
├── SKILL.md           ← Required. The skill content.
└── skill-manifest.json ← Required. Metadata and load instructions.
```

---

## SKILL.md Front Matter

```yaml
---
name: skill-name           # Lowercase, kebab-case
version: 1.0.0             # Semantic versioning
description: One sentence  # What this skill provides
author: z3rosl33p          # Usually this
tags: [tag1, tag2]         # Searchable labels
---
```

## SKILL.md Structure

A skill document should contain:

1. **What this is** — One paragraph of honest description. What does loading this skill tell the AI?
2. **Context sections** — Organized information the AI needs. Use headings.
3. **How to use** — Any operational notes, commands, or protocols the AI should follow
4. **Relationships** — How this skill connects to other parts of the ecosystem

### Writing Principles

- **Describe what IS** — Not what's planned. Mark planned items clearly with `(Planned)` or `(Roadmap)`.
- **Be specific** — Include actual file paths, actual commands, actual status.
- **Think like a context window** — This gets loaded into an AI session. Write for that constraint.
- **Update often** — A stale skill is worse than no skill.

---

## skill-manifest.json Schema

```json
{
  "name": "skill-name",
  "version": "1.0.0",
  "description": "What this skill provides in one sentence.",
  "author": "z3rosl33p",
  "license": "private | MIT | BSL",
  "tags": ["array", "of", "strings"],
  "skillFile": "SKILL.md",
  "category": "identity | architecture | world | domain | tooling",
  "loadPriority": 1,
  "dependsOn": ["other-skill-name"],
  "notes": "Any special instructions for when/how to load this skill."
}
```

### Field Definitions

| Field | Required | Description |
|---|---|---|
| `name` | Yes | Must match folder name |
| `version` | Yes | Semantic version |
| `description` | Yes | One-sentence summary |
| `author` | Yes | Creator handle |
| `license` | Yes | Governs reuse |
| `tags` | Yes | Minimum 2 |
| `skillFile` | Yes | Always `SKILL.md` |
| `category` | Yes | One of the five categories |
| `loadPriority` | Yes | 1 (first) to 5 (last). Lower numbers load first. |
| `dependsOn` | No | Other skills that should be loaded before this one |
| `notes` | No | Human-readable guidance on when to use this skill |

---

## Load Order Convention

Skills should be loaded in priority order. When composing a context for a project:

1. **Priority 1:** `ck-identity` — Always first. Sets the frame.
2. **Priority 2:** `aurelion-core` — The architectural foundation.
3. **Priority 3:** Domain/world skills — `rell-domain`, `memoria-world`, etc.
4. **Priority 4+:** Project-specific or task-specific skills.
