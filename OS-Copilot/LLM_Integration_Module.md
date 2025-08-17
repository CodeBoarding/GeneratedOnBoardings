```mermaid
graph LR
    LLM_Orchestrator["LLM Orchestrator"]
    OLLAMA_Integration["OLLAMA Integration"]
    Prompt_Generation["Prompt Generation"]
    Prompt_Dispatcher["Prompt Dispatcher"]
    Prompt_Generation -- "provides prompts to" --> Prompt_Dispatcher
    Prompt_Dispatcher -- "delegates to" --> LLM_Orchestrator
    LLM_Orchestrator -- "initiates communication with" --> OLLAMA_Integration
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The LLM subsystem within {project_name} is designed to manage interactions with Large Language Models, focusing on prompt handling and communication. The Prompt Generation component is responsible for crafting and formatting prompts, which are then passed to the Prompt Dispatcher. The Prompt Dispatcher serves as the unified entry point for external modules to initiate LLM interactions, delegating these requests to the LLM Orchestrator. The LLM Orchestrator acts as the central coordinator, directing the interaction to the specific LLM implementation, such as the OLLAMA Integration, which handles the direct communication with the OLLAMA LLM service. The LLM Communication Handler has been removed as a distinct active component.

### LLM Orchestrator
Acts as the central control point for managing the overall flow of LLM interactions. It coordinates the use of other components to achieve LLM-related tasks, such as directing requests to the appropriate LLM integration.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/utils/llms.py#L135-L147" target="_blank" rel="noopener noreferrer">`oscopilot.utils.llms.main`:135-147</a>


### OLLAMA Integration
Encapsulates the specific logic and API calls required for interacting with the OLLAMA LLM. This component provides the concrete implementation for OLLAMA-specific communication, handling the direct sending of prompts and receiving of responses.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/utils/llms.py#L73-L133" target="_blank" rel="noopener noreferrer">`oscopilot.utils.llms.OLLAMA`:73-133</a>


### Prompt Generation
Responsible for constructing and formatting prompts tailored for the LLMs, ensuring proper input structure and content. This involves prompt engineering, context injection, and managing prompt templates.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/prompts" target="_blank" rel="noopener noreferrer">`oscopilot.prompts`</a>


### Prompt Dispatcher
Provides a high-level, unified interface for external modules (e.g., Agent Core) to send chat prompts to the LLM subsystem, abstracting underlying implementation details. It acts as the public-facing entry point for initiating LLM interactions.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/utils/utils.py#L319-L337" target="_blank" rel="noopener noreferrer">`oscopilot.utils.utils.send_chat_prompts`:319-337</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)