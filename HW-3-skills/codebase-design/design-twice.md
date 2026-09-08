# Design it twice

The first interface you think of is rarely the best. When the user wants alternatives for a deepening candidate, run this parallel pattern. Vocabulary lives in [SKILL.md](SKILL.md); dependency categories live in [deepening.md](deepening.md).

## 1. Frame the problem

Write a short, user-facing brief *before* spawning helpers:

- Constraints any new interface must satisfy
- Dependencies and their categories
- A sketch that makes the constraints concrete — not a proposal

Show it to the user, then continue. They can read while the alternatives are designed.

## 2. Spawn 3+ parallel designs

Each helper gets a **different** pressure, not a paraphrase of the same idea:

1. Minimise the interface: 1–3 entry points, maximum leverage per entry.
2. Maximise flexibility: many callers and later extension.
3. Optimise the common caller: default path is trivial.
4. (If cross-seam deps exist) Ports and adapters for those deps.

Give each helper file paths, coupling notes, dependency category, and the project's domain words if a glossary exists. Ask each for:

1. Interface (types, methods, params, invariants, ordering, errors)
2. A usage example from a caller
3. What the implementation hides
4. Dependency strategy and adapters
5. Trade-offs: where leverage is high, where it is thin

Designs must be structurally different. Three names for the same method list is a failed round.

## 3. Compare, then recommend

Present designs one at a time, then compare in prose on **depth**, **locality**, and **seam placement**. Give a recommendation. A hybrid is allowed if you say which parts you are stealing and why. Be opinionated.
