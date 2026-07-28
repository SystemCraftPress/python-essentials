# Python Quick Reference

Syntax and standard library lookup tables for daily Python use. From the [Python Essentials Companion Guide](../README.md).

## Core Syntax

| Task                        | Syntax                                |
| ----------------------------- | ---------------------------------------- |
| Variable assignment          | `x = 5`                                |
| Multiple assignment          | `a, b = 1, 2`                          |
| f-string                     | `f"{name} is {age}"`                   |
| Conditional expression       | `"yes" if x else "no"`                 |
| `for` loop over a sequence   | `for item in items:`                   |
| `for` loop with index        | `for i, item in enumerate(items):`     |
| `while` loop                 | `while condition:`                     |
| Define a function            | `def name(params):`                    |
| Define a class               | `class Name:`                          |
| Import a module               | `import module`                        |
| Import specific names        | `from module import name`              |
| Context manager               | `with open(path) as f:`                |
| Exception handling            | `try: ... except Type: ...`            |
| Raise an exception            | `raise ValueError("message")`          |
| List comprehension            | `[x for x in items if condition]`      |

## String Methods

| Method              | What it does                                  |
| ---------------------- | ------------------------------------------------ |
| `.upper()` / `.lower()` | Change case                                 |
| `.strip()`           | Remove leading/trailing whitespace             |
| `.split(sep)`        | Split into a list on a separator               |
| `.join(iterable)`    | Join a list into a string with this separator  |
| `.replace(old, new)` | Replace all occurrences                        |
| `.startswith(x)` / `.endswith(x)` | Check the start or end of the string |
| `.find(x)`           | Index of first match, or `-1` if not found     |
| `.format(...)`       | Older formatting style (prefer f-strings)      |

## List Methods

| Method            | What it does                                |
| -------------------- | ---------------------------------------------- |
| `.append(x)`       | Add an item to the end                       |
| `.insert(i, x)`    | Insert an item at position `i`                |
| `.remove(x)`       | Remove the first matching value               |
| `.pop(i)`          | Remove and return item at index (default: last) |
| `.sort()`          | Sort in place                                |
| `sorted(list)`     | Return a new sorted list, original unchanged |
| `.reverse()`       | Reverse in place                             |
| `len(list)`        | Number of items                              |
| `x in list`        | Membership check                             |

## Dictionary Methods

| Method                | What it does                                |
| ------------------------- | --------------------------------------------- |
| `.get(key, default)`   | Value for key, or default if missing         |
| `.keys()`               | All keys                                     |
| `.values()`             | All values                                   |
| `.items()`              | Key-value pairs, as tuples                   |
| `.pop(key, default)`   | Remove key and return its value              |
| `.update(other)`        | Merge another dictionary in                  |
| `key in dict`           | Membership check (checks keys)               |

## Common Built-in Functions

| Function          | What it does                                |
| -------------------- | ---------------------------------------------- |
| `len(x)`           | Length of a string, list, dict, or set        |
| `range(n)`         | A sequence of numbers from 0 to n-1           |
| `enumerate(x)`     | Pairs of (index, item)                        |
| `zip(a, b)`        | Pairs items from two sequences together       |
| `sum(x)`           | Sum of a sequence of numbers                  |
| `min(x)` / `max(x)` | Smallest / largest value                     |
| `sorted(x)`        | New sorted list                               |
| `type(x)`          | The type of a value                           |
| `isinstance(x, T)` | Whether `x` is of type `T`                    |

## Common Exceptions

| Exception            | When it's raised                              |
| ------------------------ | ---------------------------------------------------------------- |
| `ValueError`           | Right type, wrong value (`int("abc")`)           |
| `TypeError`            | Operation used on the wrong type                 |
| `KeyError`             | Dictionary key doesn't exist                     |
| `IndexError`           | List index is out of range                       |
| `AttributeError`       | Object has no such attribute or method            |
| `NameError`            | Variable used before it was defined              |
| `ZeroDivisionError`    | Division or modulo by zero                       |
| `FileNotFoundError`    | File path doesn't exist                          |
| `ImportError` / `ModuleNotFoundError` | Module can't be found or imported |
| `IndentationError`     | Inconsistent or incorrect indentation            |

## Virtual Environment Commands

| Task                          | Command                          |
| --------------------------------- | ------------------------------------ |
| Create a virtual environment  | `python -m venv .venv`             |
| Activate (Windows)            | `.venv\Scripts\activate`           |
| Activate (macOS/Linux)        | `source .venv/bin/activate`        |
| Deactivate                    | `deactivate`                       |
| Install a package             | `pip install package_name`         |
| Save installed packages       | `pip freeze > requirements.txt`    |
| Install from a requirements file | `pip install -r requirements.txt` |

## Standard Library Quick Picks

| Module        | Use it for                                    |
| ---------------- | ---------------------------------------------------- |
| `datetime`     | Dates and times                                  |
| `json`         | Reading and writing JSON                         |
| `os`           | Environment variables, running processes         |
| `pathlib`      | Working with file paths                          |
| `random`       | Random numbers and choices                       |
| `math`         | Mathematical functions and constants             |
| `collections`  | `Counter`, `defaultdict`, and other containers   |
| `re`           | Regular expressions                              |

---

For the "why" behind these — plus scenario-based troubleshooting for when things go wrong — see the [Python Essentials Companion Guide](../README.md#get-the-full-companion-guide).
