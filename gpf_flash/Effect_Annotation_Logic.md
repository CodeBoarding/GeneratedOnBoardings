```mermaid
graph LR
    Effect_Annotation_Orchestrator["Effect Annotation Orchestrator"]
    Variant_Data_Model["Variant Data Model"]
    Effect_Data_Model["Effect Data Model"]
    Coding_Region_Effect_Checker["Coding Region Effect Checker"]
    Splice_Site_Effect_Checker["Splice Site Effect Checker"]
    Frameshift_Effect_Checker["Frameshift Effect Checker"]
    Untranslated_Region_UTR_Effect_Checker["Untranslated Region (UTR) Effect Checker"]
    Intron_Effect_Checker["Intron Effect Checker"]
    Promoter_Effect_Checker["Promoter Effect Checker"]
    Protein_Change_Calculator["Protein Change Calculator"]
    Effect_Annotation_Orchestrator -- "processes" --> Variant_Data_Model
    Effect_Annotation_Orchestrator -- "utilizes" --> Coding_Region_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Splice_Site_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Frameshift_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Untranslated_Region_UTR_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Intron_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Promoter_Effect_Checker
    Effect_Annotation_Orchestrator -- "utilizes" --> Protein_Change_Calculator
    Effect_Annotation_Orchestrator -- "produces" --> Effect_Data_Model
    Coding_Region_Effect_Checker -- "generates" --> Effect_Data_Model
    Splice_Site_Effect_Checker -- "generates" --> Effect_Data_Model
    Frameshift_Effect_Checker -- "generates" --> Effect_Data_Model
    Untranslated_Region_UTR_Effect_Checker -- "generates" --> Effect_Data_Model
    Intron_Effect_Checker -- "generates" --> Effect_Data_Model
    Promoter_Effect_Checker -- "generates" --> Effect_Data_Model
    Protein_Change_Calculator -- "generates" --> Effect_Data_Model
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Effect Annotation Logic subsystem is a critical computational engine within the Bioinformatics Data Platform, responsible for predicting the functional consequences of genetic variants. Its design follows a modular monolith pattern, allowing for specialized "Effect Checkers" to be integrated and orchestrated by a central Annotator.

### Effect Annotation Orchestrator
This is the primary control unit for the effect annotation process. It takes genetic variants and gene models as input, coordinates with various specialized "Effect Checkers" to determine all possible functional consequences, and aggregates their results to produce a comprehensive set of predicted effects. It manages the overall flow and ensures all relevant checks are performed.


**Related Classes/Methods**:

- `Effect Annotation Orchestrator` (1:1)


### Variant Data Model
Defines the standardized data structure for representing a genetic variant. This includes essential properties such as its chromosome, genomic position, reference allele, and alternative allele. This component ensures consistent input for the annotation process across all checkers.


**Related Classes/Methods**:

- `Variant Data Model` (1:1)


### Effect Data Model
Defines the standardized data structure for a predicted functional consequence of a genetic variant. This includes details like the effect type (e.g., "missense", "splice-site"), the affected gene, protein change, and other relevant biological context. It serves as the structured output format for the annotation results.


**Related Classes/Methods**:

- `Effect Data Model` (1:1)


### Coding Region Effect Checker
A specialized module responsible for identifying and describing effects that alter the protein-coding sequence of a gene. This includes common effects such as missense (amino acid change), nonsense (premature stop codon), and silent (no amino acid change) mutations, based on codon changes and reading frames.


**Related Classes/Methods**:

- `Coding Region Effect Checker` (1:1)


### Splice Site Effect Checker
A specialized module dedicated to detecting and characterizing genetic variants that impact RNA splicing. It focuses on mutations occurring at or near intron-exon boundaries (splice donor and acceptor sites), which can lead to altered mRNA transcripts and protein products.


**Related Classes/Methods**:

- `Splice Site Effect Checker` (1:1)


### Frameshift Effect Checker
A specialized module for identifying insertions or deletions (indels) that cause a shift in the translational reading frame of a gene. Such frameshifts typically lead to a completely altered downstream amino acid sequence and often result in a premature stop codon, producing a truncated or non-functional protein.


**Related Classes/Methods**:

- `Frameshift Effect Checker` (1:1)


### Untranslated Region (UTR) Effect Checker
Annotates variants located in the 5' and 3' untranslated regions (UTRs) of genes. While not directly coding for protein, UTRs play crucial roles in mRNA stability, translation efficiency, and localization, meaning variants here can still have significant regulatory effects.


**Related Classes/Methods**:

- `Untranslated Region (UTR) Effect Checker` (1:1)


### Intron Effect Checker
Identifies and describes variants located within intronic regions of genes. While many intronic variants are benign, some can affect splicing (e.g., by creating cryptic splice sites) or contain regulatory elements, making their annotation important for comprehensive analysis.


**Related Classes/Methods**:

- `Intron Effect Checker` (1:1)


### Promoter Effect Checker
Detects and characterizes variants in gene promoter regions. Promoters are critical regulatory sequences that control the initiation of gene transcription, so variants in these areas can significantly influence gene expression levels.


**Related Classes/Methods**:

- `Promoter Effect Checker` (1:1)


### Protein Change Calculator
Calculates and describes the specific amino acid alterations resulting from coding variants. This component translates the DNA-level changes into their precise protein-level consequences, providing the most direct functional impact.


**Related Classes/Methods**:

- `Protein Change Calculator` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)