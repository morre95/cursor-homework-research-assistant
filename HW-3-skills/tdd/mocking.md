# When to mock

Mock at **system boundaries** you do not own:

- External HTTP APIs (payments, email, identity)
- Time and randomness
- Sometimes filesystem; prefer a temp dir when you control it
- Sometimes database; prefer a real test database or an in-process stand-in

Do not mock:

- Your own modules
- Internal collaborators
- Anything this repo owns and can run in the suite

## Design the boundary so a fake is boring

Pass the dependency in. Do not construct the vendor client inside the module under test.

Prefer a small SDK-shaped port (one function per operation) over a generic `fetch(url)` that forces the fake to branch on paths.

```ts
// Easy to fake: each operation returns one shape
const payments = {
  charge: (amount: Money) => gateway.charge(amount),
};

// Hard to fake: one pipe, many meanings
const payments = {
  fetch: (path: string, init?: RequestInit) => fetch(path, init),
};
```

If you need a seam for a fake, you likely need two adapters (production + test). That is the `codebase-design` rule: one adapter is a hypothetical seam.
