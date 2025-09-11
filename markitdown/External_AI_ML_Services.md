```mermaid
graph LR
    Document_Converters["Document Converters"]
    Azure_Document_Intelligence_Adapter["Azure Document Intelligence Adapter"]
    Audio_Transcription_Adapter["Audio Transcription Adapter"]
    External_AI_ML_APIs_Azure_Document_Intelligence_["External AI/ML APIs (Azure Document Intelligence)"]
    External_AI_ML_APIs_OpenAI_["External AI/ML APIs (OpenAI)"]
    Unclassified["Unclassified"]
    Document_Converters -- "utilizes" --> Azure_Document_Intelligence_Adapter
    Document_Converters -- "utilizes" --> Audio_Transcription_Adapter
    Azure_Document_Intelligence_Adapter -- "connects to" --> External_AI_ML_APIs_Azure_Document_Intelligence_
    External_AI_ML_APIs_Azure_Document_Intelligence_ -- "sends responses to" --> Azure_Document_Intelligence_Adapter
    Audio_Transcription_Adapter -- "connects to" --> External_AI_ML_APIs_OpenAI_
    External_AI_ML_APIs_OpenAI_ -- "sends responses to" --> Audio_Transcription_Adapter
    Azure_Document_Intelligence_Adapter -- "provides results to" --> Document_Converters
    Audio_Transcription_Adapter -- "provides results to" --> Document_Converters
    click Document_Converters href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/markitdown/Document_Converters.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `markitdown` project's conversion subsystem is designed to transform various document types into Markdown, leveraging external AI/ML services for enhanced processing. The core `Document Converters` component orchestrates this process, acting as a client to specialized adapters. The `Azure Document Intelligence Adapter` facilitates interaction with the `External AI/ML APIs (Azure Document Intelligence)` for advanced document analysis, while the `Audio Transcription Adapter` interfaces with `External AI/ML APIs (OpenAI)` for transcribing audio content. These adapters abstract the complexities of external API communication, providing structured results back to the `Document Converters`. This architecture ensures a clear separation of concerns, allowing the core conversion logic to remain independent of specific external service implementations.

### Document Converters [[Expand]](./Document_Converters.md)
This component is responsible for converting various document types into Markdown. It acts as the primary client for the AI/ML service adapters, orchestrating when and how to leverage external AI/ML capabilities to enhance the conversion process.


**Related Classes/Methods**:

- `markitdown.converters._transcribe_audio`


### Azure Document Intelligence Adapter
An adapter specifically designed to interface with the Azure Document Intelligence API. It handles the communication protocol, authentication, request formatting, and response parsing for sending documents to Azure for advanced analysis and receiving structured data.


**Related Classes/Methods**:



### Audio Transcription Adapter
An adapter responsible for interacting with external audio transcription services (e.g., OpenAI's Whisper API). It manages the submission of audio streams and the retrieval of transcribed text, abstracting the external API details from the core conversion logic.


**Related Classes/Methods**:



### External AI/ML APIs (Azure Document Intelligence)
Represents the actual cloud-based Azure Document Intelligence service. This external dependency provides advanced capabilities for extracting layout, text, and structure from various document formats. This is an external service and not directly represented by internal code.


**Related Classes/Methods**:



### External AI/ML APIs (OpenAI)
Represents the actual cloud-based OpenAI service, specifically utilized by the `Audio Transcription Adapter` for converting audio streams into text. This is an external service and not directly represented by internal code.


**Related Classes/Methods**:

- `OpenAI API (External Service)`:1-10


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)