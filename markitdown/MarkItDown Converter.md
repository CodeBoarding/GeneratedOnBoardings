```mermaid
graph LR
    subgraph Input
        A[Input Data (File, URI, Stream)]
    end

    B(MarkItDown) -- Registers --> C{Converter Registration}
    B -- Determines --> D{Stream Info}
    D -- Guesses --> E{Converter Selection}
    E -- Selects --> F[DocumentConverter]
    F -- Converts --> G[DocumentConverterResult]
    G -- Returns --> B
    B -- Returns --> H[Markdown Output]
    A -- Sends Data --> B


    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px
    style C fill:#ccf,stroke:#333,stroke-width:2px
    style D fill:#ccf,stroke:#333,stroke-width:2px
    style E fill:#ccf,stroke:#333,stroke-width:2px
    style F fill:#ccf,stroke:#333,stroke-width:2px
    style G fill:#ccf,stroke:#333,stroke-width:2px
    style H fill:#f9f,stroke:#333,stroke-width:2px




```

### Component Descriptions:

**1. Input Data (File, URI, Stream)**
   - *Purpose*: Represents the various forms of input that the `MarkItDown` component can accept, including local files, URIs, and data streams.
   - *Functionality*: Provides the raw data to be converted into Markdown format.
   - *Interaction*: Sends the input data to the `MarkItDown` component for processing.
   - *Relevant source files*: N/A (Represents external input)

**2. MarkItDown**
   - *Purpose*: The central component responsible for orchestrating the conversion process.
   - *Functionality*: Manages converter registration, determines stream information, selects the appropriate converter, and returns the final Markdown output.
   - *Interaction*: Receives input data, registers converters, determines stream info, selects converter, returns markdown output.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown`

**3. Converter Registration**
   - *Purpose*: Manages the registration of available converters.
   - *Functionality*: Stores and provides access to registered `DocumentConverter` instances.
   - *Interaction*: `MarkItDown` registers converters with this component.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.ConverterRegistration`

**4. Stream Info**
   - *Purpose*: Determines information about the input stream, such as encoding and MIME type.
   - *Functionality*: Analyzes the input stream to guess its properties.
   - *Interaction*: `MarkItDown` uses this component to get stream information.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._stream_info.StreamInfo`

**5. Converter Selection**
   - *Purpose*: Selects the appropriate `DocumentConverter` based on the stream information.
   - *Functionality*: Chooses the best converter for the given input type.
   - *Interaction*: `MarkItDown` uses this component to select the converter.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown`

**6. DocumentConverter**
   - *Purpose*: Base class for all converters; responsible for converting a specific file type or data source to Markdown.
   - *Functionality*: Implements the conversion logic for a specific format.
   - *Interaction*: Selected by `Converter Selection` and used to convert the input data.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._base_converter.DocumentConverter`

**7. DocumentConverterResult**
   - *Purpose*: Represents the result of a document conversion.
   - *Functionality*: Stores the converted text and any associated metadata.
   - *Interaction*: Returned by `DocumentConverter` to `MarkItDown`.
   - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._base_converter.DocumentConverterResult`

**8. Markdown Output**
   - *Purpose*: The final Markdown output.
   - *Functionality*: Presents the converted content.
   - *Interaction*: Returned by `MarkItDown`.
   - *Relevant source files*: N/A (Represents final output)
