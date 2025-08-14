```mermaid
graph LR
    Configuration_Management["Configuration Management"]
    Data_Loading["Data Loading"]
    Data_Preprocessing["Data Preprocessing"]
    Model_Definition["Model Definition"]
    Experiment_Orchestration["Experiment Orchestration"]
    Results_Artifacts_Storage["Results & Artifacts Storage"]
    Configuration_Management -- "provides experiment configurations to" --> Experiment_Orchestration
    Configuration_Management -- "provides data paths and loading parameters to" --> Data_Loading
    Configuration_Management -- "provides preprocessing parameters to" --> Data_Preprocessing
    Configuration_Management -- "provides model architecture parameters and hyperparameters to" --> Model_Definition
    Data_Loading -- "provides raw data to" --> Data_Preprocessing
    Data_Loading -- "is utilized by" --> Experiment_Orchestration
    Data_Preprocessing -- "provides processed data to" --> Experiment_Orchestration
    Model_Definition -- "provides models to" --> Experiment_Orchestration
    Experiment_Orchestration -- "utilizes" --> Configuration_Management
    Experiment_Orchestration -- "utilizes" --> Data_Loading
    Experiment_Orchestration -- "applies" --> Data_Preprocessing
    Experiment_Orchestration -- "instantiates and trains models from" --> Model_Definition
    Experiment_Orchestration -- "generates and stores results and artifacts in" --> Results_Artifacts_Storage
    Results_Artifacts_Storage -- "receives results and artifacts from" --> Experiment_Orchestration
    Results_Artifacts_Storage -- "provides stored data, models, or previous results to" --> Experiment_Orchestration
    click Configuration_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-meeglet-paper/Configuration_Management.md" "Details"
    click Results_Artifacts_Storage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-meeglet-paper/Results_Artifacts_Storage.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Overview of the core components for the `neuro-meeglet-paper` project, focusing on their structure, flow, and purpose, aligned with Machine Learning Research/Experimentation Project patterns.

### Configuration Management [[Expand]](./Configuration_Management.md)
This component is responsible for defining and managing all experimental parameters, hyperparameters, and data paths. It acts as the single source of truth for experiment configurations, ensuring reproducibility and easy modification of experimental setups.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/config.py" target="_blank" rel="noopener noreferrer">`core.config`</a>


### Data Loading
This component handles the loading of raw or preprocessed EEG data from specified sources. It provides utilities to create datasets and data loaders suitable for training machine learning models, likely integrating with libraries like MNE-Python or Braindecode.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/dataloaders.py" target="_blank" rel="noopener noreferrer">`core.dataloaders`</a>


### Data Preprocessing
This component contains functions and classes for cleaning, transforming, and preparing the raw EEG data for model input. This includes critical steps in EEG signal processing such as filtering, epoching, artifact rejection, and normalization.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/preprocessing.py" target="_blank" rel="noopener noreferrer">`core.preprocessing`</a>


### Model Definition
This component defines the machine learning models used in the experiments. Given the project's domain, these would likely be deep learning models (e.g., PyTorch models) or traditional machine learning models tailored for EEG data.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/models.py" target="_blank" rel="noopener noreferrer">`core.models`</a>


### Experiment Orchestration
This component orchestrates the entire experimental pipeline, from loading data and applying preprocessing to training models and evaluating their performance. It manages different experimental setups and comparisons, as exemplified by the `create_benchmark_configs` function which generates various experiment configurations.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/benchmark.py" target="_blank" rel="noopener noreferrer">`core.benchmark`</a>


### Results & Artifacts Storage [[Expand]](./Results_Artifacts_Storage.md)
This component is responsible for storing the outcomes of experiments, including trained model weights, performance metrics, visualizations, logs, and any intermediate data generated during the benchmarking process. The `Benchmark.load` method, while loading, implies interaction with these stored artifacts. This ensures reproducibility and traceability of experimental results.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-meeglet-paper/blob/main/core/benchmark.py" target="_blank" rel="noopener noreferrer">`core.benchmark`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)