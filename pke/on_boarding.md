```mermaid
graph LR
    Document_Ingestion_Preprocessing["Document Ingestion & Preprocessing"]
    Candidate_Generation["Candidate Generation"]
    Candidate_Filtering["Candidate Filtering"]
    Keyphrase_Weighting_Module["Keyphrase Weighting Module"]
    Keyphrase_Output_Post_processing["Keyphrase Output & Post-processing"]
    External_Consumer["External Consumer"]
    Document_Ingestion_Preprocessing -- "produces Processed Document for" --> Candidate_Generation
    Candidate_Generation -- "generates Raw Candidates for" --> Candidate_Filtering
    Candidate_Filtering -- "provides Filtered Candidates to" --> Keyphrase_Weighting_Module
    Keyphrase_Weighting_Module -- "outputs Weighted Candidates to" --> Keyphrase_Output_Post_processing
    Keyphrase_Output_Post_processing -- "delivers Final Keyphrases to" --> External_Consumer
    click Document_Ingestion_Preprocessing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pke/Document_Ingestion_Preprocessing.md" "Details"
    click Candidate_Generation href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pke/Candidate_Generation.md" "Details"
    click Candidate_Filtering href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pke/Candidate_Filtering.md" "Details"
    click Keyphrase_Weighting_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pke/Keyphrase_Weighting_Module.md" "Details"
    click Keyphrase_Output_Post_processing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pke/Keyphrase_Output_Post_processing.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `pke` library's architecture is designed as a pipeline for automated keyphrase extraction. The process begins with the `Document Ingestion & Preprocessing` component, which handles the initial loading and linguistic analysis of raw text. The output, a processed document, then feeds into the `Candidate Generation` component, responsible for identifying potential keyphrases. These raw candidates are subsequently refined by the `Candidate Filtering` component. The core of the system lies within the `Keyphrase Weighting Module`, a highly pluggable component that applies various algorithms to score and rank the filtered candidates. Finally, the `Keyphrase Output & Post-processing` component selects and formats the top-ranked keyphrases, which are then consumed by an `External Consumer` application, such as the example scripts demonstrating the library's usage. This modular design allows for flexible integration and extension of keyphrase extraction functionalities.

### Document Ingestion & Preprocessing [[Expand]](./Document_Ingestion_Preprocessing.md)
Handles loading raw text and performing initial linguistic analysis (tokenization, POS tagging, sentence splitting).


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/pke/base.py" target="_blank" rel="noopener noreferrer">`pke/base.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/readers.py" target="_blank" rel="noopener noreferrer">`pke/readers.py`</a>


### Candidate Generation [[Expand]](./Candidate_Generation.md)
Extracts potential keyphrase candidates based on linguistic patterns or rules from the preprocessed document.


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/pke/base.py" target="_blank" rel="noopener noreferrer">`pke/base.py`</a>


### Candidate Filtering [[Expand]](./Candidate_Filtering.md)
Refines the raw candidates by applying rules to remove undesirable or irrelevant entries.


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/pke/base.py" target="_blank" rel="noopener noreferrer">`pke/base.py`</a>


### Keyphrase Weighting Module [[Expand]](./Keyphrase_Weighting_Module.md)
A pluggable component that applies various algorithms (supervised, graph-based, statistical) to score and rank filtered keyphrase candidates. This module encapsulates the core logic for determining keyphrase relevance.


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/pke/supervised/api.py" target="_blank" rel="noopener noreferrer">`pke/supervised/api.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/supervised/feature_based/" target="_blank" rel="noopener noreferrer">`pke/supervised/feature_based/`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/unsupervised/graph_based/positionrank.py" target="_blank" rel="noopener noreferrer">`pke/unsupervised/graph_based/positionrank.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/unsupervised/graph_based/textrank.py" target="_blank" rel="noopener noreferrer">`pke/unsupervised/graph_based/textrank.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/unsupervised/graph_based/topicrank.py" target="_blank" rel="noopener noreferrer">`pke/unsupervised/graph_based/topicrank.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/unsupervised/statistical/yake.py" target="_blank" rel="noopener noreferrer">`pke/unsupervised/statistical/yake.py`</a>
- <a href="https://github.com/boudinfl/pke/blob/master/pke/unsupervised/statistical/tfidf.py" target="_blank" rel="noopener noreferrer">`pke/unsupervised/statistical/tfidf.py`</a>


### Keyphrase Output & Post-processing [[Expand]](./Keyphrase_Output_Post_processing.md)
Selects the top-ranked keyphrases and performs final steps like redundancy removal or formatting.


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/pke/base.py" target="_blank" rel="noopener noreferrer">`pke/base.py`</a>


### External Consumer
An external entity that consumes the final keyphrases. This is typically an application or script utilizing the `pke` library for keyphrase extraction.


**Related Classes/Methods**:

- <a href="https://github.com/boudinfl/pke/blob/master/examples/keyphrase-extraction.py" target="_blank" rel="noopener noreferrer">`/mnt/e/StartUp/pke/examples/keyphrase-extraction.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)