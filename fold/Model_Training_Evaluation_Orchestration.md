```mermaid
graph LR
    Plan["Plan"]
    Optimizer_Builder["Optimizer Builder"]
    Data_Input_Pipeline_Manager["Data Input Pipeline Manager"]
    TensorFlow_Session_Supervisor["TensorFlow Session Supervisor"]
    Execution_Loop_Manager["Execution Loop Manager"]
    Batch_Preparer["Batch Preparer"]
    Metric_Evaluator["Metric Evaluator"]
    Summary_Generator["Summary Generator"]
    Plan -- "initializes and utilizes" --> Data_Input_Pipeline_Manager
    Plan -- "invokes" --> Optimizer_Builder
    Plan -- "interacts with" --> TensorFlow_Session_Supervisor
    Plan -- "triggers and oversees" --> Execution_Loop_Manager
    Metric_Evaluator -- "sends results to" --> Plan
    Summary_Generator -- "sends summaries to" --> Plan
    Data_Input_Pipeline_Manager -- "supplies data to" --> Batch_Preparer
    Execution_Loop_Manager -- "requests data from" --> Batch_Preparer
    Execution_Loop_Manager -- "feeds outputs to" --> Metric_Evaluator
    Execution_Loop_Manager -- "feeds outputs to" --> Summary_Generator
    Batch_Preparer -- "provides batches to" --> Execution_Loop_Manager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Model Training & Evaluation Orchestration` subsystem is responsible for managing the complete lifecycle of a Fold model, from setting up training loops and managing TensorFlow sessions to optimizing parameters and evaluating performance.

### Plan
The primary class that orchestrates the entire training and evaluation process, managing the end-to-end lifecycle, including setting up training loops, managing TensorFlow sessions, optimizing parameters, and evaluating model performance. It acts as the central coordinator.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.Plan`</a>


### Optimizer Builder
Functions responsible for configuring and instantiating TensorFlow optimizers, providing the necessary TensorFlow optimizer instances based on configuration.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L908-L914" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.build_optimizer`:908-914</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L137-L200" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.build_optimizer_from_params`:137-200</a>


### Data Input Pipeline Manager
Functions that set up the data input pipeline using Loom and TensorFlow queues, establishing and managing the efficient flow of structured data into the Fold model.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L1209-L1211" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.init_loom`:1209-1211</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L893-L899" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._create_queue`:893-899</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L858-L864" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._setup_dequeuing`:858-864</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L844-L856" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._setup_enqueuing`:844-856</a>


### TensorFlow Session Supervisor
The function that manages the TensorFlow session, including checkpointing and global step tracking, overseeing the TensorFlow session and handling model saving/restoring.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L665-L675" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.create_supervisor`:665-675</a>


### Execution Loop Manager
The core method that implements the iterative training or evaluation loop, running batches, and triggering parameter updates.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L1219-L1222" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._run`:1219-1222</a>


### Batch Preparer
Functions that transform raw input data into batched formats suitable for TensorFlow operations and construct the `feed_dict` required for TensorFlow session runs.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L1054-L1060" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.prepare_batches`:1054-1060</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L1066-L1073" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._by_input_tensor`:1066-1073</a>
- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py#L1052-L1064" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan._by_feed_dict`:1052-1064</a>


### Metric Evaluator
Functions responsible for calculating and updating various performance metrics (e.g., accuracy, loss) based on the model's outputs.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/metrics.py#L91-L104" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.metrics._update_input_type`:91-104</a>


### Summary Generator
The function that generates TensorFlow summaries for visualization tools like TensorBoard, creating summaries for visualizing training progress and model performance over time.


**Related Classes/Methods**:

- <a href="https://github.com/tensorflow/fold/blob/master/tensorflow_fold/blocks/plan.py" target="_blank" rel="noopener noreferrer">`tensorflow_fold.blocks.plan.compute_summaries`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)