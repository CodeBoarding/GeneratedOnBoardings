```mermaid
graph LR
    Tello_API_Facade["Tello API Facade"]
    Tello_Swarm_Orchestrator["Tello Swarm Orchestrator"]
    User_Application -- "initiates commands/queries to" --> Tello_API_Facade
    User_Application -- "initiates swarm commands to" --> Tello_Swarm_Orchestrator
    Tello_API_Facade -- "sends commands/queries to" --> Tello_Drone
    Tello_Drone -- "sends responses/state/video to" --> Tello_API_Facade
    Tello_Swarm_Orchestrator -- "manages/interacts with" --> Tello_API_Facade
    click Tello_API_Facade href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/DJITelloPy/Tello_API_Facade.md" "Details"
    click Tello_Swarm_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/DJITelloPy/Tello_Swarm_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The DJITelloPy library's architecture is designed around two core internal components: the Tello API Facade and the Tello Swarm Orchestrator. The Tello API Facade (djitellopy.tello.Tello) serves as the primary interface for direct interaction with a single Tello drone, handling all low-level communication protocols, command translation, and data processing (including drone state and video feeds). Building upon this, the Tello Swarm Orchestrator (djitellopy.swarm.TelloSwarm) provides capabilities for managing and coordinating multiple Tello API Facade instances, enabling synchronized control over a fleet of drones. External user applications interact with these components to issue commands and receive data, which are then relayed to and from the physical Tello drones.

### Tello API Facade [[Expand]](./Tello_API_Facade.md)
The central component providing a high-level, simplified interface for controlling a single Tello drone. It abstracts complex UDP communication, state parsing, and video stream handling, encapsulating internal mechanisms for command dispatch, state reception, and video processing.


**Related Classes/Methods**:

- <a href="https://github.com/damiafuentes/DJITelloPy/blob/master/djitellopy/tello.py" target="_blank" rel="noopener noreferrer">`djitellopy.tello.Tello`</a>


### Tello Swarm Orchestrator [[Expand]](./Tello_Swarm_Orchestrator.md)
Offers a higher-level abstraction for controlling multiple Tello drones simultaneously. It manages a collection of Tello API Facade instances to enable synchronized or sequential commands across a fleet of drones.


**Related Classes/Methods**:

- <a href="https://github.com/damiafuentes/DJITelloPy/blob/master/djitellopy/swarm.py#L12-L159" target="_blank" rel="noopener noreferrer">`djitellopy.swarm.TelloSwarm`:12-159</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)