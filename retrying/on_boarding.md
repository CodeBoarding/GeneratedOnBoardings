```mermaid
graph LR
    Retry_Decorator_Interface["Retry Decorator Interface"]
    Retry_Orchestrator["Retry Orchestrator"]
    Attempt_Context["Attempt Context"]
    Retry_Strategy_Implementations["Retry Strategy Implementations"]
    Retry_Exception["Retry Exception"]
    Retry_Decorator_Interface -- "configures" --> Retry_Orchestrator
    Retry_Orchestrator -- "manages" --> Attempt_Context
    Retry_Orchestrator -- "evaluates" --> Retry_Strategy_Implementations
    Retry_Orchestrator -- "applies" --> Retry_Strategy_Implementations
    Retry_Orchestrator -- "raises" --> Retry_Exception
    click Retry_Decorator_Interface href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/retrying/Retry_Decorator_Interface.md" "Details"
    click Retry_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/retrying/Retry_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `retrying` library provides a robust mechanism for adding retry logic to Python functions. At its core, the `Retry Decorator Interface` serves as the primary entry point, allowing developers to easily configure retry behavior for their functions. This decorator, in turn, `configures` the `Retry Orchestrator`, which is the central component responsible for managing the entire retry lifecycle. The `Retry Orchestrator` `manages` the `Attempt Context`, which encapsulates the state of each individual function execution attempt. During the retry process, the `Orchestrator` `evaluates` various `Retry Strategy Implementations` (e.g., stop conditions, retry conditions) to determine if another attempt is warranted. If so, it `applies` other `Retry Strategy Implementations` (e.g., wait intervals) before the next attempt. Should all retry attempts be exhausted without success, the `Retry Orchestrator` `raises` a `Retry Exception`, signaling the ultimate failure of the decorated operation. This modular design ensures clear separation of concerns, making the retry mechanism flexible and extensible.

### Retry Decorator Interface [[Expand]](./Retry_Decorator_Interface.md)
The public API for applying retry logic to functions. It acts as the entry point for users to configure retry behavior.


**Related Classes/Methods**:

- <a href="https://github.com/rholder/retrying/blob/master/retrying.py#L32-L59" target="_blank" rel="noopener noreferrer">`retrying.retry`:32-59</a>


### Retry Orchestrator [[Expand]](./Retry_Orchestrator.md)
The central engine that manages the entire retry lifecycle, including the retry loop, function invocation, and application of strategies.


**Related Classes/Methods**:

- <a href="https://github.com/rholder/retrying/blob/master/retrying.py#L62-L250" target="_blank" rel="noopener noreferrer">`retrying.Retrying`:62-250</a>


### Attempt Context
A data structure that encapsulates the state of a single execution attempt of the decorated function.


**Related Classes/Methods**:

- <a href="https://github.com/rholder/retrying/blob/master/retrying.py#L253-L283" target="_blank" rel="noopener noreferrer">`retrying.Attempt`:253-283</a>


### Retry Strategy Implementations
A collection of pluggable components that define the conditions for stopping retries, the duration of pauses between retries, and the criteria for triggering a retry.


**Related Classes/Methods**:

- <a href="https://github.com/rholder/retrying/blob/master/retrying.py#L26-L29" target="_blank" rel="noopener noreferrer">`retrying._retry_if_exception_of_type`:26-29</a>


### Retry Exception
A custom exception raised when all retry attempts have been exhausted and the decorated function still fails.


**Related Classes/Methods**:

- <a href="https://github.com/rholder/retrying/blob/master/retrying.py#L286-L295" target="_blank" rel="noopener noreferrer">`retrying.RetryError`:286-295</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)