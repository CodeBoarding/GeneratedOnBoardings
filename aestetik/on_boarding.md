```mermaid
graph LR
    AESTETIK_API_Orchestration["AESTETIK API & Orchestration"]
    Data_Pipeline["Data Pipeline"]
    Core_Autoencoder_Model["Core Autoencoder Model"]
    Training_Inference_Engine["Training & Inference Engine"]
    Post_processing_Analysis["Post-processing & Analysis"]
    AESTETIK_API_Orchestration -- "Initiates data preparation; Requests batched data." --> Data_Pipeline
    Data_Pipeline -- "Provides prepared and batched data." --> Training_Inference_Engine
    Training_Inference_Engine -- "Utilizes model for forward/backward passes; Receives latent representations." --> Core_Autoencoder_Model
    Training_Inference_Engine -- "Returns trained model; Provides learned latent representations." --> AESTETIK_API_Orchestration
    AESTETIK_API_Orchestration -- "Passes latent representations; Passes model outputs." --> Post_processing_Analysis
    Post_processing_Analysis -- "Provides analyzed results; Provides visualizations." --> AESTETIK_API_Orchestration
    click AESTETIK_API_Orchestration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/aestetik/AESTETIK_API_Orchestration.md" "Details"
    click Data_Pipeline href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/aestetik/Data_Pipeline.md" "Details"
    click Core_Autoencoder_Model href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/aestetik/Core_Autoencoder_Model.md" "Details"
    click Training_Inference_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/aestetik/Training_Inference_Engine.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The AESTETIK library is structured around a clear data flow, starting with the `AESTETIK API & Orchestration` component, which serves as the central control point. This component initiates the data preparation process by interacting with the `Data Pipeline`. The `Data Pipeline` is responsible for loading, preprocessing, and batching spatial transcriptomics and morphology data, providing it in a consumable format to the `Training & Inference Engine`. The `Training & Inference Engine` then utilizes the `Core Autoencoder Model` for both training and inference, managing the deep learning workflow and generating latent space representations. Finally, the `AESTETIK API & Orchestration` component passes these representations and model outputs to the `Post-processing & Analysis` component, which performs clustering and visualization to derive biological insights.

### AESTETIK API & Orchestration [[Expand]](./AESTETIK_API_Orchestration.md)
The primary user interface for the AESTETIK library, managing the overall workflow from data input to model output. It orchestrates the data pipeline, model training, and inference via `fit()` and `predict()` methods.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/AESTETIK.py" target="_blank" rel="noopener noreferrer">`src/aestetik/AESTETIK.py`</a>


### Data Pipeline [[Expand]](./Data_Pipeline.md)
Responsible for the entire data handling process, from initial loading and preprocessing of raw spatial transcriptomics and morphology data (including grid construction and normalization) to efficient batching and augmentation for model consumption.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_data.py" target="_blank" rel="noopener noreferrer">`src/aestetik/utils/utils_data.py`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_grid.py" target="_blank" rel="noopener noreferrer">`src/aestetik/utils/utils_grid.py`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/dataloader.py" target="_blank" rel="noopener noreferrer">`src/aestetik/dataloader.py`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/data_modules/data_module.py" target="_blank" rel="noopener noreferrer">`src/aestetik/data_modules/data_module.py`</a>


### Core Autoencoder Model [[Expand]](./Core_Autoencoder_Model.md)
Implements the deep learning architecture, specifically the convolutional autoencoder. It encompasses both the Encoder (for learning compact latent space representations) and the Decoder (for reconstructing input features).


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/models/model.py" target="_blank" rel="noopener noreferrer">`src/aestetik/models/model.py`</a>


### Training & Inference Engine [[Expand]](./Training_Inference_Engine.md)
Encapsulates the core autoencoder model within a PyTorch Lightning `LightningModule`. It defines the training, validation, and test steps, integrates optimizers, manages the overall training and inference loops, and applies loss functions and metrics.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/modules/aestetik_module.py" target="_blank" rel="noopener noreferrer">`src/aestetik/modules/aestetik_module.py`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/metrics/loss_function.py" target="_blank" rel="noopener noreferrer">`src/aestetik/metrics/loss_function.py`</a>


### Post-processing & Analysis
Handles downstream tasks after model inference, including applying clustering algorithms to the learned latent space representations to identify distinct spatial domains or cell types, and providing utilities for visualizing results.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_clustering.py" target="_blank" rel="noopener noreferrer">`src/aestetik/utils/utils_clustering.py`</a>
- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_visualization.py" target="_blank" rel="noopener noreferrer">`src/aestetik/utils/utils_visualization.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)