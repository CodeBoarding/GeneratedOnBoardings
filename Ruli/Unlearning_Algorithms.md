```mermaid
graph LR
    PrefixUnlearn["PrefixUnlearn"]
    GradientAscent["GradientAscent"]
    GradientAscentPlus["GradientAscentPlus"]
    FineTune["FineTune"]
    Scrub["Scrub"]
    NegGrad["NegGrad"]
    Retrain["Retrain"]
    PrefixUnlearn -- "invokes" --> GradientAscent
    PrefixUnlearn -- "invokes" --> GradientAscentPlus
    PrefixUnlearn -- "triggers" --> FineTune
    PrefixUnlearn -- "initiates" --> Scrub
    PrefixUnlearn -- "calls" --> NegGrad
    PrefixUnlearn -- "initiates" --> Retrain
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Unlearning Algorithms subsystem is a core part of the project, focusing on implementing and orchestrating various machine unlearning techniques.

### PrefixUnlearn
Acts as the orchestrator and high-level entry point for initiating various unlearning processes. It provides a unified interface for triggering different unlearning algorithms and manages the overall unlearning workflow.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/text/unlearner.py#L9-L142" target="_blank" rel="noopener noreferrer">`text.unlearner.PrefixUnlearn`:9-142</a>


### GradientAscent
Implements the Gradient Ascent unlearning algorithm. Its core function is to modify a given model to remove the influence of specified "forget" data, adhering to its respective algorithmic principles.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/gradient_ascent.py#L12-L60" target="_blank" rel="noopener noreferrer">`core.unlearn.gradient_ascent.GradientAscent`:12-60</a>


### GradientAscentPlus
An enhanced variant of the Gradient Ascent algorithm. It implements a distinct machine unlearning technique to modify a model and remove the influence of specified "forget" data.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/gradient_ascent.py#L63-L182" target="_blank" rel="noopener noreferrer">`core.unlearn.gradient_ascent.GradientAscentPlus`:63-182</a>


### FineTune
Implements an unlearning strategy based on fine-tuning. Its core function is to modify a given model to remove the influence of specified "forget" data, adhering to its respective algorithmic principles.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/fine_tune.py#L29-L96" target="_blank" rel="noopener noreferrer">`core.unlearn.fine_tune.FineTune`:29-96</a>


### Scrub
Implements a "scrubbing" or data sanitization unlearning method. Its core function is to modify a given model to remove the influence of specified "forget" data, adhering to its respective algorithmic principles.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/scrub.py#L31-L127" target="_blank" rel="noopener noreferrer">`core.unlearn.scrub.Scrub`:31-127</a>


### NegGrad
Implements the Negative Gradient unlearning algorithm. Its core function is to modify a given model to remove the influence of specified "forget" data, adhering to its respective algorithmic principles.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/negrad.py#L44-L162" target="_blank" rel="noopener noreferrer">`core.unlearn.negrad.NegGrad`:44-162</a>


### Retrain
Represents a baseline unlearning method by retraining the model from scratch on the "retain" data. Its core function is to modify a given model to remove the influence of specified "forget" data, adhering to its respective algorithmic principles.


**Related Classes/Methods**:

- <a href="https://github.com/datasec-lab/Ruli/blob/main/core/unlearn/retrain.py#L10-L112" target="_blank" rel="noopener noreferrer">`core.unlearn.retrain.Retrain`:10-112</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)