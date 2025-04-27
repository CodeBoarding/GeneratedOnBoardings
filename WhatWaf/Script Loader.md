```mermaid
flowchart LR
    subgraph ScriptLoader [ScriptLoader]
        style ScriptLoader fill:#f9f,stroke:#333,stroke-width:2px
        A[importlib.import_module] -- "imports" --> B((Script Module))
    end

    B -- "provides" --> C(ScriptQueue) 
    C -- "uses" --> ScriptLoader



```

### Component Description

This diagram illustrates the role of the `ScriptLoader` in dynamically importing script modules and making them available to the `ScriptQueue`. The `ScriptLoader` utilizes `importlib.import_module` to import script modules, which are then used by the `ScriptQueue` for WAF detection.

