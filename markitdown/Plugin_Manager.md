```mermaid
graph LR
    Plugin_Manager["Plugin Manager"]
    Core_Conversion_Engine["Core Conversion Engine"]
    Document_Converters["Document Converters"]
    Unclassified["Unclassified"]
    Plugin_Manager -- "Loads and Registers" --> Document_Converters
    Plugin_Manager -- "Provides Access To" --> Core_Conversion_Engine
    Core_Conversion_Engine -- "Requests Converters From" --> Plugin_Manager
    Core_Conversion_Engine -- "Utilizes" --> Document_Converters
    Document_Converters -- "Are Executed By" --> Core_Conversion_Engine
    click Plugin_Manager href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Plugin_Manager.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `markitdown` library's conversion subsystem is built around a pluggable architecture. The `Plugin Manager` is responsible for discovering and registering various `Document Converters`, which are specialized components designed to transform specific document formats into Markdown. These converters adhere to a common interface defined by `BaseConverter`. The `Core Conversion Engine` acts as the central orchestrator, leveraging the `Plugin Manager` to access and utilize the appropriate `Document Converters` to perform the actual conversion process. This design allows for easy extension and integration of new document formats without modifying the core conversion logic.

### Plugin Manager [[Expand]](./Plugin_Manager.md)
Responsible for identifying, loading, and registering external document converters and processing plugins. It acts as the gateway for extending the library's capabilities without altering the core codebase.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown:enable_plugins`</a>


### Core Conversion Engine
The central orchestrator of the document conversion process. It utilizes the plugins and converters made available by the `Plugin Manager` to transform various input documents into Markdown format. The `MarkItDown` class embodies this engine.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py#L93-L776" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown`:93-776</a>


### Document Converters
These are the individual, pluggable components (both built-in and external) that perform the actual format-specific conversion tasks (e.g., PDF to Markdown, DOCX to Markdown). They adhere to a defined interface, allowing them to be discovered and utilized by the `Plugin Manager` and `Core Conversion Engine`.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_base_converter.py" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.BaseConverter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_pdf_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._pdf_converter.PdfConverter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_docx_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._docx_converter.DocxConverter`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)