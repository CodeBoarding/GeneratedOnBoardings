```mermaid
graph LR
    CLI_Interface["CLI Interface"]
    CLI_Workflow_Adapter["CLI Workflow Adapter"]
    Web_UI_Input_Selector["Web UI Input Selector"]
    Web_UI_Processing_Handler["Web UI Processing Handler"]
    CLI_Interface -- "passes user input to" --> CLI_Workflow_Adapter
    CLI_Workflow_Adapter -- "sends status and output to" --> CLI_Interface
    Web_UI_Input_Selector -- "passes selected input to" --> Web_UI_Processing_Handler
    Web_UI_Processing_Handler -- "updates UI via" --> Web_UI_Input_Selector
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The DeepCode system provides dual user interaction channels: a Command-Line Interface (CLI) and a Web User Interface (Web UI). The `CLI Interface` serves as the primary command-line interaction point, capturing user input and displaying processing feedback. It delegates complex workflow orchestration to the `CLI Workflow Adapter`, which translates CLI commands into structured inputs for the DeepCode engine and manages the execution flow. Concurrently, the `Web UI Input Selector` facilitates web-based input collection, passing user-selected data to the `Web UI Processing Handler`. This handler is responsible for initiating and managing the core DeepCode processing triggered by the Web UI, providing real-time status updates back to the user interface. Both `CLI Workflow Adapter` and `Web UI Processing Handler` act as crucial intermediaries, bridging their respective frontends with the DeepCode's multi-agent backend for code generation and analysis.

### CLI Interface
Serves as the direct command-line interaction point. It is responsible for capturing various forms of user input (e.g., file paths, URLs, chat messages) and for displaying real-time processing status, intermediate feedback, and the final generated code or reports to the user.


**Related Classes/Methods**:



### CLI Workflow Adapter
Acts as an orchestrator for CLI-driven workflows. It adapts raw CLI user input into a structured format suitable for the core DeepCode engine, manages the execution flow of complex processing pipelines (e.g., chat-based interactions, full code generation pipelines), and bridges the CLI with the multi-agent system's core.


**Related Classes/Methods**:



### Web UI Input Selector
Provides the web-based user interface with options for selecting input methods (e.g., URL, file upload, direct chat input) and collects the corresponding user-provided data.


**Related Classes/Methods**:



### Web UI Processing Handler
Manages the execution of the core DeepCode processing workflow triggered by user actions within the Web UI. This includes handling asynchronous tasks, updating the UI with processing status, and tracking overall progress. It serves as the primary interface between the web frontend and the multi-agent backend.


**Related Classes/Methods**:

- <a href="https://github.com/HKUDS/DeepCode/blob/main/ui/handlers.py#L57-L74" target="_blank" rel="noopener noreferrer">`handlers`:57-74</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)