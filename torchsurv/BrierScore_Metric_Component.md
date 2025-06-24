```mermaid
graph LR
    BrierScore_Metric_Component["BrierScore Metric Component"]
    Input_Validation_Component["Input Validation Component"]
    IPCW_Component["IPCW Component"]
    Kaplan_Meier_Estimator_Component["Kaplan-Meier Estimator Component"]
    BrierScore_Metric_Component -- "depends on" --> Input_Validation_Component
    BrierScore_Metric_Component -- "utilizes" --> IPCW_Component
    IPCW_Component -- "relies on" --> Kaplan_Meier_Estimator_Component
    click BrierScore_Metric_Component href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/BrierScore_Metric_Component.md" "Details"
    click Kaplan_Meier_Estimator_Component href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/Kaplan_Meier_Estimator_Component.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The BrierScore Metric Component is the cornerstone for calculating and statistically analyzing the time-dependent Brier Score within the torchsurv project. It provides a comprehensive suite of functionalities, including core Brier Score computation, handling of Inverse Probability of Censoring Weighting (IPCW) for censored data, and advanced statistical methods such as integrated Brier Score calculation, confidence interval estimation (parametric and bootstrap), p-value determination for hypothesis testing, and comparative analysis between different Brier Score instances. It maintains internal state related to the input data and computed scores for subsequent analysis.

### BrierScore Metric Component [[Expand]](./BrierScore_Metric_Component.md)
The primary component responsible for computing the time-dependent Brier Score, handling IPCW, and performing statistical analyses like integrated Brier Score, confidence intervals, and p-value calculations.


**Related Classes/Methods**:

- `BrierScore Metric Component` (1:1)


### Input Validation Component
Ensures the integrity and correctness of all input data (e.g., survival data, evaluation times, estimates) before any Brier Score calculations are performed, preventing erroneous results or runtime errors.


**Related Classes/Methods**:

- `Input Validation Component` (1:1)


### IPCW Component
Provides the Inverse Probability of Censoring Weighting (IPCW) mechanism, which is essential for accurately calculating the Brier Score in the presence of censored survival data.


**Related Classes/Methods**:

- `IPCW Component` (1:1)


### Kaplan-Meier Estimator Component [[Expand]](./Kaplan_Meier_Estimator_Component.md)
Implements the Kaplan-Meier estimator, a foundational method in survival analysis used to estimate the survival function. It is indirectly used by the IPCW component to estimate the censoring distribution.


**Related Classes/Methods**:

- `Kaplan-Meier Estimator Component` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)