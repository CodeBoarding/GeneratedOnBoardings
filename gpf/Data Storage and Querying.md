## Data Storage and Querying Overview

This component handles the storage, indexing, and querying of variant data using various storage backends. It provides an abstraction layer for accessing data from different sources, including Impala, Google BigQuery, DuckDB, and in-memory storage. The core functionality revolves around the `QueryVariants` abstract class, which defines the interface for querying summary and family variants. Concrete implementations of this class, such as `ImpalaVariants` and `BigQueryVariants`, provide access to data stored in specific backends. The `QueryBuilder` component assists in constructing SQL queries for variant retrieval.

```mermaid
flowchart LR
    subgraph DataLoaders [Data Loaders]
    VcfLoader[VcfLoader
    (Loads variants from VCF files)]
    DenovoLoader[DenovoLoader
    (Loads denovo variants from DAE files)]
    FamiliesLoader[FamiliesLoader
    (Loads family data for pedigree information)]
    end

    subgraph StorageBackends [Storage Backends]
    ImpalaVariants[ImpalaVariants
    (Accesses variants in Impala)]
    BigQueryVariants[BigQueryVariants
    (Accesses variants in BigQuery)]
    DuckDb2Variants[DuckDb2Variants
    (Accesses variants in DuckDB)]
    RawMemoryVariants[RawMemoryVariants
    (Accesses variants in memory)]
    Schema2ImportStorage[Schema2ImportStorage
    (Storage for schema2-based data import)]
    end

    subgraph Querying
    QueryVariants[QueryVariants
    (Abstract base class for querying variants)]
    QueryBuilder[QueryBuilder
    (Builds SQL queries for variant retrieval)]
    ImpalaQueryRunner[ImpalaQueryRunner
    (Executes SQL queries against Impala)]
    BigQueryQueryRunner[BigQueryQueryRunner
    (Executes SQL queries against BigQuery)]
    QueryVariantsBase[QueryVariantsBase
    (Base class for Schema2 query interface)]
    end

    VcfLoader --> Schema2ImportStorage
    DenovoLoader --> Schema2ImportStorage
    FamiliesLoader --> ImpalaVariants
    FamiliesLoader --> BigQueryVariants
    FamiliesLoader --> DuckDb2Variants
    FamiliesLoader --> RawMemoryVariants

    Schema2ImportStorage --> DuckDb2Variants
    ImpalaVariants -- uses --> ImpalaQueryRunner
    BigQueryVariants -- uses --> BigQueryQueryRunner
    ImpalaVariants -- implements --> QueryVariants
    BigQueryVariants -- implements --> QueryVariants
    DuckDb2Variants -- implements --> QueryVariants
    RawMemoryVariants -- implements --> QueryVariants
    ImpalaVariants -- extends --> QueryVariantsBase
    BigQueryVariants -- extends --> QueryVariantsBase
    DuckDb2Variants -- extends --> QueryVariantsBase
    RawMemoryVariants -- extends --> QueryVariantsBase
    QueryVariantsBase -- uses --> QueryBuilder




```

### Component Descriptions:

**1. VcfLoader**
   - *Description*: Loads variants from VCF files. Parses VCF files and transforms the data into internal variant representations.
   - *Interaction*: Sends data to `Schema2ImportStorage`.
   - *Relevant source files*: `dae.variants_loaders.vcf.loader.VcfLoader`

**2. DenovoLoader**
   - *Description*: Loads denovo variants from DAE files. Reads and parses DAE files containing denovo mutations.
   - *Interaction*: Sends data to `Schema2ImportStorage`.
   - *Relevant source files*: `dae.variants_loaders.dae.loader.DenovoLoader`

**3. FamiliesLoader**
   - *Description*: Loads family data for pedigree information. Reads and parses pedigree files to create family objects.
   - *Interaction*: Provides family data to `ImpalaVariants`, `BigQueryVariants`, `DuckDb2Variants`, and `RawMemoryVariants`.
   - *Relevant source files*: `dae.pedigrees.loader.FamiliesLoader`

**4. Schema2ImportStorage**
   - *Description*: Storage for schema2-based data import. Manages the import of variant data into a schema2-compatible storage format.
   - *Interaction*: Receives data from `VcfLoader` and `DenovoLoader`, and sends data to `DuckDb2Variants`.
   - *Relevant source files*: `dae.schema2_storage.schema2_import_storage.Schema2ImportStorage`

**5. ImpalaVariants**
   - *Description*: Provides access to variants stored in Impala. It builds and executes SQL queries against Impala to retrieve variant data.
   - *Interaction*: Uses `ImpalaQueryRunner` to execute queries, receives family data from `FamiliesLoader`, and implements the `QueryVariants` interface.
   - *Relevant source files*: `impala_storage.schema1.impala_variants.ImpalaVariants`

**6. BigQueryVariants**
   - *Description*: Provides access to variants stored in Google BigQuery. It formulates and executes queries using BigQuery's SQL dialect.
   - *Interaction*: Uses `BigQueryQueryRunner` to execute queries, receives family data from `FamiliesLoader`, and implements the `QueryVariants` interface.
   - *Relevant source files*: `gcp_storage.gcp_storage.bigquery_variants.BigQueryVariants`

**7. DuckDb2Variants**
   - *Description*: Provides access to variants stored in DuckDB. Enables querying of variant data stored in DuckDB databases.
   - *Interaction*: Receives data from `Schema2ImportStorage`, receives family data from `FamiliesLoader`, and implements the `QueryVariants` interface.
   - *Relevant source files*: `dae.duckdb_storage.duckdb2_variants.DuckDb2Variants`

**8. RawMemoryVariants**
   - *Description*: Provides access to variants stored in memory. Used for testing and small datasets.
   - *Interaction*: Receives family data from `FamiliesLoader` and implements the `QueryVariants` interface.
   - *Relevant source files*: `dae.inmemory_storage.raw_variants.RawMemoryVariants`

**9. QueryVariants**
   - *Description*: Abstract base class for querying variants from different storage backends. Defines the interface for querying summary and family variants.
   - *Interaction*: Implemented by `ImpalaVariants`, `BigQueryVariants`, `DuckDb2Variants`, and `RawMemoryVariants`.
   - *Relevant source files*: `dae.query_variants.query_variants.QueryVariants`

**10. QueryBuilder**
    - *Description*: Abstract base class for building SQL queries for variant retrieval. Defines the interface for constructing SQL queries based on user-specified criteria.
    - *Interaction*: Used by `QueryVariantsBase` to construct queries.
    - *Relevant source files*: `dae.query_variants.sql.schema2.sql_query_builder.QueryBuilderBase`

**11. ImpalaQueryRunner**
    - *Description*: Executes SQL queries against Impala. Handles connection pooling and result deserialization.
    - *Interaction*: Used by `ImpalaVariants` to execute queries.
    - *Relevant source files*: `impala_storage.helpers.impala_query_runner.ImpalaQueryRunner`

**12. BigQueryQueryRunner**
    - *Description*: Executes SQL queries against Google BigQuery. Manages connections and data transfer.
    - *Interaction*: Used by `BigQueryVariants` to execute queries.
    - *Relevant source files*: `gcp_storage.bigquery_query_runner.BigQueryQueryRunner`

**13. QueryVariantsBase**
    - *Description*: Base class for Schema2 query interface. Implements common functionalities like deserialization and tags processing.
    - *Interaction*: Extends `QueryVariants` and uses `QueryBuilder`.
    - *Relevant source files*: `dae.query_variants.query_variants.QueryVariantsBase`