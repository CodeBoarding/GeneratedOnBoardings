```mermaid
graph LR
    Annotation_Pipeline["Annotation Pipeline"]
    Annotator_Base["Annotator Base"]
    Annotation_Factory["Annotation Factory"]
    Annotation_Configuration["Annotation Configuration"]
    Effect_Annotator["Effect Annotator"]
    Gene_Score_Annotator["Gene Score Annotator"]
    Liftover_Annotator["Liftover Annotator"]
    Normalize_Allele_Annotator["Normalize Allele Annotator"]
    Annotation_Pipeline -- "utilizes" --> Annotator_Base
    Annotation_Pipeline -- "configures with" --> Annotation_Configuration
    Annotation_Pipeline -- "creates annotators via" --> Annotation_Factory
    Annotation_Factory -- "registers" --> Effect_Annotator
    Annotation_Factory -- "registers" --> Gene_Score_Annotator
    Annotation_Factory -- "registers" --> Liftover_Annotator
    Annotation_Factory -- "registers" --> Normalize_Allele_Annotator
    Effect_Annotator -- "implements" --> Annotator_Base
    Gene_Score_Annotator -- "implements" --> Annotator_Base
    Liftover_Annotator -- "implements" --> Annotator_Base
    Normalize_Allele_Annotator -- "implements" --> Annotator_Base
    Genomic_Resources_Manager -- "provides data to" --> Effect_Annotator
    Genomic_Resources_Manager -- "provides data to" --> Gene_Score_Annotator
    Genomic_Resources_Manager -- "provides data to" --> Liftover_Annotator
    Configuration_Management -- "provides settings to" --> Annotation_Configuration
    Variant_Query_Processor -- "sends variants to" --> Annotation_Pipeline
    Data_Import_ETL -- "can trigger" --> Annotation_Pipeline
    click Annotation_Pipeline href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Annotation_Pipeline.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Annotation Pipeline` is the core "Annotation Engine" responsible for applying a sequence of annotators to genetic variants. It provides a flexible and configurable framework to orchestrate various annotation steps, allowing for complex and customizable annotation workflows.

### Annotation Pipeline [[Expand]](./Annotation_Pipeline.md)
The central orchestrator of the annotation process. It takes a configuration and a stream of genetic variants, applies a sequence of annotators in a defined order, and outputs the variants enriched with annotation data. It manages the overall flow and coordination of annotation tasks.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/annotation_pipeline.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/annotation_pipeline.py` (1:1)</a>


### Annotator Base
Defines the abstract interface and common functionalities that all specific annotators must implement. This promotes a standardized, plugin-like architecture, allowing for easy integration of new annotation types without modifying the core pipeline logic.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/annotator_base.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/annotator_base.py` (1:1)</a>


### Annotation Factory
Responsible for dynamically creating instances of specific annotators based on the provided configuration. It acts as a registry, mapping annotator names or types to their respective classes and handling their instantiation, potentially resolving any dependencies or loading required resources.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/annotation_factory.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/annotation_factory.py` (1:1)</a>


### Annotation Configuration
Manages and parses the configuration settings for the entire annotation pipeline. This includes defining the sequence of annotators to apply, their specific parameters, and any global settings relevant to the annotation process. It typically reads structured configuration data (e.g., from YAML or JSON files).


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/annotation_config.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/annotation_config.py` (1:1)</a>


### Effect Annotator
A concrete implementation of an annotator that determines the predicted functional consequence of genetic variants (e.g., missense, silent, frameshift, splice site). It typically relies on gene models, transcript information, and sequence data to predict the impact of a variant on a protein.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/effect_annotator.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/effect_annotator.py` (1:1)</a>


### Gene Score Annotator
A concrete annotator that adds gene-level scores (e.g., constraint scores, pathogenicity scores, expression levels) to variants based on the genes they affect. These scores provide quantitative measures of a gene's tolerance to variation or its relevance to specific biological processes.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/gene_score_annotator.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/gene_score_annotator.py` (1:1)</a>


### Liftover Annotator
A concrete annotator responsible for converting genomic coordinates between different reference genome assemblies (e.g., from hg19 to hg38). This is essential when integrating data from various sources that may have been aligned to different reference versions.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/liftover_annotator.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/liftover_annotator.py` (1:1)</a>


### Normalize Allele Annotator
A concrete annotator that normalizes variant representations to a canonical form. This involves standardizing how insertions, deletions, and complex variants are represented, which is crucial for consistent downstream analysis, database storage, and comparison across different datasets.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/annotation/normalize_allele_annotator.py#L1-L1" target="_blank" rel="noopener noreferrer">`dae/annotation/normalize_allele_annotator.py` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)