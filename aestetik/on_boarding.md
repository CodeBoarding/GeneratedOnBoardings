```mermaid
graph LR
    AESTETIK_API_Orchestrator["AESTETIK API & Orchestrator"]
    Data_Preparation_Loading["Data Preparation & Loading"]
    Core_Autoencoder_Model["Core Autoencoder Model"]
    PyTorch_Lightning_Training_Module["PyTorch Lightning Training Module"]
    Loss_Function_Metrics["Loss Function & Metrics"]
    Post_processing_Analysis["Post-processing & Analysis"]
    Visualization_Utilities["Visualization Utilities"]
    AESTETIK_API_Orchestrator -- "triggers" --> Data_Preparation_Loading
    AESTETIK_API_Orchestrator -- "configures" --> PyTorch_Lightning_Training_Module
    Data_Preparation_Loading -- "provides data to" --> PyTorch_Lightning_Training_Module
    PyTorch_Lightning_Training_Module -- "interacts with" --> Core_Autoencoder_Model
    PyTorch_Lightning_Training_Module -- "sends outputs and targets to" --> Loss_Function_Metrics
    Loss_Function_Metrics -- "returns computed loss to" --> PyTorch_Lightning_Training_Module
    Core_Autoencoder_Model -- "outputs latent space and reconstructed data to" --> PyTorch_Lightning_Training_Module
    PyTorch_Lightning_Training_Module -- "outputs trained model and latent space to" --> AESTETIK_API_Orchestrator
    AESTETIK_API_Orchestrator -- "sends latent space to" --> Post_processing_Analysis
    Post_processing_Analysis -- "sends results to" --> AESTETIK_API_Orchestrator
    AESTETIK_API_Orchestrator -- "sends analysis results to" --> Visualization_Utilities
    Visualization_Utilities -- "sends generated visualizations to" --> AESTETIK_API_Orchestrator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The AESTETIK library orchestrates a comprehensive spatial transcriptomics analysis pipeline. It begins with the `AESTETIK API & Orchestrator` initiating `Data Preparation & Loading` to process raw data, including calibration and grid construction. This prepared data is then fed into the `PyTorch Lightning Training Module`, which encapsulates the `Core Autoencoder Model` (comprising encoder and decoder) and interacts with `Loss Function & Metrics` during training. After training, the `AESTETIK API & Orchestrator` retrieves the trained model and latent space, passing the latter to `Post-processing & Analysis` for clustering. Finally, the results are channeled to `Visualization Utilities` to generate insightful plots, completing the analytical workflow.

### AESTETIK API & Orchestrator
The central control unit, managing the entire AESTETIK workflow from data input to result visualization. It provides the user interface and coordinates interactions between all other components.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/AESTETIK.py#L22-L492" target="_blank" rel="noopener noreferrer">`aestetik.AESTETIK`:22-492</a>


### Data Preparation & Loading
Responsible for ingesting raw spatial transcriptomics data, performing necessary preprocessing steps (e.g., calibration, grid building), and creating efficient data loaders for model consumption.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_data.py" target="_blank" rel="noopener noreferrer">`aestetik.utils.utils_data`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/dataloader.py" target="_blank" rel="noopener noreferrer">`aestetik.dataloader`</a>


### Core Autoencoder Model
Implements the autoencoder neural network architecture, consisting of an encoder for dimensionality reduction and a decoder for data reconstruction. This is the core machine learning component.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/models/model.py" target="_blank" rel="noopener noreferrer">`aestetik.models.model`</a>


### PyTorch Lightning Training Module
Encapsulates the `Core Autoencoder Model` within the PyTorch Lightning framework, handling training, validation, and testing loops, and integrating with optimization and loss calculation.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/modules/aestetik_module.py" target="_blank" rel="noopener noreferrer">`aestetik.modules.aestetik_module`</a>


### Loss Function & Metrics
Provides the mathematical functions (e.g., reconstruction loss, triplet loss) used to guide the autoencoder's learning process and evaluate its performance.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/metrics/loss_function.py" target="_blank" rel="noopener noreferrer">`aestetik.metrics.loss_function`</a>


### Post-processing & Analysis
Performs downstream analysis on the latent space generated by the autoencoder, primarily focusing on clustering to identify biological patterns.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_clustering.py" target="_blank" rel="noopener noreferrer">`aestetik.utils.utils_clustering`</a>


### Visualization Utilities
Generates various plots and visual representations of the AESTETIK analysis results, aiding in the interpretation of biological insights.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_visualization.py" target="_blank" rel="noopener noreferrer">`aestetik.utils.utils_visualization`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)