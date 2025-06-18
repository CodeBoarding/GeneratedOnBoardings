```mermaid
graph LR
    Core_Engine_MarkItDown_["Core Engine (MarkItDown)"]
    Converter_Registry["Converter Registry"]
    Plugin_Manager["Plugin Manager"]
    Abstract_Document_Converter["Abstract Document Converter"]
    Specific_Converters["Specific Converters"]
    Input_Handler["Input Handler"]
    Exception_Handler["Exception Handler"]
    Core_Engine_MarkItDown_ -- "uses" --> Converter_Registry
    Core_Engine_MarkItDown_ -- "uses" --> Plugin_Manager
    Core_Engine_MarkItDown_ -- "uses" --> Input_Handler
    Converter_Registry -- "registers" --> Specific_Converters
    Plugin_Manager -- "loads" --> Specific_Converters
    Specific_Converters -- "uses" --> Exception_Handler
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

Component overview of the MarkItDown conversion system.

### Core Engine (MarkItDown)
Main orchestrator for the conversion process.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L92-L770" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._markitdown.MarkItDown` (92:770)</a>


### Converter Registry
Manages registration of all available converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L628-L658" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._markitdown.MarkItDown.register_converter` (628:658)</a>


### Plugin Manager
Loads and manages external plugins.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L64-L81" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._markitdown._load_plugins` (64:81)</a>


### Abstract Document Converter
Abstract base class for all specific converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter` (41:104)</a>


### Specific Converters
Individual converters for different file formats.


**Related Classes/Methods**:

- `markitdown.converters.PdfConverter` (100:150)
- `markitdown.converters.DocxConverter` (151:250)


### Input Handler
Handles various input types.


**Related Classes/Methods**: _None_

### Exception Handler
Centralized error handling.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_exceptions.py#L1-L50" target="_blank" rel="noopener noreferrer">`markitdown._exceptions` (1:50)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)