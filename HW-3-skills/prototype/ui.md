# UI prototype

Several **structurally different** UI variants on one route, switched from a floating bar. The user flips, picks, or steals pieces, then the rest is thrown away.

If the question is logic/state, use [logic.md](logic.md) instead.

## Prefer hosting on a real page

Variants are easier to judge against the real header, sidebar, density, and data.

- **A (default):** the route already exists, or the new UI would naturally live inside an existing page. Gate rendering with `?variant=`. Keep existing data loading, params, and auth. Only the rendered subtree swaps.
- **B (last resort):** genuinely no host page (new top-level surface). Add a throwaway route using the project's existing routing convention, with `prototype` in the path or filename. Same `?variant=` pattern.

Do not invent a parallel app just to mock a card.

## Process

### 1. State the question and N

Default to **3** variants. Cap at 5.

One line in a comment or nearby note:

> Three variants of the settings page, `?variant=` on the existing `/settings` route.

### 2. Draft variants that disagree

Each variant must differ in layout, information hierarchy, or primary action — not only colour or copy. If two come out as the same card grid, redo one with an explicit constraint ("no card grid").

Use the project's styling system. Export clear names (`VariantA`, …). Sharing a header is fine. Sharing a layout defeats the point.

### 3. Wire a switcher

Read `variant` from the search param (default `A`). Render that variant plus a shared floating bar:

- Fixed bottom-centre, visually *not* part of the design (high-contrast pill)
- Previous / current label / next, wrapping
- Updates the URL via the framework router so the variant is shareable and reload-stable
- Arrow keys cycle, but not while focus is in an input, textarea, or `contenteditable`
- Hidden in production builds (`NODE_ENV !== 'production'` or equivalent)

Keep data fetching above the switcher on an existing page. Do not wire variants to real mutations; stub writes. The question is how it looks, not whether the backend works.

### 4. Hand over, then fold the winner

Give them the URL and the `?variant=` keys. Typical useful feedback: "header from B, sidebar from C".

When a winner exists: rewrite it properly into the real page (prototype code has no tests and thin errors). Drop losers and the switcher from main. Keep the full set on the throwaway branch as in [SKILL.md](SKILL.md). For sub-shape B, promote the winner to a real route and delete the prototype route from main.
