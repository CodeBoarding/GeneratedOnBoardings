```mermaid
graph LR
    Client_Orchestrator["Client Orchestrator"]
    Input_Handler["Input Handler"]
    Server_State_Parser["Server State Parser"]
    Client_Side_Entity_Manager["Client-Side Entity Manager"]
    Player_Prediction_Handler["Player Prediction Handler"]
    View_Scene_Renderer["View & Scene Renderer"]
    Screen_Manager["Screen Manager"]
    Sound_System["Sound System"]
    Client_Orchestrator -- "Pulls user commands from the input handler to process the current frame." --> Input_Handler
    Client_Orchestrator -- "Provides user commands to the prediction handler to simulate the next predicted state." --> Player_Prediction_Handler
    Client_Orchestrator -- "Invokes the view renderer to calculate the scene and camera perspective for the frame." --> View_Scene_Renderer
    Client_Orchestrator -- "Triggers the sound system to play audio based on game events." --> Sound_System
    Server_State_Parser -- "Pushes updated entity states from the server into the entity manager." --> Client_Side_Entity_Manager
    Server_State_Parser -- "Provides authoritative server state to correct the prediction handler." --> Player_Prediction_Handler
    Screen_Manager -- "Pulls the prepared scene data (camera, culling info) from the view renderer to draw the 3D world." --> View_Scene_Renderer
    Screen_Manager -- "Pulls the list of interpolated entities from the entity manager to render them." --> Client_Side_Entity_Manager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Client Orchestrator
The central hub of the client. It initializes all client systems, runs the main frame loop, and coordinates the flow of data between input, prediction, and rendering components.


**Related Classes/Methods**:

- `cl_main.c`


### Input Handler
Manages all raw input from the keyboard, mouse, and joystick. It translates these hardware events into game-specific commands (e.g., `+forward`, `+attack`) for the orchestrator.


**Related Classes/Methods**:

- `cl_input.c`


### Server State Parser
Decodes and interprets all messages sent from the server. It is responsible for updating the client's view of the game world, including entity states, game events, and player scores.


**Related Classes/Methods**:

- `cl_parse.c`


### Client-Side Entity Manager
Manages the local representation of all game entities (players, items, projectiles). It performs interpolation to smooth entity movement between infrequent server updates.


**Related Classes/Methods**:

- `cl_ents.c`


### Player Prediction Handler
Reduces input latency by predicting the local player's movement on the client side without waiting for server confirmation. This provides immediate visual feedback to the player.


**Related Classes/Methods**:

- `cl_pred.c`


### View & Scene Renderer
Calculates the camera's position and orientation based on the player's state. It prepares the 3D scene for rendering by performing culling and setting up the view matrices.


**Related Classes/Methods**:

- `cl_view.c`


### Screen Manager
The final presentation layer. It orchestrates the drawing of all visual elements, including the 3D world, the 2D HUD, menus, and the console, calling the low-level renderer to execute the draw calls.


**Related Classes/Methods**:

- `cl_scrn.c`


### Sound System
Manages all audio playback. This includes loading sound assets, mixing multiple sound sources, and interacting with the platform's audio hardware to produce the final audio output.


**Related Classes/Methods**:

- `snd_dma.c`
- `snd_mix.c`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)