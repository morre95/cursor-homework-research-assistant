# Good and bad tests

## Good

Behaviour through the public interface.

```ts
test("user can checkout with a valid cart", async () => {
  const cart = createCart();
  cart.add(product);
  const result = await checkout(cart, paymentMethod);
  expect(result.status).toBe("confirmed");
});
```

- Names WHAT, not HOW
- Public API only
- Survives internal refactors
- One logical assertion (a group of related checks on one outcome is fine)

```ts
test("createUser makes the user retrievable", async () => {
  const user = await createUser({ name: "Alice" });
  const retrieved = await getUser(user.id);
  expect(retrieved.name).toBe("Alice");
});
```

## Bad

```ts
// Implementation detail
test("checkout calls paymentService.process", async () => {
  const mockPayment = jest.fn();
  await checkout(cart, mockPayment);
  expect(mockPayment).toHaveBeenCalledWith(cart.total);
});

// Side channel instead of the interface
test("createUser writes a row", async () => {
  await createUser({ name: "Alice" });
  const row = await db.query("SELECT * FROM users WHERE name = ?", ["Alice"]);
  expect(row).toBeDefined();
});

// Tautology: expected value restates the implementation
test("calculateTotal sums line items", () => {
  const items = [{ price: 10 }, { price: 5 }];
  const expected = items.reduce((sum, i) => sum + i.price, 0);
  expect(calculateTotal(items)).toBe(expected);
});
```

Independent expected value:

```ts
test("calculateTotal sums line items", () => {
  expect(calculateTotal([{ price: 10 }, { price: 5 }])).toBe(15);
});
```
