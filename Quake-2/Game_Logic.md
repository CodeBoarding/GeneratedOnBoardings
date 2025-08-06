```mermaid
graph LR
    Server["Server"]
    Game_Main_Loop["Game Main Loop"]
    Entity_Management["Entity Management"]
    Physics_Movement["Physics & Movement"]
    Combat_Items["Combat & Items"]
    Client_Commands["Client Commands"]
    Game_API["Game API"]
    Server -- "Invokes game logic via" --> Game_API
    Game_Main_Loop -- "Implements" --> Game_API
    Game_Main_Loop -- "Calls engine functions via" --> Game_API
    Game_Main_Loop -- "Manages entity updates" --> Entity_Management
    Game_Main_Loop -- "Executes physics simulation for entities" --> Physics_Movement
    Game_Main_Loop -- "Delegates combat & item logic" --> Combat_Items
    Game_Main_Loop -- "Dispatches client commands" --> Client_Commands
    Combat_Items -- "Spawns projectiles/effects" --> Entity_Management
    Physics_Movement -- "Triggers damage on collision" --> Combat_Items
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Server
The main engine's Server component that loads and interacts with the Game Logic module.


**Related Classes/Methods**:

- `sv_game.c`


### Game Main Loop
The central entry point and orchestrator for the game logic module. It contains the `G_RunFrame` function, which is called by the server for every frame of the simulation. It manages the game state and delegates tasks to other components.


**Related Classes/Methods**:

- `g_main.c`


### Entity Management
Responsible for the lifecycle of all game entities. This includes spawning new entities (players, monsters, items) based on the map and game state, as well as freeing them when they are no longer needed.


**Related Classes/Methods**:

- `g_spawn.c`
- `g_utils.c`


### Physics & Movement
Manages all physical simulations within the game world. It handles entity movement, collision detection between entities and the world, gravity, and the effects of environmental hazards like lava or slime.


**Related Classes/Methods**:

- `g_phys.c`


### Combat & Items
Implements the rules for all combat interactions and item behaviors. This includes weapon firing mechanics, damage calculation, health and armor systems, and the logic for power-ups and inventory items.


**Related Classes/Methods**:

- `g_combat.c`
- `g_weapon.c`
- `g_items.c`


### Client Commands
Processes and executes game-specific commands sent from the client. This includes player actions like using items, changing weapons, or activating objectives, which are then validated and run on the server.


**Related Classes/Methods**:

- `g_cmds.c`


### Game API
Defines the bidirectional contract between the game logic module and the main engine. It consists of functions exported by the game logic (`game_export_t`) for the server to call (e.g., `G_RunFrame`), and a table of functions imported from the engine (`game_import_t`) that the game logic uses to call back into the engine for services like console commands or filesystem access.


**Related Classes/Methods**:

- `g_public.h`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)