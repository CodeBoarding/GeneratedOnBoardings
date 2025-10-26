```mermaid
graph LR
    Core_Translation_Engine["Core Translation Engine"]
    Translator_Initialization_Language_Mapper["Translator Initialization & Language Mapper"]
    File_Translation_Orchestrator["File Translation Orchestrator"]
    DOCX_Content_Extractor["DOCX Content Extractor"]
    PDF_Content_Extractor["PDF Content Extractor"]
    Batch_Translation_Orchestrator["Batch Translation Orchestrator"]
    Abstract_Translation_Logic["Abstract Translation Logic"]
    Language_Support_Query["Language Support Query"]
    Core_Translation_Engine -- "initializes with" --> Translator_Initialization_Language_Mapper
    Core_Translation_Engine -- "delegates to" --> File_Translation_Orchestrator
    Core_Translation_Engine -- "delegates to" --> Batch_Translation_Orchestrator
    Core_Translation_Engine -- "exposes" --> Language_Support_Query
    Translator_Initialization_Language_Mapper -- "utilized by" --> Core_Translation_Engine
    File_Translation_Orchestrator -- "depends on" --> DOCX_Content_Extractor
    File_Translation_Orchestrator -- "depends on" --> PDF_Content_Extractor
    File_Translation_Orchestrator -- "invokes" --> Abstract_Translation_Logic
    DOCX_Content_Extractor -- "used by" --> File_Translation_Orchestrator
    PDF_Content_Extractor -- "used by" --> File_Translation_Orchestrator
    Batch_Translation_Orchestrator -- "invokes" --> Abstract_Translation_Logic
    Abstract_Translation_Logic -- "invoked by" --> File_Translation_Orchestrator
    Abstract_Translation_Logic -- "invoked by" --> Batch_Translation_Orchestrator
    Language_Support_Query -- "provides information to" --> Core_Translation_Engine
    click Core_Translation_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/deep-translator/Core_Translation_Engine.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Core Translation Engine` subsystem is primarily encapsulated within the `deep_translator.base` module, specifically centered around the `BaseTranslator` class and its associated methods. This module acts as the foundational layer for all translation operations, providing abstract interfaces and common functionalities that concrete translator implementations extend.

### Core Translation Engine [[Expand]](./Core_Translation_Engine.md)
The central orchestrator and facade for all translation operations. It provides the foundational structure and common functionalities for specific translator implementations, embodying the Adapter and Facade patterns to simplify complex operations and promote modularity and extensibility.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L16-L183" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator`:16-183</a>


### Translator Initialization & Language Mapper
Manages the initial setup of a translator instance, including handling language mapping from human-readable names to standardized codes to ensure consistency across all translation operations.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:__init__`:1-1000</a>
- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:_map_language_to_code`:1-1000</a>


### File Translation Orchestrator
Orchestrates the translation of entire files by delegating file content extraction to specific readers (DOCX, PDF) and then invoking the core translation logic on the extracted text.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:_translate_file`:1-1000</a>


### DOCX Content Extractor
Extracts plain text content from DOCX formatted files, preparing the text for subsequent translation processing.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:_read_docx`:1-1000</a>


### PDF Content Extractor
Extracts plain text content from PDF formatted files, making the text available for translation.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:_read_pdf`:1-1000</a>


### Batch Translation Orchestrator
Manages the translation of multiple text segments or a list of texts by iterating through them and applying the core translation logic to each item.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:_translate_batch`:1-1000</a>


### Abstract Translation Logic
Defines the abstract interface for the core translation mechanism. This method must be implemented by concrete translator classes (adapters) and is the actual point where text is translated.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:translate`:1-1000</a>


### Language Support Query
Provides functionalities to query and verify the languages supported by a specific translator implementation, ensuring valid translation requests.


**Related Classes/Methods**:

- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:get_supported_languages`:1-1000</a>
- <a href="https://github.com/nidhaloff/deep-translator/blob/master/deep_translator/base.py#L1-L1000" target="_blank" rel="noopener noreferrer">`deep_translator.base.BaseTranslator:is_language_supported`:1-1000</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)