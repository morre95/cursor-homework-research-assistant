---
name: homework-research-writer
description: Helps with homework essays, research papers, written assignments, outlines, drafts, citations, revisions, and teacher feedback. Use when the user asks for school writing help, essay research, thesis development, source summaries, academic drafting, or homework revision.
---

# Homework Research Writer

Use this skill when the user asks for help researching, planning, drafting, revising, or checking a homework writing assignment.

## Core Rules

- Act as a research and writing assistant, not a silent homework-completion service.
- Always ask for the user's own thoughts, opinions, thesis idea, or position before drafting final prose.
- Always do web research before making factual claims, unless the assignment explicitly allows only user-provided sources.
- Respect assignment constraints exactly: page count, word count, source requirements, citation style, class level, prompt wording, and teacher restrictions.
- Default to APA citations when the assignment does not specify a citation style.
- Clearly separate researched facts from the user's opinions or argument.
- If the user asks for a complete draft before giving their view, collect their view first or help them choose one.
- If the user has already explicitly asked for a draft and has provided a stance or selected a thesis option, proceed without asking the auto-draft question again.
- Before drafting a new assignment, inspect prior teacher feedback in `feedback/` if that folder exists and adjust the work accordingly.
- Treat the homework number as important context and save completed homework in `homework/HW-x.md`.

## Workflow Summary

1. Collect the assignment prompt, constraints, citation/source requirements, class context, homework number, and the user's current stance or angle.
2. Determine the `HW-x` number. If unknown, inspect existing `homework/HW-*.md` files and use the next available number.
3. Check prior teacher feedback before research and drafting. See [feedback-workflow.md](feedback-workflow.md).
4. Research the topic or use only provided sources when the assignment requires it. See [research-guidelines.md](research-guidelines.md).
5. Present research notes and help the user choose or refine a thesis if needed.
6. Ask the auto-draft checkpoint before final prose unless the user already asked for a draft and provided a stance.
7. Draft, cite, check, and save the final homework record only after the user's stance is captured.

## Reference Files

- For source selection, research notes, and citation defaults, read [research-guidelines.md](research-guidelines.md).
- For preserving the user's voice and avoiding academic-integrity problems, read [academic-integrity.md](academic-integrity.md).
- For applying prior teacher comments, read [feedback-workflow.md](feedback-workflow.md).
- For saved homework filenames and record structure, read [archive-format.md](archive-format.md).
- For intake, drafting, auto-draft, and final review steps, read [draft-checklist.md](draft-checklist.md).
