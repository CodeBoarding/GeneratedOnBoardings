```mermaid
classDiagram
    class MarkItDown {
        - _converters: List<ConverterRegistration>
        - _requests_session: requests.Session
        - _magika: magika.Magika
        + __init__(enable_builtins: bool, enable_plugins: bool, **kwargs)
        + enable_builtins(**kwargs) : None
        + enable_plugins(**kwargs) : None
        + convert(source: Union[str, requests.Response, Path, BinaryIO], stream_info: Optional<StreamInfo>, **kwargs) : DocumentConverterResult
        + convert_local(path: Union[str, Path], stream_info: Optional<StreamInfo>, **kwargs) : DocumentConverterResult
        + convert_stream(stream: BinaryIO, stream_info: Optional<StreamInfo>, **kwargs) : DocumentConverterResult
        + convert_uri(uri: str, stream_info: Optional<StreamInfo>, **kwargs) : DocumentConverterResult
        + convert_response(response: requests.Response, stream_info: Optional<StreamInfo>, **kwargs) : DocumentConverterResult
        - _convert(file_stream: BinaryIO, stream_info_guesses: List<StreamInfo>, **kwargs) : DocumentConverterResult
        + register_converter(converter: DocumentConverter, priority: float) : None
        - _get_stream_info_guesses(file_stream: BinaryIO, base_guess: StreamInfo) : List<StreamInfo>
        - _normalize_charset(charset: str) : str
    }

    class ConverterRegistration {
        - converter: DocumentConverter
        - priority: float
    }

    class DocumentConverter {
        + accepts(file_stream: BinaryIO, stream_info: StreamInfo, **kwargs) : bool
        + convert(file_stream: BinaryIO, stream_info: StreamInfo, **kwargs) : DocumentConverterResult
    }

    class DocumentConverterResult {
        + text_content: str
        + title: str
    }

    class StreamInfo {
        + mimetype: Optional<str>
        + extension: Optional<str>
        + charset: Optional<str>
        + filename: Optional<str>
        + local_path: Optional<str>
        + url: Optional<str>
        + copy_and_update(*args, **kwargs) : StreamInfo
    }

    MarkItDown "1" -- "*" ConverterRegistration : _converters
    ConverterRegistration "1" -- "1" DocumentConverter : converter
```

**Component Description:**

The `MarkItDown` component is responsible for converting various file formats and web resources into Markdown. It acts as an orchestrator, managing a collection of `DocumentConverter` instances, each specialized in handling a specific file type. The main class, `MarkItDown`, provides methods to convert content from local files, streams, URLs, and HTTP responses. It uses `StreamInfo` to store metadata about the input source, which helps in selecting the appropriate converter. The `DocumentConverter` is an abstract base class that defines the interface for all converters. Concrete converter implementations (e.g., `PdfConverter`, `DocxConverter`) inherit from `DocumentConverter` and provide the logic to convert specific file types to Markdown. The `ConverterRegistration` class associates a `DocumentConverter` with a priority, which determines the order in which converters are tried. The `DocumentConverterResult` class encapsulates the output of a conversion, containing the Markdown content and the document's title.

**Visualization:**

The class diagram above illustrates the structure of the `MarkItDown` component, highlighting the relationships between the main classes involved in the conversion process.