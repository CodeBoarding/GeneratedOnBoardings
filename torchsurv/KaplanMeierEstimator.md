```mermaid
graph LR
    KaplanMeierEstimator["KaplanMeierEstimator"]
    InputValidator["InputValidator"]
    KaplanMeierEstimator -- "invokes" --> InputValidator
    click KaplanMeierEstimator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/KaplanMeierEstimator.md" "Details"
    click InputValidator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/InputValidator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This subsystem focuses on performing Kaplan-Meier survival estimation, a fundamental statistical method in survival analysis. It is designed to be robust, handling data validation and core computations efficiently.

### KaplanMeierEstimator [[Expand]](./KaplanMeierEstimator.md)
This is the primary and central component of the subsystem. It orchestrates the entire Kaplan-Meier survival estimation process. It takes validated survival data as input, internally computes the necessary counts (individuals at risk, number of events), and then calculates the survival probabilities and their standard errors. It acts as the main interface for users to perform survival analysis.


**Related Classes/Methods**:

- `KaplanMeierEstimator:__call__` (0:0)
- `KaplanMeierEstimator:_compute_counts` (0:0)


### InputValidator [[Expand]](./InputValidator.md)
This component is responsible for ensuring the validity and correct format of the input survival data (event times and event indicators). It performs crucial checks such as data type validation, dimension consistency, and non-negativity, acting as a safeguard against malformed or incorrect data that could lead to errors in subsequent computations.


**Related Classes/Methods**:

- `validate_survival_data` (0:0)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)