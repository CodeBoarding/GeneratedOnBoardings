```mermaid
graph LR
    Data_Management["Data Management"]
    Geometric_Layers["Geometric Layers"]
    Wavelet_Layers["Wavelet Layers"]
    Core_Deep_Learning_Models["Core Deep Learning Models"]
    Training_Experimentation["Training & Experimentation"]
    Data_Management -- "provides processed input data to" --> Core_Deep_Learning_Models
    Geometric_Layers -- "are integrated into the architecture of" --> Core_Deep_Learning_Models
    Wavelet_Layers -- "are integrated into the architecture of" --> Core_Deep_Learning_Models
    Training_Experimentation -- "instantiates and trains" --> Core_Deep_Learning_Models
    Training_Experimentation -- "configures optimizers for" --> Core_Deep_Learning_Models
    click Data_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Data_Management.md" "Details"
    click Geometric_Layers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Geometric_Layers.md" "Details"
    click Wavelet_Layers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Wavelet_Layers.md" "Details"
    click Core_Deep_Learning_Models href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Core_Deep_Learning_Models.md" "Details"
    click Training_Experimentation href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Training_Experimentation.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `neuro-green` project is structured as a modular Deep Learning Research Library/Framework, focusing on computational neuroscience applications. Its architecture emphasizes clear separation of concerns for data handling, specialized neural network layers, core model definitions, and training orchestration.

### Data Management [[Expand]](./Data_Management.md)
This component is responsible for the entire data pipeline, including loading, preprocessing, and preparing neurophysiological data (e.g., EEG/MEG epochs) into a format suitable for deep learning models. It encapsulates dataset creation and any necessary data transformations.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/data_utils.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.data_utils` (1:1000)</a>


### Geometric Layers [[Expand]](./Geometric_Layers.md)
This component implements specialized neural network layers and operations that operate on Symmetric Positive Definite (SPD) matrices. It leverages geometric deep learning principles to handle covariance matrices or other SPD-valued data within the neural network architecture.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/spd_layers.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.spd_layers` (1:1000)</a>


### Wavelet Layers [[Expand]](./Wavelet_Layers.md)
This component provides custom neural network layers for extracting time-frequency features using wavelet transforms, specifically Gabor wavelets. These layers are crucial for time-frequency analysis of neurophysiological signals within the deep learning models.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/wavelet_layers.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.wavelet_layers` (1:1000)</a>


### Core Deep Learning Models [[Expand]](./Core_Deep_Learning_Models.md)
This central component defines the main deep learning architectures (`Green`, `GreenG2`, `GreenRegressorLM`, `GreenClassifierLM`) built using PyTorch Lightning. These models integrate the specialized `Geometric Layers` and `Wavelet Layers` to perform specific tasks (e.g., regression, classification) on neurophysiological data. It also includes auxiliary functions directly supporting model operations.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/pl_utils.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.research_code.pl_utils` (1:1000)</a>


### Training & Experimentation [[Expand]](./Training_Experimentation.md)
This component manages the entire training and experimentation lifecycle of the deep learning models. It handles aspects such as cross-validation setups, optimizer configuration, and the overall execution flow for model training and evaluation using PyTorch Lightning.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/crossval_utils.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.research_code.crossval_utils` (1:1000)</a>
- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/pl_utils.py#L1-L1000" target="_blank" rel="noopener noreferrer">`green.research_code.pl_utils` (1:1000)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)