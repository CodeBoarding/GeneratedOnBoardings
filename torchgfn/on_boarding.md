```mermaid
graph LR
    Data_Abstractions["Data & Abstractions"]
    Environment["Environment"]
    Neural_Network_Modules["Neural Network Modules"]
    GFlowNet_Algorithms["GFlowNet Algorithms"]
    Utilities["Utilities"]
    Data_Abstractions -- "Generates data for" --> GFlowNet_Algorithms
    Data_Abstractions -- "Provides input to" --> Neural_Network_Modules
    Environment -- "Defines problem space for" --> GFlowNet_Algorithms
    Data_Abstractions -- "Interacts with" --> Environment
    GFlowNet_Algorithms -- "Trains" --> Neural_Network_Modules
    GFlowNet_Algorithms -- "Orchestrates" --> Data_Abstractions
    Utilities -- "Used by" --> Neural_Network_Modules
    Utilities -- "Used by" --> GFlowNet_Algorithms
    click Environment href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchgfn/Environment.md" "Details"
    click Neural_Network_Modules href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchgfn/Neural_Network_Modules.md" "Details"
    click GFlowNet_Algorithms href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchgfn/GFlowNet_Algorithms.md" "Details"
    click Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/torchgfn/Utilities.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Data & Abstractions
Defines the fundamental data structures for representing states and actions (gfn.states, gfn.actions). It also handles the generation of trajectories, storage in replay buffers, and preprocessing of data for neural network input. This component provides the raw and processed data for the learning process.


**Related Classes/Methods**:

- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/states.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.states` (0:1)</a>
- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/actions.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.actions` (0:1)</a>
- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/samplers.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.samplers` (0:1)</a>
- `gfn.containers` (0:1)
- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/preprocessors.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.preprocessors` (0:1)</a>


### Environment [[Expand]](./Environment.md)
Encapsulates the problem domain, defining state transitions, reward functions, and valid actions. It serves as the interface for the GFlowNet agent to interact with the specific task, including concrete implementations for various problems.


**Related Classes/Methods**:

- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/env.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.env` (0:1)</a>
- `gfn.gym` (0:1)


### Neural Network Modules [[Expand]](./Neural_Network_Modules.md)
Implements the neural network architectures used to estimate GFlowNet-related quantities (e.g., policies, state flows). These are the learnable components that process data and inform decision-making within the GFN framework.


**Related Classes/Methods**:

- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/modules.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.modules` (0:1)</a>
- <a href="https://github.com/gfnorg/torchgfn/blob/master/src/gfn/utils/modules.py#L0-L1" target="_blank" rel="noopener noreferrer">`gfn.utils.modules` (0:1)</a>


### GFlowNet Algorithms [[Expand]](./GFlowNet_Algorithms.md)
Implements the core GFlowNet training objectives and algorithms (e.g., Detailed Balance, Trajectory Balance). It orchestrates the entire training loop, coordinating data flow, module optimization, and environment interaction to learn the GFN.


**Related Classes/Methods**:

- `gfn.gflownet` (0:1)


### Utilities [[Expand]](./Utilities.md)
A collection of general-purpose helper functions and modules for common tasks such as device management, random seeding, graph operations, probability calculations, and training utilities. It provides foundational support across the library.


**Related Classes/Methods**:

- `gfn.utils` (0:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)