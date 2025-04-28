## Storage Component Overview

This document provides an overview of the `Storage` component, which is responsible for storing variant and pedigree data in a persistent storage solution. It supports different storage backends like Impala and Google Cloud Platform (GCP).

```mermaid
flowchart LR
    subgraph GCP Storage
        GcpImportStorage -- generates import task graph --> GcpGenotypeStorage
        GcpGenotypeStorage -- uses --> BigQueryVariants
        BigQueryVariants -- executes queries using --> BigQueryQueryRunner
    end

    subgraph Impala Storage
        ImpalaVariants -- queries --> ImpalaGenotypeStorage
    end

    Storage -- uses --> GCP Storage
    Storage -- uses --> Impala Storage

    style Storage fill:#f9f,stroke:#333,stroke-width:2px
```

### Component Descriptions

*   **Storage**: The main entry point for interacting with different storage backends. It determines which backend to use based on the configuration and delegates operations accordingly.
    *   Description: Stores variant and pedigree data in a persistent storage solution. It supports different storage backends like Impala and Google Cloud Platform.
    *   Relevant source files: `impala_storage`, `gcp_storage`

*   **GcpImportStorage**: Handles importing datasets into GCP storage. It generates import task graphs and manages study configurations, streamlining the data import process.
    *   Description: Handles importing datasets into GCP storage.
    *   Interaction: Generates import task graphs for `GcpGenotypeStorage`.
    *   Relevant source files: `repos.gpf.gcp_storage.gcp_storage.gcp_import_storage.GcpImportStorage`

*   **GcpGenotypeStorage**: Manages genotype storage in Google Cloud Platform (GCP). It handles importing, loading, and building backends for datasets in BigQuery.
    *   Description: Manages genotype storage in GCP.
    *   Interaction: Uses `BigQueryVariants` to query data.
    *   Relevant source files: `repos.gpf.gcp_storage.gcp_storage.gcp_genotype_storage.GcpGenotypeStorage`

*   **BigQueryVariants**: Provides functionality for querying variants stored in BigQuery. It handles deserialization of summary and family variants, enabling access to variant data within BigQuery.
    *   Description: Provides functionality for querying variants stored in BigQuery.
    *   Interaction: Uses `BigQueryQueryRunner` to execute queries.
    *   Relevant source files: `repos.gpf.gcp_storage.gcp_storage.bigquery_variants.BigQueryVariants`

*   **BigQueryQueryRunner**: Executes queries against BigQuery. It manages the query execution lifecycle, including finalization and result queue handling, ensuring efficient and reliable query execution.
    *   Description: Executes queries against BigQuery.
    *   Interaction: Called by `BigQueryVariants` to run queries.
    *   Relevant source files: `repos.gpf.gcp_storage.gcp_storage.bigquery_query_runner.BigQueryQueryRunner`

*   **ImpalaVariants**: Provides functionality for querying variants stored in Impala.
    *   Description: Provides functionality for querying variants stored in Impala.
    *   Interaction: Queries `ImpalaGenotypeStorage` to retrieve data.
    *   Relevant source files: `impala_storage.schema1.impala_variants.ImpalaVariants`

*   **ImpalaGenotypeStorage**: Manages genotype storage in Impala.
    *   Description: Manages genotype storage in Impala.
    *   Interaction: Provides data to `ImpalaVariants`.
    *   Relevant source files: `impala_storage.schema1.impala_genotype_storage.ImpalaGenotypeStorage`