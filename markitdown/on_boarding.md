```mermaid
graph LR
    CLI_API_Interface["CLI/API Interface"]
    Core_Conversion_Engine["Core Conversion Engine"]
    Converter_Plugins["Converter Plugins"]
    Input_Output_Management["Input/Output Management"]
    External_Service_Connectors["External Service Connectors"]
    MCP_Server["MCP Server"]
    CLI_API_Interface -- "invokes" --> Core_Conversion_Engine
    Core_Conversion_Engine -- "orchestrates" --> Converter_Plugins
    Core_Conversion_Engine -- "interacts with" --> Input_Output_Management
    Converter_Plugins -- "utilize" --> External_Service_Connectors
    Converter_Plugins -- "process data from" --> Input_Output_Management
    MCP_Server -- "utilizes" --> Core_Conversion_Engine
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### CLI/API Interface
Provides the command-line and programmatic entry points for users to interact with the markitdown library, handling argument parsing and initiating conversion workflows.


**Related Classes/Methods**:



### Core Conversion Engine
The central orchestrator for document conversion. It manages the lifecycle of converters (including plugin loading and registration), dispatches conversion requests to appropriate converters, and handles the overall input/output flow.


**Related Classes/Methods**:



### Converter Plugins
A collection of specialized plugins, each responsible for converting a specific document type (e.g., PDF, DOCX, HTML, Images) into a standardized markdown format. These components encapsulate the logic for handling different file formats and implement the Base Converter Interface.


**Related Classes/Methods**:



### Input/Output Management
Manages the abstraction of input sources (files, URIs, streams) and output destinations, providing a unified way for the Core Conversion Engine to access and store data regardless of its origin or final destination.


**Related Classes/Methods**:



### External Service Connectors
Encapsulates interactions with third-party services, such as Azure Document Intelligence for advanced document analysis or OpenAI for LLM-based content generation.


**Related Classes/Methods**:



### MCP Server
Acts as a backend service, exposing an HTTP API to provide document conversion capabilities over a network, enabling remote access to the markitdown functionality.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)