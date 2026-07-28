# Diagram: New Project Setup Flow

The sequence from [Example 4](../examples/04-project-setup-workflow.md).

```mermaid
flowchart LR
    A["mkdir project && cd project"] --> B["python -m venv .venv"]
    B --> C["activate .venv"]
    C --> D["pip install ..."]
    D --> E["pip freeze > requirements.txt"]
    E --> F["write code"]
    F --> G["commit requirements.txt<br/>(never commit .venv/)"]
```

The `.venv` folder itself never gets committed — `requirements.txt` is what makes the environment reproducible for anyone else who clones the project.
