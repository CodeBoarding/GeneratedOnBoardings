## Genomic Resources Repository (GRR) Overview

The Genomic Resources Repository (GRR) component manages and provides access to genomic resources like reference genomes and gene models. It uses a hierarchical structure to organize resources, allowing for efficient retrieval and utilization of genomic data.

```mermaid
flowchart LR
    %% Nodes
    Factory(Repository Factory)
    GroupRepo(GenomicResourceGroupRepo)
    ResourceRepo(GenomicResourceProtocolRepo)
    RefGenomeBuilder(ReferenceGenome Builder)
    ReferenceGenome(Reference Genome)
    SequenceFile((Sequence File))
    IndexFile((Index File))
    GeneModelBuilder(GeneModels Builder)
    GeneModels(Gene Models)
    GeneModelData((Gene Model Data))
    GenomicResource(Genomic Resource)

    %% Subgraphs
    subgraph GRR["Genomic Resource Repository"]
        direction TB
        Factory -- Builds --> GroupRepo
        GroupRepo -- Contains --> ResourceRepo
        ResourceRepo -- Provides --> ReferenceGenome
        ResourceRepo -- Provides --> GeneModels
    end

    subgraph RG["Reference Genome"]
        direction TB
        RefGenomeBuilder -- Builds --> ReferenceGenome
        ReferenceGenome -- Opens --> SequenceFile
        ReferenceGenome -- Uses --> IndexFile
    end

    subgraph GM["Gene Models"]
        direction TB
        GeneModelBuilder -- Builds --> GeneModels
        GeneModels -- Loads --> GeneModelData
    end

    %% Cross Connections
    Factory -- Configures --> GroupRepo
    ResourceRepo -- Provides --> GenomicResource
    GenomicResource -- Uses --> RefGenomeBuilder
    GenomicResource -- Uses --> GeneModelBuilder

    %% Styling
    classDef grrStyle fill:#f9f,stroke:#333,stroke-width:2px;
    classDef rgStyle fill:#ccf,stroke:#333,stroke-width:2px;
    classDef gmStyle fill:#ccf,stroke:#333,stroke-width:2px;
    
    class Factory,GroupRepo,Resource

```

### Component Descriptions:

**1. Repository Factory**
   - *Purpose*: Creates and configures different types of genomic resource repositories based on a definition file.
   - *Functionality*: Reads a configuration file (YAML) specifying the repository type (e.g., HTTP, file, group) and builds the corresponding repository object. It supports creating group repositories, which are composed of other repositories.
   - *Interaction*: Configures and builds `GenomicResourceGroupRepo` and `GenomicResourceProtocolRepo`.
   - *Relevant source files*: `dae/genomic_resources/repository_factory.py`

**2. GenomicResourceGroupRepo**
   - *Purpose*: A repository that groups multiple other repositories.
   - *Functionality*: Organizes a collection of `GenomicResourceRepo` instances. It implements the `GenomicResourceRepo` interface, allowing it to be treated as a single repository. It searches for resources in its child repositories.
   - *Interaction*: Contains and manages `GenomicResourceRepo` instances. Used by `Repository Factory` to create group repositories.
   - *Relevant source files*: `dae/genomic_resources/group_repository.py`

**3. GenomicResourceProtocolRepo**
   - *Purpose*: A repository that accesses resources using a specified protocol (e.g., HTTP, file).
   - *Functionality*: Provides access to genomic resources stored at a specific location using a protocol like HTTP or file system. It uses `fsspec` to handle different protocols.
   - *Interaction*: Interacts with `ReferenceGenome` and `GeneModels` by providing access to resource files. Built by `Repository Factory`.
   - *Relevant source files*: `dae/genomic_resources/repository.py`

**4. Reference Genome**
   - *Purpose*: Provides access to the reference genome sequence.
   - *Functionality*: Loads the reference genome sequence and index, allowing for efficient retrieval of nucleotide sequences for specific regions. It handles chromosome lengths and pseudoautosomal regions.
   - *Interaction*: Uses `SequenceFile` and `IndexFile` to access genome data. Used by other components needing sequence information.
   - *Relevant source files*: `dae/genomic_resources/reference_genome/reference_genome.py`, `dae/genomic_resources/reference_genome/build_reference_genome_from_resource.py`

**5. Gene Models**
   - *Purpose*: Provides access to gene models and transcript structures.
   - *Functionality*: Loads gene models from a resource file, providing access to transcript structures, exons, CDS regions, and UTRs. It supports querying gene models by gene name or genomic location.
   - *Interaction*: Loads `GeneModelData` and provides gene models to other components. Uses `TranscriptModel` and `Exon` classes to represent gene structures.
   - *Relevant source files*: `dae/genomic_resources/gene_models/gene_models.py`, `dae/genomic_resources/gene_models/gene_models/build_gene_models_from_resource.py`
