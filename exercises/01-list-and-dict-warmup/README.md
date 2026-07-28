# Exercise 1: List and Dict Warmup

**Goal:** get comfortable manipulating the two data structures you'll use constantly, without reaching for a tutorial mid-task.

**Time:** ~10 minutes

## Task 1: Deduplicate a list, preserving order

```python
items = ["a", "b", "a", "c", "b", "d"]
# Expected result: ["a", "b", "c", "d"]
```

A `set` alone won't preserve order. Find an approach that does.

## Task 2: Invert a dictionary

```python
scores = {"Ada": 92, "Grace": 88, "Alan": 95}
# Expected result: {92: "Ada", 88: "Grace", 95: "Alan"}
```

## Task 3: Count occurrences

```python
words = ["cat", "dog", "cat", "bird", "dog", "cat"]
# Expected result: {"cat": 3, "dog": 2, "bird": 1}
```

Solve it two ways: once by hand with a plain `dict`, once using `collections.Counter`.

## Task 4: Filter and transform in one pass

```python
prices = [12.99, 45.00, 8.50, 120.00, 33.25]
# Expected: a list of prices over $20, each with 10% tax added, rounded to 2 decimals
# [49.5, 132.0, 36.58]
```

Use a list comprehension.

## Checkpoints

- [ ] Task 1 works with no imports required
- [ ] Task 2 handles the case where two original values could map to the same key correctly (which one wins? make sure you know)
- [ ] Task 3's two solutions produce identical output
- [ ] Task 4 is a single list comprehension, not a loop with `.append()`

## Reference

The [cheat sheet](../../cheatsheet/python-essentials-cheatsheet.md) and [quick reference](../../reference/quick-reference.md) cover every method needed here.
