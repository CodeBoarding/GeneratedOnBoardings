```mermaid
graph LR
    EvalSuite["EvalSuite"]
    EvalCase["EvalCase"]
    EvalRubric["EvalRubric"]
    Critic["Critic"]
    EvalSuite -- "Aggregates and executes" --> EvalCase
    EvalCase -- "Is evaluated against" --> EvalRubric
    EvalRubric -- "Uses strategy from" --> Critic
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### EvalSuite
The primary orchestrator for the evaluation process. It aggregates a collection of `EvalCase` instances and manages their execution, compiling the results into a final report.


**Related Classes/Methods**:

- `arcade_evals/eval.py`


### EvalCase
Represents a single, atomic test scenario. It encapsulates the inputs for a tool, the expected outputs, and a reference to the `EvalRubric` used for judging the outcome.


**Related Classes/Methods**:

- `arcade_evals/eval.py`


### EvalRubric
Defines the specific criteria and logic for judging an `EvalCase`. It acts as a bridge, associating a test case with the appropriate `Critic` that will perform the actual evaluation.


**Related Classes/Methods**:

- `arcade_evals/eval.py`


### Critic
An abstract component that defines the contract for all evaluation strategies. Its concrete implementations (e.g., `NumericCritic`, `SimilarityCritic`) contain the specific logic for comparing a tool's actual output against the expected output defined in an `EvalCase`.


**Related Classes/Methods**:

- `arcade_evals/critic.py`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)