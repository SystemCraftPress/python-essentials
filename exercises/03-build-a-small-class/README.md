# Exercise 3: Build a Small Class

**Goal:** design a class from scratch for a real (if small) problem, rather than following along with someone else's.

**Time:** ~20 minutes

## Task

Build a `Stack` class that supports the standard stack operations:

```python
stack = Stack()
stack.push(1)
stack.push(2)
stack.push(3)
stack.peek()     # 3, without removing it
stack.pop()      # 3, removes and returns it
len(stack)       # 2
stack.is_empty() # False
```

Requirements:

1. `push(item)` — adds an item to the top
2. `pop()` — removes and returns the top item; raise a clear error if the stack is empty
3. `peek()` — returns the top item without removing it; raise a clear error if empty
4. `is_empty()` — returns `True`/`False`
5. Support `len(stack)` via `__len__`
6. Support printing via `__repr__` — printing an empty stack and a non-empty one should look different and useful

## Checkpoints

- [ ] Calling `pop()` or `peek()` on an empty stack raises a specific exception with a clear message, not an `IndexError` from an unguarded list operation leaking through
- [ ] `len(stack)` works because you implemented `__len__`, not because you exposed the internal list
- [ ] You did not implement `push`/`pop` by exposing `stack.items` directly for external code to mutate

## Stretch Goal

Add a `max_size` parameter to `__init__`. `push()` should raise an error if the stack is full, so a caller can't silently overflow it.

## Reference

See the [small class example](../../examples/03-a-small-class-in-practice.md) for a class of similar shape, and the [cheat sheet](../../cheatsheet/python-essentials-cheatsheet.md#classes) for bare syntax.
