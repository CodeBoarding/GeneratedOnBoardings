```mermaid
graph LR
    Trading_Environment_Core["Trading Environment Core"]
    Environment_State_Management["Environment State Management"]
    Trading_Action_Execution_Logic["Trading Action Execution Logic"]
    Episode_Data_Preparation["Episode Data Preparation"]
    Trading_Environment_Core -- "exposes" --> Environment_State_Management
    Trading_Environment_Core -- "contains" --> Trading_Action_Execution_Logic
    Trading_Environment_Core -- "contains" --> Episode_Data_Preparation
    Environment_State_Management -- "calls" --> Episode_Data_Preparation
    Environment_State_Management -- "invokes" --> Trading_Action_Execution_Logic
    Environment_State_Management -- "updates" --> Trading_Environment_Core
    Trading_Action_Execution_Logic -- "modifies" --> Trading_Environment_Core
    Episode_Data_Preparation -- "provides data to" --> Trading_Environment_Core
    click Trading_Environment_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/TradingGym/Trading_Environment_Core.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the Trading Environment Core Subsystem, focusing on its central components and their interactions within the trading simulation engine.

### Trading Environment Core [[Expand]](./Trading_Environment_Core.md)
This is the central class that defines and manages the entire trading simulation environment. It holds the current market state, the agent's portfolio, and orchestrates the simulation flow, acting as the primary interface for agents.


**Related Classes/Methods**:

- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L12-L381" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1.trading_env`:12-381</a>


### Environment State Management
This component is responsible for controlling the lifecycle of a simulation episode. The `reset` method initializes the environment for a new episode, while the `step` method processes an agent's action, updates the environment's state, calculates rewards, and determines if the episode has concluded.


**Related Classes/Methods**:

- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L78-L126" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1.reset`:78-126</a>
- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L177-L271" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1.step`:177-271</a>


### Trading Action Execution Logic
This component encapsulates the specific business logic for executing various trading operations. Each method handles the financial calculations and state updates (e.g., portfolio changes, cash balance adjustments) corresponding to a particular trading action.


**Related Classes/Methods**:

- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L129-L141" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._long`:129-141</a>
- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L143-L155" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._short`:143-155</a>
- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L165-L171" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._long_cover`:165-171</a>
- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L157-L163" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._short_cover`:157-163</a>
- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L173-L175" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._stayon`:173-175</a>


### Episode Data Preparation
Responsible for selecting and preparing the historical market data segment that will be used for a given simulation episode. This ensures that each training episode can utilize a different, randomly chosen section of the available data.


**Related Classes/Methods**:

- <a href="https://github.com/Yvictor/TradingGym/blob/master/trading_env/envs/training_v1.py#L68-L76" target="_blank" rel="noopener noreferrer">`trading_env.envs.training_v1._random_choice_section`:68-76</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)