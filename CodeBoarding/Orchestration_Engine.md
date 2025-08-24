```mermaid
graph LR
    Orchestration_Engine_DiagramGenerator_["Orchestration Engine (DiagramGenerator)"]
    Pre_Analysis_Stage["Pre-Analysis Stage"]
    Static_Analysis_Generator["Static Analysis Generator"]
    Core_Analysis_Driver["Core Analysis Driver"]
    Component_Processor["Component Processor"]
    Orchestration_Engine_DiagramGenerator_ -- "orchestrates" --> Pre_Analysis_Stage
    Orchestration_Engine_DiagramGenerator_ -- "orchestrates" --> Core_Analysis_Driver
    Pre_Analysis_Stage -- "calls" --> Static_Analysis_Generator
    Core_Analysis_Driver -- "submits tasks to" --> Component_Processor
    click Orchestration_Engine_DiagramGenerator_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Orchestration_Engine_DiagramGenerator_.md" "Details"
    click Pre_Analysis_Stage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Pre_Analysis_Stage.md" "Details"
    click Static_Analysis_Generator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Static_Analysis_Generator.md" "Details"
    click Core_Analysis_Driver href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Core_Analysis_Driver.md" "Details"
    click Component_Processor href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Component_Processor.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Orchestration Engine subsystem, centered around the DiagramGenerator, manages the entire documentation generation pipeline. It coordinates analysis stages, from pre-analysis and static analysis to core analysis and component-level processing.

### Orchestration Engine (DiagramGenerator) [[Expand]](./Orchestration_Engine_DiagramGenerator_.md)
The central control unit that manages the entire documentation generation pipeline, coordinating all analysis and generation stages. It initializes and manages the lifecycle of all analysis agents.


**Related Classes/Methods**:

- `diagram_analysis.diagram_generator.DiagramGenerator`:25-202


### Pre-Analysis Stage [[Expand]](./Pre_Analysis_Stage.md)
Performs preparatory steps before the main analysis begins. This includes generating static analysis results and instantiating all the necessary AI agents with their respective contexts.


**Related Classes/Methods**:

- `diagram_analysis.diagram_generator.DiagramGenerator:pre_analysis`


### Static Analysis Generator [[Expand]](./Static_Analysis_Generator.md)
Executes the static code analysis phase. It scans the repository for programming languages, creates language-specific LSP clients, and builds static analysis data (references, call graphs, class hierarchies, package dependencies).


**Related Classes/Methods**:

- `diagram_analysis.diagram_generator.DiagramGenerator:generate_static_analysis`


### Core Analysis Driver [[Expand]](./Core_Analysis_Driver.md)
Drives the core, multi-level analysis process. It checks for updates, performs initial project abstraction, plans the analysis of components by levels, and orchestrates the parallel processing of components.


**Related Classes/Methods**:

- `diagram_analysis.diagram_generator.DiagramGenerator:generate_analysis`


### Component Processor [[Expand]](./Component_Processor.md)
Focuses on the detailed analysis of a single component. It checks for existing analysis, applies feedback if a partial update is needed, and performs a series of detailed analysis steps (sub-CFG, CFG, structure enhancement, analysis) using the DetailsAgent. It then validates the analysis and plans for new components.


**Related Classes/Methods**:

- `diagram_analysis.diagram_generator.DiagramGenerator:process_component`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)