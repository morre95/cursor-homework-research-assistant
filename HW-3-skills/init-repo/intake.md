# Intake questions

Ask in rounds. Lead with the recommended option. Skip anything already answered in the conversation.

## Round A — what are we building?

**Product type** (pick one):

- Web app (SPA or SSR)
- Mobile app (iOS, Android, or both)
- Backend API
- Full-stack (web + API in one repo)
- CLI
- Library / package
- Desktop
- Other (they describe it)

**Purpose:** one or two sentences. Who it is for, what success looks like on day one.

## Round B — stack

Propose one default for the type, then let them change pieces:

| Type | Default to propose (adjust after current docs) |
| --- | --- |
| Web app | TypeScript, a current mainstream framework they know or you confirm in docs, the framework's default package manager |
| Mobile | The official cross-platform or native toolchain they prefer; do not pick for them if they have a store target (iOS vs Android vs both) |
| Backend API | TypeScript or Python, one web framework, one test runner |
| Full-stack | One framework that covers both sides, unless they want a split |
| CLI | Go or TypeScript, depending on distribution needs |
| Library | Same language as the consumers they name |
| Desktop | Ask native vs webview; do not assume |

Then, only the extras that apply:

- Package manager
- Styling (web/mobile)
- Database (none is a valid default)
- Auth (none is a valid default)
- Test runner (use the stack default)
- Hosting (optional; do not scaffold deploy unless they ask)

## Round C — where

- New directory name (lowercase, hyphens) vs current folder
- `git init`? Recommended: yes
- Copy this skill catalog into `.cursor/skills/`? Recommended: yes

Stop when these are answered. Do not add a round about issue trackers, ADR layouts, or triage labels.
