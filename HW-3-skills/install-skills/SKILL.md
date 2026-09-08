---
name: install-skills
description: Copy this engineering-skills catalog into a target repository's .cursor/skills directory so the agent can use them immediately. Use when the user wants to install, drop in, or add these skills to another repo or to the current project.
disable-model-invocation: true
---

# Install Skills

Drop this catalog into a repo's `.cursor/skills/` by copying folders. There is no setup script, no issue-tracker scaffolding, and no extra config files required. After the copy, Cursor can load each skill from its `SKILL.md`.

## Catalog root

This skill lives inside the catalog. Treat the **parent of this skill folder** as the catalog root: a directory whose children are skill folders (`code-review`, `tdd`, `init-repo`, …), each containing `SKILL.md`.

Typical locations:

- `HW-3-skills/` in the catalog repo
- `.cursor/skills/` after a previous install

If you cannot see sibling skill folders, ask the user for the catalog path.

## Process

### 1. Confirm target

Ask, with a recommended default:

1. **Target repo** — current workspace, or an absolute path they name
2. **Which skills** — all of them (recommended), or a subset they list

Destination is always:

```text
<target>/.cursor/skills/<skill-name>/
```

Create `.cursor/skills/` if it is missing.

### 2. Plan the copy

List skill folders at the catalog root (directories that contain `SKILL.md`). Include `install-skills` and `init-repo` unless the user asked to omit them. Do not copy `README.md` as a skill; it is catalog documentation. You may copy it to `<target>/.cursor/skills/README.md` only if the user wants it.

For each skill folder:

- **Missing in target** → copy
- **Same name already exists** → do **not** overwrite. Show what is there and ask: skip, overwrite, or write to a different name

Never copy into `~/.cursor/skills-cursor/` (reserved). Never delete target skills the catalog does not contain.

### 3. Copy

Copy whole skill directories (every file under each skill). Preserve names. After copying, list `<target>/.cursor/skills/` and confirm each expected `SKILL.md` exists.

Do not write `docs/agents/`, issue-tracker files, triage labels, or `CONTEXT.md`. This catalog is meant to work with zero extra layout.

Optional, only if the user wants a pointer: add a short "Engineering skills" bullet list to an existing `AGENTS.md` or `README.md`. Do not create those files just for the install. Do not create `CLAUDE.md` unless they ask.

### 4. Done

Report:

- Target path
- Skills copied
- Skills skipped (already present)
- How to invoke one, e.g. `Use the tdd skill to add X.`
