---
name: tdd
description: Test-driven development with a red-green loop. Use when the user wants to build a feature or fix a bug test-first, mentions red-green-refactor, tracer bullets, or wants tests written before implementation.
---

# Test-Driven Development

TDD here is **red → green**, one vertical slice at a time. The tests you keep should still pass after a rewrite of the internals.

If `CONTEXT.md` or ADRs exist in the area you are touching, read them so test names use the project's language.

## What a good test is

A test is a specification of observable behaviour through a public interface. Internals may change completely; the test should not.

Good: `user can checkout with a valid cart`. Bad: `checkout calls paymentService.process`.

Examples: [good-tests.md](good-tests.md). Mocking: [mocking.md](mocking.md).

## Seams

A **seam** is the public boundary you observe from. Tests live at seams, never against private internals.

Before writing the first test, write down the seams under test and confirm them with the user. No test at an unconfirmed seam. You cannot test everything; agreeing the seams is how effort lands on critical paths instead of every edge.

Ask: "What is the public interface, and which seams should we test?"

If the shape of that interface is itself the question (how deep the module is, where the seam belongs), use `codebase-design` as a reference for the words **module, interface, depth, seam, adapter, leverage, locality**. That skill is a vocabulary, not a session to run unless the user wants a design pass.

## Anti-patterns

- **Implementation-coupled**: mocks of internal collaborators, private-method tests, or assertions through a side channel (raw SQL instead of the interface). Tell: the test breaks when you refactor and behaviour did not change.
- **Tautological**: the expected value is computed the same way as the code (`expect(add(a,b)).toBe(a+b)`). Expected values come from an independent source: a known literal, a worked example, the spec.
- **Horizontal slicing**: all tests first, then all code. That tests imagined shape, not learned behaviour. Work in **vertical slices**: one test → one implementation → repeat. Each test is a tracer bullet that can change what the next cycle does.

## Rules of the loop

- **Red before green.** Write the failing test first. Then only enough code to pass it. No speculative features.
- **One slice at a time.** One seam, one test, one minimal implementation per cycle.
- **Refactoring is not this loop.** Keep the cycle red → green. Broader cleanup belongs to a later `code-review` (or a dedicated cleanup pass the user asks for), not sandwiched into every green.

Use the project's existing test runner. Do not add a new framework unless the repo has none and the user agrees.
