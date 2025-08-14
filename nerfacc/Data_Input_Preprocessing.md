```mermaid
graph LR
    Data_Input_Preprocessing["Data Input & Preprocessing"]
    nerf_synthetic["nerf_synthetic"]
    dnerf_synthetic["dnerf_synthetic"]
    nerf_360_v2["nerf_360_v2"]
    torch_utils_data_Dataset["torch.utils.data.Dataset"]
    File_System["File System"]
    Training_Pipeline["Training Pipeline"]
    Rendering_Engine["Rendering Engine"]
    Data_Input_Preprocessing -- "contains" --> nerf_synthetic
    Data_Input_Preprocessing -- "contains" --> dnerf_synthetic
    Data_Input_Preprocessing -- "contains" --> nerf_360_v2
    nerf_synthetic -- "inherits from" --> torch_utils_data_Dataset
    nerf_synthetic -- "reads from" --> File_System
    nerf_synthetic -- "provides data to" --> Training_Pipeline
    nerf_synthetic -- "provides data to" --> Rendering_Engine
    dnerf_synthetic -- "inherits from" --> torch_utils_data_Dataset
    dnerf_synthetic -- "reads from" --> File_System
    dnerf_synthetic -- "provides data to" --> Training_Pipeline
    dnerf_synthetic -- "provides data to" --> Rendering_Engine
    nerf_360_v2 -- "inherits from" --> torch_utils_data_Dataset
    nerf_360_v2 -- "reads from" --> File_System
    nerf_360_v2 -- "provides data to" --> Training_Pipeline
    nerf_360_v2 -- "provides data to" --> Rendering_Engine
    torch_utils_data_Dataset -- "is inherited by" --> nerf_synthetic
    torch_utils_data_Dataset -- "is inherited by" --> dnerf_synthetic
    torch_utils_data_Dataset -- "is inherited by" --> nerf_360_v2
    File_System -- "provides data to" --> nerf_synthetic
    File_System -- "provides data to" --> dnerf_synthetic
    File_System -- "provides data to" --> nerf_360_v2
    Training_Pipeline -- "consumes data from" --> nerf_synthetic
    dnerf_synthetic -- "consumes data from" --> dnerf_synthetic
    nerf_360_v2 -- "consumes data from" --> nerf_360_v2
    Rendering_Engine -- "consumes data from" --> nerf_synthetic
    dnerf_synthetic -- "consumes data from" --> dnerf_synthetic
    nerf_360_v2 -- "consumes data from" --> nerf_360_v2
    click Data_Input_Preprocessing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/nerfacc/Data_Input_Preprocessing.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Data Input & Preprocessing subsystem is a critical part of the NeRFacc project, responsible for efficiently loading, augmenting, and preparing diverse NeRF datasets for subsequent use by the Training Pipeline and Rendering Engine. It acts as an intermediary, abstracting the complexities of data handling from the core NeRF model operations. This subsystem leverages the torch.utils.data.Dataset interface, ensuring seamless integration with PyTorch's data loading utilities. It interacts directly with the File System to retrieve raw data and provides structured data to downstream components.

### Data Input & Preprocessing [[Expand]](./Data_Input_Preprocessing.md)
The overarching subsystem responsible for managing the loading, augmentation, and preparation of various NeRF datasets. It orchestrates the activities of specific dataset handlers.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/nerf_synthetic.py" target="_blank" rel="noopener noreferrer">`nerf_synthetic`</a>
- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/dnerf_synthetic.py" target="_blank" rel="noopener noreferrer">`dnerf_synthetic`</a>
- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/nerf_360_v2.py" target="_blank" rel="noopener noreferrer">`nerf_360_v2`</a>


### nerf_synthetic
Specializes in loading, augmenting, and preparing static synthetic NeRF datasets. It implements the torch.utils.data.Dataset interface to provide structured data.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/nerf_synthetic.py" target="_blank" rel="noopener noreferrer">`nerf_synthetic`</a>


### dnerf_synthetic
Handles the loading, augmentation, and preparation of dynamic synthetic NeRF datasets, also adhering to the torch.utils.data.Dataset interface.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/dnerf_synthetic.py" target="_blank" rel="noopener noreferrer">`dnerf_synthetic`</a>


### nerf_360_v2
Manages the loading, augmentation, and preparation of real-world 360-degree NeRF datasets, including integration with COLMAP data for camera pose information. It implements the torch.utils.data.Dataset interface.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/examples/datasets/nerf_360_v2.py" target="_blank" rel="noopener noreferrer">`nerf_360_v2`</a>


### torch.utils.data.Dataset
This is a foundational PyTorch abstract class that defines the standard interface for data loading. All specific dataset components (nerf_synthetic, dnerf_synthetic, nerf_360_v2) inherit from it, ensuring compatibility with PyTorch's data utilities (e.g., DataLoader).


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/" target="_blank" rel="noopener noreferrer">`torch.utils.data.Dataset`</a>


### File System
An external dependency representing the underlying storage mechanism from which raw dataset files (images, camera poses, metadata) are read.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/" target="_blank" rel="noopener noreferrer">`File System`</a>


### Training Pipeline
A downstream component that consumes the preprocessed and augmented data provided by the Data Input & Preprocessing subsystem for training NeRF models.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/" target="_blank" rel="noopener noreferrer">`Training Pipeline`</a>


### Rendering Engine
Another downstream component that utilizes the prepared dataset information (e.g., camera poses, scene metadata) for rendering NeRF scenes.


**Related Classes/Methods**:

- <a href="https://github.com/nerfstudio-project/nerfacc/blob/master/" target="_blank" rel="noopener noreferrer">`Rendering Engine`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)