```mermaid
graph LR
    Environment_Manager["Environment Manager"]
    Action_Preprocessor["Action Preprocessor"]
    Physics_Engine_Interface["Physics Engine Interface"]
    Drone_Dynamics["Drone Dynamics"]
    State_Manager["State Manager"]
    Observation_Feedback_Generator["Observation & Feedback Generator"]
    Environment_Manager -- "calls" --> Action_Preprocessor
    Environment_Manager -- "calls" --> Physics_Engine_Interface
    Environment_Manager -- "calls" --> Drone_Dynamics
    Environment_Manager -- "calls" --> State_Manager
    Environment_Manager -- "invokes" --> Observation_Feedback_Generator
    Drone_Dynamics -- "provides calculated forces/torques to" --> Physics_Engine_Interface
    State_Manager -- "provides state data to" --> Observation_Feedback_Generator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Simulation Core` subsystem is the heart of the `gym-pybullet-drones` project, responsible for orchestrating the simulated environment, managing drone dynamics, and providing the necessary interface for reinforcement learning agents. Its boundaries are primarily defined by the `gym_pybullet_drones.envs.BaseAviary` class and its encapsulated methods, which collectively manage the simulation's progression and state.

### Environment Manager
This is the primary orchestrator of the entire simulation environment. It initializes the PyBullet physics engine, defines the action and observation spaces, manages the simulation's step-by-step progression, and handles environment resets. It serves as the main interface for external agents (e.g., RL algorithms) to interact with the simulated world.


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary`</a>


### Action Preprocessor
This component is responsible for transforming the high-level actions received from an external agent (e.g., desired motor thrusts) into a format directly usable by the PyBullet physics engine, such as specific forces or torques to be applied to the drone's rigid bodies.


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_preprocessAction`</a>


### Physics Engine Interface
This component directly interacts with the PyBullet physics engine. It applies the calculated forces and torques to the simulated drones, updates their rigid body states, and handles collision detection within the environment. It is the bridge between the abstract dynamics and the underlying physics simulation.


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_physics`</a>


### Drone Dynamics
This component calculates and applies drone-specific dynamics, including forces, torques, and rotational updates, based on the preprocessed actions and the drone's current state. It incorporates specialized calculations like quaternion integration (`_integrateQ`) to ensure accurate and stable drone orientation updates.


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_dynamics`</a>
- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_integrateQ`</a>


### State Manager
This component is responsible for managing and storing the current kinematic state (position, velocity, orientation) of all drones and relevant objects within the simulation. It ensures that the environment's state is consistently updated and available for observation generation and reward calculation.


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_updateAndStoreKinematicInformation`</a>


### Observation & Feedback Generator
This composite component is responsible for gathering raw simulation data and processing it into a structured observation space suitable for an RL agent. It also calculates the reward signal based on the simulation's state and actions, and determines if the current episode has reached a terminal state (e.g., crash) or should be truncated (e.g., time limit).


**Related Classes/Methods**:

- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_computeObs`</a>
- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_computeReward`</a>
- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_computeTerminated`</a>
- <a href="https://github.com/utiasDSL/gym-pybullet-drones/blob/main/gym_pybullet_drones/envs/BaseAviary.py" target="_blank" rel="noopener noreferrer">`gym_pybullet_drones.envs.BaseAviary:_computeTruncated`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)