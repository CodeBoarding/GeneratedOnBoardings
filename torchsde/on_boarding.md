```mermaid
graph LR
    SDE_Model_Definition["SDE Model Definition"]
    Brownian_Motion_Generation["Brownian Motion Generation"]
    SDE_Solver_Engine["SDE Solver Engine"]
    Numerical_Solvers["Numerical Solvers"]
    Gradient_Computation_Adjoint_["Gradient Computation (Adjoint)"]
    User_Applications_Examples["User Applications/Examples"]
    SDE_Model_Definition -- "Defines SDE for" --> SDE_Solver_Engine
    SDE_Model_Definition -- "Provides SDE functions to" --> Numerical_Solvers
    Brownian_Motion_Generation -- "Supplies noise to" --> SDE_Solver_Engine
    SDE_Solver_Engine -- "Delegates stepping to" --> Numerical_Solvers
    SDE_Solver_Engine -- "Leverages for backpropagation" --> Gradient_Computation_Adjoint_
    Numerical_Solvers -- "Evaluates f and g from" --> SDE_Model_Definition
    Gradient_Computation_Adjoint_ -- "Accesses SDE definition for" --> SDE_Model_Definition
    User_Applications_Examples -- "Defines SDEs using" --> SDE_Model_Definition
    User_Applications_Examples -- "Invokes SDE integration via" --> SDE_Solver_Engine
    click SDE_Model_Definition href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsde/SDE_Model_Definition.md" "Details"
    click Brownian_Motion_Generation href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsde/Brownian_Motion_Generation.md" "Details"
    click SDE_Solver_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsde/SDE_Solver_Engine.md" "Details"
    click Numerical_Solvers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsde/Numerical_Solvers.md" "Details"
    click Gradient_Computation_Adjoint_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchsde/Gradient_Computation_Adjoint_.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `torchsde` architecture is designed as a modular ML toolkit for differentiable SDE solving. At its core, the **SDE Solver Engine** orchestrates the numerical integration of SDEs, receiving SDE definitions from the **SDE Model Definition** component and stochastic noise from **Brownian Motion Generation**. The engine delegates the actual computation to various **Numerical Solvers** and, crucially for deep learning, leverages the **Gradient Computation (Adjoint)** component for efficient backpropagation. This design allows **User Applications/Examples** to seamlessly define and solve SDEs while benefiting from PyTorch's autograd capabilities, making `torchsde` a flexible and powerful tool for SDE-based machine learning models.

### SDE Model Definition [[Expand]](./SDE_Model_Definition.md)
Provides the abstract interface for users to define their SDEs, specifying the drift (`f`) and diffusion (`g`) functions. This component is central to how users interact with the library to describe their stochastic processes.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/base_sde.py" target="_blank" rel="noopener noreferrer">`torchsde._core.base_sde`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/adjoint_sde.py" target="_blank" rel="noopener noreferrer">`torchsde._core.adjoint_sde`</a>


### Brownian Motion Generation [[Expand]](./Brownian_Motion_Generation.md)
Manages the generation, interpolation, and access patterns for the stochastic noise (Brownian motion) required by SDEs. It ensures that the noise is available to the solver as needed.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_brownian/brownian_interval.py" target="_blank" rel="noopener noreferrer">`torchsde._brownian.brownian_interval`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_brownian/derived.py" target="_blank" rel="noopener noreferrer">`torchsde._brownian.derived`</a>


### SDE Solver Engine [[Expand]](./SDE_Solver_Engine.md)
The core orchestrator of the SDE integration process. It takes the SDE definition and Brownian motion, applies numerical methods, and manages adaptive stepping. It also initiates the adjoint state computation for gradients.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/sdeint.py" target="_blank" rel="noopener noreferrer">`torchsde._core.sdeint`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/base_solver.py" target="_blank" rel="noopener noreferrer">`torchsde._core.base_solver`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/adaptive_stepping.py" target="_blank" rel="noopener noreferrer">`torchsde._core.adaptive_stepping`</a>


### Numerical Solvers [[Expand]](./Numerical_Solvers.md)
Contains the implementations of various numerical algorithms for integrating SDEs (e.g., Milstein, SRK). These solvers perform the actual step-by-step computation based on the SDE's drift and diffusion functions.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/methods/milstein.py" target="_blank" rel="noopener noreferrer">`torchsde._core.methods.milstein`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/methods/srk.py" target="_blank" rel="noopener noreferrer">`torchsde._core.methods.srk`</a>


### Gradient Computation (Adjoint) [[Expand]](./Gradient_Computation_Adjoint_.md)
Implements the adjoint method for efficient and memory-conscious gradient computation through SDE solutions. This component is critical for integrating `torchsde` into deep learning models that rely on backpropagation. It utilizes low-level autograd utilities.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/adjoint.py" target="_blank" rel="noopener noreferrer">`torchsde._core.adjoint`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/torchsde/_core/misc.py" target="_blank" rel="noopener noreferrer">`torchsde._core.misc`</a>


### User Applications/Examples
Demonstrates practical use cases and integration of the `torchsde` library within various machine learning models (e.g., DDPM, Latent SDEs, SDE-GANs). These are external components that showcase the library's capabilities.


**Related Classes/Methods**:

- <a href="https://github.com/google-research/torchsde/blob/master/examples/cont_ddpm.py" target="_blank" rel="noopener noreferrer">`examples.cont_ddpm`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/examples/latent_sde.py" target="_blank" rel="noopener noreferrer">`examples.latent_sde`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/examples/sde_gan.py" target="_blank" rel="noopener noreferrer">`examples.sde_gan`</a>
- <a href="https://github.com/google-research/torchsde/blob/master/examples/unet.py" target="_blank" rel="noopener noreferrer">`examples.unet`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)