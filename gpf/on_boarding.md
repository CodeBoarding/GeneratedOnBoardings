# GPF Project Onboarding Document

## Project Description

The Genomic Platform (GPF) project is a comprehensive suite of tools and a web application (WDAE) designed for analyzing and managing genomic data. It provides functionalities for variant annotation, storage, querying, and reporting, with a focus on supporting research in genetics and genomics. GPF enables researchers to explore variant data in the context of families, genes, and genomic regions, facilitating the discovery of disease-causing mutations and the understanding of genetic mechanisms.

## Project Flow Diagram

```mermaid
graph LR
    subgraph Data Ingestion and Management
        A[Raw Genomic Data] --> B(GPFInstance)
        B --> C(Genomic Resources Management)
        B --> D(Families Data Management)
        B --> E(Annotation Pipeline)
        B --> F(Variants Data Access)
        F --> G(Genotype Storage)
    end

    subgraph Web Application and API
        H(User) --> I(WDAEConfig)
        I --authenticates--> J(User Management and Authentication)
        I --configures--> K(API Endpoints)
        K --queries--> F
        K --accesses--> C
		K --accesses--> D
        K --manages--> L(Query Management)
    end

    subgraph Data Analysis and Reporting
        L --uses--> F
        L --saves/loads--> M(Query State)
    end

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style H fill:#f9f,stroke:#333,stroke-width:2px

## Component Descriptions

*   **Raw Genomic Data:** Represents the initial input data, such as VCF files or other variant call formats, that needs to be processed and analyzed by the GPF system.

*   **GPFInstance:** The central component that orchestrates the entire GPF system. It initializes and configures all other components, providing a unified access point to genomic resources, variant data, and analysis tools. It manages the lifecycle of the application and ensures that all components are properly configured and interconnected.

*   **Genomic Resources Management:** This component is responsible for managing and providing access to essential genomic resources, such as reference genomes, gene models, and annotation databases. It handles the retrieval, storage, and organization of these resources, ensuring that they are readily available for variant annotation and analysis.

*   **Families Data Management:** This component manages pedigree information, representing family relationships and individual characteristics. It provides functionalities for accessing and analyzing family structures, which is crucial for understanding the inheritance patterns of genetic variants.

*   **Annotation Pipeline:** This component handles the annotation of genetic variants, enriching them with relevant information such as gene effects, functional predictions, and population frequencies. It uses genomic resources and external databases to add context to the variants, facilitating their interpretation and prioritization.

*   **Variants Data Access:** This component provides a unified interface for accessing variant data stored in different formats and storage systems. It abstracts the underlying storage mechanisms, allowing users to query and retrieve variant information without needing to know the specific details of the data storage.

*   **Genotype Storage:** This component manages the storage and retrieval of genotype data, providing efficient access to variant information. It supports various storage systems, such as Impala, Parquet, and in-memory databases, allowing the GPF system to scale and adapt to different data sizes and performance requirements.

*   **User:** Represents a researcher or analyst who interacts with the WDAE web application to explore and analyze genomic data.

*   **WDAEConfig:** This component configures the WDAE web application, loading extensions and preparing the application for use. It sets up the necessary parameters and settings for the web interface to interact with the GPF system.

*   **User Management and Authentication:** This component handles user creation, authentication, authorization, and profile management for the WDAE web interface. It ensures that only authorized users can access sensitive genomic data and analysis tools.

*   **API Endpoints:** This component provides a set of RESTful APIs for accessing various functionalities of the GPF system, including variant querying, genomic resource retrieval, and analysis tools. These APIs allow external applications and services to interact with the GPF system programmatically.

*   **Query Management:** This component handles user queries, interacting with the data access layer to retrieve variant information. It also provides functionalities for saving, loading, and deleting query states, allowing users to persist and retrieve their search configurations.

*   **Query State:** This component represents the saved state of a user query, including the search parameters, filters, and other settings. It allows users to easily resume their analysis from where they left off, without needing to re-enter their query configurations.
```
