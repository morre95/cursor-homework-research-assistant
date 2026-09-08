# Logic prototype

One self-contained HTML file. Anyone can open it and drive a state model with buttons. Use this when the question is **business logic, transitions, or data shape** — things that look fine on paper until you push real cases through them.

If the question is visual, use [ui.md](ui.md) instead.

## Process

### 1. State the question

One visible paragraph at the top of the demo, not only a comment: which model, which question. A prototype that answers the wrong question is waste.

### 2. Isolate liftable logic

Put the actual logic in one `<script>` block as a small pure module that could later move into the real codebase. The page around it is disposable; this module is not.

Pick the shape that matches the question:

- Reducer `(state, action) => state` for discrete events and one state value
- Explicit state machine when legal actions depend on the current state
- Pure functions over a plain data type when there is no "current" state
- A small object with a clear method surface when it genuinely owns ongoing state

Keep it pure: no DOM, no `document`, no handlers reaching inside. The page calls in. Nothing flows the other way.

### 3. Build the file

Plain HTML/CSS/JS. No framework, bundler, or server. Labels in **domain language**, not reducer-speak.

Top to bottom:

1. Title and the question from step 1
2. Current state as labelled fields (not a raw JSON dump), re-rendered after every click, with a short "what just changed" hint when it helps
3. Free-play: one button per action, always available, any order
4. Guided walkthroughs as tabs: happy path, an awkward edge, an illegal attempt. Each step is a real button. Starting a walkthrough resets to a known initial state

Clean typography, one accent colour, no animation competing with the state.

### 4. Hand over, then capture

Let them click. The useful moments are "that should not be possible" and "I thought X would be different" — bugs in the *idea*. Add actions or scenarios if they ask.

When the question is answered: lift the validated module into real code; keep the HTML shell on the throwaway branch as described in [SKILL.md](SKILL.md).

## Anti-patterns

- Tests on a prototype
- Real database
- Generalising for a future that is not the question
- Logic that touches the DOM (no longer liftable)
- A framework, bundler, or dev server
- Shipping the HTML shell to production
