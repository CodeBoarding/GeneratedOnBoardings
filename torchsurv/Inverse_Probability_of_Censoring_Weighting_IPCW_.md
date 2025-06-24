```mermaid
graph LR
    Inverse_Probability_of_Censoring_Weighting_IPCW_["Inverse Probability of Censoring Weighting (IPCW)"]
    get_ipcw["get_ipcw"]
    _inverse_censoring_dist["_inverse_censoring_dist"]
    KaplanMeierEstimator["KaplanMeierEstimator"]
    validate_inputs_validate_survival_data["validate_inputs.validate_survival_data"]
    get_ipcw -- "calls" --> validate_inputs_validate_survival_data
    get_ipcw -- "initializes" --> KaplanMeierEstimator
    get_ipcw -- "calls" --> _inverse_censoring_dist
    _inverse_censoring_dist -- "is called by" --> get_ipcw
    KaplanMeierEstimator -- "is initialized by" --> get_ipcw
    KaplanMeierEstimator -- "is used by" --> get_ipcw
    click Inverse_Probability_of_Censoring_Weighting_IPCW_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/Inverse_Probability_of_Censoring_Weighting_IPCW_.md" "Details"
    click get_ipcw href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/get_ipcw.md" "Details"
    click KaplanMeierEstimator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/KaplanMeierEstimator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Given the previous analysis and the limited information from `getClassHierarchy`, I will proceed with the following components, focusing on their functional roles and interactions as identified in the initial analysis. The components chosen are fundamental because they directly contribute to the core functionality of IPCW calculation or are essential for data preparation and statistical modeling within this context.

### Inverse Probability of Censoring Weighting (IPCW) [[Expand]](./Inverse_Probability_of_Censoring_Weighting_IPCW_.md)
This is the overarching component responsible for providing the Inverse Probability of Censoring Weighting functionality. It orchestrates the use of other sub-components to achieve its goal of adjusting for censoring in survival analysis.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/ipcw.py#L1-L1" target="_blank" rel="noopener noreferrer">`torchsurv.stats.ipcw` (1:1)</a>


### get_ipcw [[Expand]](./get_ipcw.md)
This is the primary public function within the IPCW component. It calculates the inverse probability censoring weights. It acts as the entry point for users to compute IPCW, coordinating the validation of inputs, fitting the censoring model, and calculating the inverse censoring distribution.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/ipcw.py#L11-L76" target="_blank" rel="noopener noreferrer">`torchsurv.stats.ipcw:get_ipcw` (11:76)</a>


### _inverse_censoring_dist
This is an internal helper function, crucial for the `get_ipcw` function. Its sole responsibility is to compute the inverse of the censoring distribution, which is a core mathematical step in deriving the IPCW. It encapsulates the specific logic for this calculation.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/ipcw.py#L79-L103" target="_blank" rel="noopener noreferrer">`torchsurv.stats.ipcw:_inverse_censoring_dist` (79:103)</a>


### KaplanMeierEstimator [[Expand]](./KaplanMeierEstimator.md)
This component, residing in the `kaplan_meier` module, is a fundamental external dependency. It's responsible for fitting the Kaplan-Meier censoring estimator, which is essential for modeling the censoring distribution. The IPCW calculation relies heavily on an accurate estimation of this distribution.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/kaplan_meier.py#L9-L252" target="_blank" rel="noopener noreferrer">`torchsurv.stats.kaplan_meier.KaplanMeierEstimator` (9:252)</a>


### validate_inputs.validate_survival_data
This component is responsible for ensuring the integrity and correctness of the input survival data (`event` and `time` tensors). It acts as a gatekeeper, preventing erroneous calculations by validating the data format and types before they are used in the IPCW computation.


**Related Classes/Methods**:

- `torchsurv.utils.validate_inputs.validate_survival_data` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)