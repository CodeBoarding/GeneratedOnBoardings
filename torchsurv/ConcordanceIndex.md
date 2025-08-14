```mermaid
graph LR
    ConcordanceIndex_Calculator["ConcordanceIndex Calculator"]
    Input_Validator["Input Validator"]
    IPCW_Calculator["IPCW Calculator"]
    ConcordanceIndex_Calculator -- "uses" --> Input_Validator
    ConcordanceIndex_Calculator -- "uses" --> IPCW_Calculator
    click ConcordanceIndex_Calculator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/ConcordanceIndex_Calculator.md" "Details"
    click IPCW_Calculator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/IPCW_Calculator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Component Overview for `ConcordanceIndex` Subsystem

### ConcordanceIndex Calculator [[Expand]](./ConcordanceIndex_Calculator.md)
This is the central component responsible for computing the Concordance Index (C-index). It handles the core logic for calculating concordance, discordance, and tied pairs, incorporating Inverse Probability of Censoring Weighting (IPCW) if provided. Beyond basic C-index computation, it offers robust statistical functionalities, including calculating confidence intervals (using Noether, Conservative, or Bootstrap methods), p-values for hypothesis testing (against a null of 0.5), and comparative analysis between two C-index values.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/metrics/cindex.py#L12-L910" target="_blank" rel="noopener noreferrer">`torchsurv.metrics.cindex.ConcordanceIndex` (12:910)</a>


### Input Validator
This component ensures the integrity and correctness of input data (event status, time-to-event, and risk estimates) before they are processed by the ConcordanceIndex Calculator. It performs checks on data types, shapes, and values to prevent computational errors and ensure reliable C-index calculations.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L3-L37" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs.validate_survival_data` (3:37)</a>
- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/tools/validate_inputs.py#L86-L120" target="_blank" rel="noopener noreferrer">`torchsurv.tools.validate_inputs.validate_estimate` (86:120)</a>


### IPCW Calculator [[Expand]](./IPCW_Calculator.md)
This component is responsible for calculating Inverse Probability of Censoring Weights (IPCW). These weights are crucial for adjusting the C-index calculation in the presence of censored data, as recommended by Uno et al. (2011), to provide a more robust and unbiased estimate of the concordance index.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/ipcw.py#L11-L76" target="_blank" rel="noopener noreferrer">`torchsurv.stats.ipcw.get_ipcw` (11:76)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)