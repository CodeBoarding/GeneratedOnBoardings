```mermaid
graph LR
    Core_Orchestrator["Core Orchestrator"]
    Communication_Pivoting_Layer["Communication & Pivoting Layer"]
    Task_Execution_Engine["Task Execution Engine"]
    Stealth_Evasion_Engine["Stealth & Evasion Engine"]
    Stealth_Evasion_Engine -- "Loads" --> Core_Orchestrator
    Core_Orchestrator -- "Fetches Tasks" --> Communication_Pivoting_Layer
    Communication_Pivoting_Layer -- "Delivers Tasks" --> Core_Orchestrator
    Core_Orchestrator -- "Dispatches Task" --> Task_Execution_Engine
    Task_Execution_Engine -- "Returns Result" --> Core_Orchestrator
    click Core_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CobaltStrikeBeaconCppSource/Core_Orchestrator.md" "Details"
    click Communication_Pivoting_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CobaltStrikeBeaconCppSource/Communication_Pivoting_Layer.md" "Details"
    click Task_Execution_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CobaltStrikeBeaconCppSource/Task_Execution_Engine.md" "Details"
    click Stealth_Evasion_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CobaltStrikeBeaconCppSource/Stealth_Evasion_Engine.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Core Orchestrator [[Expand]](./Core_Orchestrator.md)
The central component that manages the agent's lifecycle, initializes other components, and orchestrates the main event loop, acting as the intermediary between communication and task execution.


**Related Classes/Methods**:

- `src/beacon.cpp`
- `src/beacon.h`


### Communication & Pivoting Layer [[Expand]](./Communication_Pivoting_Layer.md)
Abstracts all communication protocols (TCP, SMB) for interacting with the C2 server. It handles data transmission and provides advanced capabilities for pivoting through other compromised hosts and using external C2 channels.


**Related Classes/Methods**:

- `src/channel.cpp`
- `src/client.cpp`
- `src/client_tcp.cpp`
- `src/client_smb.cpp`
- `src/beacon_extc2.cpp`
- `src/beacon_pivot.cpp`


### Task Execution Engine [[Expand]](./Task_Execution_Engine.md)
Parses commands received from the C2 server and executes the corresponding feature module. This component contains the implant's collection of capabilities, such as file system operations, privilege escalation, and in-memory code execution.


**Related Classes/Methods**:

- `src/commands.cpp`
- `src/execute.cpp`
- `src/files.cpp`
- `src/elevate.cpp`
- `src/boff.cpp`


### Stealth & Evasion Engine [[Expand]](./Stealth_Evasion_Engine.md)
Responsible for evading detection by security products. Its primary mechanism is Reflective DLL Injection, which loads the implant into a target process's memory without writing to the disk.


**Related Classes/Methods**:

- `src/ReflectiveDll.cpp`
- `src/ReflectiveLoader.cpp`
- `src/ReflectiveDLLInjection.h`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)