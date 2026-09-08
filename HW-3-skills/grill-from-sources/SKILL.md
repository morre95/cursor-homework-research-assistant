---
name: grill-from-sources
description: A relentless interview that sharpens a plan or design against the repo, official docs, and other primary sources, then writes down the glossary and decisions as they crystallise. Use when the user wants to grill a design, pressure-test a plan, or refine terminology before building.
disable-model-invocation: true
---

# Grill From Sources

An interview, not a brainstorm. The job is to make the plan precise, find the contradictions, and leave behind better sources than you found.

You do **not** implement during this session unless the user explicitly asks to stop grilling and start building.

## 1. Gather sources first

Do not start questioning from a blank context. Collect, then grill.

Search in this order. Quote what you found. If a source is missing, say so; do not invent it.

1. **The user's plan** in this conversation (and any path they passed).
2. **Repo sources**: `README`, `AGENTS.md`, `CONTEXT.md`, `docs/`, ADRs, specs, tickets, OpenAPI/schema files, relevant tests.
3. **The code that would actually change**: current types, module seams, and the happy-path callers.
4. **Official third-party sources** when the plan depends on a library, framework, SDK, API, or cloud service: current docs via Context7 (`resolve-library-id` then `query-docs`), otherwise first-party docs. Not blog roundups.
5. **Constraints already decided**: existing ADRs, lint/CI rules, compatibility promises.

If sources disagree, that disagreement is the first interview topic.

Details: [interview.md](interview.md).

## 2. Interview without mercy

Work through the plan in small pieces. One fuzzy claim at a time. Do not accept "we'll figure it out later" for something that would change the shape.

Pressure every claim with:

- **Term**: is this the project's word, or a new one colliding with an old one?
- **Source**: which file, doc, or API page supports this? If none, is it a new decision?
- **Scenario**: a concrete case that should work, one that should be illegal, one at the boundary.
- **Failure**: what happens when the dependency is down, the input is partial, or the user retries?
- **Undo**: how expensive is it to reverse this later?

When the user uses a vague or overloaded word, stop and pin a canonical term. When they describe behaviour the code does not do, show the contradiction and ask which side is true.

Keep asking until the remaining unknowns are named and bounded, not until the user is tired. If they want to stop, summarise what is still unresolved and stop.

## 3. Write sources as you go

Capture the moment a term or decision crystallises. Do not batch it for "later".

**Glossary** (`CONTEXT.md` at the repo root, or the nearest existing domain doc): terms and relationships only. No implementation details, no file paths, no framework names. Create the file lazily, on the first resolved term.

**Decisions**: offer an ADR under `docs/adr/` (or the repo's existing ADR folder) only when all three are true:

1. Hard to reverse
2. Surprising without context
3. A real trade-off with rejected alternatives

Skip the ADR if any of the three is missing. A one-line note in the session summary is enough.

ADR shape:

```markdown
# <number>. <title>

* Status: accepted
* Date: <ISO date>

## Context
## Decision
## Consequences
## Alternatives considered
```

## 4. Close the session

End with:

1. **Sharpened plan** — what we are actually doing, in the project's language
2. **Decisions made** — and where they were written
3. **Open questions** — still unresolved, with why they matter
4. **Suggested next skill** — `to-tickets`, `prototype`, `tdd`, or `codebase-design`, depending on what is still shaky

Do not start implementation from this closeout unless the user asks.
