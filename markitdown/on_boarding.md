```mermaid
graph LR
    Main_Application["Main Application"]
    MarkItDown["MarkItDown"]
    ConverterRegistry["ConverterRegistry"]
    StreamInfo["StreamInfo"]
    File_Converters["File Converters"]
    Main_Application -- "uses" --> MarkItDown
    MarkItDown -- "uses" --> ConverterRegistry
    MarkItDown -- "uses" --> StreamInfo
    ConverterRegistry -- "registers" --> File_Converters
    File_Converters -- "uses" --> StreamInfo
    click MarkItDown href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/MarkItDown.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Main Application
The entry point, responsible for initializing the system and triggering the conversion process.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/__main__.py#L1-L10" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown.__main__` (1:10)</a>


### MarkItDown
The core orchestrator. Manages converters, input streams, and the overall conversion workflow.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L92-L770" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._markitdown.MarkItDown` (92:770)</a>


### ConverterRegistry
Registers and manages available converters. Provides access to the appropriate converter based on file type or input source.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L85-L89" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._markitdown.ConverterRegistration` (85:89)</a>


### StreamInfo
Handles input sources (files, URLs, etc.), providing a consistent interface for converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_stream_info.py#L5-L31" target="_blank" rel="noopener noreferrer">`packages.markitdown.src.markitdown._stream_info.StreamInfo` (5:31)</a>


### File Converters
A group of individual converters (AudioConverter, PDFConverter, etc.). Each handles a specific file type, implementing a common interface. They share utility functions.


**Related Classes/Methods**:

- `packages.markitdown.src.markitdown.converters.*` (1:200)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)