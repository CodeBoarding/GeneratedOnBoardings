```mermaid
graph LR
    MarkItDown["MarkItDown"]
    DocumentConverter["DocumentConverter"]
    PdfConverter["PdfConverter"]
    DocxConverter["DocxConverter"]
    ConverterRegistration["ConverterRegistration"]
    PdfHelper["PdfHelper"]
    DocxHelper["DocxHelper"]
    Markdownify["Markdownify"]
    ExiftoolWrapper["ExiftoolWrapper"]
    LLMCaptionGenerator["LLMCaptionGenerator"]
    MarkItDownException["MarkItDownException"]
    ConversionException["ConversionException"]
    PdfConversionException["PdfConversionException"]
    DocxConversionException["DocxConversionException"]
    UnsupportedFormatException["UnsupportedFormatException"]
    MarkItDown -- "uses" --> ConverterRegistration
    ConverterRegistration -- "uses" --> PdfConverter
    ConverterRegistration -- "uses" --> DocxConverter
    PdfConverter -- "uses" --> PdfHelper
    DocxConverter -- "uses" --> DocxHelper
    PdfConverter -- "uses" --> Markdownify
    DocxConverter -- "uses" --> Markdownify
    PdfConverter -- "uses" --> ExiftoolWrapper
    DocxConverter -- "uses" --> ExiftoolWrapper
    PdfConverter -- "uses" --> LLMCaptionGenerator
    DocxConverter -- "uses" --> LLMCaptionGenerator
    PdfConverter -- "throws" --> PdfConversionException
    DocxConverter -- "throws" --> DocxConversionException
    PdfConverter -- "throws" --> UnsupportedFormatException
    DocxConverter -- "throws" --> UnsupportedFormatException
    PdfHelper -- "uses" --> ExiftoolWrapper
    DocxHelper -- "uses" --> ExiftoolWrapper
    click MarkItDown href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/MarkItDown.md" "Details"
    click DocumentConverter href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/DocumentConverter.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### MarkItDown
Main entry point. Receives document path, determines type, selects appropriate converter, handles exceptions, and outputs Markdown.


**Related Classes/Methods**: _None_

### DocumentConverter
Defines the interface for all converters: `convert(filepath)` returning Markdown string.


**Related Classes/Methods**: _None_

### PdfConverter
Converts PDF to Markdown.


**Related Classes/Methods**: _None_

### DocxConverter
Converts DOCX to Markdown.


**Related Classes/Methods**: _None_

### ConverterRegistration
Registers converters and selects the appropriate one based on file extension.


**Related Classes/Methods**: _None_

### PdfHelper
Encapsulates PDF-specific logic.


**Related Classes/Methods**: _None_

### DocxHelper
Encapsulates DOCX-specific logic.


**Related Classes/Methods**: _None_

### Markdownify
Generates Markdown from processed data.


**Related Classes/Methods**: _None_

### ExiftoolWrapper
Wrapper for exiftool library (optional). Handles metadata extraction.


**Related Classes/Methods**: _None_

### LLMCaptionGenerator
Generates captions using an LLM (optional).


**Related Classes/Methods**: _None_

### MarkItDownException
Base class for all exceptions.


**Related Classes/Methods**: _None_

### ConversionException
Generic conversion error.


**Related Classes/Methods**: _None_

### PdfConversionException
PDF-specific conversion error.


**Related Classes/Methods**: _None_

### DocxConversionException
DOCX-specific conversion error.


**Related Classes/Methods**: _None_

### UnsupportedFormatException
Unsupported file format.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)