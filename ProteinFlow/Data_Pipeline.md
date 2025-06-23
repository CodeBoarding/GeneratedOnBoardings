```mermaid
graph LR
    Data_Downloader["Data Downloader"]
    Data_Processor["Data Processor"]
    Ligand_Processor["Ligand Processor"]
    PDBEntry["PDBEntry"]
    SAbDabEntry["SAbDabEntry"]
    Data_Downloader -- "provides raw data to" --> Data_Processor
    Data_Processor -- "transforms data into" --> PDBEntry
    Data_Processor -- "utilizes" --> Ligand_Processor
    Ligand_Processor -- "modifies/enriches" --> PDBEntry
    SAbDabEntry -- "inherits from" --> PDBEntry
    PDBEntry -- "consumed by" --> ProteinDataset
    PDBEntry -- "consumed by" --> DataSplitter
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `Data Pipeline` subsystem is responsible for the initial stages of data handling, from raw data acquisition to the creation of structured protein entries. It encompasses components for downloading, parsing, filtering, and transforming protein and ligand data into a standardized format for further use.

### Data Downloader
This component is solely responsible for retrieving raw protein data files, specifically PDB (Protein Data Bank) and SAbDab (Structural Antibody Database) files, from their respective external repositories. It ensures that the necessary raw input is available for the subsequent processing steps.


**Related Classes/Methods**:

- `Data Downloader` (1:1)


### Data Processor
This is the core processing engine of the pipeline. It takes the raw protein data provided by the `Data Downloader`, performs essential parsing to extract relevant information, applies filtering criteria (e.g., based on chain types or quality), and transforms this raw information into structured `PDBEntry` objects. It orchestrates the integration of ligand-specific data processing by utilizing the `Ligand Processor`.


**Related Classes/Methods**:

- `Data Processor` (1:1)


### Ligand Processor
This specialized component handles all operations related to ligands associated with protein structures. Its functionalities include loading SMILES strings, merging ligand information with protein chains, and performing clustering based on ligand similarity (e.g., Tanimoto clustering). It acts as a helper for the `Data Processor` when ligand data is present, enriching the `PDBEntry` objects with ligand-specific features.


**Related Classes/Methods**:

- `Ligand Processor` (1:1)


### PDBEntry
This is the fundamental `Core Data Model` representing a single protein structure or entry, primarily derived from PDB files. It encapsulates all relevant information about a protein, including its sequence, atomic coordinates, chain identifiers, and potentially integrated ligand features. It provides methods for accessing specific parts (e.g., CDRs) and manipulating the structure. `SAbDabEntry` inherits from this class, extending its functionality for antibody-specific data.


**Related Classes/Methods**:

- `PDBEntry` (1:1)


### SAbDabEntry
A specialized data model for antibody structures, inheriting directly from `PDBEntry`. It extends the base `PDBEntry` model with specific attributes and methods relevant to SAbDab data, such as detailed antibody chain definitions and numbering schemes. This allows for specialized handling of antibody structures while leveraging the common functionalities of `PDBEntry`.


**Related Classes/Methods**:

- `SAbDabEntry` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)