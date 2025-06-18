```mermaid
graph LR
    Main_Application["Main Application"]
    MarkItDown_Core["MarkItDown Core"]
    Document_Converter["Document Converter"]
    Core_Converters["Core Converters"]
    Utility_Modules["Utility Modules"]
    Main_Application -- "uses" --> MarkItDown_Core
    MarkItDown_Core -- "uses" --> Document_Converter
    Document_Converter -- "implements" --> Core_Converters
    MarkItDown_Core -- "uses" --> Utility_Modules
    Core_Converters -- "uses" --> OMMLParser
    click Main_Application href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Main_Application.md" "Details"
    click MarkItDown_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/MarkItDown_Core.md" "Details"
    click Core_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Core_Converters.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Main Application
The entry point of the application. Parses command-line arguments, initializes the MarkItDown core, and handles the overall workflow.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/__main__.py#L12-L199" target="_blank" rel="noopener noreferrer">`markitdown.__main__.main` (12:199)</a>


### MarkItDown Core
The central orchestrator. Manages the conversion process, initializes converters (built-in and plugins), and handles input/output streams.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L92-L770" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown` (92:770)</a>


### Document Converter
Abstract base class defining the interface for all specific document converters (e.g., HTML, DOCX, EPUB).


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter` (41:104)</a>


### Core Converters
A group of concrete converter classes implementing the DocumentConverter interface. Handles the actual conversion logic for different document types.


**Related Classes/Methods**:

- `markitdown.converters.HtmlConverter` (1:150)
- `markitdown.converters.DocxConverter` (1:200)


### Utility Modules
Supporting modules providing reusable functionality.


**Related Classes/Methods**:

- `markitdown.utils.StreamInfo` (1:100)
- `markitdown.utils.OMMLParser` (101:150)
- `markitdown.utils.URIUtils` (251:50)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)