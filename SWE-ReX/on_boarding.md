```mermaid
graph LR
    External_Clients["External Clients"]
    API_Gateway["API Gateway"]
    Runtime_Core["Runtime Core"]
    Execution_Engines["Execution Engines"]
    Deployment_Orchestrator["Deployment Orchestrator"]
    Cloud_Service_Utilities["Cloud Service Utilities"]
    External_Clients -- "sends requests to" --> API_Gateway
    API_Gateway -- "delegates requests to" --> Runtime_Core
    Execution_Engines -- "implements" --> Runtime_Core
    API_Gateway -- "uses" --> Runtime_Core
    Execution_Engines -- "interacts with" --> API_Gateway
    Deployment_Orchestrator -- "manages and provisions" --> Execution_Engines
    Deployment_Orchestrator -- "utilizes" --> Cloud_Service_Utilities
    Execution_Engines -- "returns results via" --> Runtime_Core
    Runtime_Core -- "forwards results to" --> API_Gateway
    API_Gateway -- "sends responses to" --> External_Clients
    click API_Gateway href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/SWE-ReX/API_Gateway.md" "Details"
    click Runtime_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/SWE-ReX/Runtime_Core.md" "Details"
    click Execution_Engines href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/SWE-ReX/Execution_Engines.md" "Details"
    click Deployment_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/SWE-ReX/Deployment_Orchestrator.md" "Details"
    click Cloud_Service_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/SWE-ReX/Cloud_Service_Utilities.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Remote Execution Framework / Sandboxed Environment Orchestration for AI Agents

### External Clients
Represents AI agents or other external systems that initiate requests for sandboxed code execution and interact with the SWE-ReX system.


**Related Classes/Methods**: _None_

### API Gateway [[Expand]](./API_Gateway.md)
The primary external interface of SWE-ReX. It exposes RESTful API endpoints (e.g., /create_session, /execute, /read_file) to receive commands, handles request parsing, and delegates execution to the appropriate Runtime Core.


**Related Classes/Methods**:

- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/server.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.server` (1:1)</a>


### Runtime Core [[Expand]](./Runtime_Core.md)
Defines the fundamental abstract interface (AbstractRuntime) and common data models (Pydantic models) for command execution, observations, and session management within sandboxed environments. It serves as the contract that all concrete execution engines must adhere to.


**Related Classes/Methods**:

- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/runtime/abstract.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.runtime.abstract` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/runtime/config.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.runtime.config` (1:1)</a>


### Execution Engines [[Expand]](./Execution_Engines.md)
Provides concrete implementations for executing commands within sandboxed environments. This includes LocalRuntime for direct execution on the host system (leveraging BashSession) and RemoteRuntime for interacting with a remote SWE-ReX instance via HTTP, acting as a client.


**Related Classes/Methods**:

- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/runtime/local.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.runtime.local` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/runtime/remote.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.runtime.remote` (1:1)</a>


### Deployment Orchestrator [[Expand]](./Deployment_Orchestrator.md)
Manages the lifecycle (provisioning, starting, and stopping) of sandboxed execution environments across various platforms (e.g., Docker, AWS Fargate, Modal, Local). It defines the abstract deployment interface (AbstractDeployment) and incorporates deployment hooks for custom logic.


**Related Classes/Methods**:

- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/abstract.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.abstract` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/config.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.config` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/docker.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.docker` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/fargate.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.fargate` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/modal.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.modal` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/local.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.local` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/remote.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.remote` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/hooks/abstract.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.hooks.abstract` (1:1)</a>
- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/deployment/hooks/status.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.deployment.hooks.status` (1:1)</a>


### Cloud Service Utilities [[Expand]](./Cloud_Service_Utilities.md)
A collection of helper functions and wrappers for interacting with specific cloud services (e.g., AWS Boto3). These utilities are crucial for supporting the provisioning and management of cloud-based sandboxed environments by the Deployment Orchestrator.


**Related Classes/Methods**:

- <a href="https://github.com/synth-laboratories/SWE-ReX/src/swerex/utils/aws.py#L1-L1" target="_blank" rel="noopener noreferrer">`src.swerex.utils.aws` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)