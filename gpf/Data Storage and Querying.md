## Data Storage and Querying

This component handles the storage, indexing, and querying of variant data within the `{project_name}` project. It supports multiple storage backends, providing an abstract interface for querying variants regardless of the underlying storage implementation. The core functionality revolves around abstracting data access and query execution.

```mermaid
graph LR
    subgraph Storage Backends
        impala_storage((Impala Storage))
        gcp_storage((GCP Storage))
        schema2_storage((Schema2 Storage))
        duckdb_storage((DuckDB Storage))
        inmemory_storage((In-Memory Storage))
    end

    query_variants((Query Variants))

    User[User] -- "queries" --> query_variants
    query_variants -- "uses" --> Storage Backends
    Storage Backends -- "provides data" --> query_variants



```

