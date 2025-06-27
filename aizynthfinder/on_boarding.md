```mermaid
graph LR
    Core_Orchestrator["Core Orchestrator"]
    Core_Orchestrator -- "manages search environment" --> System_Context_Configuration
    Core_Orchestrator -- "utilizes for chemical representations" --> Chemical_Data_Management
    Core_Orchestrator -- "initiates and controls search" --> Search_Route_Generation
    Core_Orchestrator -- "sends results to and receives control from" --> Analysis_User_Interaction
    Search_Route_Generation -- "queries for policies and stock" --> System_Context_Configuration
    Search_Route_Generation -- "uses for chemical entity manipulation" --> Chemical_Data_Management
    Analysis_User_Interaction -- "utilizes for evaluation" --> System_Context_Configuration
    Analysis_User_Interaction -- "processes generated routes" --> Search_Route_Generation
    click Core_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/aizynthfinder/Core_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Final Architecture Overview for `aizynthfinder`

### Core Orchestrator [[Expand]](./Core_Orchestrator.md)
The central component that initiates, coordinates, and manages the entire retrosynthesis process, from setting up the search to collecting and preparing results.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/aizynthfinder/aizynthfinder/aizynthfinder.py#L1-L1" target="_blank" rel="noopener noreferrer">`aizynthfinder.aizynthfinder` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)