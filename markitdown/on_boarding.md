```mermaid
graph LR
    Core_Conversion_Engine["Core Conversion Engine"]
    Converter_Interface_Base["Converter Interface & Base"]
    Format_Specific_Converters["Format-Specific Converters"]
    External_Service_Integration_Converters["External Service Integration Converters"]
    Document_Pre_processing_Utilities["Document Pre-processing Utilities"]
    Command_Line_Interface_CLI_["Command-Line Interface (CLI)"]
    Plugin_System["Plugin System"]
    Markitdown_Conversion_Proxy_MCP_Application["Markitdown Conversion Proxy (MCP) Application"]
    Stream_Information_URI_Utilities["Stream Information & URI Utilities"]
    Command_Line_Interface_CLI_ -- "invokes conversion methods on" --> Core_Conversion_Engine
    Markitdown_Conversion_Proxy_MCP_Application -- "serves as HTTP facade for" --> Core_Conversion_Engine
    Core_Conversion_Engine -- "registers and invokes" --> Converter_Interface_Base
    Core_Conversion_Engine -- "dispatches requests to" --> Format_Specific_Converters
    Core_Conversion_Engine -- "dispatches requests to" --> External_Service_Integration_Converters
    Core_Conversion_Engine -- "discovers and loads plugins from" --> Plugin_System
    Format_Specific_Converters -- "utilizes" --> Document_Pre_processing_Utilities
    Core_Conversion_Engine -- "relies on" --> Stream_Information_URI_Utilities
    Format_Specific_Converters -- "implements" --> Converter_Interface_Base
    External_Service_Integration_Converters -- "implements" --> Converter_Interface_Base
    Plugin_System -- "registers converters with" --> Core_Conversion_Engine
    Plugin_System -- "extends capabilities of" --> Core_Conversion_Engine
    click Core_Conversion_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Core_Conversion_Engine.md" "Details"
    click Converter_Interface_Base href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Converter_Interface_Base.md" "Details"
    click Format_Specific_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Format_Specific_Converters.md" "Details"
    click External_Service_Integration_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/External_Service_Integration_Converters.md" "Details"
    click Document_Pre_processing_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Document_Pre_processing_Utilities.md" "Details"
    click Plugin_System href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Plugin_System.md" "Details"
    click Markitdown_Conversion_Proxy_MCP_Application href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Markitdown_Conversion_Proxy_MCP_Application.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `markitdown` project is structured around a `Core Conversion Engine` (`markitdown._markitdown.MarkItDown`) that acts as the central hub for all document conversion operations. This engine is responsible for identifying the input source type (local file, stream, URI, or HTTP response) using `Stream Information & URI Utilities` (`markitdown._stream_info.StreamInfo`, `markitdown._uri_utils.file_uri_to_path`, `markitdown._uri_utils.parse_data_uri`) and then dispatching the conversion task to the appropriate `DocumentConverter` implementation. All converters adhere to the `Converter Interface & Base` (`markitdown._base_converter.DocumentConverter`), ensuring a standardized approach. The system includes `Format-Specific Converters` for common document types (e.g., `PptxConverter`, `DocxConverter`, `PdfConverter`, `HtmlConverter`) and `External Service Integration Converters` that leverage external AI/LLM services (`DocumentIntelligenceConverter`, `LLMCaptionConverter`, `AudioConverter`). Some converters, particularly for DOCX, rely on `Document Pre-processing Utilities` (`pre_process_docx`, `OmmlToLatexConverter`) to prepare the content before conversion. The `Core Conversion Engine` is extensible through a `Plugin System` (`MarkItDown.enable_plugins`, `register_converters`), allowing external modules to register custom converters. Users can interact with the system via a `Command-Line Interface (CLI)` (`markitdown.__main__.main`) or through the `Markitdown Conversion Proxy (MCP) Application` (`markitdown_mcp.__main__.main`), which provides an HTTP API facade for the conversion services.

### Core Conversion Engine [[Expand]](./Core_Conversion_Engine.md)
The central orchestrator responsible for managing the conversion process, registering converters, and providing a unified API for various input types.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py#L92-L770" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown`:92-770)</a>


