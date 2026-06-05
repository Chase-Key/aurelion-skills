# New Skill Template

Copy this folder to `skills/your-skill-name/` and fill in the sections below.

---

## SKILL.md Template

```markdown
---
name: your-skill-name
version: 1.0.0
description: One sentence description of what this skill provides.
author: z3rosl33p
tags: [tag1, tag2, tag3]
---

# Your Skill Title

## What This Is

[One paragraph. Be honest. Describe what loading this skill tells an AI about this domain.]

---

## [Section 1: Primary Context]

[The most important information about this domain. File paths, commands, current status.]

---

## [Section 2: Architecture / Structure]

[How is this domain organized? What are the key components?]

---

## [Section 3: How to Use / Operate]

[Commands, workflows, protocols specific to this domain.]

---

## [Section 4: Relationships]

[How does this domain connect to other parts of the ecosystem?]

---

## Status Note

[Be explicit about what's built vs. planned. Use (Planned) markers clearly.]
```

---

## skill-manifest.json Template

```json
{
  "name": "your-skill-name",
  "version": "1.0.0",
  "description": "One sentence description.",
  "author": "z3rosl33p",
  "license": "private",
  "tags": ["tag1", "tag2"],
  "skillFile": "SKILL.md",
  "category": "domain",
  "loadPriority": 3,
  "dependsOn": ["ck-identity"],
  "notes": "When should an AI load this skill?"
}
```

---

## Checklist Before Submitting a New Skill

- [ ] Folder name is lowercase, kebab-case, matches `name` in manifest
- [ ] `SKILL.md` front matter is complete
- [ ] All sections describe what IS (not aspirational)
- [ ] File paths are absolute and accurate
- [ ] Planned items are marked `(Planned)` or `(Roadmap)`
- [ ] `skill-manifest.json` is valid JSON
- [ ] Skill is registered in `SKILLS_REGISTRY.md`
