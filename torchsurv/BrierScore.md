```mermaid
graph LR
    Brier_Score_Metric_Core["Brier Score Metric Core"]
    Input_Validation_Utilities["Input Validation Utilities"]
    Brier_Score_Metric_Core -- "uses" --> Input_Validation_Utilities
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the `torchsurv` package focusing on the `BrierScore` class, identifying core metric calculation and input validation as key components and their interdependencies.

### Brier Score Metric Core
This is the central component responsible for the comprehensive calculation, integration, and statistical analysis of the time-dependent Brier Score. It encapsulates the logic for computing the Brier Score, its integral (Integrated Brier Score), and performing various statistical inferences such as confidence interval estimation, p-value calculation for hypothesis testing, and comparisons between different Brier Score instances. It supports both parametric and bootstrap statistical methods and can account for censoring through Inverse Probability of Censoring Weighting (IPCW).


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/metrics/brier_score.py#L10-L903" target="_blank" rel="noopener noreferrer">`BrierScore` (10:903)</a>
- `BrierScore.__call__` (1:1)
- `BrierScore.integral` (1:1)
- `BrierScore.confidence_interval` (1:1)
- `BrierScore.p_value` (1:1)
- `BrierScore.compare` (1:1)
- `_brier_score_se` (1:1)
- `_confidence_interval_parametric` (1:1)
- `_confidence_interval_bootstrap` (1:1)
- `_p_value_parametric` (1:1)
- `_p_value_bootstrap` (1:1)
- `_compare_parametric` (1:1)
- `_compare_bootstrap` (1:1)
- `_bootstrap_brier_score` (1:1)
- `_find_torch_unique_indices` (1:1)
- `_validate_brier_score_inputs` (1:1)
- `_update_brier_score_new_time` (1:1)
- `_update_brier_score_weight` (1:1)


### Input Validation Utilities
This component provides a set of robust utility functions dedicated to validating the format, type, and constraints of input data used across the `torchsurv` library, specifically for survival analysis metrics. It ensures that survival data (event, time), evaluation times, and model estimates conform to expected standards, thereby preventing runtime errors and ensuring the reliability and correctness of subsequent calculations within the `Brier Score Metric Core`.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L3-L37" target="_blank" rel="noopener noreferrer">`validate_inputs.validate_survival_data` (3:37)</a>
- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L40-L83" target="_blank" rel="noopener noreferrer">`validate_inputs.validate_evaluation_time` (40:83)</a>
- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L86-L120" target="_blank" rel="noopener noreferrer">`validate_inputs.validate_estimate` (86:120)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)