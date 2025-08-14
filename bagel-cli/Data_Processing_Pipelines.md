```mermaid
graph LR
    CLI_Orchestrator["CLI Orchestrator"]
    Data_Processing_Utilities["Data Processing Utilities"]
    Mapping_Service["Mapping Service"]
    Data_Models["Data Models"]
    Model_Utilities["Model Utilities"]
    CLI_Orchestrator -- "extracts data using" --> Data_Processing_Utilities
    CLI_Orchestrator -- "constructs models via" --> Model_Utilities
    CLI_Orchestrator -- "directly instantiates" --> Data_Models
    Data_Processing_Utilities -- "translates terms with" --> Mapping_Service
    Model_Utilities -- "creates and populates" --> Data_Models
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### CLI Orchestrator
A unified component that serves as the user-facing command-line interface and the central orchestrator for the data processing pipeline. It parses the pheno command, manages the workflow, and directs the extraction, transformation, and model instantiation processes.


**Related Classes/Methods**:

- `bagel/cli.py`


### Data Processing Utilities
A collection of specialized modules that perform the "Extract" and "Transform" phases for different data types (phenotypic, BIDS). They handle reading source files and applying initial transformations, including semantic mapping of terms.


**Related Classes/Methods**:

- `bagel/utilities/pheno_utils.py`
- `bagel/utilities/bids_utils.py`


### Mapping Service
A shared service responsible for semantic mapping. It translates terms from input files into the standardized Neurobagel vocabulary, ensuring data consistency. It is utilized by the data processing utilities during the transformation stage.


**Related Classes/Methods**:

- `bagel/mappings.py`


### Data Models
A set of Pydantic models defining the formal schema for the output "bagel." These models are instantiated directly by the orchestrator and populated via model utilities to ensure the final data structure is valid.


**Related Classes/Methods**:

- `bagel/models.py`


### Model Utilities
Provides helper functions that facilitate the creation and population of the Pydantic Data Models. It acts as a bridge between raw processed data and the final structured models.


**Related Classes/Methods**:

- `bagel/utilities/model_utils.py`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)