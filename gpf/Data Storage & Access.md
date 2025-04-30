## Component Overview: Data Storage & Access

The `Data Storage & Access` component is responsible for the persistence, retrieval, and querying of genotype and phenotype data within the GPF system. It provides the necessary interfaces and abstractions to interact with various storage backends and retrieve variant and family data, as well as phenotype information.

```mermaid
componentDiagram
    direction LR

    [WDAE Interface] --> [GPF Instance] : requests data
    [GPF Instance] --> [Variants Database] : accesses genotype data
    [GPF Instance] --> [Phenotype Registry] : accesses phenotype data

    [Variants Database] --> [Genotype Storage Registry] : gets storage backend
    [Variants Database] --> [Genotype Data] : provides genotype data instance

    [Genotype Data] --> [Query Variants Base] : uses for querying
    [Genotype Data] --> [Families Data] : uses pedigree info

    [Query Variants Base] --> [Genotype Storage Base] : interacts with storage
    [Query Variants Base] --> [Query Runner Base] : produces query runner
    [Query Variants Base] --> [Summary Variant] : produces summary variants
    [Query Variants Base] --> [Family Variant] : produces family variants

    [Genotype Storage Registry] --> [Genotype Storage Base] : provides instance
    [Specific Genotype Storage Backends] ..|> [Genotype Storage Base] : implements

    [Query Runner Base] --> [Query Result] : produces query result
    [Query Runner Base] --> [Genotype Storage Base] : interacts with storage

    [Query Result] --> [Summary Variant] : contains
    [Query Result] --> [Family Variant] : contains

    [SQL Schema 2 Variants Base] ..|> [Query Variants Base] : implements
    [SQL Schema 2 Variants Base] --> [SQL Query Builder] : uses to build queries

    [Family Variant] --> [Families Data] : uses pedigree info

    [Phenotype Registry] --> [Phenotype Data Base] : provides instance
    [Phenotype Data Base] --> [Phenotype Storage Base] : interacts with storage
    [Phenotype Data Base] --> [Families Data] : uses pedigree info
    [Phenotype Storage Base] --> [Phenotype Data Base] : used by

    [Data Storage & Access] --> [Genotype Storage Base]
    [Data Storage & Access] --> [Specific Genotype Storage Backends]
    [Data Storage & Access] --> [Query Variants Base]
    [Data Storage & Access] --> [SQL Schema 2 Variants Base]
    [Data Storage & Access] --> [Query Runner Base]
    [Data Storage & Access] --> [Query Result]
    [Data Storage & Access] --> [Summary Variant]
    [Data Storage & Access] --> [Family Variant]
    [Data Storage & Access] --> [Families Data]
    [Data Storage & Access] --> [Phenotype Data Base]
    [Data Storage & Access] --> [Phenotype Storage Base]
    [Data Storage & Access] --> [SQL Query Builder]

    note as DataStorageAccessNote
        **Data Storage & Access**
        Manages persistence, retrieval, and querying
        of genotype and phenotype data.
    end

    [Data Storage & Access]:::mainComponent

    classDef mainComponent fill:#f9f,stroke:#333,stroke-width:2px;
```

### Component Descriptions:

*   **Genotype Storage Base**: An abstract base class defining the interface for different genotype storage backends. Concrete implementations interact with the underlying storage system and are used by Query Variants Base implementations. Relevant source file: `dae/genotype_storage/genotype_storage.py`.

*   **Specific Genotype Storage Backends**: Concrete implementations for storing and querying genotype data using various technologies like in-memory, Parquet, DuckDB, Impala, and BigQuery. These implement the `Genotype Storage Base` interface and interact with the underlying storage systems. Relevant source files: `dae/inmemory_storage/raw_variants.py`, `gcp_storage/bigquery_variants.py`, `impala_storage/schema1/impala_variants.py`, `impala2_storage/schema2/impala_variants.py`, `dae/parquet_storage/storage.py`, `dae/duckdb_storage/duckdb2_variants.py`.

*   **Query Variants Base**: An abstract base class for defining methods to query genetic variants. Implementations interact with `Genotype Storage Base` implementations to retrieve data and produce `Query Runner Base` instances. Relevant source file: `dae/query_variants/base_query_variants.py`.

*   **SQL Schema 2 Variants Base**: A concrete implementation of `Query Variants Base` for querying variants stored in SQL databases using Schema 2. It interacts with SQL databases via a `Genotype Storage Base` implementation, building `Query Runner Base` instances using `SQL Query Builder`. Relevant source file: `dae/query_variants/sql/schema2/base_variants.py`.

*   **Query Runner Base**: An abstract base class for executing variant queries and managing their results asynchronously. It interacts with the storage backend via a `Query Variants Base` implementation and produces a `Query Result`. Relevant source file: `dae/query_variants/query_runners.py`.

*   **Query Result**: Represents the result of a variant query, allowing iteration over returned variants. It provides access to `Family Variant` and `Summary Variant` instances. Relevant source file: `dae/query_variants/query_runners.py`.

*   **Summary Variant**: Represents a summary of a genetic variant across all families in a study. It is created by `Query Variants Base` implementations or Variants Loader Base. Relevant source file: `dae/variants/variant.py`.

*   **Family Variant**: Represents a genetic variant within a specific family, including genotype and inheritance information. It is created by `Query Variants Base` implementations or Variants Loader Base and uses `Families Data`. Relevant source file: `dae/variants/family_variant.py`.

*   **Families Data**: Represents the loaded and structured family and pedigree information. It is used by `Genotype Data`, `Family Variant`, and `Phenotype Data Base`. Relevant source file: `dae/pedigrees/families_data.py`.

*   **Phenotype Data Base**: An abstract base class for accessing and managing phenotype data associated with individuals in studies. Concrete implementations interact with `Phenotype Storage Base` and are used by the Phenotype Registry and GPF Instance. Relevant source file: `dae/pheno/pheno_data.py`.

*   **Phenotype Storage Base**: An abstract base class defining the interface for different phenotype data storage backends. Concrete implementations interact with the actual storage system and are used by `Phenotype Data Base` implementations. Relevant source file: `dae/pheno/storage.py`.

*   **SQL Query Builder**: Responsible for constructing SQL queries based on the provided query parameters and the database schema. It is used by `SQL Schema 2 Variants Base` to generate the actual SQL statements executed against the storage backend. Relevant source file: `dae/query_variants/sql/schema2/sql_query_builder.py`.
