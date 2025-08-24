```mermaid
graph LR
    Document_Acquisition_Tools["Document Acquisition Tools"]
    Document_Segmentation_Core["Document Segmentation Core"]
    Document_Segmentation_Agent["Document Segmentation Agent"]
    Document_Segmentation_Agent -- "initiates acquisition via" --> Document_Acquisition_Tools
    Document_Segmentation_Agent -- "delegates tasks to" --> Document_Segmentation_Core
    Document_Acquisition_Tools -- "provides documents to" --> Document_Segmentation_Agent
    Document_Segmentation_Core -- "returns results to" --> Document_Segmentation_Agent
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Document Processing Agents` subsystem is responsible for the entire lifecycle of external document handling, from acquisition and preprocessing to segmentation and analysis. It acts as a self-contained unit for transforming raw external documents into structured, segmented information usable by other agents in the system.

### Document Acquisition Tools
Responsible for retrieving raw documents from various external sources (e.g., PDF files, Git repositories) and converting them into a standardized, processable format suitable for further analysis.


**Related Classes/Methods**:

- <a href="https://github.com/HKUDS/DeepCode/blob/main/tools/pdf_downloader.py" target="_blank" rel="noopener noreferrer">`/home/ubuntu/CodeBoarding/repo/DeepCode/tools/pdf_downloader.py`</a>
- <a href="https://github.com/HKUDS/DeepCode/blob/main/tools/git_command.py" target="_blank" rel="noopener noreferrer">`/home/ubuntu/CodeBoarding/repo/DeepCode/tools/git_command.py`</a>
- <a href="https://github.com/HKUDS/DeepCode/blob/main/tools/pdf_converter.py" target="_blank" rel="noopener noreferrer">`/home/ubuntu/CodeBoarding/repo/DeepCode/tools/pdf_converter.py`</a>


### Document Segmentation Core
Provides the core functionalities for in-depth analysis and intelligent segmentation of document content. This includes detecting document types, determining optimal segmentation strategies, and applying various algorithms for semantic chunking and preserving algorithm integrity.


**Related Classes/Methods**:

- <a href="https://github.com/HKUDS/DeepCode/blob/main/tools/document_segmentation_server.py" target="_blank" rel="noopener noreferrer">`/home/ubuntu/CodeBoarding/repo/DeepCode/tools/document_segmentation_server.py`</a>


### Document Segmentation Agent
Acts as a specialized agent within the multi-agent system, orchestrating the entire document segmentation workflow. It manages the lifecycle of document processing, from initiating acquisition to delegating segmentation tasks and validating the output.


**Related Classes/Methods**:

- <a href="https://github.com/HKUDS/DeepCode/blob/main/workflows/agents/document_segmentation_agent.py" target="_blank" rel="noopener noreferrer">`/home/ubuntu/CodeBoarding/repo/DeepCode/workflows/agents/document_segmentation_agent.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)