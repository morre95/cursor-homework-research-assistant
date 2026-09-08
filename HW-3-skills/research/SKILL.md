---
name: research
description: Investigate a question against high-trust primary sources and save a cited Markdown memo in the repo. Use when the user wants a topic researched, API or framework facts gathered, or reading delegated so they can keep working.
---

# Research

Answer one question from **primary sources**, then leave a memo the next session can trust.

If the work will take a while and a background agent is available, run the research there so this session can continue. Otherwise do it in-session. Same quality bar either way.

## Sources

Follow every claim back to the owner of the fact:

1. Official docs, specs, RFCs, first-party API references
2. For libraries, frameworks, SDKs, CLIs, and cloud services: current docs via Context7 (`resolve-library-id`, then `query-docs` with the full question). Do this even when the API "seems familiar"
3. Source code of the dependency or this repo, when docs are silent or contradict behaviour
4. Release notes / changelogs for version-specific behaviour

Do **not** treat secondary write-ups, unofficial summaries, or training memory as the source of truth. If you use a secondary source to find a lead, verify against the owner.

Prefer the version the project actually uses (`package.json`, lockfile, go.mod, etc.). Say so when a fact is version-specific.

## Memo

Write one Markdown file. Match the repo's existing research/notes convention if there is one. Otherwise:

```text
docs/research/<yyyy-mm-dd>-<short-slug>.md
```

Create `docs/research/` if needed. Tell the user the path.

Each factual claim gets a citation (URL, file path, or doc heading). Separate **facts**, **inferences**, and **open questions**. If sources conflict, show both and say which you would trust and why.

Template: [report-format.md](report-format.md).

## Done when

- The original question is answered, or the unknowns are explicit
- A reader can click through to the owner of each important claim
- The memo is saved in the repo and the path is reported
