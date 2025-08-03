```mermaid
graph LR
    Core_Application_Logic["Core Application Logic"]
    Command_Line_Interface_CLI_Layer["Command-Line Interface (CLI) Layer"]
    Configuration_Management["Configuration Management"]
    LLM_Integration_Layer["LLM Integration Layer"]
    LSP_Integration_Layer["LSP Integration Layer"]
    Model_Context_Protocol_MCP_Layer["Model Context Protocol (MCP) Layer"]
    Terminal_UI_Output["Terminal UI/Output"]
    Utility_Shared_Components["Utility/Shared Components"]
    Command_Line_Interface_CLI_Layer -- "delegates parsed commands and user input to" --> Core_Application_Logic
    Core_Application_Logic -- "sends prompts and requests to" --> LLM_Integration_Layer
    LLM_Integration_Layer -- "returns generated responses and model outputs to" --> Core_Application_Logic
    Core_Application_Logic -- "requests code context from" --> LSP_Integration_Layer
    LSP_Integration_Layer -- "provides structured code context to" --> Core_Application_Logic
    Core_Application_Logic -- "exchanges detailed model context data with" --> Model_Context_Protocol_MCP_Layer
    Model_Context_Protocol_MCP_Layer -- "exchanges detailed model context data with" --> Core_Application_Logic
    Core_Application_Logic -- "queries for application settings and API keys" --> Configuration_Management
    Configuration_Management -- "provides validated configuration data to" --> Core_Application_Logic
    Core_Application_Logic -- "sends data and messages to" --> Terminal_UI_Output
    Core_Application_Logic -- "utilizes for common services" --> Utility_Shared_Components
    Command_Line_Interface_CLI_Layer -- "utilizes for common services" --> Utility_Shared_Components
    Configuration_Management -- "utilizes for common services" --> Utility_Shared_Components
    LLM_Integration_Layer -- "utilizes for common services" --> Utility_Shared_Components
    LSP_Integration_Layer -- "utilizes for common services" --> Utility_Shared_Components
    Model_Context_Protocol_MCP_Layer -- "utilizes for common services" --> Utility_Shared_Components
    Terminal_UI_Output -- "utilizes for common services" --> Utility_Shared_Components
    click Core_Application_Logic href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Core_Application_Logic.md" "Details"
    click Configuration_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Configuration_Management.md" "Details"
    click LLM_Integration_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/LLM_Integration_Layer.md" "Details"
    click LSP_Integration_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/LSP_Integration_Layer.md" "Details"
    click Model_Context_Protocol_MCP_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Model_Context_Protocol_MCP_Layer.md" "Details"
    click Terminal_UI_Output href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Terminal_UI_Output.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Core Application Logic [[Expand]](./Core_Application_Logic.md)
The central orchestrator, managing sessions, maintaining context, and coordinating interactions between all other components. It processes user requests and directs them to appropriate backend services.


**Related Classes/Methods**:

- `internal/app/app.go` (1:1)
- `internal/app/lsp.go` (1:1)


### Command-Line Interface (CLI) Layer
Responsible for parsing command-line arguments, handling subcommands, and managing user input. It serves as the primary interface for user interaction.


**Related Classes/Methods**:

- `cmd/root.go` (1:1)
- `cmd/generate.go` (1:1)


### Configuration Management [[Expand]](./Configuration_Management.md)
Handles loading, merging, and validating application configurations from various sources (e.g., local files, environment variables, global settings).


**Related Classes/Methods**:

- `internal/config/config.go` (1:1)


### LLM Integration Layer [[Expand]](./LLM_Integration_Layer.md)
Provides an abstraction layer for interacting with various Large Language Model (LLM) providers (e.g., OpenAI, Anthropic, Google Gemini). It manages API calls, request/response formatting, and provider-specific error handling.


**Related Classes/Methods**:

- `internal/llm/provider.go` (1:1)
- `internal/llm/openai.go` (1:1)


### LSP Integration Layer [[Expand]](./LSP_Integration_Layer.md)
Manages connections with Language Server Protocol (LSP) clients, sending requests for code context (e.g., definitions, references) and processing their responses.


**Related Classes/Methods**:

- `internal/lsp/client.go` (1:1)
- `internal/lsp/protocol.go` (1:1)


### Model Context Protocol (MCP) Layer [[Expand]](./Model_Context_Protocol_MCP_Layer.md)
Manages interactions with Model Context Protocol (MCP) servers, supporting various transport types (stdio, HTTP, SSE) for efficient data exchange related to model context.


**Related Classes/Methods**:

- `internal/mcp/server.go` (1:1)
- `internal/mcp/http.go` (1:1)


### Terminal UI/Output [[Expand]](./Terminal_UI_Output.md)
Responsible for rendering all application output to the terminal, ensuring a consistent, readable, and user-friendly experience.


**Related Classes/Methods**:

- `internal/ui/printer.go` (1:1)
- `internal/ui/styles.go` (1:1)


### Utility/Shared Components
Contains common functionalities and helper modules used across multiple components, such as logging, error handling, data structures, and general-purpose utilities.


**Related Classes/Methods**:

- `internal/util/logger.go` (1:1)
- `internal/util/errors.go` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)