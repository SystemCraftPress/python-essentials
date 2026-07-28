# Diagram: The try/except/else/finally Flow

How Python actually executes each block, from [Example 2](../examples/02-error-handling-in-practice.md).

```mermaid
flowchart TD
    A["try block runs"] --> B{"Exception raised?"}
    B -- "No" --> C["else block runs"]
    B -- "Yes, matches an except" --> D["matching except block runs"]
    B -- "Yes, no match" --> E["exception propagates up<br/>(program crashes here<br/>unless caught elsewhere)"]
    C --> F["finally block runs"]
    D --> F
    E --> F
    F --> G["execution continues<br/>(or re-raises if the<br/>except block raised again)"]
```

`finally` runs no matter what happened above it — success, a caught exception, or an uncaught one propagating through. That's what makes it the right place for cleanup (closing files, releasing locks) that must happen either way.
