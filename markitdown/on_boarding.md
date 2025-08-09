```mermaid
graph LR
    Core_Conversion_Engine["Core Conversion Engine"]
    Converter_Framework["Converter Framework"]
    Format_Specific_Converters["Format-Specific Converters"]
    Input_Output_Stream_Handlers["Input/Output Stream Handlers"]
    User_Interfaces_CLI_MCP_Server_["User Interfaces (CLI & MCP Server)"]
    Plugin_System["Plugin System"]
    Document_Pre_processing_Utilities["Document Pre-processing Utilities"]
    Core_Conversion_Engine -- "orchestrates" --> Format_Specific_Converters
    Core_Conversion_Engine -- "utilizes" --> Input_Output_Stream_Handlers
    Core_Conversion_Engine -- "integrates" --> Plugin_System
    Core_Conversion_Engine -- "serves" --> User_Interfaces_CLI_MCP_Server_
    Core_Conversion_Engine -- "relies on" --> Converter_Framework
    Converter_Framework -- "defines interface for" --> Format_Specific_Converters
    Format_Specific_Converters -- "implements" --> Converter_Framework
    Format_Specific_Converters -- "leverages" --> Document_Pre_processing_Utilities
    Input_Output_Stream_Handlers -- "provides data to" --> Core_Conversion_Engine
    User_Interfaces_CLI_MCP_Server_ -- "invokes" --> Core_Conversion_Engine
    Plugin_System -- "extends" --> Core_Conversion_Engine
    Document_Pre_processing_Utilities -- "supports" --> Format_Specific_Converters
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `markitdown` project is designed as a modular document conversion system. Its core functionality revolves around the `Core Conversion Engine`, which orchestrates the conversion process by utilizing a flexible `Converter Framework`. This framework defines a standard interface that `Format-Specific Converters` implement to handle various document types. Input and output operations are managed by `Input/Output Stream Handlers`, ensuring data is correctly ingested and emitted. Users interact with the system through `User Interfaces`, which can be a Command-Line Interface or a server. The system's extensibility is facilitated by a `Plugin System`, allowing dynamic addition of new conversion capabilities. Additionally, `Document Pre-processing Utilities` assist in preparing content before the main conversion.

### Core Conversion Engine
The central orchestrator managing conversion workflows, converter registration, and selection.


**Related Classes/Methods**:



### Converter Framework
Defines the standard interface (`DocumentConverter`) for all format-specific converters.


**Related Classes/Methods**:



### Format-Specific Converters
Modules specialized in converting particular document formats to Markdown.


**Related Classes/Methods**:



### Input/Output Stream Handlers
Manages various input data streams, extracts metadata, and handles output.


**Related Classes/Methods**:



### User Interfaces (CLI & MCP Server)
Provides direct command-line interaction and a web service interface for conversion requests.


**Related Classes/Methods**:



### Plugin System
Enables dynamic extension of conversion capabilities through external modules.


**Related Classes/Methods**:



### Document Pre-processing Utilities
Offers specialized functions to prepare document content before main conversion.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)