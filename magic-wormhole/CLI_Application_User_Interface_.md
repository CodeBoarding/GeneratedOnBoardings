```mermaid
graph LR
    CLI_Application["CLI Application"]
    Send_Command_Handler["Send Command Handler"]
    Receive_Command_Handler["Receive Command Handler"]
    CLI_Application -- "uses" --> Send_Command_Handler
    CLI_Application -- "uses" --> Receive_Command_Handler
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Initial analysis of the Wormhole CLI, focusing on the main application and its 'send' and 'receive' command handlers.

### CLI Application
Entry point for the Wormhole CLI application.


**Related Classes/Methods**:



### Send Command Handler
Handles the 'send' command, encrypting and transferring files.


**Related Classes/Methods**:



### Receive Command Handler
Handles the 'receive' command, decrypting and receiving files.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)