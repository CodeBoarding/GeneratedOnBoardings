```mermaid
graph LR
    WDAE_Application["WDAE Application"]
    GPF_Instance_View["GPF Instance View"]
    Users_API["Users API"]
    Datasets_API["Datasets API"]
    Genotype_Browser_API["Genotype Browser API"]
    Pheno_Browser_API["Pheno Browser API"]
    Enrichment_API["Enrichment API"]
    Gene_Profiles_API["Gene Profiles API"]
    Gene_Sets_API["Gene Sets API"]
    Common_Reports_API["Common Reports API"]
    Family_API["Family API"]
    Gene_Scores_API["Gene Scores API"]
    Genomic_Scores_API["Genomic Scores API"]
    Groups_API["Groups API"]
    Measures_API["Measures API"]
    Person_Sets_API["Person Sets API"]
    Pheno_Tool_API["Pheno Tool API"]
    Query_State_Save_API["Query State Save API"]
    User_Queries_API["User Queries API"]
    WDAE_Application -- "includes URLs from" --> Datasets_API
    WDAE_Application -- "includes URLs from" --> Users_API
    WDAE_Application -- "includes URLs from" --> Genotype_Browser_API
    WDAE_Application -- "includes URLs from" --> Enrichment_API
    WDAE_Application -- "includes URLs from" --> Gene_Profiles_API
    WDAE_Application -- "includes URLs from" --> Pheno_Browser_API
    WDAE_Application -- "includes URLs from" --> Gene_Sets_API
    WDAE_Application -- "includes URLs from" --> Common_Reports_API
    WDAE_Application -- "includes URLs from" --> Family_API
    WDAE_Application -- "includes URLs from" --> Gene_Scores_API
    WDAE_Application -- "includes URLs from" --> Genomic_Scores_API
    WDAE_Application -- "includes URLs from" --> Groups_API
    WDAE_Application -- "includes URLs from" --> Measures_API
    WDAE_Application -- "includes URLs from" --> Person_Sets_API
    WDAE_Application -- "includes URLs from" --> Pheno_Tool_API
    WDAE_Application -- "includes URLs from" --> Query_State_Save_API
    WDAE_Application -- "includes URLs from" --> User_Queries_API
    Users_API -- "access data through" --> GPF_Instance_View
    Datasets_API -- "access data through" --> GPF_Instance_View
    Genotype_Browser_API -- "access data through" --> GPF_Instance_View
    Pheno_Browser_API -- "access data through" --> GPF_Instance_View
    Enrichment_API -- "access data through" --> GPF_Instance_View
    Gene_Profiles_API -- "access data through" --> GPF_Instance_View
    Gene_Sets_API -- "access data through" --> GPF_Instance_View
    Common_Reports_API -- "access data through" --> GPF_Instance_View
    Family_API -- "access data through" --> GPF_Instance_View
    Gene_Scores_API -- "access data through" --> GPF_Instance_View
    Genomic_Scores_API -- "access data through" --> GPF_Instance_View
    Groups_API -- "access data through" --> GPF_Instance_View
    Measures_API -- "access data through" --> GPF_Instance_View
    Person_Sets_API -- "access data through" --> GPF_Instance_View
    Pheno_Tool_API -- "access data through" --> GPF_Instance_View
    Query_State_Save_API -- "access data through" --> GPF_Instance_View
    User_Queries_API -- "access data through" --> GPF_Instance_View
    Users_API -- "provides authentication for" --> Datasets_API
    Users_API -- "provides authentication for" --> Genotype_Browser_API
    Users_API -- "provides authentication for" --> Pheno_Browser_API
    Users_API -- "provides authentication for" --> Enrichment_API
    Users_API -- "provides authentication for" --> Gene_Profiles_API
    Users_API -- "provides authentication for" --> Gene_Sets_API
    Users_API -- "provides authentication for" --> Common_Reports_API
    Users_API -- "provides authentication for" --> Family_API
    Users_API -- "provides authentication for" --> Gene_Scores_API
    Users_API -- "provides authentication for" --> Genomic_Scores_API
    Users_API -- "provides authentication for" --> Groups_API
    Users_API -- "provides authentication for" --> Measures_API
    Users_API -- "provides authentication for" --> Person_Sets_API
    Users_API -- "provides authentication for" --> Pheno_Tool_API
    Users_API -- "provides authentication for" --> Query_State_Save_API
    Users_API -- "provides authentication for" --> User_Queries_API
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

An analysis of the `gpf/wdae` subsystem reveals a modular architecture built around a central Django application that integrates multiple specialized APIs to provide a comprehensive web-based interface for genomic data analysis.

### WDAE Application
The core Django project that orchestrates the web application. It defines global settings, includes URL configurations from all other API components, and serves as the main container for the system.


**Related Classes/Methods**:

- `gpf.wdae.wdae.urls` (1:1)
- `gpf.wdae.wdae.settings` (1:1)


### GPF Instance View
A critical bridge component that initializes and provides a singleton `GPFInstance` object. This object is the main entry point for all data queries and interactions with the GPF core engine.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gpf_instance/gpf_instance.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gpf_instance.gpf_instance` (1:1)</a>


