## Stream Metadata Handler Overview

This component focuses on managing and updating metadata associated with the input stream throughout the conversion process. It ensures consistent access and modification of stream information.

### Data Flow Diagram

```mermaid
graph LR
    A[MarkItDown] -- "Initializes" --> B(StreamInfo)
    B -- "Provides" --> C{Converter (e.g., HtmlConverter)}
    C -- "Updates" --> B
    C -- "Uses" --> D[Output]
    B -- "Provides" --> D


```

### Component Descriptions

*   **MarkItDown**: The main class that initiates the conversion process. It creates and initializes the `StreamInfo` object based on the input provided (file, stream, URI, etc.).
    *   Purpose: Orchestrates the conversion process.
    *   Interaction: Initializes `StreamInfo` and passes it to the appropriate converter.
    *   Relevant source files: `markitdown._markitdown.MarkItDown`

*   **StreamInfo**: Represents the metadata associated with the input stream. It stores information like mimetype, filename, charset, and URL. Converters can access and update this information.
    *   Purpose: Manages and provides stream metadata.
    *   Interaction: Initialized by `MarkItDown`, accessed and updated by converters, and used to provide metadata for the output.
    *   Relevant source files: `markitdown._stream_info.StreamInfo`

*   **Converter (e.g., HtmlConverter)**: A specific converter responsible for converting a particular type of input (e.g., HTML). It uses the `StreamInfo` object to access stream metadata and may update it during the conversion process.
    *   Purpose: Converts the input to the desired output format.
    *   Interaction: Receives `StreamInfo` from `MarkItDown`, uses it to guide the conversion, and updates it if necessary.
    *   Relevant source files: `markitdown.converters._html_converter.HtmlConverter`, `markitdown.converters._zip_converter.ZipConverter`, `markitdown.converters._pptx_converter.PptxConverter`, `markitdown.converters._epub_converter.EpubConverter`

*   **Output**: Represents the final output of the conversion process. It utilizes the stream metadata from `StreamInfo` to generate the output in the desired format.
    *   Purpose: Generates the final output.
    *   Interaction: Receives converted content from the converter and stream metadata from `StreamInfo`.
    *   Relevant source files: N/A (Represents the final result, not a specific class)
