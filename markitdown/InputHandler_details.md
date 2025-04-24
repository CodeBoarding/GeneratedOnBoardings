### Component Overview: Markitdown Document Conversion

The `Markitdown` component is responsible for converting documents of various formats into Markdown. It orchestrates the process of identifying the document type, selecting an appropriate converter, and performing the conversion. The component supports built-in converters and plugins for extending its capabilities.

**Main Classes and Their Purposes:**

*   **`MarkItDown`**: The central class that manages the conversion process. It handles converter registration, stream information guessing, and the overall conversion workflow.
*   **`DocumentConverter`**: An abstract base class for all document converters. It defines the `accepts` and `convert` methods that concrete converters must implement.
*   **`StreamInfo`**: A data class that encapsulates information about the input stream, such as MIME type, file extension, and charset. This information is used to determine the appropriate converter to use.
*   **`ConverterRegistration`**: A data class that associates a `DocumentConverter` with a priority.
*   **`main`**: The entry point of the `markitdown` application. It parses command-line arguments, initializes the `MarkItDown` class, and performs the conversion based on the provided input.

**Main Flow:**

```mermaid
sequenceDiagram
    participant CLI
    participant MarkItDown
    participant StreamInfo
    participant Converter
    participant FileStream

    CLI->>MarkItDown: convert(source, stream_info)
    MarkItDown->>StreamInfo: _get_stream_info_guesses(file_stream, base_guess)
    loop For each stream_info_guess
        MarkItDown->>Converter: accepts(file_stream, stream_info_guess)
        alt accepts == True
            MarkItDown->>Converter: convert(file_stream, stream_info_guess)
            Converter-->>MarkItDown: DocumentConverterResult
            MarkItDown-->>CLI: DocumentConverterResult
        else accepts == False
            MarkItDown->>FileStream: seek(original_position)
        end
    end
    alt No converter found
        MarkItDown-->>CLI: Error
    end
```

**Class Diagram:**

```mermaid
classDiagram
    class MarkItDown {
        - _converters: List<ConverterRegistration>
        - _magika: Magika
        + __init__(enable_builtins, enable_plugins, **kwargs)
        + convert(source, stream_info, **kwargs) DocumentConverterResult
        + convert_local(path, stream_info, **kwargs) DocumentConverterResult
        + convert_stream(stream, stream_info, **kwargs) DocumentConverterResult
        + convert_uri(uri, stream_info, **kwargs) DocumentConverterResult
        + convert_response(response, stream_info, **kwargs) DocumentConverterResult
        + register_converter(converter, priority)
        - _get_stream_info_guesses(file_stream, base_guess) List<StreamInfo>
        - _convert(file_stream, stream_info_guesses, **kwargs) DocumentConverterResult
    }

    class DocumentConverter {
        <<abstract>>
        + accepts(file_stream, stream_info, **kwargs) bool
        + convert(file_stream, stream_info, **kwargs) DocumentConverterResult
    }

    class StreamInfo {
        - mimetype: Optional<str>
        - extension: Optional<str>
        - charset: Optional<str>
        - filename: Optional<str>
        - local_path: Optional<str>
        - url: Optional<str>
        + copy_and_update(**kwargs) StreamInfo
    }

    class ConverterRegistration {
        - converter: DocumentConverter
        - priority: float
    }

    MarkItDown "1" -- "*" ConverterRegistration : has
    ConverterRegistration "1" -- "1" DocumentConverter : associates with
    MarkItDown "1" *-- "1..*" StreamInfo : uses
```