---
name: codebase-design
description: Shared vocabulary for designing deep modules with small interfaces, clean seams, and tests that travel through those interfaces. Use when designing or reshaping a module, placing a seam, improving testability or agent-navigability, or when another skill needs this design language.
---

# Codebase Design

Design **deep modules**: lots of behaviour behind a small interface, sitting on a clean seam, tested through that same interface.

The point is leverage for callers, locality for the next person who has to change it, and tests that survive refactors. Use these words exactly. Do not swap in "component", "service", "API", or "boundary".

## Vocabulary

**Module**: anything with an interface and an implementation. Scale-agnostic: a function, a class, a package, or a slice that crosses tiers.

**Interface**: everything a caller must know to use the module correctly. Not only the type signature: invariants, ordering, error modes, required config, and performance characteristics.

**Implementation**: the body. Distinct from **adapter**, which names the *role* a concrete thing plays at a seam (Postgres repo, in-memory fake), not how big the body is.

**Depth**: behaviour a caller can exercise per unit of interface they have to learn. Deep = large behaviour, small interface. Shallow = interface almost as complex as the body.

**Seam**: the *place* you can change behaviour without editing that place. Where the interface lives. Placing the seam is a separate decision from what sits behind it.

**Adapter**: a concrete thing that satisfies an interface at a seam.

**Leverage**: what callers get from depth. One implementation pays back across many call sites and tests.

**Locality**: what maintainers get from depth. Change, bugs, and verification concentrate in one place.

## Deep vs shallow

```
Deep                         Shallow (avoid)
┌──────────────────┐         ┌────────────────────────────┐
│ small interface  │         │        large interface     │
├──────────────────┤         ├────────────────────────────┤
│                  │         │ thin pass-through body     │
│  hidden work     │         └────────────────────────────┘
│                  │
└──────────────────┘
```

When shaping an interface, ask: fewer methods? simpler parameters? more complexity pushed inside?

## Principles

- **Depth is an interface property.** Internals may be small, mockable, swappable pieces. Those pieces are not the public interface. A module may have **internal seams** (private, used by its own tests) and one **external seam**.
- **Deletion test.** Delete the module. If complexity vanishes, it was a pass-through. If the same complexity reappears across N callers, it was earning its keep.
- **The interface is the test surface.** Callers and tests cross the same seam. If you need to test *past* the interface, the module is the wrong shape.
- **One adapter is a hypothetical seam. Two adapters make it real.** Do not introduce a seam until something actually varies across it (usually production + test).

## Testability

1. **Accept dependencies, do not construct them inside.**
2. **Return values. Do not hide the result in a mutation** unless mutation *is* the interface.
3. **Keep the surface small.** Fewer methods and params means fewer tests and simpler fixtures.

```ts
// Prefer
function priceOrder(order: Order, rates: TaxRates): Price {}

// Avoid
function priceOrder(order: Order): void {
  const rates = loadTaxRatesFromDisk();
  order.total = compute(order, rates);
}
```

## Relationships

- A module has one interface (the surface callers and tests share).
- Depth is measured against that interface.
- A seam is where the interface lives.
- An adapter sits at a seam and satisfies the interface.
- Depth produces leverage for callers and locality for maintainers.

## Rejected shortcuts

- Depth as "implementation lines / interface lines": rewards padding.
- "Interface" meaning only a language `interface` keyword or a class's public methods: too narrow.
- "Boundary" as a synonym: overloaded. Say **seam** or **interface**.

## Going deeper

- Deepening a cluster given its dependencies: [deepening.md](deepening.md)
- Exploring alternative interfaces in parallel: [design-twice.md](design-twice.md)
