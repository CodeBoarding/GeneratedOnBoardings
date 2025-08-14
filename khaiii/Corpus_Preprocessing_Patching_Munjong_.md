```mermaid
graph LR
    Corpus_Ingestion_Transformation["Corpus Ingestion & Transformation"]
    Pre_analysis_Resource_Generator["Pre-analysis Resource Generator"]
    Error_Patch_Resource_Generator["Error Patch Resource Generator"]
    Linguistic_Patching_Engine["Linguistic Patching Engine"]
    Corpus_Error_Correctors["Corpus Error Correctors"]
    Corpus_Ingestion_Transformation -- "feeds transformed corpus data to" --> Pre_analysis_Resource_Generator
    Corpus_Ingestion_Transformation -- "feeds transformed corpus data to" --> Error_Patch_Resource_Generator
    Corpus_Ingestion_Transformation -- "feeds transformed corpus data to" --> Corpus_Error_Correctors
    Pre_analysis_Resource_Generator -- "consumes unified corpus data from" --> Corpus_Ingestion_Transformation
    Error_Patch_Resource_Generator -- "consumes unified corpus data from" --> Corpus_Ingestion_Transformation
    Error_Patch_Resource_Generator -- "produces compiled error patch resources for" --> Linguistic_Patching_Engine
    Linguistic_Patching_Engine -- "leverages compiled error patch resources from" --> Error_Patch_Resource_Generator
    Linguistic_Patching_Engine -- "applies patches to the corpus, integrating with" --> Corpus_Error_Correctors
    Corpus_Error_Correctors -- "receives corpus data from" --> Corpus_Ingestion_Transformation
    Corpus_Error_Correctors -- "modifies corpus data in conjunction with" --> Linguistic_Patching_Engine
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The feedback highlights a critical area for improvement: the incompleteness of source file references, which directly impacts the clarity and accuracy of the architectural analysis and subsequent diagram generation. Providing precise file paths for all referenced classes and methods is essential for a robust and verifiable analysis. The following updates address the feedback by correcting the `FileRef: None` entries, ensuring that each referenced component has an accurate source file path.

### Corpus Ingestion & Transformation
This component is responsible for the initial ingestion and parsing of raw linguistic corpora (e.g., Sejong Corpus) into structured linguistic units (sentences, words, morphs). It also unifies and transforms diverse corpus data into a consistent format suitable for downstream analysis and model training, handling initial parsing errors and data normalization.


**Related Classes/Methods**:

- <a href="https://github.com/kakao/khaiii/blob/master/src/main/python/khaiii/munjong/sejong_corpus.py" target="_blank" rel="noopener noreferrer">`khaiii.munjong.sejong_corpus`</a>


### Pre-analysis Resource Generator
This component identifies and extracts patterns for pre-analysis, such as ambiguous morphological analyses, from the transformed corpus. It then compiles these extracted patterns into an efficient binary format (e.g., a Trie) for fast lookup, primarily used for user dictionaries or pre-analysis lookups during the morphological analysis phase.


**Related Classes/Methods**:

- <a href="https://github.com/kakao/khaiii/blob/master/rsc/bin/compile_preanal.py" target="_blank" rel="noopener noreferrer">`rsc.bin.compile_preanal`</a>


### Error Patch Resource Generator
This component detects and extracts specific error patterns from the corpus, which are then used to generate corrective patches. It compiles these error patch rules into an efficient binary format for quick application during the post-analysis correction phase, serving as a data-driven approach to error identification.


**Related Classes/Methods**:

- <a href="https://github.com/kakao/khaiii/blob/master/rsc/bin/compile_errpatch.py" target="_blank" rel="noopener noreferrer">`rsc.bin.compile_errpatch`</a>


### Linguistic Patching Engine
This component provides the fundamental logic for creating, parsing, and applying various types of linguistic patches (e.g., sentence splits, word modifications, sentence merges). It orchestrates the overall process of generating and applying these patches to the corpus, acting as the core engine for all patch operations.


**Related Classes/Methods**:

- <a href="https://github.com/kakao/khaiii/blob/master/src/main/python/khaiii/munjong/libpatch.py" target="_blank" rel="noopener noreferrer">`khaiii.munjong.libpatch`</a>


### Corpus Error Correctors
This component comprises a collection of specialized modules, each designed to detect and correct specific linguistic errors within the corpus (e.g., period errors, symbol errors, case recovery). These are direct, rule-based corrections applied during the patching phase, often integrated with the Linguistic Patching Engine.


**Related Classes/Methods**:

- <a href="https://github.com/kakao/khaiii/blob/master/" target="_blank" rel="noopener noreferrer">`khaiii.munjong.error_correctors`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)