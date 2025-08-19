```mermaid
graph LR
    FormalLanguageDatasetManager["FormalLanguageDatasetManager"]
    OnlineDataGenerator["OnlineDataGenerator"]
    DatasetIntegrityUtility["DatasetIntegrityUtility"]
    FormalLanguageDatasetManager -- "uses" --> DatasetIntegrityUtility
    OnlineDataGenerator -- "is a peer of" --> FormalLanguageDatasetManager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Data Pipeline subsystem is crucial for managing all data aspects within the xLSTM project, from initial generation and loading to preprocessing, ensuring data integrity and efficient access for model training. It embodies the project's focus on modularity and configurability by providing distinct mechanisms for data handling.

### FormalLanguageDatasetManager
Acts as the primary interface for managing formal language datasets. It handles the complete lifecycle, including initial dataset generation, seeding, providing structured data access for training and validation, and calculating dataset-specific metrics. This component ensures that data is consistently prepared and available for model consumption. Its role is fundamental for offline, pre-generated dataset scenarios.


**Related Classes/Methods**:

- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/formal_language/formal_language_dataset.py" target="_blank" rel="noopener noreferrer">`FormalLanguageDatasetManager`</a>


### OnlineDataGenerator
Specializes in dynamic, on-demand data generation and retrieval. This component is crucial for scenarios where datasets are too large to be fully pre-generated or require continuous streaming. It efficiently provides data batches and corresponding masks, optimizing memory usage and enabling flexible data access during training.


**Related Classes/Methods**:

- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/formal_language/online_generate.py" target="_blank" rel="noopener noreferrer">`OnlineDataGenerator`</a>


### DatasetIntegrityUtility
Provides a set of utility functions focused on ensuring the integrity and consistency of generated or processed datasets. Its primary role is to verify data existence, prevent redundant generation, and confirm the correctness of data post-generation through hashing mechanisms.


**Related Classes/Methods**:

- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/utils.py" target="_blank" rel="noopener noreferrer">`DatasetIntegrityUtility`</a>
- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/utils.py#L57-L75" target="_blank" rel="noopener noreferrer">`check_exist`:57-75</a>
- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/utils.py#L77-L83" target="_blank" rel="noopener noreferrer">`post_generate`:77-83</a>
- <a href="https://github.com/NX-AI/xlstm/blob/main/experiments/data/utils.py#L85-L87" target="_blank" rel="noopener noreferrer">`dataset_hash`:85-87</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)