## Command-Line Interface Component Overview

This component acts as the entry point for the `markitdown` tool, handling command-line arguments, initiating the conversion process, and managing the final output.

### Data Flow Diagram

```mermaid
graph LR
    A[Command-Line Interface] -- Parses arguments & input --> B(MarkItDown) 
    B -- Selects converter --> C{Converter (e.g., HtmlConverter, PdfConverter)}
    C -- Converts document --> D(DocumentConverterResult)
    D -- Sends result --> E[_handle_output]
    E -- Writes output --> F((Output (File or Stdout)))

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px
    style C fill:#ccf,stroke:#333,stroke-width:2px
    style D fill:#ccf,stroke:#333,stroke-width:2px
    style E fill:#f9f,stroke:#333,stroke-width:2px
    style F fill:#f9f,stroke:#333,stroke-width:2px


```

### Component Descriptions

*   **Command-Line Interface:** This is the entry point of the application. It parses command-line arguments using `argparse`, determines the input source (file, URL, or standard input), and calls the `MarkItDown` class to initiate the conversion. It also handles errors and calls `_handle_output` to write the converted Markdown to the specified output.
    *   Relevant source files: `repos.markitdown.packages.markitdown.src.markitdown.__main__.main`, `repos.markitdown.packages.markitdown.src.markitdown.__main__._exit_with_error`, `repos.markitdown.packages.markitdown.src.markitdown.__main__._handle_output`

*   **MarkItDown:** The core class responsible for managing the conversion process. It receives the input from the CLI, determines the input type, selects the appropriate converter based on file type or content (using `magika` if necessary), and orchestrates the conversion. It also handles stream information and converter registration.
    *   Relevant source files: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown`, `repos.markitdown.packages.markitdown.src.markitdown._markitdown.ConverterRegistration`, `repos.markitdown.packages.markitdown.src.markitdown._markitdown._get_stream_info_guesses`

*   **Converter (e.g., HtmlConverter, PdfConverter):** These are the individual converters responsible for converting specific file types to Markdown. The `MarkItDown` class selects the appropriate converter based on the input file type. Each converter implements the `DocumentConverter` interface.
    *   Relevant source files: `markitdown._base_converter.DocumentConverter`, `markitdown.converters.PlainTextConverter`, `markitdown.converters.HtmlConverter`, `markitdown.converters.PdfConverter`, `markitdown.converters.DocxConverter`

*   **DocumentConverterResult:** This dataclass represents the result of the conversion process. It contains the converted Markdown content and any relevant metadata.
    *   Relevant source files: `markitdown._base_converter.DocumentConverterResult`

*   **_handle_output:** This function receives the converted Markdown from the `MarkItDown` class and writes it to the specified output (either a file or standard output). It handles file creation and writing, and also handles potential errors during the output process.
    *   Relevant source files: `repos.markitdown.packages.markitdown.src.markitdown.__main__._handle_output`
