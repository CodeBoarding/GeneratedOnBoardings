```mermaid
graph LR
    Dataloader["Dataloader"]
    _DataLoaderIter["_DataLoaderIter"]
    _stream_shuffle_data_generator["_stream_shuffle_data_generator"]
    Dataloader -- "delegates to" --> _DataLoaderIter
    _DataLoaderIter -- "retrieves data from" --> _stream_shuffle_data_generator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Dataloader` subsystem provides a robust mechanism for preparing graph datasets for model training. It exposes a `Dataloader` interface for users, which orchestrates the data pipeline by delegating to an internal `_DataLoaderIter`. The `_DataLoaderIter` is responsible for managing the iteration state and retrieving data from the `_stream_shuffle_data_generator`. The `_stream_shuffle_data_generator` is the central processing unit of this subsystem, encapsulating the logic for generating raw data samples, applying shuffling based on generated indices, and then forming these samples into optimized batches for efficient consumption by machine learning models. This design ensures that data is delivered in a randomized and batched format, crucial for effective model training, while abstracting the complexities of data handling from the user.

### Dataloader
The primary user-facing interface and orchestrator for loading, preprocessing, and batching graph datasets. It encapsulates the entire data preparation pipeline, providing the public API for data access.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PGL/blob/main/apps/Graph4Rec/env_run/src/datasets/dist_dataloader.py#L38-L130" target="_blank" rel="noopener noreferrer">`Dataloader`:38-130</a>


### _DataLoaderIter
An internal iterator class that manages the state and progression of data loading. It controls the flow of data through the pipeline, ensuring proper iteration control and resource management by interacting with the data generation pipeline.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PGL/blob/main/apps/Graph4Rec/env_run/src/datasets/dist_dataloader.py#L133-L242" target="_blank" rel="noopener noreferrer">`_DataLoaderIter`:133-242</a>


### _stream_shuffle_data_generator
The core internal data pipeline component responsible for generating raw data chunks, obtaining shuffled indices, performing in-memory shuffling of these chunks, and then aggregating them into batches. It ensures efficient, randomized, and memory-friendly data access for training. This component encapsulates the functionality previously attributed to `_data_generator`, `_stream_shuffle_index_generator`, and `_batch_data_generator` as distinct top-level components.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PGL/blob/main/apps/Graph4Rec/env_run/src/datasets/dist_dataloader.py#L184-L227" target="_blank" rel="noopener noreferrer">`_stream_shuffle_data_generator`:184-227</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)