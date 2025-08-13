```mermaid
graph LR
    Keras_Model["Keras Model"]
    tf_data_Dataset["tf.data Dataset"]
    AutoGraph_API["AutoGraph API"]
    Feature_Columns["Feature Columns"]
    Keras_Model -- "consumes data from" --> tf_data_Dataset
    Keras_Model -- "leverages" --> AutoGraph_API
    Keras_Model -- "integrates" --> Feature_Columns
    tf_data_Dataset -- "supplies data to" --> Keras_Model
    tf_data_Dataset -- "uses" --> AutoGraph_API
    tf_data_Dataset -- "consumes transformed data from" --> Feature_Columns
    AutoGraph_API -- "compiles logic for" --> Keras_Model
    AutoGraph_API -- "compiles functions for" --> tf_data_Dataset
    Feature_Columns -- "defines input for" --> Keras_Model
    Feature_Columns -- "integrates into pipelines for" --> tf_data_Dataset
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `User API Layer` serves as the primary interface for users to interact with TensorFlow, enabling them to define, train, and evaluate machine learning models, and manage data input pipelines. It provides high-level abstractions that simplify complex ML tasks.

### Keras Model
The core abstraction for defining, compiling, training, evaluating, and predicting with machine learning models. It encapsulates the model's architecture, optimization process, loss computation, and performance tracking, providing a high-level, user-friendly interface for model development.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/keras/engine/training.py" target="_blank" rel="noopener noreferrer">`tensorflow.python.keras.engine.training.Model.fit`</a>


### tf.data Dataset
Provides a robust API for constructing flexible and high-performance data input pipelines. It abstracts the complexities of data loading, preprocessing, and batching, enabling efficient data consumption by models and supporting various data sources and transformations.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/data/ops/dataset_ops.py" target="_blank" rel="noopener noreferrer">`tensorflow.python.data.ops.dataset_ops.Dataset.from_tensor_slices`</a>


### AutoGraph API
A utility that transforms standard imperative Python code into equivalent TensorFlow graph operations. This conversion enables significant performance benefits through graph-based optimizations, static analysis, and deployment to various TensorFlow runtimes, bridging the gap between Python's flexibility and TensorFlow's graph execution efficiency.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/autograph/impl/api.py#L493-L588" target="_blank" rel="noopener noreferrer">`tensorflow.python.autograph.impl.api.tf_convert`:493-588</a>


### Feature Columns
Offers a high-level abstraction to describe and transform input features, bridging the gap between raw data and the format expected by machine learning models. They are crucial for handling various data types (e.g., categorical, numerical, text) and applying transformations like embedding or one-hot encoding, simplifying data preparation for models.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/feature_column/feature_column_v2.py#L435-L515" target="_blank" rel="noopener noreferrer">`tensorflow.python.feature_column.feature_column_v2.embedding_column`:435-515</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)