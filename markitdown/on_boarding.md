```mermaid
graph LR
    MarkItDown_Core_["MarkItDown (Core)"]
    ConverterRegistry["ConverterRegistry"]
    DocumentConverter_Abstract_["DocumentConverter (Abstract)"]
    InputProcessor["InputProcessor"]
    OutputFormatter["OutputFormatter"]
    MarkItDown_Core_ -- "uses" --> ConverterRegistry
    MarkItDown_Core_ -- "uses" --> InputProcessor
    MarkItDown_Core_ -- "uses" --> DocumentConverter_Abstract_
    MarkItDown_Core_ -- "uses" --> OutputFormatter
    ConverterRegistry -- "contains" --> DocumentConverter_Abstract_
    InputProcessor -- "provides" --> StreamInfo
    DocumentConverter_Abstract_ -- "uses" --> StreamInfo
    click MarkItDown_Core_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/MarkItDown_Core_.md" "Details"
    click DocumentConverter_Abstract_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/DocumentConverter_Abstract_.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### MarkItDown (Core)
The central orchestrator. Manages the conversion process, including converter registration and plugin execution. It's the main entry point for initiating conversions.


**Related Classes/Methods**: _None_

### ConverterRegistry
A registry that manages the mapping between file types and their corresponding converters. Allows for dynamic addition of converters.


**Related Classes/Methods**: _None_

### DocumentConverter (Abstract)
An abstract base class defining the interface for all specific converters. Each concrete converter (e.g., PdfConverter, HtmlConverter) inherits from this.


**Related Classes/Methods**: _None_

### InputProcessor
Handles the initial processing of input, including file identification, validation, and stream creation. Provides StreamInfo objects to converters.


**Related Classes/Methods**: _None_

### OutputFormatter
Formats the final Markdown output, potentially handling different output styles or options.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)