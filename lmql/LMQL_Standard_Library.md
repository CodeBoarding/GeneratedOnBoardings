```mermaid
graph LR
    LMQL_Action_Executor["LMQL Action Executor"]
    LMQL_Type_System["LMQL Type System"]
    LMQL_Data_Management["LMQL Data Management"]
    LMQL_Chat_Server["LMQL Chat Server"]
    Chat_Output_Formatter["Chat Output Formatter"]
    LMQL_Chat_Server -- "invokes methods within" --> LMQL_Action_Executor
    LMQL_Action_Executor -- "returns results to" --> LMQL_Chat_Server
    LMQL_Chat_Server -- "sends output to" --> Chat_Output_Formatter
    Chat_Output_Formatter -- "provides formatted messages to" --> LMQL_Chat_Server
    LMQL_Action_Executor -- "queries" --> LMQL_Type_System
    LMQL_Type_System -- "provides services to" --> LMQL_Action_Executor
    LMQL_Action_Executor -- "requests data from" --> LMQL_Data_Management
    LMQL_Data_Management -- "provides data to" --> LMQL_Action_Executor
    LMQL_Type_System -- "interacts with" --> LMQL_Data_Management
    LMQL_Data_Management -- "provides data samples to" --> LMQL_Type_System
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The LMQL Standard Library subsystem, encapsulated within the `lmql.lib` package, provides built-in functions, utilities, and core operational components to extend the LMQL language's capabilities, serving as a comprehensive and extensible part of the LMQL DSL runtime and development platform.

### LMQL Action Executor
This component is responsible for interpreting and executing various LMQL-defined actions. These actions include integrations with external tools (e.g., `wiki`, `lookup`), mathematical computations (`calc`), and general expression evaluation. It forms the operational backbone for executing dynamic behaviors within LMQL programs.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/lmql/blob/main/src/lmql/lib/actions.py" target="_blank" rel="noopener noreferrer">`src/lmql/lib/actions.py`</a>


### LMQL Type System
Manages the LMQL language's type system, encompassing schema definition, rigorous type validation, and conversion of type instances. Its primary role is to ensure data consistency and correctness throughout LMQL programs, facilitating structured input and output, especially crucial when interacting with LLMs.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/lmql/blob/main/src/lmql/lib/types.py" target="_blank" rel="noopener noreferrer">`src/lmql/lib/types.py`</a>


### LMQL Data Management
This component handles the loading, parsing, and caching of diverse datasets, such as GSM8K and Wikidata. It provides structured data samples that are essential for LMQL programs, supporting experimentation, benchmarking, and the generation of data-driven queries.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/lmql/blob/main/src/lmql/lib/data.py" target="_blank" rel="noopener noreferrer">`src/lmql/lib/data.py`</a>


### LMQL Chat Server
Implements the interactive chat environment, managing WebSocket communication for real-time interaction. It executes LMQL queries within a chat context and streams results back to connected clients, serving as the core backend for the LMQL Playground IDE.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/lmql/blob/main/src/lmql/lib/chat/chatserver.py" target="_blank" rel="noopener noreferrer">`src/lmql/lib/chat/chatserver.py`</a>


### Chat Output Formatter
Responsible for formatting and decorating messages specifically for display within the chat interface. This ensures that the output from LMQL program executions is consistently readable, structured, and user-friendly.


**Related Classes/Methods**:

- <a href="https://github.com/eth-sri/lmql/blob/main/src/lmql/lib/chat/output.py" target="_blank" rel="noopener noreferrer">`src/lmql/lib/chat/output.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)