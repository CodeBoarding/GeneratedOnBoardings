```mermaid
graph LR
    A[Input Sudoku Grid] --> B(Sudoku Checker)
    B -- Validates --> C{Valid Sudoku?}
    C -- Yes --> D[Output: Valid]
    C -- No --> E[Output: Invalid, with Errors]
```

