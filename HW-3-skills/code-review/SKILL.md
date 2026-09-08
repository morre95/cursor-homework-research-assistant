---
name: code-review
description: Review the diff since a fixed point along two separate axes — Standards (repo conventions and design smells) and Intent (does the change match the spec, issue, or stated goal). Use when reviewing a branch, PR, WIP diff, or when the user asks to review since a commit, tag, or base branch.
---

# Code Review

Review `HEAD` against a fixed point the user names (commit, branch, tag, merge-base). Score the change on **two axes** and keep the reports apart:

- **Standards**: does the code match this repo's documented conventions, plus a light design-smell baseline?
- **Intent**: does the code actually deliver what the spec, ticket, or stated goal asked for?

A change can pass one axis and fail the other. Do not merge the findings into one ranked list. That ranking is how a pretty-but-wrong patch hides, or how a correct-but-messy patch gets waved through.

## Process

### 1. Pin the baseline

Use the fixed point the user gave. If they did not give one, ask.

Confirm it resolves and the diff is non-empty before any deeper work:

```bash
git rev-parse <fixed-point>
git diff <fixed-point>...HEAD
git log <fixed-point>..HEAD --oneline
```

Three-dot diff compares against the merge-base. A bad ref or empty diff stops here.

### 2. Find the intent source

Look in this order, then stop at the first real source:

1. Issue/ticket IDs in the commit messages, fetched with whatever tracker the repo already uses (`gh`, Linear, Jira, local markdown under `tickets/` or `.scratch/`).
2. A path the user passed.
3. A spec under `docs/`, `specs/`, `tickets/`, or similar that matches the branch or feature name.
4. The user's stated goal in this conversation.

If nothing exists, ask. If they say there is no spec, skip the Intent axis and say so in the report.

### 3. Find the standards sources

Read whatever the repo already uses to describe how code should look: `CONTRIBUTING.md`, `CODING_STANDARDS.md`, `AGENTS.md`, linter/formatter config, and nearby module docs.

Repo rules always win over the smell baseline below. Skip anything the project's tooling already enforces (formatter, typecheck, lint). Smell hits are **judgement calls**, never hard blockers by themselves.

Smell baseline (name it, quote the hunk, suggest the fix):

- **Opaque name**: identifier does not say what it holds or does → rename, or redesign if no honest name exists.
- **Copy-paste shape**: same logic appears in more than one hunk → extract the shared shape.
- **Feature envy**: a function lives off another object's data more than its own → move it onto that data.
- **Data clump**: the same few values travel together → they want a type.
- **Primitive stand-in**: a string/number is really a domain concept → give it a small type.
- **Repeated branch-on-type**: the same `switch`/`if` cascade on the same kind of value → polymorphism or one shared map.
- **Shotgun edit**: one idea required scattered edits across many files → gather what changes together.
- **Kitchen-sink module**: one file changed for several unrelated reasons → split by reason.
- **Speculative hook**: abstraction added for a need the spec does not have → delete until a real caller appears.
- **Long reach**: `a.b().c().d()` the caller should not know about → hide the walk.
- **Pass-through wrapper**: a type that mostly delegates → call the real target.
- **Hollow inheritance**: subclass ignores most of what it inherits → compose instead.

### 4. Run the two axes in parallel

If sub-agents are available, spawn both at once so they do not pollute each other. Otherwise run them sequentially with a fresh brief each time.

**Standards brief** must include: the diff command, commit list, paths of standards files, and the smell baseline above pasted in full. Ask for: (a) documented-standard breaches with file + rule; (b) baseline smells with name + hunk quote. Hard vs judgement. Skip tooling-enforced rules. Under 400 words.

**Intent brief** must include: the diff command, commit list, and the spec/goal text. Ask for: (a) asked-for behaviour that is missing or partial; (b) behaviour nobody asked for; (c) behaviour that looks implemented but looks wrong. Quote the spec/goal line for each finding. Under 400 words.

### 5. Report

Present the two write-ups under `## Standards` and `## Intent`. Clean lightly; do not rerank across axes.

Close with one line per axis: finding count, and the worst issue *inside that axis*. Do not pick a single winner across axes.
