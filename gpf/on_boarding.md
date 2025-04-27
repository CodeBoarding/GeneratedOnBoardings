Okay, I'm ready to generate the high-level data flow diagram for the `gpf` project.

**1. Project Description:**

GPF (Genomic Prediction Framework) is a comprehensive framework designed for managing, analyzing, and annotating genomic data. It provides tools and infrastructure for variant storage, retrieval, annotation, and analysis, with a focus on supporting research in genetics and genomics. GPF integrates various genomic resources, pedigree information, and annotation pipelines to facilitate the discovery of disease-causing variants and the study of genetic inheritance patterns.

**2. Data Flow Diagram (Mermaid Format):**

```mermaid
graph LR
    subgraph Core Data Flow
    A[Configuration Management] -- provides --> B(GPF Instance)
    B -- uses --> C(Genomic Resources)
    B -- uses --> D(Pedigree Management)
    E(Variants Loader) -- loads --> B
    E -- uses --> D
    B -- uses --> F(Annotation Pipeline)
    F -- uses --> C
    end

    subgraph User Interface
    G(Web Interface (WDAE)) -- interacts with --> B
    end
```

**3. Component Descriptions:**

*   **Configuration Management:** This component is responsible for parsing, validating, and managing the configuration files that define the GPF environment. It provides the GPF Instance with the necessary settings and resource locations.
*   **GPF Instance:** The central component of the GPF framework, it manages access to configured resources, datasets, and functionalities. It utilizes Genomic Resources and Pedigree Management to provide a unified interface for interacting with genomic data. It also triggers the Annotation Pipeline to enrich variant data. The Web Interface interacts with the GPF Instance to provide users with access to data and analysis tools.
*   **Genomic Resources:** This component manages genomic resources such as reference genomes, gene models, and annotation databases. It provides essential data to the GPF Instance and the Annotation Pipeline for variant interpretation and annotation.
*   **Variants Loader:** This component loads variant data from various file formats into a unified representation within the GPF Instance. It uses Pedigree Management to associate variants with family structures.
*   **Pedigree Management:** This component loads, manipulates, and represents pedigree data, defining family relationships and individual characteristics. It is used by the Variants Loader to associate variants with specific families, and its data is accessed by the GPF Instance.
*   **Annotation Pipeline:** This component annotates genomic variants with functional and biological information, enriching the data with context for interpretation and prioritization. It uses Genomic Resources to access annotation databases and tools.
*   **Web Interface (WDAE):** This component provides a web-based interface for users to interact with GPF data, perform queries, and visualize results. It relies on the GPF Instance to access data and functionalities.