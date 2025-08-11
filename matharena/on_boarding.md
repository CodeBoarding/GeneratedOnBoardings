```mermaid
graph LR
    Configuration_Management["Configuration Management"]
    LLM_Interaction_Execution["LLM Interaction & Execution"]
    Core_Evaluation_Engine["Core Evaluation Engine"]
    Data_Processing_Grading["Data Processing & Grading"]
    Data_Reporting_Tools["Data & Reporting Tools"]
    Core_Evaluation_Engine -- "loads settings from" --> Configuration_Management
    Core_Evaluation_Engine -- "initiates queries to" --> LLM_Interaction_Execution
    Core_Evaluation_Engine -- "exchanges data with" --> Data_Processing_Grading
    Data_Reporting_Tools -- "prepares input for" --> Core_Evaluation_Engine
    Data_Reporting_Tools -- "consumes evaluation results from" --> Core_Evaluation_Engine
    Data_Reporting_Tools -- "consumes grading results from" --> Data_Processing_Grading
    click LLM_Interaction_Execution href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/matharena/LLM_Interaction_Execution.md" "Details"
    click Core_Evaluation_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/matharena/Core_Evaluation_Engine.md" "Details"
    click Data_Processing_Grading href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/matharena/Data_Processing_Grading.md" "Details"
    click Data_Reporting_Tools href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/matharena/Data_Reporting_Tools.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The MathArena project is designed to evaluate Large Language Models (LLMs) on mathematical problems. The core flow involves loading configurations, running evaluation tasks, interacting with LLMs, processing their outputs, and generating reports.

### Configuration Management
Manages the loading, parsing, and validation of all system configurations, including LLM model parameters, competition details, and evaluation settings.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/configs.py" target="_blank" rel="noopener noreferrer">`src/matharena/configs.py`</a>


### LLM Interaction & Execution [[Expand]](./LLM_Interaction_Execution.md)
Provides a unified interface for interacting with various Large Language Model APIs and offers a secure sandbox for executing LLM-generated code.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/api.py" target="_blank" rel="noopener noreferrer">`src/matharena/api.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/code_execution.py" target="_blank" rel="noopener noreferrer">`src.matharena.code_execution.py`</a>


### Core Evaluation Engine [[Expand]](./Core_Evaluation_Engine.md)
The central orchestrator of the evaluation workflow, managing problem loading, initiating LLM queries, coordinating output processing, and implementing advanced prompting strategies like Chain-of-Thought.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/runner.py" target="_blank" rel="noopener noreferrer">`src/matharena/runner.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/cot_solver.py" target="_blank" rel="noopener noreferrer">`src/matharena/cot_solver.py`</a>


### Data Processing & Grading [[Expand]](./Data_Processing_Grading.md)
Extracts, normalizes, and validates answers from diverse LLM output formats, then performs automated scoring against ground truth or predefined criteria.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/parser.py" target="_blank" rel="noopener noreferrer">`src/matharena/parser.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/src/matharena/grader.py" target="_blank" rel="noopener noreferrer">`src/matharena/grader.py`</a>


### Data & Reporting Tools [[Expand]](./Data_Reporting_Tools.md)
A suite of scripts and utilities for preparing and managing competition data, as well as for post-evaluation analysis, statistical reporting, and visualization of results.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/curation/judge_parser.py" target="_blank" rel="noopener noreferrer">`scripts/curation/judge_parser.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/curation/upload_competition.py" target="_blank" rel="noopener noreferrer">`scripts/curation/upload_competition.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/app.py" target="_blank" rel="noopener noreferrer">`scripts/app.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/extraction/leaderboard.py" target="_blank" rel="noopener noreferrer">`scripts/extraction/leaderboard.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/extraction/type_scoring.py" target="_blank" rel="noopener noreferrer">`scripts/extraction/type_scoring.py`</a>
- <a href="https://github.com/eth-sri/matharena/blob/main/scripts/extraction/comparison.py" target="_blank" rel="noopener noreferrer">`scripts/extraction/comparison.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)