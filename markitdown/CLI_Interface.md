```mermaid
graph LR
    markitdown___main___CLI_Entry_Point_["markitdown.__main__ (CLI Entry Point)"]
    MarkItDown_Core["MarkItDown Core"]
    Document_Converters["Document Converters"]
    Unclassified["Unclassified"]
    markitdown___main___CLI_Entry_Point_ -- "invokes" --> MarkItDown_Core
    MarkItDown_Core -- "orchestrates" --> Document_Converters
    MarkItDown_Core -- "receives requests from" --> markitdown___main___CLI_Entry_Point_
    Document_Converters -- "processes input from" --> MarkItDown_Core
    click MarkItDown_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/MarkItDown_Core.md" "Details"
    click Document_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Document_Converters.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The MarkItDown application follows a clear architectural pattern, with the markitdown.__main__ (CLI Entry Point) acting as the initial interface for user interaction and command parsing. This entry point then delegates the core responsibility of document conversion to the MarkItDown Core. The MarkItDown Core serves as the central orchestrator, intelligently selecting and managing various Document Converters to transform diverse input formats into Markdown. This modular design ensures that the application can easily extend its capabilities to support new document types by simply adding new converters, without altering the fundamental core logic.

### markitdown.__main__ (CLI Entry Point)
The initial interface for user interaction and command parsing.


**Related Classes/Methods**:

- `markitdown.__main__`:13-200


### MarkItDown Core [[Expand]](./MarkItDown_Core.md)
Serves as the central orchestrator, intelligently selecting and managing various Document Converters to transform diverse input formats into Markdown.


**Related Classes/Methods**:

- `markitdown._markitdown`


### Document Converters [[Expand]](./Document_Converters.md)
Perform the actual transformation of the document content into Markdown.


**Related Classes/Methods**:



### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)