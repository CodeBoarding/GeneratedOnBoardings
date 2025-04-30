## Analysis & Reporting Component Overview

The `Analysis & Reporting` component provides the tools and infrastructure for performing various analyses on genetic data, such as enrichment analysis and gene profiling, and for managing collections of gene sets used in these analyses. It is composed of three main sub-components: `Enrichment Tooling`, `Gene Profile Management`, and `Gene Set Management`. These components interact with external data sources like Genotype Data and Genomic Resources to perform their functions and generate results or provide data for reporting.

```mermaid
componentDiagram
    direction LR
    component "Genotype Data" as GD
    component "Genomic Resources" as GR
    component "Gene Set Management" as GSM
    component "Enrichment Tooling" as ET
    component "Gene Profile Management" as GPM
    component "Gene Profile Database" as GPDB

    GD --> ET : Provides variant data
    GR --> ET : Provides backgrounds/counters
    GR --> GSM : Provides gene set definitions
    GSM --> ET : Provides gene sets
    ET --> GPM : (Results can update profiles)
    GPM --> GPDB : Reads/Writes profiles
    ET --> AnalysisReporting : Outputs results
    GPM --> AnalysisReporting : Outputs profiles

    component "Analysis & Reporting" as AnalysisReporting {
        component "Enrichment Tooling"
        component "Gene Profile Management"
        component "Gene Set Management"
    }
```

### Component Descriptions:

*   **Enrichment Tooling**
    *   **Purpose:** Provides the core logic for performing enrichment analysis on genetic data.
    *   **Functionality:** Configures and runs enrichment tests using various background models and event counters. It processes genotype data and utilizes gene sets to calculate statistical enrichment.
    *   **Interactions:** Receives genotype data from `Genotype Data`, loads resources (like background models) from `Genomic Resources`, and obtains gene sets from `Gene Set Management`. It produces enrichment results that can potentially be used to update gene profiles managed by `Gene Profile Management` and are outputted by the `Analysis & Reporting` component.
    *   **Relevant Files:** `dae.enrichment_tool.enrichment_helper.py`, `dae.enrichment_tool.base_enrichment_background.py`, `dae.enrichment_tool.event_counters.py`, `dae.enrichment_tool.genotype_helper.py`.

*   **Gene Profile Management**
    *   **Purpose:** Manages the storage, retrieval, and querying of pre-calculated gene profile statistics.
    *   **Functionality:** Handles interactions with the gene profile database (DuckDB/SQLite), allowing for querying gene profiles by symbol, filtering, sorting, and pagination. It also includes functionality for building and updating the database.
    *   **Interactions:** Primarily interacts with the `Gene Profile Database` for data persistence. It receives potential updates from `Enrichment Tooling` results and provides gene profile data to the broader `Analysis & Reporting` system for display or further use.
    *   **Relevant Files:** `dae.gene_profile.db.py`, `dae.gene_profile.statistic.py`.

*   **Gene Set Management**
    *   **Purpose:** Provides a centralized way to load, store, and access collections of gene sets.
    *   **Functionality:** Reads gene set definitions from various formats (map, gmt, directory) stored as `Genomic Resources`. It allows querying for specific gene sets or retrieving all gene sets within a collection.
    *   **Interactions:** Loads gene set data from `Genomic Resources`. Provides gene sets to `Enrichment Tooling` for use in enrichment analysis. It is a foundational component for analyses that rely on predefined gene groups.
    *   **Relevant Files:** `dae.gene_sets.gene_sets_db.py`, `dae.gene_sets.gene_term.py`.
