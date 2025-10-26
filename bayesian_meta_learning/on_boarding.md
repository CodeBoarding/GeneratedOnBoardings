```mermaid
graph LR
    Agent_Implementations["Agent Implementations"]
    Task_Orchestrator["Task Orchestrator"]
    Bayesian_Learning_Engine["Bayesian Learning Engine"]
    Strategy_Repository["Strategy Repository"]
    LLM_Adapters["LLM Adapters"]
    Performance_Evaluator["Performance Evaluator"]
    Task_Definition_Module["Task Definition Module"]
    Agent_Implementations -- "initiates task and passes to" --> Task_Orchestrator
    Task_Orchestrator -- "requests strategy recommendation from" --> Bayesian_Learning_Engine
    Task_Orchestrator -- "retrieves strategy from" --> Strategy_Repository
    Task_Orchestrator -- "utilizes" --> Task_Definition_Module
    Task_Orchestrator -- "invokes" --> LLM_Adapters
    Task_Orchestrator -- "submits output to" --> Performance_Evaluator
    Bayesian_Learning_Engine -- "provides strategy insights to" --> Task_Orchestrator
    Bayesian_Learning_Engine -- "receives evaluation results from" --> Performance_Evaluator
    Strategy_Repository -- "provides strategy to" --> Task_Orchestrator
    LLM_Adapters -- "returns response to" --> Task_Orchestrator
    Performance_Evaluator -- "provides evaluation results to" --> Bayesian_Learning_Engine
    Task_Definition_Module -- "provides task structure to" --> Task_Orchestrator
    click Task_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/bayesian_meta_learning/Task_Orchestrator.md" "Details"
    click Bayesian_Learning_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/bayesian_meta_learning/Bayesian_Learning_Engine.md" "Details"
    click LLM_Adapters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/bayesian_meta_learning/LLM_Adapters.md" "Details"
    click Performance_Evaluator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/bayesian_meta_learning/Performance_Evaluator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `bayesian_meta_learning` project is architected as a self-improving AI system, designed around a robust feedback loop for optimizing strategy selection in LLM-driven tasks. At its core, the Task Orchestrator acts as the central coordinator, initiating task execution based on inputs from Agent Implementations. It dynamically selects strategies by consulting the Bayesian Learning Engine, which maintains and updates probabilistic priors based on past performance, and retrieves these strategies from the Strategy Repository. Interactions with external Large Language Models are abstracted through LLM Adapters. The outputs are then rigorously evaluated by the Performance Evaluator, with results feeding back into the Bayesian Learning Engine to refine future strategy choices. This continuous cycle, supported by the structured task definitions from the Task Definition Module, enables the system to adapt and improve its performance over time, making it highly suitable for dynamic AI/ML applications requiring adaptive strategy management.

### Agent Implementations
Entry points for specific applications (e.g., LLM judging, code generation) that initiate the meta-learning process.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/examples/llm_judge_agent.py" target="_blank" rel="noopener noreferrer">`examples/llm_judge_agent.py`</a>
- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/examples/code_generation_agent.py" target="_blank" rel="noopener noreferrer">`examples/code_generation_agent.py`</a>


### Task Orchestrator [[Expand]](./Task_Orchestrator.md)
The central control unit managing the entire meta-learning feedback loop, coordinating strategy selection, LLM interaction, performance evaluation, and Bayesian updates.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/core/controller.py" target="_blank" rel="noopener noreferrer">`core/controller.py`</a>


### Bayesian Learning Engine [[Expand]](./Bayesian_Learning_Engine.md)
Implements the core meta-learning algorithm, maintaining and updating probabilistic priors for strategies based on their observed performance, guiding strategy selection.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/core/bayesian_prior.py" target="_blank" rel="noopener noreferrer">`core/bayesian_prior.py`</a>


### Strategy Repository
A module responsible for storing, managing, and providing access to a collection of predefined strategies.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/strategies/default_strategies.py" target="_blank" rel="noopener noreferrer">`strategies/default_strategies.py`</a>


### LLM Adapters [[Expand]](./LLM_Adapters.md)
A set of interfaces that abstract interactions with various external Large Language Models (e.g., GPT-4o), ensuring modularity and extensibility.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/adapters/base_adapter.py" target="_blank" rel="noopener noreferrer">`adapters/base_adapter.py`</a>
- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/adapters/gpt4o_adapter.py" target="_blank" rel="noopener noreferrer">`adapters/gpt4o_adapter.py`</a>


### Performance Evaluator [[Expand]](./Performance_Evaluator.md)
Assesses the quality and effectiveness of the outputs generated by the LLM based on the chosen strategy, providing crucial feedback for the Bayesian update process.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/examples/llm_judge_agent.py" target="_blank" rel="noopener noreferrer">`examples/llm_judge_agent.py`</a>
- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/examples/code_generation_agent.py" target="_blank" rel="noopener noreferrer">`examples/code_generation_agent.py`</a>


### Task Definition Module
Defines the data structures, schemas, and types for various tasks, ensuring consistent input and output formats across the system.


**Related Classes/Methods**:

- <a href="https://github.com/allthingssecurity/bayesian_meta_learning/blob/main/core/task.py" target="_blank" rel="noopener noreferrer">`core/task.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)