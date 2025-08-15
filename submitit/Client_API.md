```mermaid
graph LR
    Job_Submission_Facade["Job Submission Facade"]
    Auto_Executor["Auto-Executor"]
    Job_Submission_Facade -- "leverages" --> Auto_Executor
    Auto_Executor -- "provides to" --> Job_Submission_Facade
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Client API` subsystem serves as the primary public interface for users to define, configure, and submit computational jobs within the `submitit` library. It abstracts the complexities of backend executor selection and job submission, providing a simplified, high-level entry point for users.

### Job Submission Facade
This component provides the high-level public API for users to define and submit computational jobs. It includes methods like `submit`, `submit_array`, and `map_array`, acting as a simplified facade over the complex underlying job submission process. It is the primary entry point for users interacting with the `submitit` library.


**Related Classes/Methods**:

- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/core/core.py#L729-L738" target="_blank" rel="noopener noreferrer">`submitit.core.core.submit`:729-738</a>
- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/core/core.py#L774-L803" target="_blank" rel="noopener noreferrer">`submitit.core.core.submit_array`:774-803</a>
- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/core/core.py#L746-L772" target="_blank" rel="noopener noreferrer">`submitit.core.core.map_array`:746-772</a>
- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/core/core.py#L872-L915" target="_blank" rel="noopener noreferrer">`submitit.core.core._internal_process_submissions`:872-915</a>
- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/core/utils.py#L116-L165" target="_blank" rel="noopener noreferrer">`submitit.core.utils.DelayedSubmission`:116-165</a>


### Auto-Executor
This component is responsible for intelligently determining and selecting the most suitable execution backend (e.g., Slurm, Local, Debug) based on environmental factors or user configuration. It also handles the initialization and configuration of the chosen executor, ensuring that the correct backend is prepared for job execution.


**Related Classes/Methods**:

- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/auto/auto.py#L64-L89" target="_blank" rel="noopener noreferrer">`submitit.auto.auto.__init__`:64-89</a>
- <a href="https://github.com/facebookincubator/submitit/blob/main/submitit/auto/auto.py#L91-L100" target="_blank" rel="noopener noreferrer">`submitit.auto.auto.which`:91-100</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)