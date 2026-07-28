# Example: Choosing the Right Data Structure

A worked example of picking between list, tuple, dict, and set — using a realistic task: processing a batch of customer orders.

## The Data

```python
orders = [
    {"id": "A101", "customer": "Jordan Lee", "total": 42.50, "status": "shipped"},
    {"id": "A102", "customer": "Sam Rivera", "total": 18.00, "status": "pending"},
    {"id": "A103", "customer": "Jordan Lee", "total": 71.25, "status": "shipped"},
]
```

## Task 1: Get all unique customers

You don't care about order, and you don't want duplicates. That's a **set**.

```python
customers = {order["customer"] for order in orders}
# {"Jordan Lee", "Sam Rivera"}
```

## Task 2: Look up an order by ID quickly

You need fast lookup by a key. That's a **dict**, keyed by order ID.

```python
orders_by_id = {order["id"]: order for order in orders}
orders_by_id["A102"]["status"]
# "pending"
```

## Task 3: Keep orders in the order they arrived

You need to preserve arrival order and might add more. That's a **list**.

```python
order_ids_in_order = [order["id"] for order in orders]
# ["A101", "A102", "A103"]
```

## Task 4: Represent a fixed coordinate pair (e.g. a warehouse shelf location)

`(aisle, shelf)` — this never changes shape and shouldn't be accidentally mutated. That's a **tuple**.

```python
shelf_location = (3, "B")
```

## The Decision in One Table

| Need | Structure |
|---|---|
| Fast lookup by key | `dict` |
| No duplicates, don't care about order | `set` |
| Ordered, might change | `list` |
| Ordered, fixed, shouldn't change | `tuple` |

See the [decision diagram](../diagrams/data-structure-decision.md) for this as a flowchart, or the [cheat sheet](../cheatsheet/python-essentials-cheatsheet.md) for the syntax side by side.
