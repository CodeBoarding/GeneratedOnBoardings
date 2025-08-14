```mermaid
graph LR
    Geometric_Layers["Geometric Layers"]
    Core_Green_Models["Core Green Models"]
    Data_Utilities["Data Utilities"]
    Wavelet_Layers["Wavelet Layers"]
    Research_Utilities["Research Utilities"]
    Core_Green_Models -- "utilizes" --> Geometric_Layers
    Core_Green_Models -- "utilizes" --> Data_Utilities
    Core_Green_Models -- "utilizes" --> Wavelet_Layers
    Research_Utilities -- "interacts with" --> Core_Green_Models
    Research_Utilities -- "interacts with" --> Data_Utilities
    click Geometric_Layers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Geometric_Layers.md" "Details"
    click Wavelet_Layers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/neuro-green/Wavelet_Layers.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Deep Learning Research Library/Framework

### Geometric Layers [[Expand]](./Geometric_Layers.md)
This component implements specialized neural network layers and operations designed to process Symmetric Positive Definite (SPD) matrices. It leverages geometric deep learning principles to handle covariance matrices or other SPD-valued data directly within the neural network architecture, enabling the model to operate on the Riemannian manifold of SPD matrices.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/spd_layers.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.spd_layers` (1:100)</a>


### Core Green Models
This component encompasses the primary deep learning models that utilize the `Geometric Layers` for processing Symmetric Positive Definite (SPD) data. These models are likely built using PyTorch Lightning for structured training and experimentation.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/pl_utils.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.research_code.pl_utils` (1:100)</a>


### Data Utilities
This component provides utility functions and classes for handling and preparing data, likely including transformations, loading, and preprocessing steps necessary for the `Core Green Models` to consume.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/data_utils.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.data_utils` (1:100)</a>


### Wavelet Layers [[Expand]](./Wavelet_Layers.md)
This component likely implements neural network layers or operations that incorporate wavelet transforms, potentially for feature extraction or signal processing within the deep learning models.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/wavelet_layers.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.wavelet_layers` (1:100)</a>


### Research Utilities
This component contains various utility functions and scripts specifically designed to support research activities, such as cross-validation, example notebooks, and general PyTorch Lightning utilities for experimental setups.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/crossval_utils.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.research_code.crossval_utils` (1:100)</a>
- `green.research_code.example` (1:100)
- `green.research_code.example_wo_wav` (1:100)
- <a href="https://github.com/Roche/neuro-green/blob/main/green/research_code/pl_utils.py#L1-L100" target="_blank" rel="noopener noreferrer">`green.research_code.pl_utils` (1:100)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)