### Users API
Manages user accounts, groups, and permissions. It handles authentication (login, registration) and authorization, which are cross-cutting concerns applied across other APIs to secure access to data and features.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/users_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.users_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/users_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.users_api.urls` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/utils/authentication.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.utils.authentication` (1:1)</a>


### Datasets API
Exposes REST endpoints for browsing and managing genomic datasets, including metadata, access permissions, and hierarchies.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/datasets_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.datasets_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/datasets_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.datasets_api.urls` (1:1)</a>


### Genotype Browser API
Provides the backend for querying genetic variants. It supports complex filtering based on genomic location, variant properties, and family structure.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/genotype_browser/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.genotype_browser.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/genotype_browser/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.genotype_browser.urls` (1:1)</a>


### Pheno Browser API
Provides REST access to phenotype data, allowing users to browse, filter, and query observable traits associated with individuals.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/pheno_browser_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.pheno_browser_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/pheno_browser_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.pheno_browser_api.urls` (1:1)</a>


### Enrichment API
Supports gene enrichment analysis by providing endpoints to perform and retrieve statistical enrichment tests on gene sets.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/enrichment_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.enrichment_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/enrichment_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.enrichment_api.urls` (1:1)</a>


### Gene Profiles API
Provides REST endpoints for retrieving detailed gene-related information, such as gene scores and expression data.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_profiles_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_profiles_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_profiles_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_profiles_api.urls` (1:1)</a>


### Gene Sets API
Manages collections of genes (gene sets) that can be used in various analyses. It provides endpoints for creating, querying, and managing these sets.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_sets/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_sets.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_sets/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_sets.urls` (1:1)</a>


### Common Reports API
Generates and provides access to common study reports, such as study statistics and variant distributions.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/common_reports_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.common_reports_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/common_reports_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.common_reports_api.urls` (1:1)</a>


### Family API
Exposes endpoints for querying and retrieving data about families within the loaded studies.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/family_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.family_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/family_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.family_api.urls` (1:1)</a>


### Gene Scores API
Provides access to precomputed gene scores (e.g., RVIS, LGD) that can be used for filtering and analysis.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_scores/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_scores.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/gene_scores/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.gene_scores.urls` (1:1)</a>


### Genomic Scores API
Exposes endpoints for accessing genomic scores, which are annotations for specific genomic positions (e.g., conservation scores).


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/genomic_scores_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.genomic_scores_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/genomic_scores_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.genomic_scores_api.urls` (1:1)</a>


### Groups API
Manages user-defined groups and their associated metadata.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/groups_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.groups_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/groups_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.groups_api.urls` (1:1)</a>


### Measures API
Provides access to phenotype measures available in the loaded datasets.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/measures_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.measures_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/measures_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.measures_api.urls` (1:1)</a>


### Person Sets API
Manages collections of individuals (person sets) for use in targeted queries and analyses.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/person_sets_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.person_sets_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/person_sets_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.person_sets_api.urls` (1:1)</a>


### Pheno Tool API
Provides backend support for the interactive pheno tool, which allows for building and testing complex phenotype queries.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/pheno_tool_api/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.pheno_tool_api.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/pheno_tool_api/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.pheno_tool_api.urls` (1:1)</a>


### Query State Save API
Allows users to save and restore the state of their queries, enabling them to resume work later.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/query_state_save/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.query_state_save.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/query_state_save/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.query_state_save.urls` (1:1)</a>


### User Queries API
Manages and stores user-defined queries for reuse.


**Related Classes/Methods**:

- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/user_queries/views.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.user_queries.views` (1:1)</a>
- <a href="https://github.com/iossifovlab/gpf/blob/master/wdae/wdae/user_queries/urls.py#L1-L1" target="_blank" rel="noopener noreferrer">`gpf.wdae.wdae.user_queries.urls` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)