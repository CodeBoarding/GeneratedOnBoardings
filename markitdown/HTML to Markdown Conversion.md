```markdown
## HTML to Markdown Conversion Overview

This document provides an overview of the HTML to Markdown conversion component within the `markitdown` project. The core functionality revolves around converting HTML content into Markdown format, utilizing `BeautifulSoup` for parsing and a customized `Markdownify` class for the actual conversion.

### Data Flow Diagram

```mermaid
graph LR
    A["StreamInfo (provides info)"] -- provides info --> B("HtmlConverter")
    B -- parses HTML --> C("BeautifulSoup")
    C -- creates soup --> D("_CustomMarkdownify")
    D -- converts soup --> E("DocumentConverterResult")

click A href "Stream Information Handler.md"
click B href "HTML to Markdown Conversion.md"
click D href "HTML to Markdown Conversion.md"
click E href "Conversion Result.md"
```

### Component Descriptions

*   **StreamInfo**: Provides information about the input stream, such as mimetype, extension, charset, and URL. It helps `HtmlConverter` determine if it can handle the input and passes encoding information to `BeautifulSoup`. Relevant source file: `repos.markitdown.packages.markitdown.src.markitdown._stream_info.StreamInfo`

*   **HtmlConverter**: Converts HTML content to Markdown. It accepts HTML files or streams, parses them using `BeautifulSoup`, and then uses `_CustomMarkdownify` to perform the conversion. It receives stream information from `StreamInfo` and sends the converted document to `DocumentConverterResult`. Relevant source file: `repos.markitdown.packages.markitdown.src.markitdown.converters._html_converter.HtmlConverter`

*   **BeautifulSoup**: A library for parsing HTML and XML. `HtmlConverter` uses `BeautifulSoup` to parse the input HTML stream and extract the relevant content. It creates a BeautifulSoup object (soup) that is passed to `_CustomMarkdownify`. Relevant source file: N/A (external library)

*   **_CustomMarkdownify**: A customized version of Markdownify that handles the core HTML to Markdown conversion. It overrides some of the base Markdownify methods to customize heading styles, remove javascript links, truncate large data URIs, and ensure URIs are properly escaped. It receives the BeautifulSoup object and converts it to Markdown, sending the result to `DocumentConverterResult`. Relevant source file: `repos.markitdown.packages.markitdown.src.markitdown.converters._markdownify._CustomMarkdownify`

*   **DocumentConverterResult**: Represents the result of a document conversion, containing the converted Markdown and the title of the document. It receives the converted Markdown from `_CustomMarkdownify`. Relevant source file: `repos.markitdown.packages.markitdown.src.markitdown._base_converter.DocumentConverterResult`
```