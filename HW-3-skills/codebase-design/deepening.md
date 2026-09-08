# Deepening

How to fold a cluster of shallow modules into one deeper module without losing a test story. Uses the vocabulary in [SKILL.md](SKILL.md).

## Classify dependencies first

The category decides how you test across the new seam.

1. **In-process.** Pure computation, in-memory state, no I/O. Merge and test through the new interface. No adapter.
2. **Local stand-in exists.** Postgres-in-process, fake filesystem, embedded queue. Deepen and run the stand-in in the suite. The seam stays internal.
3. **Remote but owned.** Your own services over the network. Put a **port** at the seam. The deep module owns the logic; transport is an injected adapter. Tests use an in-memory adapter. Production uses HTTP/gRPC/queue.
4. **True external.** Third parties you do not control (payments, email, identity). Inject a port. Tests supply a fake adapter. Do not mock your own internals.

## Seam rules

- Do not add a port until at least two adapters are justified (typically production + test).
- Internal seams used by a module's own tests stay private. Do not leak them through the public interface just because tests touch them.

## Replace, do not layer

- Once tests exist at the deepened module's interface, delete the old unit tests that pinned the shallow pieces.
- New tests assert observable outcomes through the interface, not internal state.
- If a test must change when the implementation changes, it is testing past the interface.
