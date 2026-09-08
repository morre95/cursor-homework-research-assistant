---
name: diagnosing-bugs
description: Disciplined diagnosis loop for hard bugs and performance regressions. Use when the user says diagnose or debug this, or reports something broken, throwing, failing, flaky, or slow.
---

# Diagnosing Bugs

A loop for bugs that do not yield to a quick read of the code. Skip a phase only when you can say why.

If `CONTEXT.md` or nearby ADRs exist, read them first so you use the project's words for the modules involved.

**Redact secrets** in every command, log, and artifact you show. Write `<REDACTED>`. Drive loops with env vars so credentials never appear in output. Quote only the lines that carry signal.

## Phase 1: Build a feedback loop

This is the skill. Everything else consumes the loop. If you have one command that goes **red on this exact symptom**, you can bisect, hypothesise, and instrument. If you do not, staring at code will not save you.

Spend most of the time here. Be aggressive. Do not give up early.

Try, in roughly this order:

1. Failing test at a seam that actually reaches the bug
2. HTTP script against a running dev server
3. CLI invocation with a fixture, diffed against a known-good snapshot
4. Headless browser script that asserts on DOM, console, or network
5. Replay of a captured request, payload, or event log
6. Throwaway harness: smallest subset of the system, one call
7. Property/fuzz loop when the output is "sometimes wrong"
8. Automated bisection (`git bisect run`) between two known states
9. Differential loop: old vs new, or config A vs B, same input
10. Structured human-in-the-loop only as last resort: a short script that tells the human what to click and captures output

Then **tighten**: faster setup, sharper assertion (the user's symptom, not "didn't crash"), more deterministic (pin time, seed RNG, isolate disk/network).

A 30-second flaky loop is barely better than none. A 2-second deterministic loop is the tool.

For flakes, raise the reproduction rate until it is debuggable. Loop the trigger, add stress, narrow timing. 50% is usable. 1% is not.

If you cannot build a loop, stop. List what you tried. Ask for environment access, a redacted artifact (HAR, logs, core, screen recording with timestamps), or permission to add temporary production probes. Do **not** hypothesise without a loop.

**Phase 1 is done** when you can name **one command you have already run**, show its (redacted) output, and it is:

- Red-capable: drives the real path and asserts the user's exact symptom
- Deterministic (or a pinned high repro rate)
- Fast (seconds)
- Runnable without a human, unless you documented a structured HITL script

If you catch yourself theorising before that command exists, stop.

## Phase 2: Reproduce and minimise

Run the loop. Confirm it fails the way the **user** described, not a nearby different failure. Capture the exact symptom.

Then shrink: drop inputs, callers, config, data, and steps **one at a time**, re-run after each cut, keep only what is load-bearing. Done when removing any remaining piece makes the loop go green.

## Phase 3: Hypothesise

Write **3–5 ranked, falsifiable hypotheses** before testing any of them.

> If \<X\> is the cause, then changing Y will make the bug disappear / changing Z will make it worse.

No prediction → not a hypothesis. Show the list to the user; they often re-rank instantly. Do not block if they are away.

## Phase 4: Instrument

Each probe maps to one prediction. Change one variable at a time.

Prefer: debugger/REPL, then targeted logs at the boundaries that distinguish hypotheses. Never "log everything and grep".

Tag debug logs with a unique prefix, e.g. `[DEBUG-a4f2]`. Cleanup is then one search.

For performance regressions, measure first: timing harness, profiler, query plan. Bisect on the number. Logs are usually the wrong tool.

## Phase 5: Fix and lock it

Write the regression test **before** the fix only if there is a **correct seam**: one that exercises the real bug pattern as it happens at the call site. A unit test that cannot recreate the chain is false confidence.

If no correct seam exists, that is the finding. The architecture is blocking the lock-down. Note it.

Otherwise: minimised repro → failing test → fix → test green → re-run the original (un-minimised) Phase 1 loop.

## Phase 6: Cleanup

- [ ] Phase 1 loop is green on the original repro
- [ ] Regression test passes, or missing seam is documented
- [ ] All `[DEBUG-...]` probes removed
- [ ] Throwaway harnesses deleted or moved to an obvious debug location
- [ ] The winning hypothesis is in the commit/PR message
