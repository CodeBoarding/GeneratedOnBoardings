```mermaid
graph LR
    SurvivalDataValidator["SurvivalDataValidator"]
    EvaluationTimeValidator["EvaluationTimeValidator"]
    PredictionValidator["PredictionValidator"]
    SurvivalDataValidator -- "validates" --> Loss_Functions
    SurvivalDataValidator -- "validates" --> Metrics
    EvaluationTimeValidator -- "validates" --> Metrics
    EvaluationTimeValidator -- "validates" --> Statistics
    PredictionValidator -- "validates" --> Loss_Functions
    PredictionValidator -- "validates" --> Metrics
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This component is a utility responsible for rigorously validating various input data types, including survival event indicators, event/censoring times, evaluation time points, and model predictions. Its primary purpose is to ensure data integrity and adherence to expected formats and constraints (e.g., data types, dimensions, value ranges), thereby preventing errors and ensuring the robust and reliable operation of survival metric calculations and model training processes within the torchsurv library.

### SurvivalDataValidator
This component is responsible for validating the core survival data, specifically the event times and event indicators. It ensures that these inputs are correctly formatted (e.g., as PyTorch tensors), have appropriate data types (e.g., float for times, boolean/integer for indicators), and adhere to logical constraints (e.g., event times are non-negative).


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L3-L37" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs.validate_survival_data` (3:37)</a>


### EvaluationTimeValidator
This component focuses on validating the time points at which survival metrics or predictions are to be evaluated. It checks for correct data types, tensor format, and logical consistency of these time points.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L40-L83" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs.validate_evaluation_time` (40:83)</a>


### PredictionValidator
This component is dedicated to validating the model's output predictions, such as survival probabilities or hazard functions. It verifies the format, data type, and dimensions of these predictions to ensure they are suitable for subsequent calculations (e.g., loss computation, metric evaluation).


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L86-L120" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs.validate_estimate` (86:120)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)