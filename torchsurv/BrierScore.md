```mermaid
graph LR
    BrierScore_Metric_Component["BrierScore Metric Component"]
    Input_Validation_Utilities_Component["Input Validation Utilities Component"]
    BrierScore_Metric_Component -- "validates inputs using" --> Input_Validation_Utilities_Component
    click BrierScore_Metric_Component href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/BrierScore_Metric_Component.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

These two components are fundamental to the `BrierScore` subsystem. The `BrierScore Metric Component` is the core, encapsulating all logic for calculating, analyzing, and interpreting the time-dependent Brier Score, including complex statistical computations and advanced features. The `Input Validation Utilities Component` is critical for robustness and reliability, ensuring that the `BrierScore Metric Component` always operates on valid and correctly formatted data, preventing errors and guaranteeing accuracy and stability.

### BrierScore Metric Component [[Expand]](./BrierScore_Metric_Component.md)
This component is the central entity for calculating and statistically analyzing the time-dependent Brier Score. It provides a comprehensive set of functionalities, including the core Brier Score computation, handling of Inverse Probability of Censoring Weighting (IPCW) for censored data, and advanced statistical methods such as integrated Brier Score calculation, confidence interval estimation (parametric and bootstrap), p-value determination for hypothesis testing, and comparative analysis between different Brier Score instances. It maintains internal state related to the input data and computed scores for subsequent analysis.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/metrics/brier_score.py#L1-L1" target="_blank" rel="noopener noreferrer">`torchsurv.metrics.brier_score` (1:1)</a>


### Input Validation Utilities Component
This component provides a collection of general-purpose utility functions dedicated to validating the format, type, and constraints of input data across the `torchsurv` library, particularly for survival analysis metrics. Its role is to ensure that all incoming data, such as survival event indicators, time-to-event data, evaluation time points, and model estimates, adhere to the expected standards. This pre-computation validation is critical for preventing runtime errors, ensuring data integrity, and guaranteeing the reliability and accuracy of subsequent metric calculations.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L1-L1" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)