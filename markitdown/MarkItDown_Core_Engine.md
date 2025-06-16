```mermaid
graph LR
    MarkItDown_Core_Engine["MarkItDown Core Engine"]
    Base_Converter["Base Converter"]
    Document_Converter_Result["Document Converter Result"]
    Stream_Information["Stream Information"]
    URI_Utilities["URI Utilities"]
    HTML_Converter["HTML Converter"]
    Custom_Markdownify["Custom Markdownify"]
    MarkItDown_Core_Engine -- "manages" --> Base_Converter
    MarkItDown_Core_Engine -- "uses" --> Stream_Information
    MarkItDown_Core_Engine -- "uses" --> URI_Utilities
    MarkItDown_Core_Engine -- "produces" --> Document_Converter_Result
    Base_Converter -- "defines" --> Document_Converter_Result
    Base_Converter -- "consumes" --> Stream_Information
    HTML_Converter -- "extends" --> Base_Converter
    HTML_Converter -- "delegates to" --> Custom_Markdownify
    HTML_Converter -- "produces" --> Document_Converter_Result
    click MarkItDown_Core_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/MarkItDown_Core_Engine.md" "Details"
    click Base_Converter href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Base_Converter.md" "Details"
    click Custom_Markdownify href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//markitdown/Custom_Markdownify.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `MarkItDown Core Engine` subsystem is the central processing unit of the `markitdown` library, orchestrating the conversion of various document types into Markdown. It intelligently identifies input types, manages a registry of document converters, and dispatches conversion tasks to the appropriate handlers. This subsystem is designed for extensibility, allowing for both built-in and plugin-based converters.

### MarkItDown Core Engine
This is the primary orchestrator, responsible for managing the conversion process from input to Markdown. It maintains a registry of converters, determines the appropriate converter for a given input, and executes the conversion. It also handles plugin loading for extended functionality.


**Related Classes/Methods**:

- `markitdown.MarkItDown` (0:0)


### Base Converter
Defines the abstract interface (`DocumentConverter`) that all concrete document converters must implement. It specifies the `accepts()` method for input type determination and the `convert()` method for performing the actual conversion, ensuring a standardized contract for all converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter` (41:104)</a>


### Document Converter Result
A data structure (`DocumentConverterResult`) used to encapsulate the outcome of a document conversion. It primarily holds the converted Markdown string and an optional document title.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_base_converter.py#L4-L38" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverterResult` (4:38)</a>


### Stream Information
This component (`StreamInfo`) is a data class that stores and provides crucial metadata about the input stream, such as its MIME type, file extension, character set, filename, and source URL. This information is vital for the `MarkItDown` engine to select the correct converter.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_stream_info.py#L5-L31" target="_blank" rel="noopener noreferrer">`markitdown._stream_info.StreamInfo` (5:31)</a>


### URI Utilities
This module provides utility functions (`file_uri_to_path`, `parse_data_uri`) for handling and parsing various Uniform Resource Identifiers (URIs), including `file://` and `data:` schemes. It ensures that the `MarkItDown` engine can correctly interpret and access content from diverse URI sources.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_uri_utils.py#L0-L0" target="_blank" rel="noopener noreferrer">`markitdown._uri_utils` (0:0)</a>


### HTML Converter
A concrete implementation of `DocumentConverter` specifically designed to transform HTML input (from file streams or strings) into Markdown. It parses HTML using BeautifulSoup, performs cleaning (e.g., removing script/style tags), and delegates the core Markdown conversion.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_html_converter.py#L19-L89" target="_blank" rel="noopener noreferrer">`markitdown.converters._html_converter.HtmlConverter` (19:89)</a>


### Custom Markdownify
This component (`_CustomMarkdownify`) is a specialized Markdown converter that takes a BeautifulSoup object (representing parsed HTML) and transforms it into a Markdown string. It extends an external library (`markdownify`) and applies custom rules for formatting headings, handling links, and managing image data URIs.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_markdownify.py#L7-L110" target="_blank" rel="noopener noreferrer">`markitdown.converters._markdownify._CustomMarkdownify` (7:110)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)