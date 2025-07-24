```mermaid
graph LR
    CopilotKit_SDK_Core["CopilotKit SDK Core"]
    Remote_Endpoint_Communication["Remote Endpoint Communication"]
    Agent_Abstraction_Layer["Agent Abstraction Layer"]
    Agent_Framework_Integrations["Agent Framework Integrations"]
    CopilotKit_SDK_Core -- "utilizes" --> Remote_Endpoint_Communication
    CopilotKit_SDK_Core -- "orchestrates" --> Agent_Abstraction_Layer
    Agent_Abstraction_Layer -- "is implemented by" --> Agent_Framework_Integrations
    click CopilotKit_SDK_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CopilotKit/CopilotKit_SDK_Core.md" "Details"
    click Remote_Endpoint_Communication href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CopilotKit/Remote_Endpoint_Communication.md" "Details"
    click Agent_Abstraction_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CopilotKit/Agent_Abstraction_Layer.md" "Details"
    click Agent_Framework_Integrations href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CopilotKit/Agent_Framework_Integrations.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### CopilotKit SDK Core [[Expand]](./CopilotKit_SDK_Core.md)
The central programmatic interface for developers, orchestrating AI capabilities, managing agent lifecycles, and providing a unified API for integrating CopilotKit into backend applications. It acts as the primary orchestrator of AI interactions.


**Related Classes/Methods**:

- `copilotkit.sdk`


### Remote Endpoint Communication [[Expand]](./Remote_Endpoint_Communication.md)
Responsible for all network-level communication, handling API requests, responses, and data serialization/deserialization between the SDK and external CopilotKit services or AI providers. It ensures secure and efficient data exchange.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/protocol.py#L1-L1" target="_blank" rel="noopener noreferrer">`copilotkit.protocol` (1:1)</a>


### Agent Abstraction Layer [[Expand]](./Agent_Abstraction_Layer.md)
Defines a standardized interface or contract for all AI agents within the CopilotKit ecosystem. This layer ensures interoperability, allowing the SDK Core to interact uniformly with diverse agent frameworks.


**Related Classes/Methods**:

- `copilotkit.agent`


### Agent Framework Integrations [[Expand]](./Agent_Framework_Integrations.md)
Contains specific adapters and wrappers (e.g., for LangGraph, CrewAI) that enable popular AI agent frameworks to conform to the Agent Abstraction Layer. This component facilitates the seamless integration and utilization of various agent technologies within CopilotKit.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/langgraph.py#L1-L1" target="_blank" rel="noopener noreferrer">`copilotkit.langgraph` (1:1)</a>
- `copilotkit.crewai` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)