```mermaid
graph LR
    CLI_Layer["CLI Layer"]
    Core_Application_Logic["Core Application Logic"]
    Configuration_Management["Configuration Management"]
    LLM_Integration_Layer["LLM Integration Layer"]
    LSP_Integration_Layer["LSP Integration Layer"]
    Model_Context_Protocol_MCP_Layer["Model Context Protocol (MCP) Layer"]
    Terminal_UI_Output["Terminal UI/Output"]
    CLI_Layer -- "initiates requests to" --> Core_Application_Logic
    Core_Application_Logic -- "retrieves and applies application settings from" --> Configuration_Management
    Core_Application_Logic -- "sends LLM requests to and receives responses from" --> LLM_Integration_Layer
    Core_Application_Logic -- "requests and receives code context from" --> LSP_Integration_Layer
    Core_Application_Logic -- "exchanges model-specific context data with" --> Model_Context_Protocol_MCP_Layer
    Core_Application_Logic -- "sends data for display to" --> Terminal_UI_Output
    click CLI_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/CLI_Layer.md" "Details"
    click Core_Application_Logic href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Core_Application_Logic.md" "Details"
    click Configuration_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Configuration_Management.md" "Details"
    click LLM_Integration_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/LLM_Integration_Layer.md" "Details"
    click LSP_Integration_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/LSP_Integration_Layer.md" "Details"
    click Model_Context_Protocol_MCP_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Model_Context_Protocol_MCP_Layer.md" "Details"
    click Terminal_UI_Output href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/crush/Terminal_UI_Output.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of a Go project, mapping conceptual components to likely Go directories/files. Due to the project being Go and available tools being Python-specific, direct source code retrieval and precise line-number references are not possible. Source paths are inferred based on common Go project structures.

### CLI Layer [[Expand]](./CLI_Layer.md)
Serves as the primary user interface, responsible for parsing command-line arguments, subcommands, and user input, translating them into actionable requests.


**Related Classes/Methods**:

- `internal/cmd/root.go` (1:1)
- `internal/cmd/run.go` (1:1)
- `internal/cmd/logs.go` (1:1)
- `internal/cmd/schema.go` (1:1)


### Core Application Logic [[Expand]](./Core_Application_Logic.md)
The central orchestrator, managing sessions, maintaining context, and coordinating interactions between all other components. It processes user requests and directs them to appropriate backend services.


**Related Classes/Methods**:

- `internal/app/app.go` (1:1)
- `internal/app/lsp.go` (1:1)


### Configuration Management [[Expand]](./Configuration_Management.md)
Handles the loading, merging, and validation of application configurations from various sources, ensuring the application operates with correct parameters.


**Related Classes/Methods**:

- `internal/config/config.go` (1:1)
- `internal/config/load.go` (1:1)
- `internal/config/merge.go` (1:1)


### LLM Integration Layer [[Expand]](./LLM_Integration_Layer.md)
Provides an abstract interface for interacting with various Large Language Model (LLM) providers, managing API calls, request/response formatting, and abstracting provider-specific complexities.


**Related Classes/Methods**: _None_

### LSP Integration Layer [[Expand]](./LSP_Integration_Layer.md)
Manages client connections to Language Server Protocol (LSP) servers, sending requests and processing responses to gather code context.


**Related Classes/Methods**:

- `internal/app/lsp.go` (1:1)


### Model Context Protocol (MCP) Layer [[Expand]](./Model_Context_Protocol_MCP_Layer.md)
Manages interactions with Model Context Protocol (MCP) servers, supporting different transport types and facilitating the exchange of model-specific context data.


**Related Classes/Methods**: _None_

### Terminal UI/Output [[Expand]](./Terminal_UI_Output.md)
Dedicated to rendering all application output to the terminal, ensuring a consistent, user-friendly, and responsive experience.


**Related Classes/Methods**:

- `internal/ansiext/ansi.go` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)