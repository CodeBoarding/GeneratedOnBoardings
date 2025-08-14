```mermaid
graph LR
    Keras_Preprocessing_Layers["Keras Preprocessing Layers"]
    Keras_Data_Utilities["Keras Data Utilities"]
    Keras_Data_Utilities -- "provides data to" --> Keras_Preprocessing_Layers
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Keras data processing subsystem is designed to efficiently handle data preparation for machine learning models. It comprises two primary components: `Keras Data Utilities` and `Keras Preprocessing Layers`. The `Keras Data Utilities` component is responsible for general-purpose data management, including loading various data formats from disk (e.g., images, audio) and performing file system operations. This component acts as the initial data provider, preparing raw data for subsequent processing. The `Keras Preprocessing Layers` component then takes this prepared data and applies in-graph transformations and augmentations. These layers are designed to be integrated directly into Keras models, enabling end-to-end differentiable pipelines and streamlined deployment by incorporating data preprocessing as part of the model's computational graph. This clear separation of concerns ensures that data loading and initial preparation are handled distinctly from the in-model data transformations, leading to a modular and efficient data pipeline.

### Keras Preprocessing Layers
This component provides a collection of Keras layers designed for in-graph data preprocessing and augmentation. These layers can be directly integrated into Keras models, allowing for efficient and scalable data transformations as part of the model's computation graph. This is crucial for building end-to-end differentiable models and for streamlined deployment.


**Related Classes/Methods**:

- <a href="https://github.com/keras-team/keras/blob/master/keras/src/layers/preprocessing/text_vectorization.py" target="_blank" rel="noopener noreferrer">`keras.src.layers.preprocessing.TextVectorization`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/layers/preprocessing/index_lookup.py" target="_blank" rel="noopener noreferrer">`keras.src.layers.preprocessing.IndexLookup`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/layers/preprocessing/discretization.py" target="_blank" rel="noopener noreferrer">`keras.src.layers.preprocessing.Discretization`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/layers/preprocessing/normalization.py" target="_blank" rel="noopener noreferrer">`keras.src.layers.preprocessing.Normalization`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/layers/preprocessing/feature_space.py" target="_blank" rel="noopener noreferrer">`keras.src.layers.preprocessing.FeatureSpace`</a>


### Keras Data Utilities
This component offers a suite of general-purpose utilities for managing, loading, and preparing various data formats, including file system operations and specialized dataset creation helpers. It supports common data-related tasks outside the direct model graph, such as loading image or audio datasets from disk.


**Related Classes/Methods**:

- <a href="https://github.com/keras-team/keras/blob/master/keras/src/utils/dataset_utils.py" target="_blank" rel="noopener noreferrer">`keras.src.utils.dataset_utils`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/utils/file_utils.py" target="_blank" rel="noopener noreferrer">`keras.src.utils.file_utils`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/utils/audio_dataset_utils.py" target="_blank" rel="noopener noreferrer">`keras.src.utils.audio_dataset_utils`</a>
- <a href="https://github.com/keras-team/keras/blob/master/keras/src/utils/image_dataset_utils.py" target="_blank" rel="noopener noreferrer">`keras.src.utils.image_dataset_utils`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)