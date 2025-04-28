```json
{
  "content": "## Annotation Pipeline Overview\n\nThe Annotation Pipeline is a crucial component for annotating genetic variants with functional and genomic information. It orchestrates a series of annotators to enrich variant data with relevant annotations. The pipeline is built from a configuration file (YAML) and uses genomic resources like reference genomes and gene models.\n\n```mermaid\nflowchart LR\n    subgraph Configuration\n        A[Annotation Config YAML] -- parses --> B(AnnotationConfigParser)\n    end\n    subgraph Resources\n        C[GenomicResourceRepo] -- provides --> D(ReferenceGenome)\n        C -- provides --> E(GeneModels)\n    end\n    subgraph Pipeline Construction\n        B -- uses --> C\n        B -- creates --> F(build_annotation_pipeline)\n        F -- creates --> G(AnnotationPipeline)\n        G -- contains --> H((Annotator))\n        H -- implements by --> I(EffectAnnotatorAdapter)\n        I -- adapts --> J(EffectAnnotator)\n        J -- uses --> D\n        J -- uses --> E\n    end\n    subgraph Annotation Flow\n        K(Annotatable) -- annotates --> G\n        G -- annotates with --> H\n        H -- uses --> D\n        H -- uses --> E\n        H -- annotates --> K\n    end\n    subgraph Reannotation\n        L(Old Annotation Pipeline) -- reannotates with --> M(ReannotationPipeline)\n        M -- uses --> G\n    end\n\n    style A fill:#f9f,stroke:#333,stroke-width:2px\n    style C fill:#ccf,stroke:#333,stroke-width:2px\n    style G fill:#ffc,stroke:#333,stroke-width:2px\n    style H fill:#cff,stroke:#333,stroke-width:2px\n    style J fill:#cfc,stroke:#333,stroke-width:2px\n\n    A -- loads --> F\n    G -- opens/closes --> H\n    H -- decorates --> InputAnnotableAnnotatorDecorator\n    H -- decorates --> ValueTransformAnnotatorDecorator\n\n\n```\n\n### Component Descriptions\n\n*   **Annotation Config YAML**: Contains the configuration for the annotation pipeline, specifying the annotators to use and their parameters.\n    *   *Functionality*: Defines the structure and behavior of the annotation pipeline.\n    *   *Interaction*: Parsed by `AnnotationConfigParser` to create the pipeline.\n    *   *Source Files*: N/A (YAML file)\n\n*   **AnnotationConfigParser**: Parses the annotation configuration file (YAML) and extracts relevant information for building the pipeline.\n    *   *Functionality*: Transforms the raw configuration into a structured format suitable for creating annotators.\n    *   *Interaction*: Reads the YAML configuration and uses `GenomicResourceRepo` to access genomic resources. Creates `AnnotatorInfo` objects.\n    *   *Source Files*: `dae.annotation.annotation_config.AnnotationConfigParser`\n\n*   **GenomicResourceRepo**: Manages access to genomic resources like reference genomes and gene models.\n    *   *Functionality*: Provides a central point for retrieving and managing genomic resources.\n    *   *Interaction*: Used by `AnnotationConfigParser` and annotators to access genomic resources.\n    *   *Source Files*: `dae.genomic_resources.repository.GenomicResourceRepo`\n\n*   **ReferenceGenome**: Provides access to the reference genome sequence.\n    *   *Functionality*: Allows annotators to retrieve the sequence of specific regions of the genome.\n    *   *Interaction*: Used by annotators like `EffectAnnotator` to determine the effects of variants.\n    *   *Source Files*: `dae.genomic_resources.reference_genome.ReferenceGenome`\n\n*   **GeneModels**: Provides access to gene models and transcript structures.\n    *   *Functionality*: Allows annotators to retrieve information about genes, transcripts, exons, and introns.\n    *   *Interaction*: Used by annotators like `EffectAnnotator` to determine the effects of variants on genes and transcripts.\n    *   *Source Files*: `dae.genomic_resources.gene_models.GeneModels`\n\n*   **build\_annotation\_pipeline**: Factory function that constructs an `AnnotationPipeline` from a configuration (YAML or dict).\n    *   *Functionality*: Uses annotator factories to create individual annotators and adds them to the pipeline.\n    *   *Interaction*: Reads the parsed configuration and creates `AnnotationPipeline` and `Annotator` instances.\n    *   *Source Files*: `dae.annotation.annotation_factory.build_annotation_pipeline`\n\n*   **AnnotationPipeline**: Orchestrates the annotation process by managing a sequence of annotators.\n    *   *Functionality*: Handles the opening and closing of annotators and applies them sequentially to annotatables.\n    *   *Interaction*: Contains a list of `Annotator` objects and applies them to `Annotatable` objects. Uses `GenomicResourceRepo` to access genomic resources.\n    *   *Source Files*: `dae.annotation.annotation_pipeline.AnnotationPipeline`\n\n*   **Annotator**: Abstract base class for annotators, responsible for adding specific annotations to variants.\n    *   *Functionality*: Defines the `annotate` method that subclasses must implement.\n    *   *Interaction*: Subclasses implement the `annotate` method to add specific annotations. Used by `AnnotationPipeline` to annotate `Annotatable` objects.\n    *   *Source Files*: `dae.annotation.annotation_pipeline.Annotator`, `dae.annotation.annotator_base.AnnotatorBase`\n\n*   **EffectAnnotatorAdapter**: Adapts the `EffectAnnotator` to fit within the annotation pipeline framework.\n    *   *Functionality*: Provides variant effect predictions. Retrieves gene models and reference genome information and configures the `EffectAnnotator`.\n    *   *Interaction*: Creates and configures an `EffectAnnotator` instance. Implements the `annotate` method to call the `EffectAnnotator`.\n    *   *Source Files*: `dae.annotation.effect_annotator.EffectAnnotatorAdapter`\n\n*   **EffectAnnotator**: Core annotator that predicts the effects of genetic variants on genes and transcripts.\n    *   *Functionality*: Uses gene models and a reference genome to determine the impact of variants.\n    *   *Interaction*: Receives variant information from `EffectAnnotatorAdapter` and uses gene models and the reference genome to predict effects.\n    *   *Source Files*: `dae.effect_annotation.annotator.EffectAnnotator`\n\n*   **Annotatable**: Represents a genomic variant or region that can be annotated.\n    *   *Functionality*: Provides a common interface for accessing variant properties like chromosome, position, and allele.\n    *   *Interaction*: Passed to the `AnnotationPipeline` for annotation.\n    *   *Source Files*: `dae.annotation.annotatable.Annotatable`\n\n*   **ReannotationPipeline**: A special pipeline that handles reannotation of a previous pipeline.\n    *   *Functionality*: Identifies which annotators need to be rerun and which attributes can be reused from the previous annotation.\n    *   *Interaction*: Uses two annotation pipelines (old and new) and determines the differences between them to optimize the reannotation process.\n    *   *Source Files*: `dae.annotation.annotation_pipeline.ReannotationPipeline`\n\n*   **InputAnnotableAnnotatorDecorator**: Defines annotator decorator to use input annotatable if defined.\n    *   *Functionality*: Decorates annotators to use a specified input annotatable from the annotation context.\n    *   *Interaction*: Wraps an annotator and retrieves the input annotatable from the context before calling the wrapped annotator's `annotate` method.\n    *   *Source Files*: `dae.annotation.annotation_pipeline.InputAnnotableAnnotatorDecorator`\n\n*   **ValueTransformAnnotatorDecorator**: Define value transformer annotator decorator. Used to transform values of attributes.\n    *   *Functionality*: Decorates annotators to transform the values of specific attributes after annotation.\n    *   *Interaction*: Wraps an annotator and applies a transformation function to the values of specified attributes after the wrapped annotator's `annotate` method is called.\n    *   *Source Files*: `dae.annotation.annotation_pipeline.ValueTransformAnnotatorDecorator`",
  "components": [
    {
      "name": "Annotation Config YAML",
      "description": "Contains the configuration for the annotation pipeline, specifying the annotators to use and their parameters.",
      "qualified_names": []
    },
    {
      "name": "AnnotationConfigParser",
      "description": "Parses the annotation configuration file (YAML) and extracts relevant information for building the pipeline.",
      "qualified_names": [
        "dae.annotation.annotation_config.AnnotationConfigParser"
      ]
    },
    {
      "name": "GenomicResourceRepo",
      "description": "Manages access to genomic resources like reference genomes and gene models.",
      "qualified_names": [
        "dae.genomic_resources.repository.GenomicResourceRepo"
      ]
    },
    {
      "name": "ReferenceGenome",
      "description": "Provides access to the reference genome sequence.",
      "qualified_names": [
        "dae.genomic_resources.reference_genome.ReferenceGenome"
      ]
    },
    {
      "name": "GeneModels",
      "description": "Provides access to gene models and transcript structures.",
      "qualified_names": [
        "dae.genomic_resources.gene_models.GeneModels"
      ]
    },
    {
      "name": "build_annotation_pipeline",
      "description": "Factory function that constructs an AnnotationPipeline from a configuration (YAML or dict).",
      "qualified_names": [
        "dae.annotation.annotation_factory.build_annotation_pipeline"
      ]
    },
    {
      "name": "AnnotationPipeline",
      "description": "Orchestrates the annotation process by managing a sequence of annotators.",
      "qualified_names": [
        "dae.annotation.annotation_pipeline.AnnotationPipeline"
      ]
    },
    {
      "name": "Annotator",
      "description": "Abstract base class for annotators, responsible for adding specific annotations to variants.",
      "qualified_names": [
        "dae.annotation.annotation_pipeline.Annotator",
        "dae.annotation.annotator_base.AnnotatorBase"
      ]
    },
    {
      "name": "EffectAnnotatorAdapter",
      "description": "Adapts the EffectAnnotator to fit within the annotation pipeline framework.",
      "qualified_names": [
        "dae.annotation.effect_annotator.EffectAnnotatorAdapter"
      ]
    },
    {
      "name": "EffectAnnotator",
      "description": "Core annotator that predicts the effects of genetic variants on genes and transcripts.",
      "qualified_names": [
        "dae.effect_annotation.annotator.EffectAnnotator"
      ]
    },
    {
      "name": "Annotatable",
      "description": "Represents a genomic variant or region that can be annotated.",
      "qualified_names": [
        "dae.annotation.annotatable.Annotatable"
      ]
    },
    {
      "name": "ReannotationPipeline",
      "description": "A special pipeline that handles reannotation of a previous pipeline.",
      "qualified_names": [
        "dae.annotation.annotation_pipeline.ReannotationPipeline"
      ]
    },
    {
      "name": "InputAnnotableAnnotatorDecorator",
      "description": "Defines annotator decorator to use input annotatable if defined.",
      "qualified_names": [
        "dae.annotation.annotation_pipeline.InputAnnotableAnnotatorDecorator"
      ]
    },
    {
      "name": "ValueTransformAnnotatorDecorator",
      "description": "Define value transformer annotator decorator. Used to transform values of attributes.",
      "qualified_names": [
        "dae.annotation.annotation_pipeline.ValueTransformAnnotatorDecorator"
      ]
    }
  ]
}
```