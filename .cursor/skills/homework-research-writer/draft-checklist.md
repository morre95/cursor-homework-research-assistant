# Draft Checklist

Use this checklist for assignment intake, thesis selection, auto-draft confirmation, drafting, and final review.

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
2. Inspect previous feedback in `feedback/` if it exists and summarize applicable guidance.
3. Share brief research notes with source links.
4. Propose or refine a thesis based on the user's view and any relevant feedback.
5. Ask whether the user wants an automatic draft.
6. If yes, create an outline sized to the required length.
7. Draft concise prose that matches the class level, assignment format, and relevant feedback.
8. Check the result against length, citations, prompt coverage, restrictions, and feedback issues to avoid.
9. Save or update the homework markdown file in `homework/HW-x.md`.

For `1-2 pages`, target roughly 300-650 words unless the user or assignment gives a different word count. Keep the structure compact: introduction, 2-4 body paragraphs, and conclusion.

## Final Output Defaults

- Use clear headings only when appropriate for the assignment.
- End with a brief checklist showing how the answer satisfies the prompt and restrictions.
- Save the final homework record to `homework/HW-x.md`.
