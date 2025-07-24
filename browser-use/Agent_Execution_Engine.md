```mermaid
graph LR
    Agent_Execution_Engine["Agent Execution Engine"]
    LLM_Integration_Layer["LLM Integration Layer"]
    Browser_Automation_Core["Browser Automation Core"]
    Protocol_Adapter["Protocol Adapter"]
    Async_Execution_Manager["Async Execution Manager"]
    File_System_Interface["File System Interface"]
    Plugin_System["Plugin System"]
    Configuration_Manager["Configuration Manager"]
    Agent_Execution_Engine -- "uses" --> Protocol_Adapter
    Agent_Execution_Engine -- "uses" --> LLM_Integration_Layer
    Agent_Execution_Engine -- "uses" --> Browser_Automation_Core
    Agent_Execution_Engine -- "uses" --> File_System_Interface
    Agent_Execution_Engine -- "uses" --> Configuration_Manager
    Browser_Automation_Core -- "uses" --> Async_Execution_Manager
    LLM_Integration_Layer -- "extends" --> Plugin_System
    click Agent_Execution_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Agent_Execution_Engine.md" "Details"
    click LLM_Integration_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/LLM_Integration_Layer.md" "Details"
    click Browser_Automation_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Browser_Automation_Core.md" "Details"
    click Protocol_Adapter href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Protocol_Adapter.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Agent Execution Engine [[Expand]](./Agent_Execution_Engine.md)
Central AI logic orchestrating browser automation, LLM decision-making, and task planning.


**Related Classes/Methods**:

- `browser_use.agent.Agent` (10:45)
- <a href="https://github.com/browser-use/browser-use/blob/main/browser_use/browser/session.py#L205-L4684" target="_blank" rel="noopener noreferrer">`browser_use.browser.session.BrowserSession` (205:4684)</a>


### LLM Integration Layer [[Expand]](./LLM_Integration_Layer.md)
Standardized abstraction for multi-provider LLM interactions (OpenAI, etc.).


**Related Classes/Methods**:

- <a href="https://github.com/browser-use/browser-use/blob/main/browser_use/llm/base.py#L12-L60" target="_blank" rel="noopener noreferrer">`browser_use.llm.base.BaseChatModel` (12:60)</a>
- `browser_use.llm.providers.OpenAIProvider` (5:25)


### Browser Automation Core [[Expand]](./Browser_Automation_Core.md)
Playwright-based browser control and DOM manipulation engine.


**Related Classes/Methods**:

- <a href="https://github.com/browser-use/browser-use/blob/main/browser_use/browser/session.py#L205-L4684" target="_blank" rel="noopener noreferrer">`browser_use.browser.session.BrowserSession` (205:4684)</a>
- `browser_use.browser.dom.DOMElement` (3:15)


### Protocol Adapter [[Expand]](./Protocol_Adapter.md)
MCP protocol implementation for interoperability with external systems.


**Related Classes/Methods**:

- `browser_use.protocol.mcp_adapter.MCPAdapter` (20:50)
- `browser_use.mcp.server.BrowserUseServer`


### Async Execution Manager
Asyncio-based task scheduler for non-blocking browser/LLM operations.


**Related Classes/Methods**:

- `browser_use.async.task_manager.TaskManager` (10:40)


### File System Interface
Abstraction layer for persistent storage of agent states and browser profiles.


**Related Classes/Methods**:

- <a href="https://github.com/browser-use/browser-use/blob/main/browser_use/filesystem/file_system.py#L21-L77" target="_blank" rel="noopener noreferrer">`browser_use.filesystem.file_system.BaseFile` (21:77)</a>


### Plugin System
Modular extension framework for adding LLM providers and browser capabilities.


**Related Classes/Methods**:

- `browser_use.plugins.PluginLoader` (5:25)


### Configuration Manager
Runtime configuration handler for agent parameters and environment settings.


**Related Classes/Methods**:

- <a href="https://github.com/browser-use/browser-use/blob/main/browser_use/config.py#L237-L242" target="_blank" rel="noopener noreferrer">`browser_use.config.AgentEntry` (237:242)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)