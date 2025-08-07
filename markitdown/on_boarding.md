```mermaid
graph LR
    CLI_Application_Entry_Point["CLI Application Entry Point"]
    API_Service_Layer_markitdown_mcp_["API Service Layer (markitdown-mcp)"]
    Core_Conversion_Orchestrator["Core Conversion Orchestrator"]
    Converter_Abstraction_Layer["Converter Abstraction Layer"]
    Specific_Document_Converters["Specific Document Converters"]
    Plugin_Management_System["Plugin Management System"]
    CLI_Application_Entry_Point -- "initiates conversion requests to" --> Core_Conversion_Orchestrator
    API_Service_Layer_markitdown_mcp_ -- "forwards conversion tasks to" --> Core_Conversion_Orchestrator
    Core_Conversion_Orchestrator -- "interacts with" --> Converter_Abstraction_Layer
    Core_Conversion_Orchestrator -- "dispatches conversion tasks to" --> Specific_Document_Converters
    Core_Conversion_Orchestrator -- "discovers and loads converters through" --> Plugin_Management_System
    Specific_Document_Converters -- "implements interface defined by" --> Converter_Abstraction_Layer
    Plugin_Management_System -- "registers new converters that conform to" --> Converter_Abstraction_Layer
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### CLI Application Entry Point
Manages command-line interactions, parses arguments, and initiates the document conversion process.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/__main__.py" target="_blank" rel="noopener noreferrer">`markitdown.__main__.main`</a>


### API Service Layer (markitdown-mcp)
Provides a web API interface for external applications to submit documents for conversion, acting as an entry point for programmatic access.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown-mcp/src/markitdown_mcp/main.py" target="_blank" rel="noopener noreferrer">`markitdown_mcp.main.convert_to_markdown`</a>


### Core Conversion Orchestrator
The central control unit that orchestrates the entire conversion workflow, managing available converters and dispatching conversion tasks based on input type.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown.convert`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown._convert`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown.register_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown._load_plugins`</a>


### Converter Abstraction Layer
Defines the standardized interface (`accepts`, `convert`) that all specific document converters must implement, ensuring consistency and enabling the Strategy Pattern.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_base_converter.py" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.BaseConverter.accepts`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_base_converter.py" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.BaseConverter.convert`</a>


### Specific Document Converters
A collection of concrete implementations, each responsible for converting a particular document format (e.g., PDF, DOCX, Image) into Markdown, adhering to the `Converter Abstraction Layer`.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_image_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._image_converter.ImageConverter.accepts`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_image_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._image_converter.ImageConverter.convert`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_docx_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._docx_converter.DocxConverter.accepts`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_docx_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._docx_converter.DocxConverter.convert`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_pdf_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._pdf_converter.PdfConverter.accepts`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_pdf_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._pdf_converter.PdfConverter.convert`</a>


### Plugin Management System
Manages the dynamic discovery, loading, and registration of external or user-defined converter plugins, extending the system's capabilities without modifying the core codebase.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown._load_plugins`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown.register_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown-sample-plugin/src/markitdown_sample_plugin/plugin.py" target="_blank" rel="noopener noreferrer">`markitdown_sample_plugin.plugin.SamplePlugin`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)