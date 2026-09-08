---
name: resolving-merge-conflicts
description: Resolve an in-progress git merge or rebase conflict hunk by hunk from each side's original intent, then finish the operation. Use when git is mid-merge or mid-rebase, when conflict markers are present, or when the user asks to resolve merge conflicts.
---

# Resolving Merge Conflicts

Finish the in-progress merge or rebase. Resolve by **intent**, not by whichever side looks newer. Do not invent behaviour that neither side had. Do not `--abort` unless the user explicitly asks to abandon the operation.

## 1. See the state

```bash
git status
git diff
```

Note whether this is a merge, rebase, cherry-pick, or revert. List conflicted files. Read recent history on both sides (`git log --oneline --left-right HEAD...MERGE_HEAD` during a merge; rebase `git log` / `REBASE_HEAD` as appropriate).

If there is no in-progress operation, stop and say so.

## 2. Recover intent per hunk

For each conflicted file, find *why* each side changed, not only *what* the markers contain:

- Commit messages touching the hunk
- Linked PR/issue if the repo uses them
- Surrounding tests and callers
- The merge/rebase's stated goal (the branch being integrated, the rebase onto target)

Read both versions of the hunk (`ours` / `theirs`) with enough surrounding context to see the full function or type.

## 3. Resolve hunk by hunk

Prefer a result that preserves **both** intents. If they cannot coexist, keep the intent that matches the operation's goal and note the trade-off in the final message.

Never leave conflict markers. Never delete one side blindly to "just make it compile" without stating what was dropped.

Stage a file only when that file is fully resolved.

## 4. Prove the tree

Discover this repo's checks (typecheck, tests, lint, format) from `package.json`, `Makefile`, CI config, or similar. Run the cheapest meaningful sequence, typically types → tests → format. Fix breakages the merge introduced. Do not "fix" unrelated red tests unless they block the operation and you say so.

## 5. Finish

Stage remaining resolved files.

- **Merge:** complete the merge commit. Use the default merge message unless the user asked otherwise; add a short note if an intent was dropped.
- **Rebase:** `git rebase --continue` until the sequence is done. Resolve later commits the same way. Do not skip commits.
- **Cherry-pick / revert:** continue until the sequence finishes.

Do not push unless the user asked. Report: files resolved, any intent that was dropped, and which checks ran.
