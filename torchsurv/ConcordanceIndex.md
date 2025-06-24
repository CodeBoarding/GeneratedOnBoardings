```mermaid
graph LR
    ConcordanceIndex_Calculator["ConcordanceIndex Calculator"]
    Input_Validator["Input Validator"]
    ConcordanceIndex_Calculator -- "uses" --> Input_Validator
    click ConcordanceIndex_Calculator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/ConcordanceIndex_Calculator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the `torchsurv` package focusing on the `ConcordanceIndex` subsystem, identifying core computational and input validation components and their relationship. The `ConcordanceIndex Calculator` is the central component for C-index computation, while the `Input Validator` ensures data quality and integrity for downstream calculations. This modularity enhances maintainability and testability.

### ConcordanceIndex Calculator [[Expand]](./ConcordanceIndex_Calculator.md)
This component is the core implementation for computing the Concordance Index (C-index), a key metric for evaluating survival models. It manages the intricate logic for identifying comparable pairs, handling tied event times and risk scores, and calculating the C-index estimate. Beyond the primary calculation, it provides robust statistical functionalities, including methods for estimating confidence intervals (using Noether, Bootstrap, and Conservative approaches), calculating p-values, and performing statistical comparisons between two C-index values. It maintains internal state related to the C-index calculation (e.g., `concordant`, `discordant`, `tied_risk`, `weight`).


**Related Classes/Methods**:

- `torchsurv.metrics.concordance.ConcordanceIndex` (1:100)


### Input Validator
This component provides essential utility functions dedicated to validating the format, data types, and logical consistency of input data used across the `torchsurv` library, particularly for survival analysis metrics. It ensures that survival data (event indicators and times) and model estimates adhere to expected structures and constraints (e.g., non-negative times, boolean events, correct tensor dimensions), thereby preventing common data-related errors and ensuring the reliability and stability of downstream computations.


**Related Classes/Methods**:

- `torchsurv.utils.validation.validate_inputs` (1:50)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)