```mermaid
graph LR
    Policy["Policy"]
    Model["Model"]
    MCTS["MCTS"]
    Data_Management_Buffer["Data Management/Buffer"]
    Training_Orchestrator["Training Orchestrator"]
    Worker["Worker"]
    Environment_Zoo_["Environment (Zoo)"]
    Reward_Model_Optional_["Reward Model (Optional)"]
    Training_Orchestrator -- "initiates training" --> Policy
    Policy -- "interacts with" --> Environment_Zoo_
    Environment_Zoo_ -- "interacts with" --> Policy
    Policy -- "queries and updates" --> Model
    Policy -- "delegates action selection to" --> MCTS
    MCTS -- "returns actions/statistics to" --> Policy
    Policy -- "stores/retrieves data from" --> Data_Management_Buffer
    Data_Management_Buffer -- "stores/retrieves data from" --> Policy
    Worker -- "facilitates interaction with" --> Policy
    Reward_Model_Optional_ -- "provides intrinsic rewards to" --> Policy
    MCTS -- "queries" --> Model
    Worker -- "manages" --> Environment_Zoo_
    click Policy href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/Policy.md" "Details"
    click Model href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/Model.md" "Details"
    click MCTS href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/MCTS.md" "Details"
    click Training_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/Training_Orchestrator.md" "Details"
    click Worker href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/Worker.md" "Details"
    click Environment_Zoo_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/LightZero/Environment_Zoo_.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The LightZero project implements a modular reinforcement learning framework centered around a Policy component. This Policy drives the learning process by interacting with a Model for state representation and prediction, and utilizing MCTS for advanced decision-making. The Training Orchestrator oversees the entire training and evaluation workflow, while Worker components efficiently manage parallel interactions between the Policy and various Environment (Zoo) instances for data collection. A Data Management/Buffer handles the storage and retrieval of experience data, and an optional Reward Model can enhance learning through intrinsic rewards. This architecture promotes clear separation of concerns, enabling flexible experimentation with different RL algorithms and environments.

### Policy [[Expand]](./Policy.md)
The central decision-maker and learning agent; it queries the Model for predictions (e.g., state representation, value, policy) and updates the Model's parameters during the learning phase.


**Related Classes/Methods**: _None_

### Model [[Expand]](./Model.md)
A passive data structure and computational graph used by the Policy for neural network computations (predictions, value estimations).


**Related Classes/Methods**: _None_

### MCTS [[Expand]](./MCTS.md)
Performs tree searches, often querying the Model for predictions to guide its search, and then returns optimal actions or statistics back to the Policy.


**Related Classes/Methods**: _None_

### Data Management/Buffer
Stores and provides experience data for the Policy's learning updates.


**Related Classes/Methods**: _None_

### Training Orchestrator [[Expand]](./Training_Orchestrator.md)
Initiates and manages the overall training process, primarily by activating and configuring the Policy.


**Related Classes/Methods**: _None_

### Worker [[Expand]](./Worker.md)
Manages interactions between the Policy and various Environment (Zoo) instances, facilitating parallel data collection and evaluation runs.


**Related Classes/Methods**: _None_

### Environment (Zoo) [[Expand]](./Environment_Zoo_.md)
Provides the simulation context, receiving actions from the Policy (via Worker) and returning new states, rewards, and termination signals.


**Related Classes/Methods**: _None_

### Reward Model (Optional)
Provides intrinsic rewards to the Policy, influencing its learning and exploration strategies.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)