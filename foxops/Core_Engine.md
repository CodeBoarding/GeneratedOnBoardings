```mermaid
graph LR
    Incarnation_Initializer["Incarnation Initializer"]
    Template_Renderer["Template Renderer"]
    Incarnation_Patcher["Incarnation Patcher"]
    Incarnation_Updater["Incarnation Updater"]
    Template_Configuration_Models["Template Configuration Models"]
    Incarnation_State_Models["Incarnation State Models"]
    Engine_Error_Handling["Engine Error Handling"]
    Service_Layer -- "calls" --> Incarnation_Initializer
    Service_Layer -- "calls" --> Incarnation_Updater
    Incarnation_Initializer -- "calls" --> Template_Renderer
    Incarnation_Updater -- "calls" --> Template_Renderer
    Incarnation_Updater -- "calls" --> Incarnation_Patcher
    Template_Renderer -- "reads" --> Template_Configuration_Models
    Incarnation_Initializer -- "writes" --> Incarnation_State_Models
    Incarnation_Updater -- "reads, writes" --> Incarnation_State_Models
    Incarnation_Initializer -- "raises" --> Engine_Error_Handling
    Template_Renderer -- "raises" --> Engine_Error_Handling
    Incarnation_Patcher -- "raises" --> Engine_Error_Handling
    Incarnation_Updater -- "raises" --> Engine_Error_Handling
    Template_Configuration_Models -- "raises" --> Engine_Error_Handling
    Incarnation_State_Models -- "raises" --> Engine_Error_Handling
    Incarnation_Initializer -- "calls" --> External_Git_Integration
    Template_Renderer -- "calls" --> External_Git_Integration
    Incarnation_Patcher -- "calls" --> External_Git_Integration
    Incarnation_Updater -- "calls" --> External_Git_Integration
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Core Engine is the central nervous system of Foxops, orchestrating the fundamental GitOps operations. It's designed to be highly modular, with distinct components handling specific aspects of template-based repository management.

### Incarnation Initializer
This component is responsible for the initial creation of a new incarnation (a repository managed by Foxops) from a specified template. It involves cloning the template, rendering it with initial variables, and committing the result to a new incarnation repository.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/initialization.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/initialization.py` (1:1)</a>


### Template Renderer
Handles the dynamic generation of content based on Jinja2 templates and provided variable data. It takes template files and a set of variables, producing the final rendered output that forms the basis of an incarnation.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/rendering.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/rendering.py` (1:1)</a>


### Incarnation Patcher
Applies changes to an existing incarnation, typically in the form of Git diffs. This component is crucial for updating incarnations by merging new template versions or variable changes into the existing repository content.


**Related Classes/Methods**:

- `foxops/engine/patching.py` (1:1)


### Incarnation Updater
Orchestrates the entire update process for an existing incarnation. This involves fetching the latest template, rendering it, calculating the necessary patches, and applying them to the incarnation repository. It ensures that an incarnation stays synchronized with its template.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/update.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/update.py` (1:1)</a>


### Template Configuration Models
Defines the data structures and validation logic for variables used in templates. These models ensure that template inputs conform to expected types and formats, preventing errors during rendering and patching.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/models/template_config.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/models/template_config.py` (1:1)</a>


### Incarnation State Models
Represents the current state and metadata of an incarnation, including its template version, variables, and other relevant properties. These models are used to persist and retrieve the state of managed repositories.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/models/incarnation_state.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/models/incarnation_state.py` (1:1)</a>


### Engine Error Handling
Defines custom exception types specific to the core engine's operations. This provides a structured way to communicate failures and allows for robust error management and user feedback.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/foxops/blob/main/src/foxops/engine/errors.py#L1-L1" target="_blank" rel="noopener noreferrer">`foxops/engine/errors.py` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)