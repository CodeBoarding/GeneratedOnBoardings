```mermaid
graph LR
    Workflow_Orchestrator["Workflow Orchestrator"]
    Anatomical_Preprocessing_Workflow["Anatomical Preprocessing Workflow"]
    Functional_Preprocessing_Workflow["Functional Preprocessing Workflow"]
    Configuration_Management["Configuration Management"]
    BIDS_Data_Management["BIDS Data Management"]
    Reporting_Component["Reporting Component"]
    Workflow_Engine_Nipype_["Workflow Engine (Nipype)"]
    Fieldmap_Estimation_Component["Fieldmap Estimation Component"]
    Workflow_Orchestrator -- "Orchestrates" --> Anatomical_Preprocessing_Workflow
    Workflow_Orchestrator -- "Orchestrates" --> Functional_Preprocessing_Workflow
    Workflow_Orchestrator -- "Utilizes" --> Configuration_Management
    Workflow_Orchestrator -- "Utilizes" --> BIDS_Data_Management
    Workflow_Orchestrator -- "Utilizes" --> Reporting_Component
    Workflow_Orchestrator -- "Integrates with" --> Workflow_Engine_Nipype_
    Workflow_Orchestrator -- "Interacts with" --> Fieldmap_Estimation_Component
    click Workflow_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/fmriprep/Workflow_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

These components and their relationships highlight the core functionality of fMRIPrep as a scientific data processing pipeline, emphasizing its modularity, data-driven nature, and reliance on a workflow engine for robust execution.

### Workflow Orchestrator [[Expand]](./Workflow_Orchestrator.md)
The central control component that constructs and manages the overall fMRIPrep processing pipeline using Nipype. It coordinates the execution of subject-level and BOLD-specific workflows, handling data flow and dependencies between processing steps.


**Related Classes/Methods**:

- <a href="https://github.com/nipreps/fmriprep/blob/master/fmriprep/cli/workflow.py#L34-L165" target="_blank" rel="noopener noreferrer">`fmriprep.cli.workflow:build_workflow` (34:165)</a>
- <a href="https://github.com/nipreps/fmriprep/blob/master/fmriprep/workflows/base.py#L49-L113" target="_blank" rel="noopener noreferrer">`fmriprep.workflows.base:init_fmriprep_wf` (49:113)</a>
- <a href="https://github.com/nipreps/fmriprep/blob/master/fmriprep/workflows/base.py#L116-L852" target="_blank" rel="noopener noreferrer">`fmriprep.workflows.base:init_single_subject_wf` (116:852)</a>


### Anatomical Preprocessing Workflow



**Related Classes/Methods**: _None_

### Functional Preprocessing Workflow



**Related Classes/Methods**: _None_

### Configuration Management



**Related Classes/Methods**: _None_

### BIDS Data Management



**Related Classes/Methods**: _None_

### Reporting Component



**Related Classes/Methods**: _None_

### Workflow Engine (Nipype)



**Related Classes/Methods**: _None_

### Fieldmap Estimation Component



**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)