```mermaid
graph LR
    Data_Loader["Data Loader"]
    Text_Data_Preparer["Text Data Preparer"]
    Text_Data_Preparer -- "utilizes" --> Data_Loader
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Data Management` subsystem encompasses all functionalities related to data handling within the project. This includes the initial loading of diverse datasets, their subsequent preprocessing (e.g., tokenization for text), and the crucial splitting of data into specific subsets required for machine unlearning and attack simulations (training, validation, forget, retain, and attack-specific partitions).

### Data Loader
This component serves as the primary utility for abstracting and managing the loading of diverse datasets from various sources, such as WikiText-103 and CIFAR-100. It provides a consistent interface for data retrieval, ensuring that other parts of the system can access raw data uniformly, regardless of its origin or format.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/utils/loader.py#L43-L136" target="_blank" rel="noopener noreferrer">`core.utils.loader.load_data`:43-136</a>


### Text Data Preparer
This component is responsible for orchestrating the comprehensive preparation of specific target datasets, with a particular focus on text-based machine learning tasks. Its responsibilities include invoking the `Data Loader` to retrieve raw data, performing necessary preprocessing steps like tokenization, and critically, splitting the processed data into specialized subsets (training, validation, forget, retain, and attack-specific partitions) essential for machine unlearning and attack simulations.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/text/target_data.py#L10-L45" target="_blank" rel="noopener noreferrer">`text.target_data.main`:10-45</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)