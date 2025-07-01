```mermaid
graph LR
    Web_Application_WDAE_["Web Application (WDAE)"]
    GPF_Core_Engine_DAE_["GPF Core Engine (DAE)"]
    ETL_Pipeline["ETL Pipeline"]
    Pluggable_Storage_Backend["Pluggable Storage Backend"]
    Federation_Module["Federation Module"]
    Command_Line_Interface_CLI_["Command Line Interface (CLI)"]
    Web_Application_WDAE_ -- "forwards user requests to" --> GPF_Core_Engine_DAE_
    Command_Line_Interface_CLI_ -- "executes commands on" --> GPF_Core_Engine_DAE_
    GPF_Core_Engine_DAE_ -- "initiates" --> ETL_Pipeline
    GPF_Core_Engine_DAE_ -- "queries data from" --> Pluggable_Storage_Backend
    ETL_Pipeline -- "writes processed data to" --> Pluggable_Storage_Backend
    GPF_Core_Engine_DAE_ -- "delegates queries to" --> Federation_Module
    click Web_Application_WDAE_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Web_Application_WDAE_.md" "Details"
    click GPF_Core_Engine_DAE_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/GPF_Core_Engine_DAE_.md" "Details"
    click ETL_Pipeline href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/ETL_Pipeline.md" "Details"
    click Federation_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Federation_Module.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Web Application (WDAE) [[Expand]](./Web_Application_WDAE_.md)
The primary user-facing entry point, built on Django. It serves the web interface and exposes a complete REST API for programmatic access. This component is responsible for handling all web-specific concerns, including user authentication, request routing, and presenting data to the client.


**Related Classes/Methods**:

- `gpf/wdae/`
- `gpf/wdae/wdae/datasets_api/`
- `gpf/wdae/wdae/users_api/`


### GPF Core Engine (DAE) [[Expand]](./GPF_Core_Engine_DAE_.md)
The central, web-agnostic brain of the platform. It provides a unified, programmatic interface for accessing and querying genotype and phenotype data. It orchestrates all major functionalities, including data querying, annotation, and federation, without any knowledge of web-specific concepts.


**Related Classes/Methods**:

- `gpf/dae/dae/gpf_instance/gpf_instance.py`


### ETL Pipeline [[Expand]](./ETL_Pipeline.md)
A consolidated pipeline responsible for all data ingestion and processing. It handles the extraction of data from various formats (e.g., VCF, DAE), followed by a multi-step annotation process that enriches the data with functional scores, gene information, and effect types before it is loaded into storage.


**Related Classes/Methods**:

- `gpf/dae/dae/variants_loaders/`
- `gpf/dae/dae/annotation/annotation_pipeline.py`
- `gpf/dae/tools/`


### Pluggable Storage Backend
A storage abstraction layer that provides a uniform API for storing and retrieving genotype data. Its plugin-based design allows the platform to support multiple, interchangeable storage backends (e.g., Impala, Filesystem, In-Memory), providing flexibility for different deployment environments.


**Related Classes/Methods**:

- `gpf/dae/dae/genotype_storage/`


### Federation Module [[Expand]](./Federation_Module.md)
Enables the platform to act as a data federation hub. This component allows the Core Engine to query and analyze data from multiple remote GPF instances as if they were a single, unified dataset, abstracting the complexity of distributed queries.


**Related Classes/Methods**:

- `gpf/federation/`


### Command Line Interface (CLI)
A set of command-line tools for direct, script-based interaction with the GPF Core Engine. It is primarily used by data administrators and bioinformaticians for offline tasks like data import, annotation, and other system management functions.


**Related Classes/Methods**:

- `gpf/dae/tools/`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)