### Converter Interface & Base [[Expand]](./Converter_Interface_Base.md)
Defines the contract that all document converters must adhere to, ensuring extensibility and interchangeability.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_base_converter.py#L41-L104" target="_blank" rel="noopener noreferrer">`markitdown._base_converter.DocumentConverter`:41-104)</a>


### Format-Specific Converters [[Expand]](./Format_Specific_Converters.md)
A collection of concrete converter implementations for standard document formats.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_pptx_converter.py#L33-L251" target="_blank" rel="noopener noreferrer">`markitdown.converters._pptx_converter.PptxConverter`:33-251)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_docx_converter.py#L27-L79" target="_blank" rel="noopener noreferrer">`markitdown.converters._docx_converter.DocxConverter`:27-79)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_pdf_converter.py#L30-L76" target="_blank" rel="noopener noreferrer">`markitdown.converters._pdf_converter.PdfConverter`:30-76)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_html_converter.py#L19-L89" target="_blank" rel="noopener noreferrer">`markitdown.converters._html_converter.HtmlConverter`:19-89)</a>


### External Service Integration Converters [[Expand]](./External_Service_Integration_Converters.md)
Specialized converters that leverage external AI/LLM services for enhanced conversion capabilities.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_doc_intel_converter.py#L124-L248" target="_blank" rel="noopener noreferrer">`markitdown.converters._doc_intel_converter.DocumentIntelligenceConverter`:124-248)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_llm_caption.py#L6-L49" target="_blank" rel="noopener noreferrer">`markitdown.converters._llm_caption.LLMCaptionConverter`:6-49)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_audio_converter.py#L22-L100" target="_blank" rel="noopener noreferrer">`markitdown.converters._audio_converter.AudioConverter`:22-100)</a>


### Document Pre-processing Utilities [[Expand]](./Document_Pre_processing_Utilities.md)
Helper functions and modules for preparing specific document types before conversion.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converter_utils/docx/pre_process.py#L117-L155" target="_blank" rel="noopener noreferrer">`markitdown.converter_utils.docx.pre_process.pre_process_docx`:117-155)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converter_utils/docx/math/omml.py#L10-L100" target="_blank" rel="noopener noreferrer">`markitdown.converter_utils.docx.math.omml.OmmlToLatexConverter`:10-100)</a>


### Command-Line Interface (CLI)
Provides a user-friendly command-line interface for direct interaction with the Core Conversion Engine.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/__main__.py#L12-L199" target="_blank" rel="noopener noreferrer">`markitdown.__main__.main`:12-199)</a>


### Plugin System [[Expand]](./Plugin_System.md)
Facilitates extensibility by allowing external modules to register custom converters.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py#L20-L770" target="_blank" rel="noopener noreferrer">`markitdown._markitdown.MarkItDown.enable_plugins`:20-770)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown-sample-plugin/src/markitdown_sample_plugin/_plugin.py#L24-L30" target="_blank" rel="noopener noreferrer">`markitdown_sample_plugin._plugin.register_converters`:24-30)</a>


### Markitdown Conversion Proxy (MCP) Application [[Expand]](./Markitdown_Conversion_Proxy_MCP_Application.md)
A separate web application exposing the conversion capabilities as an HTTP API.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown-mcp/src/markitdown_mcp/__main__.py#L81-L122" target="_blank" rel="noopener noreferrer">`markitdown_mcp.__main__.main`:81-122)</a>


### Stream Information & URI Utilities
Determines input characteristics and is crucial for the Core Conversion Engine to correctly identify and process diverse input sources.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_stream_info.py#L4-L31" target="_blank" rel="noopener noreferrer">`markitdown._stream_info.StreamInfo`:4-31)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_uri_utils.py#L7-L15" target="_blank" rel="noopener noreferrer">`markitdown._uri_utils.file_uri_to_path`:7-15)</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_uri_utils.py#L18-L51" target="_blank" rel="noopener noreferrer">`markitdown._uri_utils.parse_data_uri`:18-51)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)