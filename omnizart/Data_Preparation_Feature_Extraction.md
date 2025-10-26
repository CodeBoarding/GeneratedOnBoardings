```mermaid
graph LR
    Dataset_Manager["Dataset Manager"]
    Audio_I_O_Handler["Audio I/O Handler"]
    Core_Feature_Extraction_Layer["Core Feature Extraction Layer"]
    General_Label_Processor["General Label Processor"]
    Domain_Specific_Feature_Label_Processor_Beat["Domain-Specific Feature & Label Processor - Beat"]
    Domain_Specific_Feature_Label_Processor_Chord["Domain-Specific Feature & Label Processor - Chord"]
    Feature_Wrapper_Functions["Feature Wrapper Functions"]
    Dataset_Manager -- "provides audio file paths to" --> Audio_I_O_Handler
    Dataset_Manager -- "provides label file paths to" --> General_Label_Processor
    Audio_I_O_Handler -- "receives audio file paths from" --> Dataset_Manager
    Audio_I_O_Handler -- "feeds preprocessed audio to" --> Core_Feature_Extraction_Layer
    Core_Feature_Extraction_Layer -- "receives preprocessed audio from" --> Audio_I_O_Handler
    Core_Feature_Extraction_Layer -- "provides features to" --> Domain_Specific_Feature_Label_Processor_Beat
    Core_Feature_Extraction_Layer -- "provides features to" --> Domain_Specific_Feature_Label_Processor_Chord
    General_Label_Processor -- "receives label file paths from" --> Dataset_Manager
    General_Label_Processor -- "provides processed labels to" --> Domain_Specific_Feature_Label_Processor_Beat
    Domain_Specific_Feature_Label_Processor_Beat -- "integrates features from" --> Core_Feature_Extraction_Layer
    Domain_Specific_Feature_Label_Processor_Beat -- "receives processed labels from" --> General_Label_Processor
    Domain_Specific_Feature_Label_Processor_Chord -- "integrates features from" --> Core_Feature_Extraction_Layer
    Domain_Specific_Feature_Label_Processor_Chord -- "receives processed labels from" --> General_Label_Processor
    Feature_Wrapper_Functions -- "provides utilities to" --> Core_Feature_Extraction_Layer
    Feature_Wrapper_Functions -- "provides utilities to" --> Domain_Specific_Feature_Label_Processor_Beat
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Data Preparation & Feature Extraction` subsystem is responsible for transforming raw audio and ground truth labels into a structured format suitable for machine learning models. It encompasses the entire workflow from initial data loading and preprocessing to the extraction of various domain-specific musical features and the preparation of corresponding labels.

### Dataset Manager
Manages dataset paths, provides utilities for accessing audio-label pairs, and includes functionality for dataset download. It serves as the primary source for data paths.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/constants/datasets.py" target="_blank" rel="noopener noreferrer">`omnizart.constants.datasets`</a>


### Audio I/O Handler
Handles the loading of raw audio files from disk and performs initial signal preprocessing (e.g., resampling, normalization).


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/io.py" target="_blank" rel="noopener noreferrer">`omnizart.io`</a>


### Core Feature Extraction Layer
Encompasses the extraction of various fundamental musical features such as Constant-Q Cepstral Coefficients (CFP), Constant Q Transform (CQT), Harmonic-Percussive Features (HCFP), and beat/downbeat information. These are generic feature representations derived directly from preprocessed audio.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/feature/cfp.py" target="_blank" rel="noopener noreferrer">`omnizart.feature.cfp`</a>
- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/feature/cqt.py" target="_blank" rel="noopener noreferrer">`omnizart.feature.cqt`</a>
- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/feature/hcfp.py" target="_blank" rel="noopener noreferrer">`omnizart.feature.hcfp`</a>
- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/feature/beat_for_drum.py" target="_blank" rel="noopener noreferrer">`omnizart.feature.beat_for_drum`</a>


### General Label Processor
Loads and transforms general music ground truth labels into a format consumable by machine learning models.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/music/labels.py" target="_blank" rel="noopener noreferrer">`omnizart.music.labels`</a>


### Domain-Specific Feature & Label Processor - Beat
Extracts and processes features and ground truth labels specifically for beat tracking tasks, often combining outputs from core feature extractors with label data.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/beat/features.py" target="_blank" rel="noopener noreferrer">`omnizart.beat.features`</a>


### Domain-Specific Feature & Label Processor - Chord
Manages feature and label extraction for chord recognition, including data augmentation and segmentation, integrating core features with chord-specific label processing.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/chord/features.py" target="_blank" rel="noopener noreferrer">`omnizart.chord.features`</a>


### Feature Wrapper Functions
Provides utility functions that support various feature extraction processes, such as patching and converting between frame-based and time-based representations.


**Related Classes/Methods**:

- <a href="https://github.com/Music-and-Culture-Technology-Lab/omnizart/blob/master/omnizart/feature/wrapper_func.py" target="_blank" rel="noopener noreferrer">`omnizart.feature.wrapper_func`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)