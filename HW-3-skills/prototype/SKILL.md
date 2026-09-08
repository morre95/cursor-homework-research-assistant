---
name: prototype
description: Build throwaway prototype code that answers a design question. Use when the user wants to feel whether a state model or piece of logic is right, or explore what a UI should look like before committing.
---

# Prototype

A prototype is **throwaway code that answers one question**. The question picks the shape.

## Pick a branch

From the user's prompt, nearby code, or a short question if they are around:

- **"Does this logic / state model feel right?"** → [logic.md](logic.md). One shareable HTML file a non-developer can click through.
- **"What should this look like?"** → [ui.md](ui.md). Several structurally different UI variants, switchable on one route.

If the question is ambiguous and the user is away, default from context (backend module → logic; page/component → UI) and state the assumption at the top of the artifact.

Getting the branch wrong wastes the prototype. Do not mix them.

## Rules for both

1. **Marked throwaway, placed near the real home.** Sit it next to the module or page it is for, with `prototype` in the name or path. Do not invent a new top-level tree. For throwaway routes, follow the project's existing routing convention.
2. **Trivial to run.** Logic demo: double-click one HTML file. UI: one existing task-runner command (`pnpm <name>`, `python <path>`, …).
3. **No persistence by default.** Memory only. If the question *is* persistence, use a scratch DB or a file named so it is obvious it can be wiped.
4. **Skip polish.** No tests, no extra error handling, no abstractions. Learn something fast.
5. **Surface the state.** After every action (logic) or variant switch (UI), show the full relevant state.
6. **Capture, then leave main clean.** Fold the validated decision into real code. Keep the prototype itself on a throwaway branch (out of main) and point the implementation ticket at that branch. Write the question and the verdict in the ticket or commit. Main keeps the decision, not the playground.

## Aftercare

When the question is answered, say the verdict in one paragraph: what we learned, what we are keeping, what we are throwing away. Then stop. Implementation of the real thing is a different session (`tdd`, `codebase-design`, or ordinary coding).
