```mermaid
graph LR
    CLI_Interface["CLI Interface"]
    MarkItDown_Core["MarkItDown Core"]
    Input_Stream_Analysis["Input & Stream Analysis"]
    Document_Converters["Document Converters"]
    External_AI_ML_Services["External AI/ML Services"]
    Unclassified["Unclassified"]
    CLI_Interface -- "initiates" --> MarkItDown_Core
    MarkItDown_Core -- "orchestrates" --> Input_Stream_Analysis
    MarkItDown_Core -- "dispatches to" --> Document_Converters
    Document_Converters -- "interacts with" --> External_AI_ML_Services
    Document_Converters -- "returns processed data to" --> MarkItDown_Core
    MarkItDown_Core -- "provides output to" --> CLI_Interface
    click CLI_Interface href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/CLI_Interface.md" "Details"
    click MarkItDown_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/MarkItDown_Core.md" "Details"
    click Input_Stream_Analysis href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Input_Stream_Analysis.md" "Details"
    click Document_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Document_Converters.md" "Details"
    click External_AI_ML_Services href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/External_AI_ML_Services.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `markitdown` application is structured around a core orchestration engine, the `MarkItDown Core`, which is initiated by the `CLI Interface`. The `MarkItDown Core` is responsible for intelligently handling diverse input sources, including fetching web content via its integrated HTTP client functionality, and then leveraging the `Input & Stream Analysis` component to determine the appropriate processing strategy. It then dispatches the content to specialized `Document Converters`, which are designed to transform various formats into Markdown. Some of these converters extend their capabilities by interacting with `External AI/ML Services` for advanced content extraction and analysis. The processed Markdown output is ultimately returned through the `MarkItDown Core` back to the `CLI Interface` for presentation to the user.

### CLI Interface [[Expand]](./CLI_Interface.md)
The entry point for users, handling command-line arguments, orchestrating the main application flow, and presenting the final Markdown output.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/__main__.py" target="_blank" rel="noopener noreferrer">`markitdown.__main__`</a>


### MarkItDown Core [[Expand]](./MarkItDown_Core.md)
The central processing unit and facade of the application. It manages conversion requests, handles diverse input sources (local files, URIs, streams), directly manages external HTTP/HTTPS requests for fetching web content using an internal `requests` session, orchestrates stream analysis, dispatches conversion tasks to appropriate converters, and manages converter registration (including plugins).


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_markitdown.py" target="_blank" rel="noopener noreferrer">`markitdown._markitdown`</a>


### Input & Stream Analysis [[Expand]](./Input_Stream_Analysis.md)
Dedicated to analyzing incoming data streams to accurately determine file types, character encodings, and other crucial metadata required for appropriate converter selection.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/_stream_info.py" target="_blank" rel="noopener noreferrer">`markitdown._stream_info`</a>


### Document Converters [[Expand]](./Document_Converters.md)
A comprehensive collection of specialized modules, each designed to parse and transform content from a specific input format (e.g., PDF, DOCX, HTML, YouTube, audio) into a standardized Markdown representation. This component encapsulates all format-specific conversion logic and includes clients for external AI/ML services.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_csv_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._csv_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_html_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._html_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_doc_intel_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._doc_intel_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_transcribe_audio.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._transcribe_audio`</a>


### External AI/ML Services [[Expand]](./External_AI_ML_Services.md)
Represents the external cloud-based AI/ML APIs (e.g., Azure Document Intelligence, OpenAI) that `Document Converters` interact with for advanced document analysis, media processing, and content extraction.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_doc_intel_converter.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._doc_intel_converter`</a>
- <a href="https://github.com/microsoft/markitdown/blob/main/packages/markitdown/src/markitdown/converters/_transcribe_audio.py" target="_blank" rel="noopener noreferrer">`markitdown.converters._transcribe_audio`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)