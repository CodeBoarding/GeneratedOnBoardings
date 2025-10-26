```mermaid
graph LR
    DataSplitManager["DataSplitManager"]
    TaskDataLoader["TaskDataLoader"]
    PromptGenerator["PromptGenerator"]
    DataSplitManager -- "establishes data organization for" --> TaskDataLoader
    TaskDataLoader -- "provides pre-processed data to" --> PromptGenerator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `lighteval` data processing subsystem is designed around a clear, sequential flow, ensuring efficient and structured preparation of evaluation data for Language Model (LLM) inference. It begins with the `DataSplitManager`, which intelligently partitions and sorts raw data requests to optimize batching and processing. This organized data is then handed off to the `TaskDataLoader`, a crucial component responsible for acquiring, cleaning, and enriching task-specific datasets, including the generation of few-shot examples. The final stage involves the `PromptGenerator`, which leverages the prepared data and few-shot examples to dynamically construct and format prompts suitable for various LLM architectures and evaluation scenarios. This architecture emphasizes modularity and a clear separation of concerns, facilitating robust data handling and flexible prompt generation within the evaluation framework.

### DataSplitManager
This component is foundational for data handling within the evaluation framework. It initializes and manages data split limits (e.g., train, validation, test sets) and defines the criteria for sorting and organizing data within these splits. It ensures that raw data is structurally prepared and partitioned correctly for subsequent processing, aligning with the "Data Handlers" pattern.


**Related Classes/Methods**:

- <a href="https://github.com/huggingface/lighteval/blob/main/src/lighteval/data.py#L44-L164" target="_blank" rel="noopener noreferrer">`lighteval.data.DynamicBatchDataset`:44-164</a>


### TaskDataLoader
As the primary interface for data acquisition and pre-processing, this component is responsible for fetching datasets specific to evaluation tasks. It handles initial data cleaning, de-duplication, and the preparation of few-shot examples. This component directly implements the "Data Handlers" aspect, focusing on getting raw data into a usable state for evaluation.


**Related Classes/Methods**:

- <a href="https://github.com/huggingface/lighteval/blob/main/src/lighteval/tasks/lighteval_task.py#L147-L388" target="_blank" rel="noopener noreferrer">`lighteval.tasks.lighteval_task.LightevalTask`:147-388</a>


### PromptGenerator
This component is central to constructing the final prompts that will be fed to LLMs. It integrates task-specific data with sampled few-shot examples, supporting various prompt formats (e.g., chat, plain text) and managing different few-shot sampling strategies. It translates the prepared data and task requirements into model-consumable prompts, directly supporting the "Task Definitions" pattern.


**Related Classes/Methods**:

- <a href="https://github.com/huggingface/lighteval/blob/main/src/lighteval/tasks/prompt_manager.py#L42-L160" target="_blank" rel="noopener noreferrer">`lighteval.tasks.prompt_manager.PromptManager`:42-160</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)