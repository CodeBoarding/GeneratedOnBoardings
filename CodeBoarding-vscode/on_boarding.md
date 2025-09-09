```mermaid
graph LR
    VSCode_Extension_Core["VSCode Extension Core"]
    Code_Analysis_Engine["Code Analysis Engine"]
    Diagram_Visualization_Provider["Diagram Visualization Provider"]
    Details_View_Provider["Details View Provider"]
    Copilot_Context_Service["Copilot Context Service"]
    File_System_Git_Tracking_Service["File System & Git Tracking Service"]
    Unclassified["Unclassified"]
    VSCode_Extension_Core -- "Initializes & Orchestrates" --> Code_Analysis_Engine
    VSCode_Extension_Core -- "Initializes & Orchestrates" --> Diagram_Visualization_Provider
    VSCode_Extension_Core -- "Initializes & Orchestrates" --> Details_View_Provider
    VSCode_Extension_Core -- "Initializes & Orchestrates" --> Copilot_Context_Service
    VSCode_Extension_Core -- "Initializes & Orchestrates" --> File_System_Git_Tracking_Service
    Code_Analysis_Engine -- "Requests Data From" --> File_System_Git_Tracking_Service
    Code_Analysis_Engine -- "Provides Analysis Data To" --> Diagram_Visualization_Provider
    Code_Analysis_Engine -- "Provides Analysis Results To" --> Details_View_Provider
    Diagram_Visualization_Provider -- "Requests CFG Data From" --> Code_Analysis_Engine
    Diagram_Visualization_Provider -- "Receives Notifications From" --> File_System_Git_Tracking_Service
    Details_View_Provider -- "Queries Results From" --> Code_Analysis_Engine
    Details_View_Provider -- "Sends Context To" --> Copilot_Context_Service
    Copilot_Context_Service -- "Requests File Content From" --> File_System_Git_Tracking_Service
    Copilot_Context_Service -- "Receives Context From" --> Details_View_Provider
    File_System_Git_Tracking_Service -- "Provides File Content To" --> Code_Analysis_Engine
    File_System_Git_Tracking_Service -- "Provides File Content To" --> Copilot_Context_Service
    File_System_Git_Tracking_Service -- "Notifies Changes To" --> Diagram_Visualization_Provider
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The CodeBoarding VSCode extension operates around a core VSCode Extension Core that orchestrates the various functionalities. The Code Analysis Engine is central to the extension's purpose, performing static analysis and generating Control Flow Graphs (CFGs). These CFGs are then visualized by the Diagram Visualization Provider and detailed analysis results are presented by the Details View Provider. To enhance AI-assisted development, the Copilot Context Service prepares relevant code context. All these components rely on the File System & Git Tracking Service for accessing file content and monitoring workspace changes.

### VSCode Extension Core
The foundational component responsible for the extension's lifecycle, command registration, and overall orchestration within the VSCode environment.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/extension.ts" target="_blank" rel="noopener noreferrer">`src/extension.ts`</a>


### Code Analysis Engine
Performs static code analysis, generates Control Flow Graphs (CFGs), and manages the persistence and retrieval of analysis results.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/AnalysisService.ts" target="_blank" rel="noopener noreferrer">`src/AnalysisService.ts`</a>


### Diagram Visualization Provider
Manages the interactive rendering and display of the Control Flow Graph within a dedicated VSCode webview.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/DiagramViewProvider.ts" target="_blank" rel="noopener noreferrer">`src/DiagramViewProvider.ts`</a>


### Details View Provider
Provides a dedicated webview panel within VSCode to display detailed information about selected code elements and analysis results.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/DetailsViewProvider.ts" target="_blank" rel="noopener noreferrer">`src/DetailsViewProvider.ts`</a>


### Copilot Context Service
Handles the preparation of relevant code snippets and contextual information for AI services like GitHub Copilot.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/services/CopilotContextService.ts" target="_blank" rel="noopener noreferrer">`src/services/CopilotContextService.ts`</a>


### File System & Git Tracking Service
Monitors the workspace for file system changes, retrieves file content, and interacts with Git for version control status.


**Related Classes/Methods**:

- <a href="https://github.com/CodeBoarding/CodeBoarding-vscode/blob/main/src/FileTrackingService.ts" target="_blank" rel="noopener noreferrer">`src/FileTrackingService.ts`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)