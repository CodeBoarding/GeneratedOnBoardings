```mermaid
graph LR
    Preprocessing_Orchestrator["Preprocessing Orchestrator"]
    Data_Generation_Core["Data Generation Core"]
    Data_Loading_and_Access["Data Loading and Access"]
    Preprocessing_Orchestrator -- "orchestrates" --> Data_Generation_Core
    Data_Generation_Core -- "produces data for" --> Data_Loading_and_Access
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The Input Data Pipeline subsystem in NeuSomatic is responsible for the end-to-end management of genomic data, transforming raw input into structured datasets suitable for machine learning. It begins with the Preprocessing Orchestrator, which coordinates initial data preparation steps like scanning alignments and filtering candidates. This processed data is then fed into the Data Generation Core, where the core logic for creating detailed information matrices and handling variant data alignment takes place. Finally, the Data Loading and Access component efficiently loads these generated datasets from TSV files, decompressing and preparing them for direct use in model training and inference, including data augmentation techniques.

### Preprocessing Orchestrator
This component manages the overall preprocessing workflow for the NeuSomatic system. Its responsibilities include processing split regions, obtaining ensemble bed files, extracting candidate split regions, and initiating the dataset generation process for specific genomic regions. It acts as the high-level control for preparing input data for the downstream analysis and model training.


**Related Classes/Methods**:

- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/preprocess.py#L198-L339" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.preprocess.preprocess` (198:339)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/preprocess.py#L39-L120" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.preprocess.process_split_region` (39:120)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/preprocess.py#L147-L173" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.preprocess.get_ensemble_beds` (147:173)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/preprocess.py#L176-L195" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.preprocess.extract_candidate_split_regions` (176:195)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/preprocess.py#L123-L128" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.preprocess.generate_dataset_region` (123:128)</a>


### Data Generation Core
This component is responsible for the core logic of generating the dataset, including preparing information matrices from Tabix files, finding and merging records, and handling variant data alignment. It orchestrates the creation of the raw data structures needed for the NeuSomatic model by processing raw variant call format (VCF) data and other genomic information.


**Related Classes/Methods**:

- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L301-L569" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.prepare_info_matrices_tabix` (301:569)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L44-L166" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.get_variant_matrix_tabix` (44:166)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L169-L298" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.align_tumor_normal_matrices` (169:298)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L572-L661" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.prep_data_single_tabix` (572:661)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L782-L801" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.is_part_of` (782:801)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L33-L41" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.get_type` (33:41)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L829-L1251" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.find_records` (829:1251)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L804-L810" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.find_i_center` (804:810)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L813-L826" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.find_len` (813:826)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L732-L779" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.merge_records` (732:779)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L664-L729" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.push_lr` (664:729)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L1401-L1593" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.generate_dataset` (1401:1593)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/generate_dataset.py#L1254-L1398" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.generate_dataset.extract_ensemble` (1254:1398)</a>


### Data Loading and Access
This component handles the loading of candidate data from TSV files and the extraction of information, often involving decompression using zlib. It provides the interface for accessing the prepared dataset, primarily through the NeuSomaticDataset class, enabling efficient retrieval of data samples for downstream machine learning tasks.


**Related Classes/Methods**:

- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L41-L57" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.candidate_loader_tsv` (41:57)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L37-L38" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.extract_zlib` (37:38)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L60-L122" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.extract_info_tsv` (60:122)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L125-L425" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.NeuSomaticDataset` (125:425)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L127-L230" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.NeuSomaticDataset.__init__` (127:230)</a>
- <a href="https://github.com/bioinform/neusomatic/blob/master/neusomatic/python/dataloader.py#L244-L416" target="_blank" rel="noopener noreferrer">`neusomatic.neusomatic.python.dataloader.NeuSomaticDataset.__getitem__` (244:416)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)