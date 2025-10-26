```mermaid
graph LR
    API_Service["API Service"]
    Job_Database["Job Database"]
    Orchestration_Engine["Orchestration Engine"]
    Repository_Manager["Repository Manager"]
    Static_Analysis_Engine["Static Analysis Engine"]
    AI_Interpretation_Layer["AI Interpretation Layer"]
    Output_Generation_Engine["Output Generation Engine"]
    Unclassified["Unclassified"]
    Unclassified["Unclassified"]
    Unclassified["Unclassified"]
    Unclassified["Unclassified"]
    API_Service -- "Initiates Job" --> Job_Database
    API_Service -- "Triggers Analysis" --> Orchestration_Engine
    Orchestration_Engine -- "Manages Job State" --> Job_Database
    Orchestration_Engine -- "Requests Code" --> Repository_Manager
    Repository_Manager -- "Provides Code" --> Orchestration_Engine
    Orchestration_Engine -- "Requests Static Analysis" --> Static_Analysis_Engine
    Static_Analysis_Engine -- "Provides Richer Analysis Results" --> Orchestration_Engine
    Orchestration_Engine -- "Feeds Rich Analysis Data" --> AI_Interpretation_Layer
    AI_Interpretation_Layer -- "Returns Enhanced Architectural Insights" --> Orchestration_Engine
    AI_Interpretation_Layer -- "Queries Diff" --> Repository_Manager
    Orchestration_Engine -- "Passes Enhanced Insights for Generation" --> Output_Generation_Engine
    Output_Generation_Engine -- "Delivers Documentation" --> API_Service
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The CodeBoarding system operates through a robust, multi-layered architecture designed for comprehensive code analysis and documentation generation. The API Service serves as the primary external interface, initiating jobs and managing user interactions. All job lifecycle and status information is persistently stored and managed by the Job Database. The Orchestration Engine acts as the central coordinator, driving the entire documentation pipeline. It interacts with the Repository Manager to retrieve source code and then dispatches requests to the Static Analysis Engine. The Static Analysis Engine performs deep, language-specific analysis, now providing richer and more detailed structural information. This enhanced data is then fed by the Orchestration Engine to the AI Interpretation Layer. This layer, comprising specialized AI agents, performs sophisticated interpretation, generating enhanced high-level architectural insights, and may query the Repository Manager for diff analysis. Finally, the Orchestration Engine passes these refined insights to the Output Generation Engine, which transforms them into various documentation formats with enhanced capabilities, including integration with GitHub Actions, before delivering the final output back through the API Service. This updated architecture reflects significant internal enhancements in analysis depth and output quality, particularly within the AI interpretation and static analysis components.

### API Service
The external interface for CodeBoarding, handling user requests, job initiation, and status retrieval.


**Related Classes/Methods**:

- `local_app`


### Job Database
Persistent storage for managing the lifecycle, status, and results of all documentation generation jobs.


**Related Classes/Methods**:

- `duckdb_crud`


### Orchestration Engine
The central control unit that manages the entire documentation generation pipeline, coordinating all analysis and generation stages.


**Related Classes/Methods**:

- `diagram_generator`


### Repository Manager
Manages all interactions with source code repositories, including cloning, fetching, and extracting version differences.


**Related Classes/Methods**:

- `__init__`:21-32
- `git_diff`:27-76


### Static Analysis Engine
Performs deep, language-specific analysis of source code to extract richer, more detailed, and comprehensive structural information without semantic interpretation.


**Related Classes/Methods**:

- `scanner`:13-66
- `client`:10-214
- `analysis_result`


### AI Interpretation Layer
A collection of specialized AI agents that perform sophisticated interpretation of static analysis data, generating enhanced high-level architectural insights, including detailed abstractions, refined planning, robust validation, and comprehensive diff analysis, with structured outputs.


**Related Classes/Methods**:

- `meta_agent`
- `abstraction_agent`
- `details_agent`
- `planner_agent`
- `validator_agent`
- `diff_analyzer`
- `agent`:20-136
- `agent_responses`
- `prompts`


### Output Generation Engine
Transforms the final, validated architectural insights into various human-readable and diagram-friendly documentation formats, with enhanced capabilities for specific output formats and external integrations like GitHub Actions.


**Related Classes/Methods**:

- `html`:37-51
- `markdown`:20-34
- `mdx`:54-68
- `sphinx`
- `github_action`


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_

### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_

### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_

### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)