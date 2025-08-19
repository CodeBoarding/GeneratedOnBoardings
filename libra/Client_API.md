```mermaid
graph LR
    libra_queries["libra.queries"]
    libra_queries_predict["libra.queries.predict"]
    libra_queries_interpret["libra.queries.interpret"]
    libra_queries_tune["libra.queries.tune"]
    libra_queries_neural_network_query["libra.queries.neural_network_query"]
    libra_queries_get_models["libra.queries.get_models"]
    libra_queries_plots["libra.queries.plots"]
    libra_queries_model["libra.queries.model"]
    libra_queries_clearLog["libra.queries.clearLog"]
    libra_queries_logger["libra.queries.logger"]
    libra_queries_classification_query_ann["libra.queries.classification_query_ann"]
    libra_queries_regression_query_ann["libra.queries.regression_query_ann"]
    libra_queries -- "dispatches to" --> libra_queries_predict
    libra_queries -- "dispatches to" --> libra_queries_interpret
    libra_queries -- "dispatches to" --> libra_queries_tune
    libra_queries -- "dispatches to" --> libra_queries_neural_network_query
    libra_queries -- "dispatches to" --> libra_queries_get_models
    libra_queries -- "dispatches to" --> libra_queries_plots
    libra_queries -- "dispatches to" --> libra_queries_model
    libra_queries -- "initializes with" --> libra_queries_clearLog
    libra_queries -- "initializes with" --> libra_queries_logger
    libra_queries_predict -- "triggers" --> libra_queries_interpret
    libra_queries_neural_network_query -- "dispatches to" --> libra_queries_classification_query_ann
    libra_queries_neural_network_query -- "dispatches to" --> libra_queries_regression_query_ann
    libra_queries_get_models -- "logs via" --> libra_queries_logger
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Client API` subsystem, primarily encapsulated within `libra.queries`, serves as the user's main interaction point with the ML library. It embodies the Facade Pattern, simplifying complex underlying ML operations.

### libra.queries
The primary user-facing component, providing a high-level abstraction for interacting with the ML library. It acts as the central orchestrator, receiving user queries, managing the overall workflow, and presenting results.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py" target="_blank" rel="noopener noreferrer">`libra.queries`</a>


### libra.queries.predict
Handles user requests for making predictions using trained models, serving as a core ML inference capability.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L150-L170" target="_blank" rel="noopener noreferrer">`libra.queries.predict`:150-170</a>


### libra.queries.interpret
Provides functionalities to explain model predictions or internal workings, enhancing model transparency.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L172-L184" target="_blank" rel="noopener noreferrer">`libra.queries.interpret`:172-184</a>


### libra.queries.tune
Manages the process of optimizing model hyperparameters to improve performance.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L670-L742" target="_blank" rel="noopener noreferrer">`libra.queries.tune`:670-742</a>


### libra.queries.neural_network_query
Acts as a specialized facade for neural network-related queries, abstracting specific ANN implementations.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L188-L255" target="_blank" rel="noopener noreferrer">`libra.queries.neural_network_query`:188-255</a>


### libra.queries.get_models
Provides functionality to retrieve a list of available models within the library, enabling users to discover and select models.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L129-L137" target="_blank" rel="noopener noreferrer">`libra.queries.get_models`:129-137</a>


### libra.queries.plots
Offers functionalities for generating visualizations and reports based on model results or data, aiding in analysis and presentation.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L1218-L1228" target="_blank" rel="noopener noreferrer">`libra.queries.plots`:1218-1228</a>


### libra.queries.model
Provides a general interface for interacting with various ML models, likely for loading, saving, or querying model metadata.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py" target="_blank" rel="noopener noreferrer">`libra.queries.model`</a>


### libra.queries.clearLog
Utility for clearing logs.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L48-L54" target="_blank" rel="noopener noreferrer">`libra.queries.clearLog`:48-54</a>


### libra.queries.logger
Utility for logging information.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L57-L79" target="_blank" rel="noopener noreferrer">`libra.queries.logger`:57-79</a>


### libra.queries.classification_query_ann
Specific ANN implementation for classification queries.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L321-L378" target="_blank" rel="noopener noreferrer">`libra.queries.classification_query_ann`:321-378</a>


### libra.queries.regression_query_ann
Specific ANN implementation for regression queries.


**Related Classes/Methods**:

- <a href="https://github.com/Palashio/libra/blob/master/libra/queries.py#L259-L316" target="_blank" rel="noopener noreferrer">`libra.queries.regression_query_ann`:259-316</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)