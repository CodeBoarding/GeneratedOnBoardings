```mermaid
graph LR
    Core_Orchestrator["Core Orchestrator"]
    NLP_Processor["NLP Processor"]
    Messaging_Platform_Adapter["Messaging Platform Adapter"]
    LLM_Integration["LLM Integration"]
    Memory_Manager["Memory Manager"]
    Tool_Executor["Tool Executor"]
    Plugin_Manager["Plugin Manager"]
    Event_Bus["Event Bus"]
    NLP_Processor -- "sends interpreted intent to" --> Core_Orchestrator
    Core_Orchestrator -- "sends requests to" --> LLM_Integration
    Core_Orchestrator -- "queries/updates" --> Memory_Manager
    Core_Orchestrator -- "requests execution from" --> Tool_Executor
    Core_Orchestrator -- "requests execution from" --> Plugin_Manager
    Core_Orchestrator -- "publishes events to" --> Event_Bus
    Event_Bus -- "delivers events to" --> Core_Orchestrator
    Core_Orchestrator -- "sends responses to" --> Messaging_Platform_Adapter
    Messaging_Platform_Adapter -- "sends raw messages to" --> NLP_Processor
    LLM_Integration -- "returns responses to" --> Core_Orchestrator
    Memory_Manager -- "provides context to" --> Core_Orchestrator
    Tool_Executor -- "returns results to" --> Core_Orchestrator
    Plugin_Manager -- "returns results to" --> Core_Orchestrator
    click Core_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/MaiBot/Core_Orchestrator.md" "Details"
    click LLM_Integration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/MaiBot/LLM_Integration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Core Orchestrator [[Expand]](./Core_Orchestrator.md)
The central control unit and "brain" of MaiBot. It interprets user intent, orchestrates the entire conversational flow, and coordinates interactions between all other components to generate appropriate bot responses. It manages the overall conversational state, decision-making, and the sequence of operations (e.g., memory lookup, tool invocation, LLM interaction).


**Related Classes/Methods**:

- `maibot.core.orchestrator.Orchestrator` (1:1)
- `maibot.core.event_bus.EventBus` (1:1)


### NLP Processor
Responsible for processing natural language input from users to extract intent, entities, and other linguistic features necessary for the `Core Orchestrator` to understand the user's request.


**Related Classes/Methods**: _None_

### Messaging Platform Adapter
Handles the interface with external messaging platforms (e.g., Telegram, Discord, web chat). It translates incoming messages into a standardized internal format for the `NLP Processor` and `Core Orchestrator`, and formats outgoing responses for the specific platform.


**Related Classes/Methods**: _None_

### LLM Integration [[Expand]](./LLM_Integration.md)
Manages all interactions with Large Language Models (LLMs). It is responsible for formatting prompts, sending requests to the LLM, and processing the LLM's responses, often integrating with external LLM APIs.


**Related Classes/Methods**: _None_

### Memory Manager
Manages the conversational memory and state for the bot. This includes short-term context, long-term knowledge, and user-specific information, providing the `Core Orchestrator` with the necessary context for coherent conversations.


**Related Classes/Methods**: _None_

### Tool Executor
Responsible for executing various external tools and functionalities that the `Core Orchestrator` determines are necessary to fulfill a user's request (e.g., fetching data, performing calculations, interacting with external APIs).


**Related Classes/Methods**: _None_

### Plugin Manager
Manages the loading, lifecycle, and integration of external plugins. It allows the system to be extended with new functionalities and behaviors without modifying the core codebase, supporting the modular/plugin architecture.


**Related Classes/Methods**: _None_

### Event Bus
Facilitates decoupled communication between all components through an event-driven mechanism. Components publish events when something happens, and other components subscribe to events they are interested in, promoting loose coupling and scalability.


**Related Classes/Methods**:

- `maibot.core.event_bus.EventBus` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)