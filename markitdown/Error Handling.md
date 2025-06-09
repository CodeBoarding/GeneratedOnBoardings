```mermaid
graph LR
    Core_Conversion_Orchestrator["Core Conversion Orchestrator"]
    Document_Converters["Document Converters"]
    Exception_Handling["Exception Handling"]
    Core_Conversion_Orchestrator -- "invokes" --> Document_Converters
    Core_Conversion_Orchestrator -- "raises" --> Exception_Handling
    Document_Converters -- "raises" --> Exception_Handling
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The system, `markitdown`, is designed for robust document conversion to Markdown. It features a `Core Conversion Orchestrator` that manages the conversion workflow, handling various input types and dispatching tasks to specialized `Document Converters`. A dedicated `Exception Handling` component ensures that errors, such as missing dependencies or unsupported formats, are caught and reported effectively, contributing to the system's reliability.

### Core Conversion Orchestrator
This component, primarily embodied by the MarkItDown class, is responsible for the overall document conversion process. It handles input sources (local files, URLs, streams, HTTP responses), identifies file types using internal logic and external tools like Magika, manages and prioritizes various document converters, and orchestrates the conversion by dispatching to the appropriate converter. It also handles the registration of built-in and plugin converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L93-L771" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown` (93:771)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L529-L619" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:_convert` (529:619)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L243-L291" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:convert` (243:291)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L293-L328" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:convert_local` (293:328)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L330-L375" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:convert_stream` (330:375)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L396-L455" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:convert_uri` (396:455)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L457-L527" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:convert_response` (457:527)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L132-L221" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:enable_builtins` (132:221)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L223-L241" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:enable_plugins` (223:241)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_markitdown.py#L629-L659" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown:register_converter` (629:659)</a>


### Document Converters
This component encompasses various specialized converter classes, each designed to transform a specific document format (e.g., PPTX, XLSX, DOCX, PDF, IPYNB, Outlook MSG) into Markdown. These converters implement the core logic for parsing and extracting content from their respective file types. They are invoked by the Core Conversion Orchestrator based on the identified document type.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_pptx_converter.py#L61-L188" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._pptx_converter.PptxConverter:convert` (61:188)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_xlsx_converter.py#L63-L95" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._xlsx_converter.XlsxConverter:convert` (63:95)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_xlsx_converter.py#L125-L157" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._xlsx_converter.XlsConverter:convert` (125:157)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_docx_converter.py#L55-L80" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._docx_converter.DocxConverter:convert` (55:80)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_outlook_msg_converter.py#L73-L125" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._outlook_msg_converter.OutlookMsgConverter:convert` (73:125)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_pdf_converter.py#L54-L77" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._pdf_converter.PdfConverter:convert` (54:77)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_ipynb_converter.py#L57-L96" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._ipynb_converter.IpynbConverter:_convert` (57:96)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_doc_intel_converter.py#L128-L182" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._doc_intel_converter.DocumentIntelligenceConverter:__init__` (128:182)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/converters/_transcribe_audio.py#L23-L49" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown.converters._transcribe_audio:transcribe_audio` (23:49)</a>


### Exception Handling
This component defines and manages custom exceptions specific to the MarkItDown conversion process. These exceptions, such as FailedConversionAttempt, FileConversionException, UnsupportedFormatException, and MissingDependencyException, are raised by the Core Conversion Orchestrator or individual Document Converters to signal various types of errors or unsupported scenarios during conversion.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_exceptions.py#L42-L49" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._exceptions.FailedConversionAttempt` (42:49)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_exceptions.py#L52-L76" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._exceptions.FileConversionException` (52:76)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_exceptions.py#L34-L39" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._exceptions.UnsupportedFormatException` (34:39)</a>
- <a href="https://github.com/microsoft/markitdown/blob/master/packages/markitdown/src/markitdown/_exceptions.py#L19-L31" target="_blank" rel="noopener noreferrer">`markitdown.packages.markitdown.src.markitdown._exceptions.MissingDependencyException` (19:31)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)