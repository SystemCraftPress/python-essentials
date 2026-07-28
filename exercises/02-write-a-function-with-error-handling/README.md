# Exercise 2: Write a Function With Real Error Handling

**Goal:** practice catching specific exceptions instead of guessing, using a function that has several real ways to fail.

**Time:** ~15 minutes

## Task

Write a function `safe_divide(a, b)` that:

1. Returns `a / b` when the inputs are valid numbers and `b` is not zero.
2. Raises a clear, specific error message (not a raw traceback) when `b` is zero.
3. Raises a clear, specific error message when `a` or `b` isn't a number at all (e.g., someone passes a string).

Start here:

```python
def safe_divide(a, b):
    # your implementation
    pass
```

## Test Cases to Handle

```python
safe_divide(10, 2)      # 5.0
safe_divide(10, 0)      # should raise, with a message that says WHY
safe_divide("10", 2)    # should raise, with a message that says WHAT was wrong
safe_divide(10, 2.5)    # 4.0 — floats are valid
```

## Checkpoints

- [ ] You catch `ZeroDivisionError` specifically — not a bare `except:`
- [ ] You catch `TypeError` for the non-numeric case, or check types explicitly before dividing
- [ ] Each error message would make sense to someone who has never seen your code
- [ ] Calling `safe_divide(10, 2)` still returns a plain number, not wrapped in anything

## Stretch Goal

Extend it to a `safe_divide_all(pairs)` that takes a list of `(a, b)` tuples and returns results for the valid ones while collecting errors for the invalid ones — instead of stopping at the first failure. This mirrors a common real pattern: process a batch, report what failed, don't crash the whole job over one bad row.

## Reference

See the [error handling example](../../examples/02-error-handling-in-practice.md) and the [exception flow diagram](../../diagrams/exception-handling-flow.md) if you get stuck.
