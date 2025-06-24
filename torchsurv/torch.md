```mermaid
graph LR
    Momentum_Loss_Module["Momentum Loss Module"]
    Cox_Proportional_Hazards_Loss["Cox Proportional Hazards Loss"]
    Weibull_Accelerated_Failure_Time_Loss["Weibull Accelerated Failure Time Loss"]
    Momentum_Loss_Module -- "uses" --> Cox_Proportional_Hazards_Loss
    Momentum_Loss_Module -- "uses" --> Weibull_Accelerated_Failure_Time_Loss
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The torchsurv.loss subsystem is a critical part of the torchsurv project, focusing on providing various loss functions essential for training survival analysis models. It encompasses standard loss functions for common survival models and an advanced training module that enhances learning stability and performance.

### Momentum Loss Module
This module implements a momentum-based learning framework for survival analysis. Its primary purpose is to decouple the effective training size from the actual batch size by utilizing "online" and "target" networks, where the target network's parameters are updated via Exponential Moving Average (EMA). It maintains memory banks to pool log hazards, enabling loss computation over a larger virtual batch size. This approach, inspired by MoCo, aims to improve training stability and performance, particularly with smaller batch sizes.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/loss/momentum.py#L9-L212" target="_blank" rel="noopener noreferrer">`torchsurv.loss.momentum.Momentum` (9:212)</a>


### Cox Proportional Hazards Loss
This component provides the implementation of the negative partial log-likelihood, which is the standard loss function used for training Cox Proportional Hazards (Cox PH) models. It quantifies the discrepancy between predicted log hazards and the observed event times and statuses, aiming to maximize the likelihood of the observed data given the model's predictions.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/loss/cox.py#L9-L167" target="_blank" rel="noopener noreferrer">`torchsurv.loss.cox.neg_partial_log_likelihood` (9:167)</a>


### Weibull Accelerated Failure Time Loss
This component implements the negative log-likelihood loss function specifically tailored for Weibull Accelerated Failure Time (AFT) models. Weibull AFT models directly model the logarithm of the survival time as a linear function of covariates, and this loss function is crucial for optimizing the parameters of such models.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/torchsurv/src/torchsurv/loss/weibull.py#L7-L119" target="_blank" rel="noopener noreferrer">`torchsurv.loss.weibull.neg_log_likelihood` (7:119)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)