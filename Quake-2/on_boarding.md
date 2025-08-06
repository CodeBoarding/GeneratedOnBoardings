```mermaid
graph LR
    Engine_Core["Engine Core"]
    Server["Server"]
    Game_Logic["Game Logic"]
    Client["Client"]
    Renderer["Renderer"]
    Server -- "Loads and executes" --> Game_Logic
    Client -- "Communicates with" --> Server
    Server -- "Communicates with" --> Client
    Client -- "Renders world using" --> Renderer
    Engine_Core -- "Provides services to" --> Server
    Engine_Core -- "Provides services to" --> Client
    click Engine_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/Quake-2/Engine_Core.md" "Details"
    click Game_Logic href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/Quake-2/Game_Logic.md" "Details"
    click Client href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/Quake-2/Client.md" "Details"
    click Renderer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/Quake-2/Renderer.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Engine Core [[Expand]](./Engine_Core.md)
A foundational layer that combines platform-specific code (`System`) and shared utilities (`Common`). It provides core services like memory management, file I/O, and networking to all other components.


**Related Classes/Methods**:

- `qcommon.h`
- `sys_main.c`


### Server
The authoritative component that manages the entire game state and simulation. It processes client commands, runs the game logic, and broadcasts the world state back to the clients.


**Related Classes/Methods**:

- `sv_main.c`
- `sv_game.c`


### Game Logic [[Expand]](./Game_Logic.md)
A self-contained, swappable module that defines the actual rules of the game. It is responsible for entity management, physics, and game-specific rules (e.g., scoring, win conditions). It is loaded by the Server.


**Related Classes/Methods**:

- `g_main.c`
- `g_public.h`


### Client [[Expand]](./Client.md)
The player-facing component responsible for predicting player movement, handling user input, and managing the local game state. It communicates with the server to receive updates and sends user commands.


**Related Classes/Methods**:

- `cl_main.c`
- `cl_input.c`


### Renderer [[Expand]](./Renderer.md)
An abstracted and modular graphics backend responsible for all visual output. It is called by the Client to draw the 3D world, user interface, and other visual elements.


**Related Classes/Methods**:

- `ref.h`
- `r_main.c`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)