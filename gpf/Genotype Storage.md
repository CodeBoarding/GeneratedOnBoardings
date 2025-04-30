```mermaid
graph LR
    A[GenotypeStorageRegistry] -- configures --> B(GenotypeStorage) 
    B -- validates --> C{Configuration} 
    C -- uses --> D[Backend (e.g., BigQueryVariants, ImpalaVariants)]
    B -- builds --> D
    D -- queries --> E((Data Storage: GCP, Impala, DuckDB))



```

### Component Descriptions:

**GenotypeStorageRegistry:**
*   **Purpose:** Manages the registration and retrieval of different genotype storage configurations.
*   **Functionality:** Registers storage configurations, retrieves specific genotype storage instances based on configuration, and handles storage shutdown.
*   **Interaction:** Configures `GenotypeStorage` instances based on registered configurations.
*   **Relevant source files:** `dae.genotype_storage.genotype_storage_registry.GenotypeStorageRegistry`

**GenotypeStorage:**
*   **Purpose:** Abstract base class for genotype storage implementations.
*   **Functionality:** Defines common methods for configuration, validation, and backend building. It acts as an interface for different storage implementations.
*   **Interaction:** Validates configurations and builds the appropriate backend (e.g., `BigQueryVariants`, `ImpalaVariants`) for data access.
*   **Relevant source files:** `dae.genotype_storage.genotype_storage.GenotypeStorage`

**Configuration:**
*   **Purpose:** Represents the configuration settings for a specific genotype storage.
*   **Functionality:** Holds the parameters needed to initialize and use a particular storage backend.
*   **Interaction:** Used by `GenotypeStorage` to validate and normalize the configuration before building the backend.
*   **Relevant source files:** N/A (Represents a data structure)

**Backend (e.g., BigQueryVariants, ImpalaVariants):**
*   **Purpose:** Provides an interface to query and retrieve variant data from the underlying data storage.
*   **Functionality:** Translates high-level queries into storage-specific operations and returns the results.
*   **Interaction:** Queries the actual data storage (GCP, Impala, DuckDB) to retrieve variant data.
*   **Relevant source files:** `gcp_storage.bigquery_variants.BigQueryVariants`, `impala_storage.schema1.impala_variants.ImpalaVariants`, `impala2_storage.schema2.impala_variants.ImpalaVariants`

**Data Storage (GCP, Impala, DuckDB):**
*   **Purpose:** The actual storage location of the genotype data.
*   **Functionality:** Stores and retrieves data based on the specific storage technology.
*   **Interaction:** Provides the physical storage for the genotype data, accessed through the backend.
*   **Relevant source files:** N/A (Represents external storage systems)
