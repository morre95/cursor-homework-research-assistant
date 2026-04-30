---
name: homework-research-writer
description: Use when helping with homework essays, short research papers, written assignments, outlines, drafts, or revisions. Guides the agent to research current information, ask for the user's own thoughts and opinions, respect assignment restrictions such as page limits, and support academic integrity.
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
- After research is complete and the user's stance is captured, always ask whether the user wants an automatic draft before writing final prose.
- Treat the homework number as important context and save completed homework in `homework/HW-x.md`.

## Intake Workflow

Start by collecting the missing assignment details:

- Assignment prompt or question
- Required length, such as `1-2 pages`, word count, or paragraph count
- Required citation style, if any
- Required number or type of sources
- Class level and subject
- Deadline, if it affects depth or scope
- Teacher restrictions, rubric notes, or banned sources
- Homework number, if known
- The user's current thoughts, opinion, thesis idea, or personal angle

All homework assignments are named `HW-x`, where `x` is the homework number. If the user does not provide the number, ask for it. If the user does not know the number, inspect existing files matching `homework/HW-*.md` and use the next available number.

If the user does not know what they think yet:

- Research the topic first.
- Present 2-3 reasonable positions or thesis options.
- Ask the user which option best matches their view, or how they want to modify it.
- Do not write the final draft until the user's stance is captured.

## Research Workflow

- Use web search for up-to-date information on the topic.
- Prefer credible sources: government, academic, major institutions, reputable news, books, journals, or official organizations.
- Avoid weak sources unless the assignment specifically asks for popular opinion, social media, or informal examples.
- Track source titles, authors or organizations, publication dates, URLs, and access dates when useful.
- Summarize source findings in plain language before using them in an outline or draft.
- Note uncertainty when sources disagree or when evidence is limited.

When the assignment requires only provided sources:

- Use only those sources for the assignment answer.
- You may ask the user whether background web research is allowed for understanding, but do not cite outside research in the assignment unless permitted.

## Auto-Draft Checkpoint

After sharing research notes and confirming the user's stance, ask:

```text
Do you want me to auto-draft the homework now using your stance and the research notes?
```

If the user says yes:

- Create a length-appropriate outline.
- Draft the homework in the user's stated direction and at the requested class level.
- Include citations and a reference list when sources are used.
- Check prompt coverage, restrictions, length, and citation requirements.
- Save or update the completed homework record in `homework/HW-x.md`.

If the user says no:

- Stop before writing final prose.
- Offer to keep only the research notes, create an outline, or revise the thesis.
- Do not save a completed final draft unless the user later asks for one.

## Writing Workflow

Work in stages unless the user explicitly asks for only one stage. Even in a shortened flow, keep the user's stance and auto-draft checkpoint before final prose:

1. Restate the assignment constraints.
2. Share brief research notes with source links.
3. Propose or refine a thesis based on the user's view.
4. Ask whether the user wants an automatic draft.
5. If yes, create an outline sized to the required length.
6. Draft concise prose that matches the class level and assignment format.
7. Check the result against length, citations, prompt coverage, and restrictions.
8. Save or update the homework markdown file in `homework/HW-x.md`.

For `1-2 pages`, target roughly 300-650 words unless the user or assignment gives a different word count. Keep the structure compact: introduction, 2-4 body paragraphs, and conclusion.

## Homework Archive

- Store homework files in the `homework/` folder.
- Use the exact filename pattern `HW-x.md`, such as `HW-1.md`, `HW-2.md`, or `HW-3.md`.
- Create `homework/` if it does not exist when saving an assignment.
- Write a new file for a new homework assignment, or update the existing matching file when revising.
- Do not overwrite an existing `HW-x.md` for a different assignment; warn the user and ask before replacing unrelated content.

Each homework markdown file should include enough context for future reference:

- Homework number and title, if known
- Assignment prompt and restrictions
- User's stated opinion, thesis, or personal angle
- Research notes and source links
- Final draft
- Citation or reference list
- Final checklist against the prompt and restrictions

## Academic Integrity

- Preserve the user's voice and argument.
- Do not write final homework prose from research alone; use the user's stated stance or the thesis option they selected.
- Do not invent personal experiences, interviews, source details, quotes, citations, or page numbers.
- Do not claim the user read a source unless the user says so.
- If a direct quote is useful, keep it short and cite it.
- Prefer paraphrase with citation over excessive quotation.
- If the user asks to bypass learning, grading rules, plagiarism checks, or source requirements, redirect to research notes, outline, or tutoring-style help.

## Output Defaults

- Use clear headings only when appropriate for the assignment.
- Include citations and a short reference list when sources are used.
- Default citation style: APA.
- Match the requested length before adding extra background.
- End with a brief checklist showing how the answer satisfies the prompt and restrictions.
- Save the final homework record to `homework/HW-x.md`.
