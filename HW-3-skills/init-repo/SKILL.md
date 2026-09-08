---
name: init-repo
description: Start a new software project by interviewing the user about product type and tech stack, then scaffolding a runnable skeleton and optionally installing this skill catalog. Use when the user wants to create a new repo, bootstrap an app, or start a web, mobile, API, CLI, or library project from scratch.
disable-model-invocation: true
---

# Init Repo

Interview first, then scaffold. Do not invent a stack. Do not copy a giant template. Produce a small, runnable skeleton that matches what they asked for, then stop.

## 1. Intake

Ask in short rounds. Prefer a structured question tool when available; otherwise ask conversationally. Recommended defaults first, so they can accept in one word. Full prompt list: [intake.md](intake.md).

Minimum you must know before writing files:

1. **Product type** — web app, mobile app, backend API, full-stack, CLI, library, desktop, or other
2. **One-sentence purpose**
3. **Tech stack** — language, framework, package manager. Propose a current default for the type; let them override
4. **Location** — new directory (name it) or current empty folder
5. **Git** — `git init` on `main` unless they say no
6. **Skills catalog** — copy sibling skills into the new repo's `.cursor/skills/` unless they say no

Also collect, if relevant to the type: styling, database, auth, testing, hosting. Skip questions that do not apply (no mobile target for a CLI, no CSS for a library).

If the target directory already has a real project (lockfile, `src/` with code, existing git history with commits), stop and ask whether to use `install-skills` instead. Do not overwrite a living repo.

## 2. Confirm the plan

Show a compact plan before any writes:

- Directory name and path
- Product type and stack (with versions you will pin, once you have looked them up)
- Commands you will run (package manager, git)
- Files you will create
- Whether skills will be copied

Wait for approval.

## 3. Look up current scaffolding

For the chosen framework, language, SDK, or CLI, fetch **current** official docs before generating config. Use Context7 (`resolve-library-id` then `query-docs`) for library/framework setup. Match official defaults unless the user overrode them.

Do not rely on memory for CLI flags, config filenames, or "create" commands.

## 4. Scaffold

Keep it small:

- `.gitignore` appropriate to the stack (and always ignore `.env`, secrets, dependency dirs)
- `README.md` with purpose, how to install, how to run, how to test
- Manifest (`package.json`, `pyproject.toml`, etc.) with scripts for dev/test/lint if the ecosystem has them
- Smallest runnable entry (one page, one `GET /health`, one `hello` command — whatever fits the type)
- Test runner wired with one trivial passing test if the stack has a standard tool
- Formatter/linter only if it is the stack's obvious default and the official docs say so

For web UI, pick a distinctive visual direction and implement it; do not ship a generic purple-gradient placeholder. For APIs and CLIs, skip visual design.

Pin versions in the manifest. Do not leave "latest" unspecified in generated lockfiles if the package manager can lock.

**Do not** add this catalog's skills by rewriting them. Copy the sibling skill folders into `.cursor/skills/` using the same rules as `install-skills` (no overwrite of existing names without asking). Skip the catalog `README.md` unless they want it.

`git init -b main` if they agreed and `.git` is missing. Do not create a remote. Do not commit unless they asked.

Never write secrets. If the stack needs API keys, add `.env.example` with empty placeholders only.

## 5. Verify

Run the install/dev/test commands that the official docs specify, as far as they can run unattended. Fix scaffold mistakes you introduced.

Report:

- Path
- How to run it
- Stack choices
- Skills copied (or skipped)
- What you did not set up (auth, deploy, CI) so they know it is still a skeleton
