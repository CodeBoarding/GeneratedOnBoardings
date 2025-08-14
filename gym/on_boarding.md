```mermaid
graph LR
    Agent_External_["Agent (External)"]
    Gym_Core_API["Gym Core API"]
    Environment_Registry["Environment Registry"]
    Environment_Implementations["Environment Implementations"]
    Environment_Wrappers["Environment Wrappers"]
    Agent_External_ -- "sends Action to" --> Gym_Core_API
    Gym_Core_API -- "sends Observation, Reward, State to" --> Agent_External_
    Environment_Registry -- "instantiates Env objects" --> Gym_Core_API
    Environment_Implementations -- "implements the Env interface" --> Gym_Core_API
    Environment_Wrappers -- "wraps/modifies Env objects" --> Gym_Core_API
    click Environment_Registry href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gym/Environment_Registry.md" "Details"
    click Environment_Wrappers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gym/Environment_Wrappers.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Gym library's architecture is centered around the `Gym Core API`, which defines the fundamental `Env` interface for agent-environment interaction. `Environment Implementations` provide concrete instances of various environments, all adhering to this core API. The `Environment Registry` acts as a central catalog, enabling the discovery and instantiation of these environments. `Environment Wrappers` offer a flexible mechanism to modify environment behavior without altering the underlying implementations, allowing for pre-processing, reward shaping, and other transformations. An `Agent (External)` interacts with the system by sending actions to and receiving observations, rewards, and state information from the `Gym Core API`, forming a clear feedback loop. This modular design facilitates easy extension and customization of reinforcement learning environments.

### Agent (External)
Represents the reinforcement learning algorithm or entity that interacts with Gym environments by sending actions and receiving observations. While external to the Gym library, its interaction points are defined by the `Gym Core API`.


**Related Classes/Methods**:

- <a href="https://github.com/openai/gym/blob/master/gym/core.py" target="_blank" rel="noopener noreferrer">`gym.core.Env:step`</a>
- <a href="https://github.com/openai/gym/blob/master/gym/core.py" target="_blank" rel="noopener noreferrer">`gym.core.Env:reset`</a>


### Gym Core API
The foundational interface (`Env` class) that defines the contract for all Gym environments, standardizing agent-environment interaction (e.g., step, reset).


**Related Classes/Methods**:

- <a href="https://github.com/openai/gym/blob/master/gym/core.py" target="_blank" rel="noopener noreferrer">`gym.core.Env`</a>
- <a href="https://github.com/openai/gym/blob/master/gym/core.py" target="_blank" rel="noopener noreferrer">`gym.core.Env:step`</a>
- <a href="https://github.com/openai/gym/blob/master/gym/core.py" target="_blank" rel="noopener noreferrer">`gym.core.Env:reset`</a>


### Environment Registry [[Expand]](./Environment_Registry.md)
Manages the discovery, registration, and instantiation of various Gym environments, acting as a central catalog for available environments.


**Related Classes/Methods**:

- <a href="https://github.com/openai/gym/blob/master/gym/envs/registration.py" target="_blank" rel="noopener noreferrer">`gym.envs.registration`</a>


### Environment Implementations
Concrete implementations of diverse reinforcement learning environments (e.g., classic control, Box2D, MuJoCo) that adhere to the Gym Core API.


**Related Classes/Methods**:

- <a href="https://github.com/openai/gym/blob/master/gym/envs/classic_control/cartpole.py" target="_blank" rel="noopener noreferrer">`gym.envs.classic_control.cartpole`</a>


### Environment Wrappers [[Expand]](./Environment_Wrappers.md)
A flexible layer that allows modification of environment behavior without altering the underlying environment implementation (e.g., observation preprocessing, reward shaping).


**Related Classes/Methods**:

- <a href="https://github.com/openai/gym/blob/master/gym/wrappers/compatibility.py" target="_blank" rel="noopener noreferrer">`gym.wrappers.compatibility`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)