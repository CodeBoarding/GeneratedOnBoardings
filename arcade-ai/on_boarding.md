```mermaid
graph LR
    Arcade_Core["Arcade Core"]
    Serving_Layer["Serving Layer"]
    Developer_CLI["Developer CLI"]
    Toolkits["Toolkits"]
    Framework_Adapters["Framework Adapters"]
    Evaluation_Framework["Evaluation Framework"]
    Developer_CLI -- "Manages Deployments of" --> Toolkits
    Developer_CLI -- "Deploys to" --> Serving_Layer
    Toolkits -- "Implements" --> Arcade_Core
    Framework_Adapters -- "Consumes Tools from" --> Serving_Layer
    Serving_Layer -- "Executes Tools using" --> Arcade_Core
    Evaluation_Framework -- "Validates" --> Toolkits
    Evaluation_Framework -- "Tests using" --> Arcade_Core
    click Arcade_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/arcade-ai/Arcade_Core.md" "Details"
    click Serving_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/arcade-ai/Serving_Layer.md" "Details"
    click Evaluation_Framework href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/arcade-ai/Evaluation_Framework.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

An analysis of the Arcade AI platform's architecture, based on the provided context and Control Flow Graph (CFG) data, reveals a modular and scalable system designed for developing and serving AI agent tools. The platform's components are clearly delineated, with `arcade-core` serving as the central hub providing foundational abstractions and execution logic. The primary workflow involves developers creating `Toolkits` using these core abstractions, which are then deployed to the `Serving Layer` via the `Developer CLI`. Once live, these tools are consumed by AI agents, a process simplified by `Framework Adapters`. The `Evaluation Framework` supports this lifecycle by enabling robust testing and validation of the toolkits.

### Arcade Core [[Expand]](./Arcade_Core.md)
The foundational engine providing core abstractions, data schemas (`Toolkit`), and the `ToolExecutor` for running tools. It is the central dependency for all other platform components.


**Related Classes/Methods**:

- `arcade_core.catalog`
- `arcade_core.executor`
- `arcade_core.toolkit`


### Serving Layer [[Expand]](./Serving_Layer.md)
Exposes toolkits over a network via a worker-based system (`FastAPIWorker`). It handles incoming requests from AI agents and orchestrates tool execution using Arcade Core.


**Related Classes/Methods**:

- `arcade_serve.fastapi.worker`
- `arcade_serve.mcp.server`


### Developer CLI
The primary interface for developers. It provides commands to package, deploy, and manage toolkits on the Serving Layer, and handles developer authentication.


**Related Classes/Methods**:

- `arcade_cli.main`
- `arcade_cli.deployment.packages`


### Toolkits
User-created packages containing the business logic for a set of tools. They are built using the abstractions provided by Arcade Core.


**Related Classes/Methods**:

- `toolkits.postgres.arcade_postgres.database_engine`


### Framework Adapters
A set of modules that act as clients to the Serving Layer, enabling seamless integration and consumption of Arcade tools within popular AI agent frameworks like LangChain.


**Related Classes/Methods**:

- `contrib.langchain.langchain_arcade.manager`
- `contrib.crewai.crewai_arcade.manager`


### Evaluation Framework [[Expand]](./Evaluation_Framework.md)
Provides the necessary tools (`EvalSuite`, `Critic`) to test and validate the functionality and performance of toolkits, interacting directly with the core execution logic.


**Related Classes/Methods**:

- `arcade_evals.eval`
- `arcade_evals.critic`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)