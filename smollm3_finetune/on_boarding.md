```mermaid
graph LR
    Entry_Point["Entry Point"]
    Configuration_Management["Configuration Management"]
    Data_Pipeline["Data Pipeline"]
    Model_Abstraction["Model Abstraction"]
    Training_Orchestrator["Training Orchestrator"]
    Entry_Point -- "Initializes and Uses" --> Configuration_Management
    Entry_Point -- "Initializes" --> Data_Pipeline
    Entry_Point -- "Initializes" --> Model_Abstraction
    Entry_Point -- "Initializes and Invokes" --> Training_Orchestrator
    Configuration_Management -- "Provides Configuration To" --> Model_Abstraction
    Configuration_Management -- "Provides Configuration To" --> Data_Pipeline
    Configuration_Management -- "Provides Configuration To" --> Training_Orchestrator
    Data_Pipeline -- "Provides Data To" --> Training_Orchestrator
    Model_Abstraction -- "Provides Model To" --> Training_Orchestrator
    click Entry_Point href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/smollm3_finetune/Entry_Point.md" "Details"
    click Configuration_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/smollm3_finetune/Configuration_Management.md" "Details"
    click Data_Pipeline href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/smollm3_finetune/Data_Pipeline.md" "Details"
    click Model_Abstraction href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/smollm3_finetune/Model_Abstraction.md" "Details"
    click Training_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/smollm3_finetune/Training_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Entry Point [[Expand]](./Entry_Point.md)
The primary execution script that orchestrates the entire training process. It initializes all other major components, loads configurations, sets up the training environment, and invokes the `Training Orchestrator`.


**Related Classes/Methods**:

- `train`


### Configuration Management [[Expand]](./Configuration_Management.md)
Centralized management of all training parameters, model specifications, data paths, and hyper-parameters. It is responsible for loading, validating, and providing access to configuration settings, supporting base and custom configurations.


**Related Classes/Methods**:

- <a href="https://github.com/Josephrp/smollm3_finetune/blob/main/src/config.py#L1-L1" target="_blank" rel="noopener noreferrer">`config` (1:1)</a>


### Data Pipeline [[Expand]](./Data_Pipeline.md)
Handles the entire data lifecycle, including dataset loading, preprocessing (e.g., tokenization, formatting), and creating efficient data loaders for both training and evaluation phases.


**Related Classes/Methods**:

- <a href="https://github.com/Josephrp/smollm3_finetune/blob/main/src/data.py#L1-L1" target="_blank" rel="noopener noreferrer">`data` (1:1)</a>


### Model Abstraction [[Expand]](./Model_Abstraction.md)
Encapsulates the logic for loading pre-trained models, defining model architectures, and managing different model variants (e.g., quantization, LoRA adapters). It provides a consistent interface for model interaction.


**Related Classes/Methods**:

- <a href="https://github.com/Josephrp/smollm3_finetune/blob/main/src/model.py#L1-L1" target="_blank" rel="noopener noreferrer">`model` (1:1)</a>


### Training Orchestrator [[Expand]](./Training_Orchestrator.md)
Implements the core training and fine-tuning loop. This includes managing forward and backward passes, optimization, loss calculation, and integration with acceleration libraries (e.g., `accelerate`). It also handles callbacks and evaluation logic.


**Related Classes/Methods**:

- <a href="https://github.com/Josephrp/smollm3_finetune/blob/main/src/trainer.py#L1-L1" target="_blank" rel="noopener noreferrer">`trainer` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)