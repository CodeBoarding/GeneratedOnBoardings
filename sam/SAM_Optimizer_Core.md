```mermaid
graph LR
    SAM_Optimizer_Core["SAM Optimizer Core"]
    Core_Optimizer_Entry_Point["Core Optimizer Entry Point"]
    Gradient_Ascent_Phase["Gradient Ascent Phase"]
    Gradient_Descent_Phase["Gradient Descent Phase"]
    Gradient_Utility["Gradient Utility"]
    SAM_Optimizer_Core -- "contains" --> Core_Optimizer_Entry_Point
    SAM_Optimizer_Core -- "contains" --> Gradient_Ascent_Phase
    SAM_Optimizer_Core -- "contains" --> Gradient_Descent_Phase
    SAM_Optimizer_Core -- "contains" --> Gradient_Utility
    Core_Optimizer_Entry_Point -- "orchestrates" --> Gradient_Ascent_Phase
    Core_Optimizer_Entry_Point -- "orchestrates" --> Gradient_Descent_Phase
    Gradient_Ascent_Phase -- "utilizes" --> Gradient_Utility
    click SAM_Optimizer_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/sam/SAM_Optimizer_Core.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `SAM Optimizer Core` subsystem is primarily defined by the `sam.py` file. This file encapsulates the entire implementation of the Sharpness-Aware Minimization (SAM) algorithm, acting as a self-contained module for augmenting PyTorch optimizers.

### SAM Optimizer Core [[Expand]](./SAM_Optimizer_Core.md)
This is the overarching component that implements the Sharpness-Aware Minimization (SAM) algorithm. It acts as a wrapper around a base PyTorch optimizer, augmenting its behavior to find flatter minima through a two-step gradient update process.


**Related Classes/Methods**:

- <a href="https://github.com/davda54/sam/blob/main/sam.py#L4-L63" target="_blank" rel="noopener noreferrer">`sam`:4-63</a>


### Core Optimizer Entry Point
Provides the main public method (`step`) for users to trigger a complete SAM optimization step. It orchestrates the sequential execution of the gradient ascent and gradient descent phases.


**Related Classes/Methods**:

- <a href="https://github.com/davda54/sam/blob/main/sam.py#L40-L47" target="_blank" rel="noopener noreferrer">`sam.step`:40-47</a>


### Gradient Ascent Phase
Responsible for computing the perturbation (epsilon) by performing a gradient ascent step. This involves calculating gradients, normalizing them, and applying the perturbation to the model's parameters to move towards a sharper loss landscape region.


**Related Classes/Methods**:

- <a href="https://github.com/davda54/sam/blob/main/sam.py#L15-L27" target="_blank" rel="noopener noreferrer">`sam.first_step`:15-27</a>


### Gradient Descent Phase
Performs the final gradient descent step using the perturbed weights. It restores the original weights, computes gradients at the perturbed point, and then applies the update using the wrapped base PyTorch optimizer.


**Related Classes/Methods**:

- <a href="https://github.com/davda54/sam/blob/main/sam.py#L29-L38" target="_blank" rel="noopener noreferrer">`sam.second_step`:29-38</a>


### Gradient Utility
Provides a helper function to calculate the L2 norm of the gradients. This utility is crucial for scaling the perturbation accurately during the Gradient Ascent Phase.


**Related Classes/Methods**:

- <a href="https://github.com/davda54/sam/blob/main/sam.py#L49-L59" target="_blank" rel="noopener noreferrer">`sam._grad_norm`:49-59</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)