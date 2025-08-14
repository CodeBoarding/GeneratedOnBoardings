```mermaid
graph LR
    Indexed_Dataset_Management["Indexed Dataset Management"]
    Data_Preprocessing_Utilities["Data Preprocessing Utilities"]
    Data_Iteration_Batching["Data Iteration & Batching"]
    Indexed_Dataset_Management -- "provides raw or indexed data to" --> Data_Preprocessing_Utilities
    Indexed_Dataset_Management -- "directly supplies data to" --> Data_Iteration_Batching
    Data_Preprocessing_Utilities -- "delivers transformed and potentially pre-batched data to" --> Data_Iteration_Batching
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Dataset & Data Loading` subsystem encompasses all functionalities related to the storage, retrieval, preprocessing, and efficient delivery of data for machine learning tasks within the ERNIE project. Its primary responsibility is to bridge the gap between raw or pre-processed data files and the model's training/evaluation loop, ensuring data is available in the correct format and batches.

### Indexed Dataset Management
This component is responsible for the persistent storage and indexed access of large, pre-processed datasets. It manages the raw data content and associated metadata (like offsets and sizes), enabling efficient, direct access to individual data items. It acts as the foundational data layer, providing raw or indexed data.


**Related Classes/Methods**:

- <a href="https://github.com/thunlp/ERNIE/blob/master/code/indexed_dataset.py" target="_blank" rel="noopener noreferrer">`code.indexed_dataset`</a>


### Data Preprocessing Utilities
This component provides a collection of utility functions for transforming and preparing data for model consumption. Key functionalities include padding sequences, filtering data based on size or other criteria, and grouping individual samples into optimized batches. It takes raw or indexed data and prepares it for iteration.


**Related Classes/Methods**:

- <a href="https://github.com/thunlp/ERNIE/blob/master/code/data_utils.py" target="_blank" rel="noopener noreferrer">`code.data_utils`</a>


### Data Iteration & Batching
This component orchestrates the dynamic flow of data during training and evaluation. It manages epoch progression, handles data shuffling, implements sharding for distributed environments, and supports checkpointing of the iteration state. It acts as the primary interface between the prepared data and the training loop, delivering data in batches.


**Related Classes/Methods**:

- <a href="https://github.com/thunlp/ERNIE/blob/master/code/iterators.py" target="_blank" rel="noopener noreferrer">`code.iterators`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)