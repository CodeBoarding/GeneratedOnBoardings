```mermaid
graph LR
    Genotype_Storage_Abstraction_Interface_["Genotype Storage Abstraction (Interface)"]
    Genotype_Storage_Registry["Genotype Storage Registry"]
    ImpalaGenotypeStorage["ImpalaGenotypeStorage"]
    Impala2GenotypeStorage["Impala2GenotypeStorage"]
    DuckdbGenotypeStorage["DuckdbGenotypeStorage"]
    ParquetGenotypeStorage["ParquetGenotypeStorage"]
    InMemoryGenotypeStorage["InMemoryGenotypeStorage"]
    GCPGenotypeStorage["GCPGenotypeStorage"]
    Schema2GenotypeStorage["Schema2GenotypeStorage"]
    GPF_Core["GPF Core"]
    ImpalaGenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    Impala2GenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    DuckdbGenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    ParquetGenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    InMemoryGenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    GCPGenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    Schema2GenotypeStorage -- "implements" --> Genotype_Storage_Abstraction_Interface_
    Genotype_Storage_Registry -- "manages" --> ImpalaGenotypeStorage
    Genotype_Storage_Registry -- "manages" --> Impala2GenotypeStorage
    Genotype_Storage_Registry -- "manages" --> DuckdbGenotypeStorage
    Genotype_Storage_Registry -- "manages" --> ParquetGenotypeStorage
    Genotype_Storage_Registry -- "manages" --> InMemoryGenotypeStorage
    Genotype_Storage_Registry -- "manages" --> GCPGenotypeStorage
    Genotype_Storage_Registry -- "manages" --> Schema2GenotypeStorage
    GPF_Core -- "uses" --> Genotype_Storage_Abstraction_Interface_
    GPF_Core -- "configures/retrieves via" --> Genotype_Storage_Registry
    click Genotype_Storage_Abstraction_Interface_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Genotype_Storage_Abstraction_Interface_.md" "Details"
    click Genotype_Storage_Registry href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Genotype_Storage_Registry.md" "Details"
    click ImpalaGenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/ImpalaGenotypeStorage.md" "Details"
    click Impala2GenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Impala2GenotypeStorage.md" "Details"
    click DuckdbGenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/DuckdbGenotypeStorage.md" "Details"
    click ParquetGenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/ParquetGenotypeStorage.md" "Details"
    click Schema2GenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/Schema2GenotypeStorage.md" "Details"
    click GPF_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/GPF_Core.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Data Storage & Access Layer is a critical component in the GPF (Genomic Data Platform) architecture, designed to abstract and standardize interactions with various genotype and phenotype data storage backends. This layer ensures that the GPF Core remains independent of the specific underlying database or file format, promoting flexibility and extensibility.

### Genotype Storage Abstraction (Interface) [[Expand]](./Genotype_Storage_Abstraction_Interface_.md)
This component defines the abstract interface (GenotypeStorage) that all concrete genotype storage implementations must adhere to. It specifies the common methods and properties for interacting with genotype data, such as reading variants, accessing families, and retrieving genomic information, without dictating the underlying storage mechanism. This is crucial for maintaining a decoupled architecture.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/genotype_storage/genotype_storage.py#L13-L80" target="_blank" rel="noopener noreferrer">`GenotypeStorage` (13:80)</a>


### Genotype Storage Registry [[Expand]](./Genotype_Storage_Registry.md)
This component (GenotypeStorageRegistry) acts as a central repository for registering and retrieving different concrete GenotypeStorage implementations. It allows the system to dynamically discover and load appropriate storage backends based on configuration or runtime requirements. This supports the plugin architecture, making it easy to add new storage types without modifying the core system.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/genotype_storage/genotype_storage_registry.py#L78-L172" target="_blank" rel="noopener noreferrer">`GenotypeStorageRegistry` (78:172)</a>


### ImpalaGenotypeStorage [[Expand]](./ImpalaGenotypeStorage.md)
Provides the logic for connecting to and interacting with Impala data storage technology, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/impala_storage/impala_storage/schema1/impala_genotype_storage.py#L28-L479" target="_blank" rel="noopener noreferrer">`ImpalaGenotypeStorage` (28:479)</a>


### Impala2GenotypeStorage [[Expand]](./Impala2GenotypeStorage.md)
Provides the logic for connecting to and interacting with Impala2 data storage technology, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/impala2_storage/impala2_storage/schema2/impala2_genotype_storage.py#L33-L319" target="_blank" rel="noopener noreferrer">`Impala2GenotypeStorage` (33:319)</a>


### DuckdbGenotypeStorage [[Expand]](./DuckdbGenotypeStorage.md)
Provides the logic for connecting to and interacting with DuckDB data storage technology, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/dae/dae/duckdb_storage/duckdb_genotype_storage.py#L0-L0" target="_blank" rel="noopener noreferrer">`DuckdbGenotypeStorage` (0:0)</a>


### ParquetGenotypeStorage [[Expand]](./ParquetGenotypeStorage.md)
Provides the logic for connecting to and interacting with Parquet file storage technology, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- `ParquetGenotypeStorage` (0:0)


### InMemoryGenotypeStorage
Provides the logic for interacting with in-memory data storage, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- `InMemoryGenotypeStorage` (0:0)


### GCPGenotypeStorage
Provides the logic for connecting to and interacting with Google Cloud Platform storage, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- `GCPGenotypeStorage` (0:0)


### Schema2GenotypeStorage [[Expand]](./Schema2GenotypeStorage.md)
Provides the logic for connecting to and interacting with schema2 data storage, implementing the GenotypeStorage interface.


**Related Classes/Methods**:

- `Schema2GenotypeStorage` (0:0)


### GPF Core [[Expand]](./GPF_Core.md)
The core component of the Genomic Data Platform responsible for data access and querying.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)