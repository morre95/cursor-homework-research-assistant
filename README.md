# cursorHomeworkSetup

This repo contains a Cursor skill for homework research and writing support.

## Skill Location

The skill is stored here:

```text
.cursor/skills/homework-research-writer/SKILL.md
```

Cursor should discover the skill automatically when this repo is open.

## How To Use

Open this repo in Cursor and ask Agent for homework help, for example:

```text
Use the homework research writer skill to help me with HW-X.
The assignment is 1-2 pages about climate change and farming.
```

The skill is designed to:

- Ask for the assignment prompt, length, citation style, class level, and restrictions.
- Ask for your own thoughts, opinion, or thesis before writing the final draft.
- Use web research so factual information is up to date.
- Default to APA citations when the assignment does not specify a style.
- Respect page or word limits such as `1-2 pages`.
- Save completed homework for future reference.

## Homework Files

All homework files should be saved in:

```text
homework/
```

Use this filename format:

```text
HW-x.md
```

Examples:

```text
homework/HW-1.md
homework/HW-2.md
homework/HW-3.md
```

If you do not know the homework number, ask Cursor to inspect existing `homework/HW-*.md` files and choose the next available number.

Each homework file should include the prompt, restrictions, your opinion or thesis, research notes, source links, final draft, citations, and a checklist.
