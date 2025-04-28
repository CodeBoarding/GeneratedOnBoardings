## Variant Loader Component Overview

The Variant Loader component is responsible for loading variant data from different file formats, primarily VCF and denovo files. It handles pedigree information, matches samples to families, and prepares the data for further processing, such as annotation and storage.

```mermaid
flowchart LR
    subgraph Variant Loading
    A[FamiliesLoader] -- loads --> B(FamiliesData)
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px
    C[VcfLoader] -- uses --> B
    style C fill:#f9f,stroke:#333,stroke-width:2px
    D[SingleVcfLoader] -- reads --> E(VCF Files)
    style D fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#eee,stroke:#333,stroke-width:2px
    C -- creates --> D
    D -- creates --> F(VcfFamiliesGenotypes)
    style F fill:#f9f,stroke:#333,stroke-width:2px
    F -- creates --> G(FamilyVariant)
    style G fill:#f9f,stroke:#333,stroke-width:2px
    H[DenovoLoader] -- reads --> I(Denovo Files)
    style H fill:#f9f,stroke:#333,stroke-width:2px
    style I fill:#eee,stroke:#333,stroke-width:2px
    H -- creates --> J(DenovoFamiliesGenotypes)
    style J fill:#f9f,stroke:#333,stroke-width:2px
    J -- creates --> G
    C --> G
    H --> G
    end

    subgraph Annotation
    K[AnnotationPipelineConstruction] -- constructs --> L(AnnotationPipeline)
    style K fill:#f9f,stroke:#333,stroke-width:2px
    style L fill:#ccf,stroke:#333,stroke-width:2px
    M[AnnotationPipelineDecorator] -- annotates --> G
    style M fill:#f9f,stroke:#333,stroke-width:2px
    end

    G -- sends --> N(Storage)
    style N fill:#ccf,stroke:#333,stroke-width:2px
    L -- uses --> N

    K -- uses --> B
    M -- uses --> L

