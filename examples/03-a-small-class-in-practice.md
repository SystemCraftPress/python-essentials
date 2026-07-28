# Example: A Small Class in Practice

A minimal but realistic class — no inheritance, no abstract base classes, just the everyday shape most classes actually take.

## The Problem

You're tracking a to-do list. A plain dictionary works at first, but you keep re-writing the same logic to mark items done and to count what's left. That repetition is the signal it's time for a class.

## The Class

```python
class TaskList:
    def __init__(self, name):
        self.name = name
        self.tasks = []

    def add(self, description):
        self.tasks.append({"description": description, "done": False})

    def complete(self, index):
        self.tasks[index]["done"] = True

    def remaining(self):
        return [t for t in self.tasks if not t["done"]]

    def __repr__(self):
        done = len(self.tasks) - len(self.remaining())
        return f"TaskList('{self.name}', {done}/{len(self.tasks)} done)"
```

## Using It

```python
today = TaskList("Today")
today.add("Write the quarterly report")
today.add("Reply to client email")
today.add("Fix the failing test")

today.complete(1)

print(today)
# TaskList('Today', 1/3 done)

for task in today.remaining():
    print("-", task["description"])
# - Write the quarterly report
# - Fix the failing test
```

## Why This Is a Good First Class

- **`__init__` sets up real state**, not placeholder values — `self.tasks` starts as an empty list because that's genuinely the starting state.
- **Each method does one thing.** `add`, `complete`, and `remaining` map directly to actions you'd describe out loud.
- **`__repr__` earns its place** — printing a `TaskList` gives you something useful instead of `<TaskList object at 0x7f...>`.

## When You'd Reach for More

If you needed multiple *kinds* of tasks with different behavior (recurring tasks, tasks with due dates), that's when inheritance or composition starts to make sense. Don't reach for it before you need it — this flat, single-class version is correct for a lot of real problems.

See the [cheat sheet](../cheatsheet/python-essentials-cheatsheet.md#classes) for the bare class syntax.
