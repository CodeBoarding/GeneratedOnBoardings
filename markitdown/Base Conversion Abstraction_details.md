```text
## Component Description: Document Conversion

The `markitdown` component provides a unified interface for converting various document formats into Markdown. It orchestrates the conversion process by selecting the appropriate converter based on the input document's type and then utilizing that converter to generate the Markdown output. The core of the component lies in the `MarkItDown` class, which acts as the central point for initiating conversions. It determines the input type (local file, URL, stream, etc.) and dispatches the conversion to the relevant handler. Each specific document type has its own converter class (e.g., `HtmlConverter`, `PdfConverter`), inheriting from the `DocumentConverter` base class. These converters implement the actual logic for extracting content and formatting it into Markdown. The `StreamInfo` class encapsulates metadata about the input stream, such as MIME type and file extension, aiding in converter selection. The result of the conversion, including the Markdown content and optional title, is encapsulated in the `DocumentConverterResult` class.

## Main Flow (Sequence Diagram)

```mermaid
sequenceDiagram
    participant User
    participant MarkItDown
    participant StreamInfo
    participant Converter
    participant DocumentConverterResult

    User->>MarkItDown: convert(source)
    MarkItDown->>StreamInfo: Infer stream_info from source
    MarkItDown->>Converter: Determine converter based on stream_info
    MarkItDown->>Converter: convert(file_stream, stream_info)
    Converter->>DocumentConverterResult: Create result with markdown
    Converter-->>MarkItDown: Return DocumentConverterResult
    MarkItDown-->>User: Return DocumentConverterResult
```

## Component Structure (Class Diagram)

```mermaid
classDiagram
    class MarkItDown {
        +convert(source) DocumentConverterResult
        +convert_local(path) DocumentConverterResult
        +convert_uri(uri) DocumentConverterResult
        +convert_stream(stream) DocumentConverterResult
        +convert_response(response) DocumentConverterResult
    }
    class StreamInfo {
        +mimetype: str
        +extension: str
        +charset: str
        +filename: str
        +local_path: str
        +url: str
    }
    class DocumentConverter {
        <<abstract>>
        +accepts(file_stream, stream_info) bool
        +convert(file_stream, stream_info) DocumentConverterResult
    }
    class DocumentConverterResult {
        +markdown: str
        +title: str
    }
    class HtmlConverter {
        +convert(file_stream, stream_info) DocumentConverterResult
    }
    class PdfConverter {
        +convert(file_stream, stream_info) DocumentConverterResult
    }

    MarkItDown -- StreamInfo: Uses
    MarkItDown -- DocumentConverter: Uses
    DocumentConverter -- DocumentConverterResult: Returns
    DocumentConverter <|-- HtmlConverter: Extends
    DocumentConverter <|-- PdfConverter: Extends
```