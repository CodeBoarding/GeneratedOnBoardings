```mermaid
graph LR
    GRR[Genomic Resource Repository] -- provides --> GR[Genomic Resources]
    GR -- uses --> RG[Reference Genome]
    GR -- uses --> GM[Gene Models]
    GR -- uses --> GS[Genomic Scores]

    subgraph Genomic Resources Subsystem
    GRR
    GR
    RG
    GM
    GS
    end

    style GR fill:#f9f,stroke:#333,stroke-width:2px
```
```mermaid
classDiagram
    class GenomicResource {
        +resource_id : str
        +get_type() : str
        +get_config() : dict
        +open_raw_file(filename: str, mode: str) : IO
        +get_file_content(filename: str) : str
    }

    class ReferenceGenome {
        +chromosomes : list[str]
        +fetch(chrom: str, start: int, stop: int) : Generator[str, None, None]
        +get_sequence(chrom: str, start: int, stop: int) : str
    }

    class GeneModels {
        +get_gene(gene_id: str) : Gene
        +get_genes_by_region(chrom: str, start: int, stop: int) : list[Gene]
    }

    class GenomicScores {
        +fetch_scores(chrom: str, position: int, scores: list[str]) : dict
    }

    GenomicResource -- ReferenceGenome : uses
    GenomicResource -- GeneModels : uses
    GenomicResource -- GenomicScores : uses
```

### Components Description:

*   **Genomic Resource Repository (GRR):** Manages access to genomic resources. It provides methods to build, retrieve, and manage resources within a defined storage location. It `provides` resources to the `Genomic Resources` component.
    *   Relevant source files: `dae.genomic_resources.repository_factory`, `dae.genomic_resources.group_repository`

*   **Genomic Resources (GR):** Serves as a central access point for various genomic data. It `uses` `Reference Genome`, `Gene Models`, and `Genomic Scores` to provide a unified interface for accessing genomic information.
    *   Relevant source files: `dae.genomic_resources`

*   **Reference Genome (RG):** Represents the reference genome and provides methods to open, access, and query sequence data for specific regions or positions. `Genomic Resources` `uses` this component to retrieve sequence information.
    *   Relevant source files: `dae.genomic_resources.reference_genome`

*   **Gene Models (GM):** Represents gene models and provides methods to load, access, and query gene structures, including exons, transcripts, and coding regions. `Genomic Resources` `uses` this component to access gene annotations.
    *   Relevant source files: `dae.genomic_resources.gene_models`

*   **Genomic Scores (GS):** Component responsible for managing, accessing, and querying genomic scores, such as conservation scores or functional predictions, associated with genomic positions or regions. `Genomic Resources` `uses` this component to access precomputed scores.
    *   Relevant source files: `dae.genomic_scores`
