```mermaid
graph LR
    MarkItDown_Core["MarkItDown Core"]
    Converter_Framework["Converter Framework"]
    Specific_Converters["Specific Converters"]
    Plugin_Management["Plugin Management"]
    CLI_Module["CLI Module"]
    API_Module["API Module"]
    CLI_Module -- "initiates requests to" --> MarkItDown_Core
    API_Module -- "delegates requests to" --> MarkItDown_Core
    MarkItDown_Core -- "utilizes" --> Plugin_Management
    Plugin_Management -- "loads" --> Specific_Converters
    MarkItDown_Core -- "dispatches tasks to" --> Specific_Converters
    Specific_Converters -- "implements" --> Converter_Framework
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### MarkItDown Core
The central orchestrator of the conversion process, responsible for managing converters, dispatching requests, and integrating the plugin system.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py#L1-L1" target="_blank" rel="noopener noreferrer">`MarkItDown Core` (1:1)</a>


### Converter Framework
Defines the abstract interface (accepts, convert) that all document converters must implement, ensuring a consistent and extensible architecture.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_base_converter.py#L1-L1" target="_blank" rel="noopener noreferrer">`Converter Framework` (1:1)</a>


### Specific Converters
Concrete implementations of the Converter Framework interface, each handling the conversion logic for a particular document type (e.g., PDF, DOCX, HTML).


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/#L1-L1" target="_blank" rel="noopener noreferrer">`Specific Converters` (1:1)</a>


### Plugin Management
Handles the dynamic discovery, loading, and registration of both built-in and external Specific Converters, extending the system's capabilities.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py#L1-L1" target="_blank" rel="noopener noreferrer">`Plugin Management` (1:1)</a>


### CLI Module
Provides a command-line interface for users to interact directly with the MarkItDown Core for document conversion.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/__main__.py#L1-L1" target="_blank" rel="noopener noreferrer">`CLI Module` (1:1)</a>


### API Module
Exposes the MarkItDown Core's conversion capabilities via an API layer, enabling integration with other services and applications.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)