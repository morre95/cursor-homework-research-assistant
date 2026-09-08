# Interview moves

Use these during [SKILL.md](SKILL.md) step 2. Mix them; do not run them as a script the user has to sit through.

## Pin the words

- "You said *account*. In this repo that is the billing customer. Do you mean that, or the login identity?"
- "The glossary already defines *cancel* as X. You seem to mean Y. Which one are we changing?"

## Force a scenario

Invent cases the happy path hides:

- Partial input, replayed request, two users, timezone, empty collection, permission denied, vendor timeout
- "Walk me through the moment after the user hits retry."
- "What is illegal here, and who enforces it — the UI, the API, or the database?"

## Cross-check the code

When they state how something works, open the implementation and the tests. If they diverge, show both excerpts and ask which is the source of truth.

## Cross-check official docs

When the plan leans on a framework feature, quote the current docs (Context7 or first-party). If the plan assumes an API that does not exist, or an old one that changed, stop the plan there.

## Make the cost visible

- "If we put the seam here, every caller learns these three error modes. Is that the interface we want?"
- "This choice is cheap today and expensive the day we add a second provider. Is that acceptable?"

## Stop conditions

Keep going while answers still move the design. Stop a line of questioning when:

- The term is in the glossary and the code agrees
- The scenario has an explicit allowed/illegal outcome
- The remaining work is implementation detail, not shape
