```text
## MarkItDown Component Overview

The `MarkItDown` component is a document conversion orchestrator that converts various file types and web pages into Markdown format. It uses a chain of responsibility pattern with `DocumentConverter` implementations to handle different file types. The component identifies the file type using `StreamInfo` and `magika` and then selects the appropriate converter.

**Main Classes and Their Purposes:**

*   **`MarkItDown`**: The central orchestrator class. It manages the registration of converters, identifies the input stream type, and delegates the conversion process to the appropriate converter.
*   **`DocumentConverter`**: An abstract base class that defines the interface for all document converters. Subclasses implement the `accepts` and `convert` methods to handle specific file types.
*   **`StreamInfo`**: A data class that holds metadata about the input stream, such as MIME type, file extension, charset, filename, local path, and URL. This information is used to determine the appropriate converter to use.
*   **`ConverterRegistration`**: A data class that associates a `DocumentConverter` with a priority.
*   **`RtfConverter`**: A concrete `DocumentConverter` implementation that converts RTF files to Markdown. (Example from plugin)

**Main Flow:**

The main flow involves the `MarkItDown` orchestrator receiving a document, determining its type, and delegating the conversion to a suitable `DocumentConverter`.

```mermaid
sequenceDiagram
    participant Client
    participant MarkItDown
    participant StreamInfo
    participant Magika
    participant ConverterA
    participant ConverterB

    Client->>MarkItDown: convert(source)
    MarkItDown->>StreamInfo: Create StreamInfo from source
    MarkItDown->>Magika: identify_stream(file_stream)
    Magika-->>MarkItDown: Return stream info guesses
    MarkItDown->>ConverterA: accepts(file_stream, stream_info)
    ConverterA-->>MarkItDown: false
    MarkItDown->>ConverterB: accepts(file_stream, stream_info)
    ConverterB-->>MarkItDown: true
    MarkItDown->>ConverterB: convert(file_stream, stream_info)
    ConverterB-->>MarkItDown: DocumentConverterResult
    MarkItDown-->>Client: DocumentConverterResult
```

**Component Structure:**

The component's structure revolves around the `MarkItDown` class managing a collection of `DocumentConverter` instances. The `StreamInfo` class provides metadata to help select the appropriate converter.

```mermaid
classDiagram
    class MarkItDown {
        - _converters: List<ConverterRegistration>
        + __init__(enable_builtins: bool, enable_plugins: bool)
        + convert(source: Union[str, Path, BinaryIO], stream_info: StreamInfo) : DocumentConverterResult
        + register_converter(converter: DocumentConverter, priority: float) : void
        - _get_stream_info_guesses(file_stream: BinaryIO, base_guess: StreamInfo) : List<StreamInfo>
        - _convert(file_stream: BinaryIO, stream_info_guesses: List<StreamInfo>) : DocumentConverterResult
    }
    class DocumentConverter {
        + accepts(file_stream: BinaryIO, stream_info: StreamInfo) : bool
        + convert(file_stream: BinaryIO, stream_info: StreamInfo) : DocumentConverterResult
        <<abstract>>
    }
    class StreamInfo {
        + mimetype: Optional<str>
        + extension: Optional<str>
        + charset: Optional<str>
        + filename: Optional<str>
        + local_path: Optional<str>
        + url: Optional<str>
        + copy_and_update() : StreamInfo
    }
    class ConverterRegistration {
        + converter: DocumentConverter
        + priority: float
    }
    class RtfConverter {
        + accepts(file_stream: BinaryIO, stream_info: StreamInfo) : bool
        + convert(file_stream: BinaryIO, stream_info: StreamInfo) : DocumentConverterResult
    }

    MarkItDown "1" -- "*" ConverterRegistration : manages
    ConverterRegistration "1" -- "1" DocumentConverter : uses
    MarkItDown "1" -- "*" StreamInfo : uses
    RtfConverter --|> DocumentConverter : implements
```