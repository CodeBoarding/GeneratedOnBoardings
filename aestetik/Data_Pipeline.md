```mermaid
graph LR
    Data_Module_Configuration["Data Module Configuration"]
    Data_Preparation_Orchestrator["Data Preparation Orchestrator"]
    Spatial_Grid_Builder["Spatial Grid Builder"]
    Data_Loader_Batcher["Data Loader & Batcher"]
    Data_Module_Configuration -- "configures and validates" --> Data_Preparation_Orchestrator
    Data_Module_Configuration -- "configures and validates" --> Data_Loader_Batcher
    Data_Preparation_Orchestrator -- "delegates grid construction to" --> Spatial_Grid_Builder
    Spatial_Grid_Builder -- "provides constructed grids to" --> Data_Preparation_Orchestrator
    Data_Loader_Batcher -- "receives preprocessed data from" --> Data_Preparation_Orchestrator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Data Pipeline subsystem is critical for handling all data-related operations, from raw data ingestion and preprocessing to efficient batching and augmentation for model consumption. It ensures that the multi-modal spatial transcriptomics and morphology data is correctly prepared and delivered to the deep learning model.

### Data Module Configuration
This component serves as the high-level interface for data preparation and access, encapsulating the overall configuration and validation of data-related parameters. It adheres to the PyTorch Lightning `LightningDataModule` pattern, orchestrating the setup of datasets and data loaders.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/data_modules/data_module.py" target="_blank" rel="noopener noreferrer">`aestetik.data_modules.data_module`</a>


### Data Preparation Orchestrator
Responsible for the initial, high-level preparation of raw input data. This includes coordinating the overall data transformation, normalization, and calibrating the ratios between different data modalities (transcriptomics and morphology). It delegates specific tasks like grid construction.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_data.py" target="_blank" rel="noopener noreferrer">`aestetik.utils.utils_data`</a>


### Spatial Grid Builder
This specialized component focuses on the detailed construction of the spatial transcriptomics grid. It manages the creation of individual spots and their spatial relationships, which is fundamental for representing the unique structure of spatial transcriptomics data.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/utils/utils_grid.py" target="_blank" rel="noopener noreferrer">`aestetik.utils.utils_grid`</a>


### Data Loader & Batcher
Manages the efficient loading, batching, and iteration of preprocessed data. It supports various strategies for combining transcriptomics and morphology data and internally handles the generation of data point lists based on specified modalities, preparing data for consumption by the model.


**Related Classes/Methods**:

- <a href="https://github.com/ratschlab/aestetik/blob/main/src/aestetik/dataloader.py" target="_blank" rel="noopener noreferrer">`aestetik.dataloader`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)