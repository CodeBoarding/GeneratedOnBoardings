```mermaid
graph LR
    Agent_Framework_Integrations["Agent Framework Integrations"]
    copilotkit_agent_Agent["copilotkit.agent.Agent"]
    copilotkit_crewai_crewai_agent_CrewAIAgent["copilotkit.crewai.crewai_agent.CrewAIAgent"]
    copilotkit_langgraph_agent_LangGraphAgent["copilotkit.langgraph_agent.LangGraphAgent"]
    CrewAI_Framework["CrewAI Framework"]
    LangGraph_Framework["LangGraph Framework"]
    copilotkit_crewai_crewai_agent_CrewAIAgent -- "implements/adapts" --> copilotkit_agent_Agent
    copilotkit_langgraph_agent_LangGraphAgent -- "implements/adapts" --> copilotkit_agent_Agent
    copilotkit_crewai_crewai_agent_CrewAIAgent -- "utilizes" --> CrewAI_Framework
    copilotkit_langgraph_agent_LangGraphAgent -- "utilizes" --> LangGraph_Framework
    click Agent_Framework_Integrations href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CopilotKit/Agent_Framework_Integrations.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Agent Framework Integrations [[Expand]](./Agent_Framework_Integrations.md)
This component is responsible for integrating external AI agent frameworks like LangGraph and CrewAI into CopilotKit. It provides specific adapters and wrappers that translate the functionalities of these frameworks into a unified `Agent Abstraction Layer`, ensuring seamless interoperability within the CopilotKit ecosystem. This allows CopilotKit to leverage diverse agent capabilities without being tightly coupled to any single framework.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/agent.py#L14-L65" target="_blank" rel="noopener noreferrer">`copilotkit.agent.Agent` (14:65)</a>
- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/crewai/crewai_agent.py#L1-L1" target="_blank" rel="noopener noreferrer">`copilotkit.crewai.crewai_agent.CrewAIAgent` (1:1)</a>
- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/langgraph_agent.py#L84-L717" target="_blank" rel="noopener noreferrer">`copilotkit.langgraph_agent.LangGraphAgent` (84:717)</a>
- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/langgraph.py#L1-L1" target="_blank" rel="noopener noreferrer">`copilotkit.langgraph` (1:1)</a>
- `copilotkit.crewai` (1:1)


### copilotkit.agent.Agent
Defines the common interface and contract for all agents integrated into CopilotKit. It acts as the target abstraction that external agent frameworks must conform to.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/agent.py#L14-L65" target="_blank" rel="noopener noreferrer">`copilotkit.agent.Agent` (14:65)</a>


### copilotkit.crewai.crewai_agent.CrewAIAgent
This component specifically adapts the CrewAI framework's functionalities to adhere to the `copilotkit.agent.Agent` interface. It encapsulates CrewAI-specific logic and exposes it through the generic agent abstraction.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/crewai/crewai_agent.py#L1-L1" target="_blank" rel="noopener noreferrer">`copilotkit.crewai.crewai_agent.CrewAIAgent` (1:1)</a>


### copilotkit.langgraph_agent.LangGraphAgent
Similar to the CrewAI adapter, this component adapts the LangGraph framework to the `copilotkit.agent.Agent` interface. It handles LangGraph-specific workflows and exposes them uniformly.


**Related Classes/Methods**:

- <a href="https://github.com/CopilotKit/CopilotKit/blob/main/sdk-python/copilotkit/langgraph_agent.py#L84-L717" target="_blank" rel="noopener noreferrer">`copilotkit.langgraph_agent.LangGraphAgent` (84:717)</a>


### CrewAI Framework
An external AI agent framework utilized by CopilotKit's `CrewAIAgent`.


**Related Classes/Methods**: _None_

### LangGraph Framework
An external AI agent framework utilized by CopilotKit's `LangGraphAgent`.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)