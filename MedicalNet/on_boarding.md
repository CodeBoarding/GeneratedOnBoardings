```mermaid
graph LR
    Data_Loading_and_Preprocessing_Module["Data Loading and Preprocessing Module"]
    Model_Definition_Module["Model Definition Module"]
    Data_Loading_and_Preprocessing_Module -- "outputs processed 3D medical image tensors to" --> Model_Definition_Module
    click Data_Loading_and_Preprocessing_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/MedicalNet/Data_Loading_and_Preprocessing_Module.md" "Details"
    click Model_Definition_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/MedicalNet/Model_Definition_Module.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `MedicalNet` architecture is designed as a modular ML toolkit for 3D medical image analysis, emphasizing a clear data flow pipeline. It consists of two primary components: the `Data Loading and Preprocessing Module` and the `Model Definition Module`. The `Data Loading and Preprocessing Module` is responsible for ingesting raw 3D medical image data (NIfTI files), applying essential preprocessing steps such as intensity normalization, resizing, and cropping, and transforming them into a standardized tensor format. These prepared tensors then serve as input for the `Model Definition Module`, which encapsulates various 3D ResNet architectures (e.g., ResNet-18, ResNet-50, ResNet-101) tailored for medical image analysis tasks. This clear separation ensures efficient data preparation before model consumption, forming the foundational data pipeline for the entire system.

### Data Loading and Preprocessing Module [[Expand]](./Data_Loading_and_Preprocessing_Module.md)
Manages the entire lifecycle of raw 3D medical image data, from loading NIfTI files to transforming them into a standardized tensor format. It includes preprocessing steps like intensity normalization, resizing, and cropping, with distinct pipelines for training and testing datasets.


**Related Classes/Methods**:

- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py#L15-L201" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset`:15-201</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__getitem__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__training_data_process__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__testing_data_process__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__nii2tensorarray__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__drop_invalid_range__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__random_center_crop__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__itensity_normalize_one_volume__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__resize_data__`</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/datasets/brains18.py" target="_blank" rel="noopener noreferrer">`datasets.brains18.BrainS18Dataset.__crop_data__`</a>


### Model Definition Module [[Expand]](./Model_Definition_Module.md)
Defines and provides a suite of 3D ResNet architectures commonly used in medical image analysis. It handles the construction of neural network layers and blocks, allowing for the instantiation of various ResNet depths (e.g., ResNet-18, ResNet-50, ResNet-101).


**Related Classes/Methods**:

- <a href="https://github.com/Tencent/MedicalNet/blob/master/models/resnet.py#L112-L215" target="_blank" rel="noopener noreferrer">`models.resnet.ResNet`:112-215</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/models/resnet.py#L224-L228" target="_blank" rel="noopener noreferrer">`models.resnet.resnet18`:224-228</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/models/resnet.py#L238-L242" target="_blank" rel="noopener noreferrer">`models.resnet.resnet50`:238-242</a>
- <a href="https://github.com/Tencent/MedicalNet/blob/master/models/resnet.py#L245-L249" target="_blank" rel="noopener noreferrer">`models.resnet.resnet101`:245-249</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)