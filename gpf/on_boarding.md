```text
## GPF Project Onboarding Document

### Project Description

The GPF (Genomic Population Framework) project is a comprehensive platform designed for managing, analyzing, and exploring large-scale genomic data. It provides tools for data import, storage, annotation, and querying, with a focus on facilitating research in population genetics and genomics. The platform includes a web-based interface (WDAE) for interactive data exploration and analysis.

### Data Flow Diagram

```mermaid
graph LR
    subgraph Data Ingestion
        A[Data Import and Conversion Tools]
    end
    B[Configuration and Metadata Management]
    C[Genomic Resources and Annotation]
    D[Data Storage and Query Engine]
    E[Web Application (WDAE)]

    A--converts & loads-->D
    B--configures-->C
    B--configures-->D
    C--annotates-->D
    D--queries-->E
    E--presents-->User
```

### Component Descriptions

*   **Data Import and Conversion Tools:** This component provides command-line tools for importing and converting data from various formats (e.g., VCF, DAE) into formats suitable for GPF's data storage. It converts raw data and loads it into the Data Storage and Query Engine.

*   **Configuration and Metadata Management:** This component handles the loading, parsing, validation, and management of configuration settings and metadata for studies, datasets, and genomic resources. It configures both the Genomic Resources and Annotation component and the Data Storage and Query Engine, providing essential parameters for their operation.

*   **Genomic Resources and Annotation:** This component manages genomic resources (reference genomes, gene models, annotation scores) and annotates genetic variants with functional effects and genomic scores. It uses configurations from the Configuration and Metadata Management component to properly annotate data before passing the annotated data to the Data Storage and Query Engine.

*   **Data Storage and Query Engine:** This component provides an abstraction layer for storing and querying genotype and phenotype data, supporting various backends (Impala, DuckDB, GCP). It receives converted data from the Data Import and Conversion Tools and annotated data from the Genomic Resources and Annotation component. It then provides query capabilities to the Web Application (WDAE).

*   **Web Application (WDAE):** This component implements the web-based data exploration interface, providing API endpoints for accessing and analyzing data, managing user authentication and authorization, and handling data serialization/deserialization for web presentation. It queries the Data Storage and Query Engine to retrieve data for presentation to the user.