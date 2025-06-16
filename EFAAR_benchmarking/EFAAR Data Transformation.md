```mermaid
graph LR
    DataEmbedding["DataEmbedding"]
    ControlNormalization["ControlNormalization"]
    DataEmbedding -- "prepares data for" --> ControlNormalization
    ControlNormalization -- "further processes data from" --> DataEmbedding
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The EFAAR Data Transformation subsystem is responsible for the core data processing steps within the EFAAR method. It encompasses initial dimensionality reduction using PCA and various normalization techniques, including batch-based centering and scaling, and control-based scaling, centering, and Typical Variation Normalization (TVN). The main flow involves first embedding the raw biological data, followed by advanced normalization steps that leverage control samples to prepare the data for downstream analysis, ensuring consistency and mitigating batch effects.

### DataEmbedding
This component is responsible for embedding high-dimensional data using Principal Component Analysis (PCA) and performing initial preprocessing steps such as centering and scaling, either globally or by batch. It provides functions to prepare data for further analysis by reducing dimensionality and normalizing features.


**Related Classes/Methods**:

- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L30-L47" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.embed_by_pca_anndata` (30:47)</a>
- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L78-L104" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.embed_by_pca` (78:104)</a>
- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L50-L75" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.centerscale_by_batch` (50:75)</a>


### ControlNormalization
This component focuses on normalizing and aligning data based on control samples. It includes functionalities for fitting PCA on control units, centering and scaling embeddings relative to controls, and applying Typical Variation Normalization (TVN) to adjust for batch effects and ensure consistency across different experimental batches.


**Related Classes/Methods**:

- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L141-L167" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.pca_centerscale_on_controls` (141:167)</a>
- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L107-L138" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.centerscale_on_controls` (107:138)</a>
- <a href="https://github.com/recursionpharma/EFAAR_benchmarking/blob/master/efaar_benchmarking/efaar.py#L170-L206" target="_blank" rel="noopener noreferrer">`EFAAR_benchmarking.efaar_benchmarking.efaar.tvn_on_controls` (170:206)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)