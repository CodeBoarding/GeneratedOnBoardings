## Data Storage & Access Component Overview

The `Data Storage & Access` component is responsible for the persistence, retrieval, and querying of genotype and phenotype data within the GPF system. It provides a flexible architecture that supports various storage backends and offers standardized interfaces for accessing variant and family data.

```mermaid
component-beta
    title Data Storage & Access Flow

    GPFInstance [(
        GPF Instance
        Entry point for data access
    )]
    GenotypeData [(
        Genotype Data
        Represents a study/group
    )]
    QueryVariantsBase [(
        Query Variants Base
        Abstract variant querying
    )]
    SpecificGenotypeStorageBackends [(
        Specific Genotype Storage Backends
        Concrete storage implementations
    )]
    SQLQueryBuilding [(
        SQL Query Building
        Constructs SQL queries
    )]
    QueryExecution [(
        Query Execution
        Manages query runners
    )]
    VariantRepresentation [(
        Variant Representation
        Data structures for variants
    )]
    FamiliesDataManagement [(
        Families Data Management
        Manages pedigree data
    )]
    PhenotypeDataManagement [(
        Phenotype Data Management
        Manages phenotype data
    )]

    GPFInstance --> GenotypeData : Accesses
    GenotypeData --> QueryVariantsBase : Initiates query
    QueryVariantsBase --> SpecificGenotypeStorageBackends : Interacts with
    QueryVariantsBase --> SQLQueryBuilding : Uses (for SQL backends)
    SQLQueryBuilding --> SpecificGenotypeStorageBackends : Queries
    SpecificGenotypeStorageBackends --> QueryExecution : Executes queries
    QueryExecution --> VariantRepresentation : Produces/Consumes
    GenotypeData --> FamiliesDataManagement : Uses
    GPFInstance --> PhenotypeDataManagement : Accesses
    PhenotypeDataManagement --> FamiliesDataManagement : Uses

    classDef Abstract fill:#f9f,stroke:#333,stroke-width:2px
    class QueryVariantsBase,GenotypeStorageBase Abstract

    classDef Concrete fill:#ccf,stroke:#333,stroke-width:2px
    class SpecificGenotypeStorageBackends,SQLQueryBuilding,QueryExecution,VariantRepresentation,FamiliesDataManagement,PhenotypeDataManagement Concrete

    classDef EntryPoint fill:#cfc,stroke:#333,stroke-width:2px
    class GPFInstance EntryPoint

    classDef StudyGroup fill:#ffc,stroke:#333,stroke-width:2px
    class GenotypeData StudyGroup

```

### Component Descriptions:

*   **GPF Instance**: The central entry point for accessing all data and tools within GPF. It acts as an orchestrator, providing access to `Genotype Data` and `Phenotype Data Management` components based on the requested study or group.
    *   *Relevant Source Files*: `dae.gpf_instance.gpf_instance.GPFInstance`

*   **Genotype Data**: Represents a single genotype study or a group of studies. It provides the primary interface for initiating variant queries and interacts with the `Query Variants Base` to retrieve genetic data.
    *   *Relevant Source Files*: `dae.studies.study.GenotypeData`

*   **Query Variants Base**: An abstract base class that defines the standard interface for querying genetic variants. Concrete implementations of this class interact with `Specific Genotype Storage Backends` to fetch data.
    *   *Relevant Source Files*: `dae.query_variants.base_query_variants.QueryVariantsBase`

*   **Specific Genotype Storage Backends**: These are concrete implementations of the `Genotype Storage Base` abstract class, providing the actual logic for storing and retrieving genotype data from various sources (e.g., Parquet, DuckDB, Impala, BigQuery). They interact directly with the underlying storage and are used by `Query Variants Base` implementations.
    *   *Relevant Source Files*: `dae.parquet_storage.storage.ParquetLoaderVariants`, `dae.duckdb_storage.duckdb2_variants.DuckDb2Variants`, `gcp_storage.bigquery_variants.BigQueryVariants`, `impala_storage.schema1.impala_variants.ImpalaVariants`, `impala2_storage.schema2.impala_variants.ImpalaVariants`, `dae.inmemory_storage.raw_variants.RawMemoryVariants`

*   **SQL Query Building**: Specifically used by SQL-based genotype storage backends, this component is responsible for constructing the appropriate SQL queries based on the filtering criteria provided by the `Query Variants Base`. It interacts with `Specific Genotype Storage Backends` by providing the generated queries.
    *   *Relevant Source Files*: `dae.query_variants.sql.schema2.sql_query_builder.SqlQueryBuilder`

*   **Query Execution**: Manages the asynchronous execution of variant queries, often using background runners (`QueryRunner`) and a result queue (`QueryResult`). It receives queries from `Query Variants Base` implementations and processes them, producing results in the form of `Variant Representation` objects.
    *   *Relevant Source Files*: `dae.query_variants.query_runners.QueryRunner`, `dae.query_variants.query_runners.QueryResult`

*   **Variant Representation**: Provides the data structures (`SummaryVariant`, `FamilyVariant`, `SummaryAllele`) used to represent genetic variants retrieved from the storage backends. These objects encapsulate the variant's location, alleles, attributes, and effects, and are consumed by components that process query results.
    *   *Relevant Source Files*: `dae.variants.variant`, `dae.variants.family_variant`

*   **Families Data Management**: Handles the loading, processing, and representation of pedigree data. It provides access to information about families and individuals, which is often required alongside genotype data for analysis. It is used by both `Genotype Data` and `Phenotype Data Management`.
    *   *Relevant Source Files*: `dae.pedigrees.families_data.FamiliesData`, `dae.pedigrees.loader.FamiliesLoader`

*   **Phenotype Data Management**: Manages access to and representation of phenotype data. It includes components for handling instruments, measures, and integration with a phenotype browser. It is accessed via the `GPF Instance` and utilizes `Families Data Management` for person-related information.
    *   *Relevant Source Files*: `dae.pheno.pheno_data.PhenotypeData`, `dae.pheno.pheno_data.PhenotypeStudy`, `dae.pheno.pheno_data.PhenotypeGroup`, `dae.pheno.browser.PhenoBrowser`, `dae.pheno.registry.PhenoRegistry`, `dae.pheno.storage.PhenotypeStorage`
