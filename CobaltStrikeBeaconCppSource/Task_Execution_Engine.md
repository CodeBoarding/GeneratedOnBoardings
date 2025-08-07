```mermaid
graph LR
    Command_Parser["Command Parser"]
    Shell_Command_Executor["Shell Command Executor"]
    File_System_Manager["File System Manager"]
    Privilege_Escalation_Handler["Privilege Escalation Handler"]
    BOF_Executor["BOF Executor"]
    Command_Parser -- "invokes" --> Shell_Command_Executor
    Command_Parser -- "delegates to" --> File_System_Manager
    Command_Parser -- "initiates" --> Privilege_Escalation_Handler
    Command_Parser -- "dispatches" --> BOF_Executor
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Based on the provided analysis, the `Task Execution Engine` is a modular subsystem responsible for translating abstract tasks from the C2 server into concrete actions on the compromised host. The component choices are justified by their direct mapping to the discrete, critical capabilities required for post-exploitation, as evidenced by the provided source files.

### Command Parser
Acts as the primary entry point for the Task Execution Engine. It receives task IDs and associated parameters from the CommandDispatcher, validates them, and routes the command to the appropriate specialized execution module.


**Related Classes/Methods**:

- `src/commands.cpp`


### Shell Command Executor
Executes arbitrary shell commands and system utilities. It is responsible for creating a new process (e.g., `cmd.exe`, `powershell.exe`), redirecting its standard input/output/error streams, and capturing the results for exfiltration.


**Related Classes/Methods**:

- `src/execute.cpp`


### File System Manager
Manages all interactions with the host's file system. This includes capabilities like listing directories, reading/writing files, deleting files, and searching for sensitive documents, all executed via direct Win32 API calls to minimize detection.


**Related Classes/Methods**:

- `src/files.cpp`


### Privilege Escalation Handler
Contains logic and exploits to attempt privilege escalation on the target system. It identifies and leverages vulnerabilities or misconfigurations to gain higher-level permissions (e.g., from a standard user to SYSTEM).


**Related Classes/Methods**:

- `src/elevate.cpp`


### BOF Executor
A specialized loader and runtime environment for executing Beacon Object Files (BOFs). It handles in-memory loading, resolves necessary API functions, passes arguments, and executes these lightweight, single-function modules without writing them to disk.


**Related Classes/Methods**:

- `src/boff.cpp`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)