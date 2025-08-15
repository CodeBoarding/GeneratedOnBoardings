```mermaid
graph LR
    Neighbors_Computation["Neighbors Computation"]
    Observation_Filtering["Observation Filtering"]
    Variable_Filtering["Variable Filtering"]
    Observation_Intersection["Observation Intersection"]
    L2_Normalization["L2 Normalization"]
    Generic_Attribute_Filtering["Generic Attribute Filtering"]
    Sparse_KNN_Search["Sparse KNN Search"]
    Observation_Intersection -- "calls" --> Observation_Filtering
    Observation_Filtering -- "delegates to" --> Generic_Attribute_Filtering
    Variable_Filtering -- "delegates to" --> Generic_Attribute_Filtering
    Neighbors_Computation -- "utilizes" --> Sparse_KNN_Search
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The muon._core.preproc subsystem provides a comprehensive set of preprocessing functionalities for single-cell omics data, primarily operating on AnnData and MuData objects.

### Neighbors Computation
Computes k-nearest neighbors (KNN) graphs.


**Related Classes/Methods**: _None_

### Observation Filtering
Filters observations from data objects based on criteria.


**Related Classes/Methods**: _None_

### Variable Filtering
Filters variables from data objects based on criteria.


**Related Classes/Methods**: _None_

### Observation Intersection
Identifies and retains common observations across different data modalities.


**Related Classes/Methods**: _None_

### L2 Normalization
Applies L2 normalization to data; Scales data vectors to unit length.


**Related Classes/Methods**: _None_

### Generic Attribute Filtering
A generalized internal mechanism that abstracts common filtering logic; Provides reusable filtering implementation for Observation Filtering and Variable Filtering.


**Related Classes/Methods**: _None_

### Sparse KNN Search
An optimized internal function for efficiently finding k-nearest neighbors in sparse matrix formats; Supports Neighbors Computation by providing efficient KNN search.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)