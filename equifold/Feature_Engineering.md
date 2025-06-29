```mermaid
graph LR
    Feature_Engineering["Feature Engineering"]
    Data_Ingestion_and_Parsing["Data Ingestion and Parsing"]
    InferenceEngine["InferenceEngine"]
    Data_Ingestion_and_Parsing -- "provides parsed data to" --> Feature_Engineering
    Feature_Engineering -- "outputs processed features to" --> InferenceEngine
    click Feature_Engineering href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/equifold/Feature_Engineering.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This analysis details the 'Feature Engineering' component, primarily implemented by `openfold_light.data_pipeline`, which transforms raw data into standardized numerical features. It clarifies its dependencies on 'Data Ingestion and Parsing' for pre-processed data and its role in providing input to the 'InferenceEngine'.

### Feature Engineering [[Expand]](./Feature_Engineering.md)
This component transforms the raw data ingested by the `Data Ingestion and Parsing` module into a standardized set of numerical features suitable for the machine learning model. It generates sequence-based features, template features, protein features from structural inputs, and Multiple Sequence Alignment (MSA) features, preparing these as input tensors for the model.


**Related Classes/Methods**:

- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L38-L62" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_template_features` (38:62)</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L65-L84" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_sequence_features` (65:84)</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L87-L120" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_mmcif_features` (87:120)</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L130-L157" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_protein_features` (130:157)</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L160-L177" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_pdb_features` (160:177)</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/data_pipeline.py#L180-L213" target="_blank" rel="noopener noreferrer">`openfold_light.data_pipeline:make_msa_features` (180:213)</a>


### Data Ingestion and Parsing
Handles the initial reading and parsing of raw data formats (e.g., FASTA, A3M, mmCIF files) and provides pre-processed data structures to other components.


**Related Classes/Methods**:

- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/parsers.py" target="_blank" rel="noopener noreferrer">`openfold_light.parsers`</a>
- <a href="https://github.com/genentech/equifold/blob/main/openfold_light/mmcif_parsing.py" target="_blank" rel="noopener noreferrer">`openfold_light.mmcif_parsing`</a>


### InferenceEngine
Consumes the processed feature dictionaries from the Feature Engineering component to perform model predictions or further processing.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)