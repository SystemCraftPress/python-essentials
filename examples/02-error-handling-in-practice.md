# Example: Error Handling Done Properly

A worked example loading a JSON config file — the kind of code that looks simple until the file is missing or malformed.

## The Naive Version (don't do this)

```python
import json

def load_config(path):
    with open(path) as f:
        return json.load(f)

config = load_config("settings.json")
```

This works right up until `settings.json` doesn't exist, or exists but contains invalid JSON. Then it crashes with a raw traceback and no useful context for whoever is running it.

## The Version With Real Error Handling

```python
import json

def load_config(path):
    try:
        with open(path) as f:
            return json.load(f)
    except FileNotFoundError:
        raise FileNotFoundError(
            f"Config file not found at '{path}'. Copy settings.example.json to get started."
        )
    except json.JSONDecodeError as e:
        raise ValueError(
            f"Config file at '{path}' is not valid JSON: {e}"
        )

try:
    config = load_config("settings.json")
except (FileNotFoundError, ValueError) as e:
    print(f"Could not start: {e}")
    exit(1)
```

## What Changed, and Why

- **Caught specific exceptions** (`FileNotFoundError`, `json.JSONDecodeError`) — not a bare `except:`, which would also silently swallow real bugs like a typo in the function itself.
- **Re-raised with context** — the original error is still visible, but now with a message that tells a human what to actually do about it.
- **Handled at the call site** — `load_config()` raises; the caller decides what "failure" means for the program (here, exit cleanly with a message instead of dumping a traceback).

## The Anti-Pattern to Avoid

```python
try:
    config = load_config("settings.json")
except:
    config = {}
```

This silently hides every possible failure — including ones that have nothing to do with the file existing, like a bug in `load_config` itself. A bare `except:` is never the fix; it's the thing that makes the real bug harder to find later.

See the [exception-handling flow diagram](../diagrams/exception-handling-flow.md) and the [quick reference](../reference/quick-reference.md#common-exceptions) for the exception types themselves.
