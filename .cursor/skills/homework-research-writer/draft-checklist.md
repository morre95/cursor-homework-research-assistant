# Draft Checklist

Use this checklist for assignment intake, opinion capture, thesis selection, draft confirmation, drafting, and final review.

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
- The user's current thoughts, opinion, thesis idea, or personal angle for the assignment

All homework assignments are named `HW-x`, where `x` is the homework number. If the user does not provide the number, ask for it. If the user does not know the number, inspect existing files matching `homework/HW-*.md` and use the next available number.

## Opinion Intake

Before writing final prose, explicitly capture the user's own view. Ask concise questions such as:

```text
What do you personally think about this topic?
Which side or explanation do you lean toward?
Is there a personal example, concern, or angle you want included?
Do you want me to suggest 2-3 possible thesis options for you to choose from?
```

Use one of these paths:

- If the user already gave a clear stance, briefly restate it and ask for correction only if it is ambiguous.
- If the user hinted at a direction, ask one targeted follow-up to turn it into a usable thesis or angle.
- If the user does not know what they think, research first, present 2-3 reasonable thesis options, and ask which best matches their view or how they want to modify it.
- If the user asks for a complete draft before giving a view, pause drafting and collect their view or have them choose a thesis option.

Do not write the final draft until the user's stance is captured. Research notes, source summaries, tutoring, and outlines are allowed before this point.

## Draft Gate

After sharing research notes and confirming the user's stance, ask a short draft confirmation unless the user has already explicitly asked for a draft with that captured stance:

```text
Do you want me to draft the homework now using your stance and the research notes?
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

Work in stages unless the user explicitly asks for only one stage. Even in a shortened flow, keep the opinion intake and draft gate before final prose:

1. Restate the assignment constraints.
2. Inspect previous feedback in `feedback/` if it exists and summarize applicable guidance.
3. Share brief research notes with source links.
4. Propose or refine a thesis based on the user's view and any relevant feedback.
5. Confirm the user's stance and ask whether to draft if needed.
6. If yes, create an outline sized to the required length.
7. Draft concise prose that matches the class level, assignment format, and relevant feedback.
8. Check the result against length, citations, prompt coverage, restrictions, and feedback issues to avoid.
9. Save or update the homework markdown file in `homework/HW-x.md`.

For `1-2 pages`, target roughly 300-650 words unless the user or assignment gives a different word count. Keep the structure compact: introduction, 2-4 body paragraphs, and conclusion.

## Final Output Defaults

- Use clear headings only when appropriate for the assignment.
- End with a brief checklist showing how the answer satisfies the prompt and restrictions.
- Save the final homework record to `homework/HW-x.md`.
