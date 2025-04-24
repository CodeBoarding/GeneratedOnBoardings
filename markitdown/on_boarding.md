# MarkItDown Project Onboarding Document

## Project Description

MarkItDown is a versatile document conversion tool that transforms various file formats into Markdown. It supports a wide range of input types, including HTML, DOCX, PDF, and more, providing a flexible solution for converting documents to a universally readable and editable Markdown format. The application can be used via the command line, making it suitable for both individual use and integration into automated workflows.

## Project Flow Diagram

```mermaid
graph LR
    A[Command-Line Interface] -- parses --> B(Configuration Management)
    B -- loads --> C(Core Conversion Orchestration)
    C -- uses --> D(Document Conversion Implementations)
    C -- uses --> E(Base Abstractions and Utilities)
    D -- returns --> C
    C -- outputs --> F(File System)

## Component Descriptions

### Core Conversion Orchestration

This component serves as the central processing unit, orchestrating the entire document conversion workflow. It receives input from the CLI, utilizes configuration settings, selects the appropriate converter from the Document Conversion Implementations component based on the input file type, and manages the output process. It uses the base abstractions and utilities for stream handling and error management.

### Document Conversion Implementations

This component houses a collection of specialized converters, each responsible for transforming a specific file format (e.g., HTML, DOCX, PDF) into Markdown. Each converter implements the DocumentConverter interface and leverages format-specific libraries to extract content and convert it to Markdown.

### Command-Line Interface

The Command-Line Interface (CLI) provides the entry point for users to interact with MarkItDown. It parses command-line arguments, such as input and output file paths, and passes this information to the Core Conversion Orchestration component to initiate the conversion process.

### Configuration Management

The Configuration Management component handles the loading and management of application settings. It allows users to customize the conversion process through configuration files or command-line options, such as specifying output formats or enabling/disabling certain features.

### Base Abstractions and Utilities

This component defines fundamental classes and utilities used throughout the application. It includes the DocumentConverter base class, the DocumentConverterResult structure for representing conversion results, StreamInfo for managing input stream metadata, custom exception classes for error handling, and utilities for HTML to Markdown conversion.
