## Component Overview: Document Conversion Orchestration

This component orchestrates the conversion of various document formats into Markdown. It handles the selection of appropriate converters based on file type and content, manages input streams, and provides a unified interface for conversion.

**Main Classes and Their Purposes:**

*   **`MarkItDown`**: The central class responsible for managing the conversion process. It registers converters, determines the appropriate converter for a given input, and orchestrates the conversion. It handles different input types like local files, URLs, and streams.
*   **`StreamInfo`**: A data class that encapsulates metadata about the input stream, such as MIME type, file extension, character set, filename, and URL. It's used to help select the appropriate converter and pass relevant information to it.
*   **`DocumentConverter`**: An abstract base class for all document converters. Subclasses implement the `accepts` method to determine if they can handle a given input and the `convert` method to perform the actual conversion.
*   **`DocumentConverterResult`**: A data class that holds the result of a document conversion, including the Markdown content and an optional title.
*   **`ConverterRegistration`**: A data class that associates a `DocumentConverter` with a priority, used to determine the order in which converters are tried.

### Main Flow (Sequence Diagram)

The following diagram illustrates the main flow of the document conversion process, focusing on the core interactions between the key classes:

```mermaid
sequenceDiagram
    participant User
    participant MarkItDown
    participant StreamInfo
    participant Converter
    participant DocumentConverterResult

    User->>MarkItDown: convert(source)
    MarkItDown->>StreamInfo: _get_stream_info_guesses(file_stream, base_guess)
    MarkItDown->>Converter: accepts(file_stream, stream_info)
    alt Converter Accepts
        Converter->>Converter: convert(file_stream, stream_info)
        Converter->>DocumentConverterResult: Return markdown
        MarkItDown->>DocumentConverterResult: Return result
        User->>DocumentConverterResult: Converted markdown
    else Converter Rejects
        Converter-->>MarkItDown: False
    end
```

### Component Structure (Class Diagram)

This diagram shows the main classes in the component and their relationships:

```mermaid
classDiagram
    class MarkItDown {
        - _converters: List<ConverterRegistration>
        + convert(source) DocumentConverterResult
        + register_converter(converter: DocumentConverter, priority: float)
        - _get_stream_info_guesses(file_stream: BinaryIO, base_guess: StreamInfo) List<StreamInfo>
        - _convert(file_stream: BinaryIO, stream_info_guesses: List<StreamInfo>) DocumentConverterResult
    }
    class StreamInfo {
        - mimetype: Optional<str>
        - extension: Optional<str>
        - charset: Optional<str>
        - filename: Optional<str>
        - local_path: Optional<str>
        - url: Optional<str>
        + copy_and_update(...) StreamInfo
    }
    class DocumentConverter {
        <<abstract>>
        + accepts(file_stream: BinaryIO, stream_info: StreamInfo) bool
        + convert(file_stream: BinaryIO, stream_info: StreamInfo) DocumentConverterResult
    }
    class DocumentConverterResult {
        + markdown: str
        + title: Optional<str>
    }
    class ConverterRegistration {
        - converter: DocumentConverter
        - priority: float
    }
    class FileConversionException {
    }
    class UnsupportedFormatException {
    }

    MarkItDown "1" -- "*" ConverterRegistration : manages
    ConverterRegistration "1" -- "1" DocumentConverter : uses
    MarkItDown "1" -- "*" StreamInfo : creates
    DocumentConverter "1" -- "1" DocumentConverterResult : returns
    MarkItDown --|> FileConversionException : throws
    MarkItDown --|> UnsupportedFormatException : throws
```