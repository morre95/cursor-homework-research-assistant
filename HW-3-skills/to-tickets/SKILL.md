---
name: to-tickets
description: Break a plan, spec, or the current conversation into tracer-bullet tickets with explicit blockers. Writes local markdown by default, or native issues when the repo already uses a tracker. Use when the user wants a plan turned into tickets, issues, or a sequenced backlog.
disable-model-invocation: true
---

# To Tickets

Turn a plan, spec, or conversation into **tickets**: narrow vertical slices, each declaring what blocks it. A ticket with no blockers can start immediately.

Do not implement the tickets in this session unless the user asks.

## 1. Gather context

Use what is already in the conversation. If the user passed a spec path, issue URL, or ticket id, read it fully (body and comments).

Optional: skim the code so titles use the project's language and you can spot **prefactor** work ("make the change easy, then make the easy change"). If a glossary or ADRs exist in the area, use those words.

## 2. Draft vertical slices

Each slice is a **tracer bullet**:

- A narrow but complete path through the layers that matter (data, API, UI, tests) — not one horizontal layer
- Demoable or verifiable on its own
- Small enough for one fresh agent context window
- Prefactors first, as their own tickets, blocking the slices that need them

Give each ticket **blocking edges**: the tickets that must finish before it can start.

**Wide refactors are the exception.** A mechanical change whose blast radius fans across the tree (rename a column, retype a shared symbol) cannot land as one green tracer bullet. Sequence **expand → migrate in batches → contract**. Expand adds the new form beside the old. Each migrate batch is its own ticket, blocked by expand, sized so CI stays green. Contract deletes the old form, blocked by every migrate batch. If even the batches cannot stay green alone, they share an integration branch that all block a final verify ticket.

## 3. Quiz the user

Show a numbered list. For each ticket:

- **Title**
- **Blocked by** (or "none")
- **What it delivers** — end-to-end behaviour from the user's point of view, not a layer checklist

Ask: granularity (too coarse / too fine)? Are the blocking edges real gates? Merge or split anything? Iterate until they approve.

## 4. Publish

Default: **local markdown**, one file per ticket.

```text
tickets/<feature-slug>/<NN>-<slug>.md
```

Number from `01` in dependency order (blockers first). Never one combined file. Use [ticket-template.md](ticket-template.md).

If the repo already tracks work on GitHub/GitLab/Linear/Jira and the user wants that, publish there instead — one issue per ticket, blockers first, native blocking/sub-issue links when the platform has them. Do not close or edit a parent issue beyond linking.

In either form, avoid file paths and code dumps; they rot. Exception: a prototype snippet that encodes a decision more precisely than prose (state machine, reducer, schema). Trim to the decision, note that it came from a prototype.

Work the **frontier**: tickets whose blockers are done. A linear chain is top to bottom.
