## GPF Instance & Configuration Overview

This section provides an overview of the GPF Instance and its configuration, detailing the main components involved and their interactions.

### Data Flow Diagram

```mermaid
graph LR
    A[GPFInstance] -- loads config from --> B(GPFConfigParser)
    A -- uses --> C(VariantsDb)
    A -- uses --> D(PhenoRegistry)
    A -- uses --> E(GeneScoresDb)
    A -- uses --> F(CommonReport)
    A -- uses --> G(GeneProfileDB)
    A -- uses --> H(DenovoGeneSetsDb)
    A -- uses --> I(GeneSetsDb)
    A -- uses --> J(GenomicResourceRepository)
    J -- provides --> K(ReferenceGenome)
    J -- provides --> L(GeneModels)
    A -- uses --> M(PhenotypeStorageRegistry)
    A -- uses --> N(GenotypeStorageRegistry)











































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































































