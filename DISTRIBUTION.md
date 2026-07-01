# AURELION Skills — Distribution Log

> Tracking all distribution channels, submissions, and status for `Chase-Key/aurelion-skills`.

---

## Channel Status

| Channel | Status | Notes |
|---|---|---|
| **GitHub Topics** | ✅ Active | `agent-skills`, `ai-skills`, `cognitive-architecture`, `open-plugins`, `aurelion`, + 7 more |
| **awesome-agent-skills** | ✅ PR #647 submitted | Context Engineering section — [link](https://github.com/VoltAgent/awesome-agent-skills/pull/647) |
| **Open Plugins spec** | ✅ Compliant | `.plugin/plugin.json` present — Cursor Directory auto-detects |
| **Multi-editor paths** | ✅ All wired | See "Compatibility" section below |
| **Cursor Directory** | ⏳ Pending manual | Web form: [cursor.directory/plugins/new](https://cursor.directory/plugins/new) |
| **awesome-claude-code** | ⏳ Waiting | Repo reorganizing — submit when stable |
| **HuggingFace dataset** | ❌ Not started | Next: `huggingface.co/datasets/chase-key/aurelion-skills` |
| **PyPI (pip modules)** | ❌ Not started | Separate workstream — see `aurelion-eco/modules/` |
| **Anthropic PR #444** | 🚫 Stale | Fork is `Chase-Key/skills` — 4+ months no response |

---

## Editor Compatibility

The AURELION skill suite auto-discovers in all major AI coding agents:

| Agent | Path |
|---|---|
| Claude Code | `.claude/skills/` (via copilot-instructions) + `skills/` (canonical) |
| Cursor | `.cursor/skills/` |
| GitHub Copilot | `.github/skills/` |
| Gemini CLI | `.gemini/skills/` |
| Codex (OpenAI) | `.agents/skills/` |
| Windsurf / Codeium | `.windsurf/skills/` |
| Any Open Plugins agent | `skills/*/SKILL.md` via `.plugin/plugin.json` |

---

## Skills in This Repo

| Skill | Description |
|---|---|
| `aurelion-core` | 5-floor cognitive architecture — Foundation → Vision |
| `ck-identity` | CK's personal identity and collaboration protocol |
| `memoria-world` | Stonecrest D&D world AI context and NPC memory |
| `rell-domain` | RELL compliance domain knowledge |
| `workload-domain` | LexisNexis / TQA analyst workflows |

---

## Distribution History

### June 5, 2026
- Created `Chase-Key/aurelion-skills` as standalone public GitHub repo
- Added Open Plugins spec manifest (`.plugin/plugin.json`)
- Added GitHub Topics to both `aurelion-skills` and `Chase-Key/skills` (12 topics each)
- Added multi-editor skill paths for Windsurf, Cursor, Copilot, Gemini CLI, Codex
- Submitted PR #647 to `VoltAgent/awesome-agent-skills` — Context Engineering section

### February 2026
- Submitted PR #444 to `anthropics/skills` with Anthropic-format skills
  (aurelion-kernel, aurelion-memory, aurelion-agent, aurelion-advisor)
- Status: No merge, no response — abandoned as distribution path

---

## Next Actions

1. **Cursor Directory** (CK manual) — Go to `cursor.directory/plugins/new`, paste this repo URL. Takes 2 minutes. The `.plugin/plugin.json` manifest handles the rest.

2. **HuggingFace** — Create dataset at `huggingface.co/datasets/chase-key/aurelion-skills` and push the skill markdown files.

3. **awesome-claude-code** — Watch `hesreallyhim/awesome-claude-code` for reorganization completion. Submit when stable.

4. **PyPI** — Publish `aurelion-kernel`, `aurelion-memory`, `aurelion-agent`, `aurelion-advisor` as pip packages from `aurelion-eco/modules/`. Separate workstream.
