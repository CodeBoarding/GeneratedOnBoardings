Okay, I will generate an onboarding document for the `gpf` project based on the provided information.

**1. Project Description**

The Genotype and Phenotype Foundation (GPF) is a comprehensive platform designed for managing, analyzing, and querying large-scale genomic data. It provides tools for importing data from various sources, storing it efficiently, annotating variants, and enabling complex queries through a web-based interface and API. GPF facilitates collaborative research by managing user access and permissions, and it supports a wide range of genomic studies, including those focused on rare genetic disorders and population genetics.

**2. Data Flow Diagram (Mermaid Format)**

```mermaid
graph LR
    subgraph Data Ingestion and Management
    A[Data Sources (VCF, Denovo, CNV)]
    B[Import Tools]
    C[Storage (Impala, DuckDB, GCS)]
    end

    subgraph Genomic Resources and Annotation
    D[Genomic Resource Repositories]
    E[Annotation Pipeline]
    end

    subgraph Query and API
    F[Web API]
    G[Query Builder]
    H[Query Runner]
    I[User Interface]
    end

    subgraph User Management and Security
    J[User Authentication]
    K[Authorization and Permissions]
    end

    A--Imports data-->B
    B--Stores data-->C
    C--Provides data-->G
    D--Provides resources-->E
    E--Annotates variants-->C
    G--Builds queries-->H
    H--Executes queries-->C
    C--Returns results-->G
    G--Formats results-->I
    F--Handles requests-->G
    I--Uses-->F
    F--Authenticates-->J
    J--Authorizes-->K
    K--Controls access-->F
```

**3. Component Descriptions**

*   **Data Sources (VCF, Denovo, CNV):** This component represents the various input data formats that GPF can ingest, including VCF files for variant calls, denovo files for de novo mutations, and CNV files for copy number variations.

*   **Import Tools:** This component is responsible for importing data from various sources and formats into the GPF environment. It handles data transformation, validation, and loading into the storage backend.

*   **Storage (Impala, DuckDB, GCS):** This component represents the storage backends used by GPF to store genomic data. It supports various storage solutions like Impala, DuckDB, and Google Cloud Storage, providing efficient data access and scalability.

*   **Genomic Resource Repositories:** This component manages genomic resources such as reference genomes, gene models, and annotation scores. It provides a centralized repository for accessing and managing these resources.

*   **Annotation Pipeline:** This component performs variant annotation using genomic resources and annotation tools. It enriches variants with functional and biological information, aiding in the interpretation of genetic variations.

*   **Web API:** This component exposes API endpoints for accessing and interacting with GPF data. It provides interfaces for querying variants, accessing datasets, managing users, and performing other operations.

*   **Query Builder:** This component constructs SQL queries based on user requests and data models. It translates high-level query specifications into efficient SQL queries for the storage backend.

*   **Query Runner:** This component executes SQL queries against the storage backend and retrieves the results. It optimizes query execution and handles data retrieval.

*   **User Interface:** This component provides a web-based interface for users to interact with GPF. It allows users to browse datasets, query variants, visualize results, and manage their accounts.

*   **User Authentication:** This component handles user authentication, verifying user credentials and establishing secure sessions.

*   **Authorization and Permissions:** This component manages user authorization and permissions, controlling access to datasets and functionalities based on user roles and privileges.