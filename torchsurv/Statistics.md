```mermaid
graph LR
    Statistics["Statistics"]
    Metrics -- "leverages" --> Statistics
    click Statistics href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsurv/Statistics.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Statistics` component is chosen as a core component because it encapsulates essential statistical methodologies unique to survival analysis. Survival data, characterized by time-to-event outcomes and censoring, cannot be adequately analyzed with standard statistical tools. Therefore, specialized methods like Kaplan-Meier estimation and IPCW are fundamental. Kaplan-Meier is a cornerstone for non-parametric estimation of survival functions, providing a visual and quantitative understanding of survival probabilities over time. IPCW is vital for handling censored data in a statistically sound manner, allowing for unbiased estimation of various quantities. The `Statistics` component is fundamental because it provides the specialized statistical tools necessary to correctly interpret and analyze survival data, forming the basis for both data understanding and robust model evaluation within the `torchsurv` framework. Its interaction with the `Metrics` component highlights its role as an underlying statistical engine for performance assessment.

### Statistics [[Expand]](./Statistics.md)
This component provides fundamental statistical utilities for survival analysis. It includes methods for non-parametric estimation of survival curves, such as the Kaplan-Meier estimator, and techniques for handling censored data, specifically Inverse Probability of Censoring Weighting (IPCW). These utilities are crucial for data preparation, exploratory data analysis, and serve as foundational elements for more advanced model evaluation procedures within the `torchsurv` library, providing the necessary statistical backbone for handling survival data.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/ipcw.py#L1-L99999" target="_blank" rel="noopener noreferrer">`torchsurv.stats.ipcw` (1:99999)</a>
- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/stats/kaplan_meier.py#L1-L99999" target="_blank" rel="noopener noreferrer">`torchsurv.stats.kaplan_meier` (1:99999)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)