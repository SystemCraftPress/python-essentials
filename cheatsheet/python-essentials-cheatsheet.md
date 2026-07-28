# Python Essentials Cheat Sheet

A free, printable one-page reference for core Python. Pulled straight from the [Python Essentials Companion Guide](../README.md).

## Core Types

| Type | Example |
|------|---------|
| `int` | `age = 32` |
| `float` | `price = 19.99` |
| `str` | `name = "Ada"` |
| `bool` | `is_active = True` |
| `None` | `result = None` |

## Data Structures

| Type | Syntax | Ordered | Changeable |
|------|--------|---------|------------|
| List | `[1, 2, 3]` | Yes | Yes |
| Tuple | `(1, 2, 3)` | Yes | No |
| Dictionary | `{"key": "value"}` | Yes (3.7+) | Yes |
| Set | `{1, 2, 3}` | No | Yes |

## Control Flow

| Task | Syntax |
|------|--------|
| Conditional | `if x: ... elif y: ... else: ...` |
| Loop over items | `for item in items:` |
| Loop with index | `for i, item in enumerate(items):` |
| Loop while true | `while condition:` |
| Exit a loop | `break` |
| Skip an iteration | `continue` |

## Functions

```python
def name(param, default="value", *args, **kwargs):
    return result
```

## Common Exceptions

| Exception | Meaning |
|-----------|---------|
| `ValueError` | Right type, wrong value |
| `TypeError` | Wrong type for the operation |
| `KeyError` | Dictionary key missing |
| `IndexError` | List index out of range |
| `NameError` | Variable not defined |
| `ModuleNotFoundError` | Package not installed or env not activated |

## Virtual Environments

| Task | Command |
|------|---------|
| Create | `python -m venv .venv` |
| Activate (Windows) | `.venv\Scripts\activate` |
| Activate (macOS/Linux) | `source .venv/bin/activate` |
| Install a package | `pip install name` |
| Freeze dependencies | `pip freeze > requirements.txt` |
| Install from file | `pip install -r requirements.txt` |

## Classes

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        return f"{self.name} says woof!"
```

## Error Handling

```python
try:
    risky_operation()
except ValueError as e:
    handle_error(e)
else:
    handle_success()
finally:
    cleanup()
```

## Golden Rules

> Indentation is syntax, not style. Use 4 spaces, everywhere.

> Never use a mutable object as a default argument value.

> Catch specific exceptions. Never use a bare `except:`.

> Create a virtual environment for every project, without exception.

> Read the traceback before you search the error.

---

Want the reasoning behind every one of these rules — plus OOP patterns, module structure, and a full troubleshooting guide? See the [Python Essentials Companion Guide](../README.md#get-the-full-companion-guide).
