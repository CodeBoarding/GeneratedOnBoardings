```mermaid
graph LR
    FeatureColumn["FeatureColumn"]
    FeatureGroup["FeatureGroup"]
    FeatureGroup -- "composes" --> FeatureColumn
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This section details the architecture of the Feature Engineering subsystem within the EasyRec project, focusing on its boundaries, central components, their responsibilities, and internal interactions.

### FeatureColumn
This component is the atomic unit responsible for defining, parsing, and transforming individual raw input features (e.g., ID, Tag, Raw, Expression, Combo, Lookup, Sequence) into numerical representations. It manages essential properties such as vocabulary size, hash bucket size, and embedding dimensions. FeatureColumn is also responsible for creating both wide and deep embedding columns, including handling shared embeddings, and determining if a feature is intended for the wide or deep part of a model (is_wide, is_deep). It serves as the primary interface for feature-level transformations.


**Related Classes/Methods**:

- <a href="https://github.com/alibaba/EasyRec/blob/master/easy_rec/python/feature_column/feature_column.py#L41-L664" target="_blank" rel="noopener noreferrer">`easy_rec.python.feature_column.feature_column.FeatureColumn`:41-664</a>


### FeatureGroup
This component acts as a logical container for grouping multiple FeatureColumn instances. It facilitates the organization and collective management of related features, which is particularly useful for defining specific input sets for different parts of a neural network (e.g., different towers in a multi-tower model). FeatureGroup simplifies configuration by automatically expanding feature names within the group, providing a higher-level abstraction for managing feature sets.


**Related Classes/Methods**:

- <a href="https://github.com/alibaba/EasyRec/blob/master/easy_rec/python/feature_column/feature_group.py#L9-L60" target="_blank" rel="noopener noreferrer">`easy_rec.python.feature_column.feature_group.FeatureGroup`:9-60</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)