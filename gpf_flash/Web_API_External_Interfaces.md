```mermaid
graph LR
    WDAE_API_Endpoints["WDAE API Endpoints"]
    WDAE_Query_Base["WDAE Query Base"]
    Federation_REST_Client["Federation REST Client"]
    Federation_Remote_Extension["Federation Remote Extension"]
    DAE_Command_Line_Tools["DAE Command-Line Tools"]
    Study_Wrapper["Study Wrapper"]
    DAE_Configuration_Management["DAE Configuration Management"]
    DAE_Task_Graph_Management["DAE Task Graph Management"]
    DAE_Utilities["DAE Utilities"]
    WDAE_API_Endpoints -- "Uses common query logic" --> WDAE_Query_Base
    WDAE_API_Endpoints -- "Accesses study data" --> Study_Wrapper
    WDAE_API_Endpoints -- "Initiates remote requests" --> Federation_REST_Client
    WDAE_API_Endpoints -- "Interacts for federated operations" --> Federation_Remote_Extension
    WDAE_Query_Base -- "Queries abstract study data" --> Study_Wrapper
    WDAE_Query_Base -- "Utilizes common helpers" --> DAE_Utilities
    Federation_REST_Client -- "Retrieves remote endpoint configs" --> DAE_Configuration_Management
    Federation_REST_Client -- "Uses common helpers" --> DAE_Utilities
    Federation_Remote_Extension -- "Wraps remote studies" --> Study_Wrapper
    Federation_Remote_Extension -- "Orchestrates remote calls" --> Federation_REST_Client
    DAE_Command_Line_Tools -- "Executes data pipelines" --> DAE_Task_Graph_Management
    DAE_Command_Line_Tools -- "Reads system settings" --> DAE_Configuration_Management
    DAE_Command_Line_Tools -- "Manages study data directly" --> Study_Wrapper
    DAE_Command_Line_Tools -- "Uses common helpers" --> DAE_Utilities
    Study_Wrapper -- "Utilizes common helpers" --> DAE_Utilities
    DAE_Task_Graph_Management -- "Utilizes common helpers" --> DAE_Utilities
    click WDAE_API_Endpoints href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/WDAE_API_Endpoints.md" "Details"
    click Federation_REST_Client href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Federation_REST_Client.md" "Details"
    click Federation_Remote_Extension href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Federation_Remote_Extension.md" "Details"
    click DAE_Command_Line_Tools href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/DAE_Command_Line_Tools.md" "Details"
    click Study_Wrapper href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Study_Wrapper.md" "Details"
    click DAE_Configuration_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/DAE_Configuration_Management.md" "Details"
    click DAE_Task_Graph_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/DAE_Task_Graph_Management.md" "Details"
    click DAE_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/DAE_Utilities.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Web API & External Interfaces` subsystem serves as the primary gateway for users and other systems to interact with the GPF platform. It provides a comprehensive set of REST API endpoints, a web interface, and command-line utilities. The core functionality revolves around data querying, visualization, user management, and seamless integration with distributed GPF deployments through a federation service.

### WDAE API Endpoints [[Expand]](./WDAE_API_Endpoints.md)
This component aggregates all the REST API endpoints exposed by WDAE. It is the direct interface for users and external systems to perform operations such as querying genomic data, managing datasets, handling user authentication, and initiating various analyses (enrichment, gene profiles, etc.). It acts as the central point of interaction for the web interface.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/wdae/wdae/gpf_instance/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`wdae/wdae/gpf_instance/views.py` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/wdae/wdae/datasets_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`wdae/wdae/datasets_api/views.py` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/wdae/wdae/users_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`wdae/wdae/users_api/views.py` (1:1)</a>
- `wdae/wdae/enrichment_api.py` (1:1)
- `wdae/wdae/gene_profiles_api.py` (1:1)
- `wdae/wdae/gene_scores.py` (1:1)
- `wdae/wdae/gene_sets.py` (1:1)
- `wdae/wdae/genomes_api.py` (1:1)
- `wdae/wdae/genomic_scores_api.py` (1:1)
- `wdae/wdae/genotype_browser.py` (1:1)
- `wdae/wdae/measures_api.py` (1:1)
- `wdae/wdae/person_sets_api.py` (1:1)
- `wdae/wdae/pheno_browser_api.py` (1:1)
- `wdae/wdae/pheno_tool_api.py` (1:1)
- `wdae/wdae/common_reports_api.py` (1:1)
- `wdae/wdae/family_api.py` (1:1)


### WDAE Query Base
Provides foundational functionalities and common utilities for various data querying API endpoints within WDAE. It abstracts common query patterns, data validation, and result formatting, ensuring consistency and reusability across different data access APIs.


**Related Classes/Methods**:

- `wdae/wdae/query_base.py` (1:1)


### Federation REST Client [[Expand]](./Federation_REST_Client.md)
The core client responsible for making HTTP requests to remote GPF instances. It forms the backbone of the federation service's communication, enabling seamless access to distributed GPF deployments by abstracting the complexities of remote API calls.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/federation/federation/rest_api_client.py#L1-L1" target="_blank" rel="noopener noreferrer">`federation/rest_api_client.py` (1:1)</a>


### Federation Remote Extension [[Expand]](./Federation_Remote_Extension.md)
This module within the `federation` package orchestrates and extends various remote functionalities. It manages how local GPF services (like studies, gene sets, or enrichment analyses) can be accessed and utilized from remote federated instances, providing a unified view of distributed data.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/federation/federation/remote_extension.py#L1-L1" target="_blank" rel="noopener noreferrer">`federation/remote_extension.py` (1:1)</a>


### DAE Command-Line Tools [[Expand]](./DAE_Command_Line_Tools.md)
Contains a suite of command-line utilities for administrative tasks, data import, data processing, and other system-level operations. These tools provide a non-API interface for managing and interacting with the GPF system, often used for batch operations or system maintenance.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/tools/__init__.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/tools/__init__.py` (1:1)</a>


### Study Wrapper [[Expand]](./Study_Wrapper.md)
Abstracts the underlying data structures and access mechanisms for genomic studies. It provides a consistent interface for the WDAE API endpoints and other components to interact with study data, regardless of its storage backend or format.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/wdae/wdae/studies/study_wrapper.py#L1-L1" target="_blank" rel="noopener noreferrer">`wdae/wdae/studies/study_wrapper.py` (1:1)</a>


### DAE Configuration Management [[Expand]](./DAE_Configuration_Management.md)
Handles the loading, parsing, and management of system-wide configurations for the entire GPF platform. This includes database connections, file paths, security settings, and other operational parameters, ensuring that all components operate with the correct settings.


**Related Classes/Methods**:

- `dae/configuration/gpf_configuration.py` (1:1)


### DAE Task Graph Management [[Expand]](./DAE_Task_Graph_Management.md)
Manages the definition, execution, and monitoring of complex, multi-step data processing tasks as a directed acyclic graph (DAG). This component is vital for orchestrating data pipelines and analytical workflows, especially for computationally intensive operations.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/task_graph/__init__.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/task_graph/__init__.py` (1:1)</a>


### DAE Utilities [[Expand]](./DAE_Utilities.md)
A collection of general-purpose utility functions and helper classes used across various modules within the DAE and WDAE projects. These include common data manipulation routines, file system operations, logging helpers, and other reusable functionalities.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/utils/__init__.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/utils/__init__.py` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)