# Diagram: Choosing a Data Structure

The decision process from [Example 1](../examples/01-choosing-a-data-structure.md), as a flowchart.

```mermaid
flowchart TD
    A["Need to store multiple values"] --> B{"Need key → value<br/>lookup?"}
    B -- "Yes" --> C["dict"]
    B -- "No" --> D{"Must values<br/>be unique?"}
    D -- "Yes, order doesn't matter" --> E["set"]
    D -- "No" --> F{"Will it change<br/>after creation?"}
    F -- "Yes" --> G["list"]
    F -- "No, fixed shape" --> H["tuple"]
```

Most everyday Python code lives in `list` and `dict`. Reach for `set` when uniqueness is the point, and `tuple` when "this should never change" is part of the meaning, not just a preference.
