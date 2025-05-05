```mermaid
graph LR
    MarkItDownException["MarkItDownException"]
    MissingDependencyException["MissingDependencyException"]
    UnsupportedFormatException["UnsupportedFormatException"]
    FailedConversionAttempt["FailedConversionAttempt"]
    FileConversionException["FileConversionException"]
    MissingDependencyException -- "is a" --> MarkItDownException
    UnsupportedFormatException -- "is a" --> MarkItDownException
    FileConversionException -- "is a" --> MarkItDownException
    FileConversionException -- "stores" --> FailedConversionAttempt
```

## Component Details

### MarkItDownException
Base exception class for all custom exceptions in the MarkItDown library.
- **Related Classes/Methods**: `repos.markitdown.packages.markitdown.src.markitdown._exceptions`

### MissingDependencyException
Exception raised when a required dependency for a converter is missing. It provides information on the missing dependency and how to install it.
- **Related Classes/Methods**: `repos.markitdown.packages.markitdown.src.markitdown._exceptions`

### UnsupportedFormatException
Exception raised when no suitable converter is found for the given file format.
- **Related Classes/Methods**: `repos.markitdown.packages.markitdown.src.markitdown._exceptions`

### FailedConversionAttempt
Represents a single attempt to convert a file, storing the converter used and any exception information.
- **Related Classes/Methods**: `repos.markitdown.packages.markitdown.src.markitdown._exceptions`

### FileConversionException
Exception raised when a suitable converter is found, but the conversion process fails. It stores a list of FailedConversionAttempt objects to provide context on the failure.
- **Related Classes/Methods**: `repos.markitdown.packages.markitdown.src.markitdown._exceptions`
