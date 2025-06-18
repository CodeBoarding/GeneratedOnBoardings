```mermaid
graph LR
    Conversion_Engine["Conversion Engine"]
    Converter_Registry["Converter Registry"]
    Document_Converter["Document Converter"]
    Plugin_Loader["Plugin Loader"]
    Error_Handling["Error Handling"]
    Utility_Functions["Utility Functions"]
    Testing_Suite["Testing Suite"]
    Conversion_Engine -- "uses" --> Converter_Registry
    Conversion_Engine -- "uses" --> Plugin_Loader
    HtmlConverter -- "inherits from" --> Document_Converter
    DocxConverter -- "inherits from" --> Document_Converter
    PdfConverter -- "inherits from" --> Document_Converter
    Conversion_Engine -- "uses" --> Individual_Converters
    Main_Application -- "initializes" --> Conversion_Engine
    Conversion_Engine -- "uses" --> Error_Handling
    Converter_Registry -- "uses" --> Error_Handling
    Document_Converter -- "uses" --> Error_Handling
    Plugin_Loader -- "uses" --> Error_Handling
    Individual_Converters -- "uses" --> Error_Handling
    click Conversion_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Conversion_Engine.md" "Details"
    click Testing_Suite href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Testing_Suite.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

Refactored architecture for MarkItDown, addressing single responsibility principle violations and improving modularity.

### Conversion Engine
Orchestrates the conversion process, selects the appropriate converter, and handles the workflow.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L1-L100" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.ConversionEngine` (1:100)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L5-L50" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.ConverterRegistry` (5:50)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter` (41:104)</a>
- `markitdown.converters.HtmlConverter` (1:30)
- `markitdown.converters.DocxConverter` (1:40)
- `markitdown.converters.PdfConverter` (1:50)
- `markitdown._error_handling.ConversionError` (1:15)


### Converter Registry
Maps file types to converter instances.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L5-L50" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.ConverterRegistry` (5:50)</a>


### Document Converter
Defines the interface for all specific converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter` (41:104)</a>


### Plugin Loader
Loads and registers external plugins dynamically.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L10-L60" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.PluginLoader` (10:60)</a>


### Error Handling
Handles exceptions and provides informative error messages.


**Related Classes/Methods**:

- `markitdown._error_handling.ConversionError` (1:15)


### Utility Functions
Helper functions for file I/O, logging, etc.


**Related Classes/Methods**:

- `markitdown._utils.file_utils` (1:100)
- `markitdown._utils.logging` (1:50)


### Testing Suite
Comprehensive tests for all components.


**Related Classes/Methods**:

- `markitdown._testing.test_conversion_engine` (1:100)
- `markitdown._testing.test_converters` (1:150)
- `markitdown._testing.test_plugins` (1:50)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)