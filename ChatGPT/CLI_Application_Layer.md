```mermaid
graph LR
    CLI_Entry_Point["CLI Entry Point"]
    V1_CLI_Orchestrator["V1 CLI Orchestrator"]
    V3_CLI_Orchestrator["V3 CLI Orchestrator"]
    V1_Command_Processor["V1 Command Processor"]
    V3_Command_Processor["V3 Command Processor"]
    V1_API_Interaction_Handler["V1 API Interaction Handler"]
    V3_API_Interaction_Handler["V3 API Interaction Handler"]
    V3_Conversation_History_Manager["V3 Conversation History Manager"]
    CLI_Entry_Point -- "dispatches to" --> V1_CLI_Orchestrator
    CLI_Entry_Point -- "dispatches to" --> V3_CLI_Orchestrator
    V1_CLI_Orchestrator -- "delegates command processing to" --> V1_Command_Processor
    V1_CLI_Orchestrator -- "invokes" --> V1_API_Interaction_Handler
    V3_CLI_Orchestrator -- "delegates command processing to" --> V3_Command_Processor
    V3_CLI_Orchestrator -- "invokes" --> V3_API_Interaction_Handler
    V3_CLI_Orchestrator -- "utilizes" --> V3_Conversation_History_Manager
    V3_API_Interaction_Handler -- "updates conversation history via" --> V3_Conversation_History_Manager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The CLI Application Layer subsystem is the user-facing interface of the revChatGPT project, responsible for handling command-line interactions, managing user input, and orchestrating the application's flow for both V1 and V3 of the ChatGPT API.

### CLI Entry Point
Serves as the primary entry point for the entire CLI application, responsible for initial argument parsing and dispatching control to the appropriate version-specific main function.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/__main__.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.__main__`</a>


### V1 CLI Orchestrator
Manages the main interaction loop, handles user input, and coordinates the overall flow of commands and API interactions for V1. It also implicitly handles the setup of the V1 CLI environment.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V1.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V1:main`</a>


### V3 CLI Orchestrator
Manages the main interaction loop, handles user input, and coordinates the overall flow of commands and API interactions for V3. It also implicitly handles the setup of the V3 CLI environment.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V3.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V3:main`</a>


### V1 Command Processor
Parses and executes specific user-entered commands for V1 that control the CLI application's behavior (e.g., /reset, /exit).


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V1.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V1:handle_commands`</a>


### V3 Command Processor
Parses and executes specific user-entered commands for V3 that control the CLI application's behavior.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V3.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V3:handle_commands`</a>


### V1 API Interaction Handler
Direct interface to the core ChatGPT API from the V1 CLI, formulating requests, sending user queries, and processing responses.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V1.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V1:ask`</a>


### V3 API Interaction Handler
Direct interface to the core ChatGPT API from the V3 CLI, formulating requests, sending user queries, and processing responses, including streaming.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V3.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V3:ask`</a>
- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V3.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V3:ask_stream`</a>


### V3 Conversation History Manager
Manages and stores the conversation history specifically for the V3 CLI, ensuring context is maintained across interactions.


**Related Classes/Methods**:

- <a href="https://github.com/acheong08/ChatGPT/blob/main/src/revChatGPT/V3.py" target="_blank" rel="noopener noreferrer">`src.revChatGPT.V3:add_to_conversation`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)