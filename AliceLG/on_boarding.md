```mermaid
graph LR
    Add_on_Core["Add-on Core"]
    Configuration_State_Management["Configuration & State Management"]
    User_Interface_UI_["User Interface (UI)"]
    Lightfield_Processing["Lightfield Processing"]
    Viewport_Display["Viewport Display"]
    External_Device_Integration["External Device Integration"]
    Add_on_Core -- "orchestrates" --> User_Interface_UI_
    Add_on_Core -- "initializes" --> Configuration_State_Management
    Add_on_Core -- "coordinates" --> Lightfield_Processing
    Add_on_Core -- "coordinates" --> Viewport_Display
    Configuration_State_Management -- "provides settings to" --> User_Interface_UI_
    Configuration_State_Management -- "provides settings to" --> Lightfield_Processing
    Configuration_State_Management -- "provides settings to" --> Viewport_Display
    User_Interface_UI_ -- "triggers" --> Lightfield_Processing
    User_Interface_UI_ -- "interacts with" --> Viewport_Display
    User_Interface_UI_ -- "modifies" --> Configuration_State_Management
    Lightfield_Processing -- "consumes" --> Configuration_State_Management
    Lightfield_Processing -- "utilizes" --> External_Device_Integration
    Lightfield_Processing -- "provides data to" --> Viewport_Display
    Viewport_Display -- "consumes" --> Configuration_State_Management
    External_Device_Integration -- "provides services to" --> Lightfield_Processing
    click Configuration_State_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/AliceLG/Configuration_State_Management.md" "Details"
    click User_Interface_UI_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/AliceLG/User_Interface_UI_.md" "Details"
    click Lightfield_Processing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/AliceLG/Lightfield_Processing.md" "Details"
    click Viewport_Display href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/AliceLG/Viewport_Display.md" "Details"
    click External_Device_Integration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/AliceLG/External_Device_Integration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Add-on Core
The central orchestrator for the Blender add-on, managing its lifecycle (registration, unregistration) and coordinating the initialization and interaction between other core components.


**Related Classes/Methods**:

- `AliceLG.__init__`


### Configuration & State Management [[Expand]](./Configuration_State_Management.md)
Manages all global application state, user preferences, and configurable settings, providing a centralized and consistent data source for other components.


**Related Classes/Methods**:

- <a href="https://github.com/regcs/AliceLG/blob/master/globals.py" target="_blank" rel="noopener noreferrer">`AliceLG.globals`</a>
- `AliceLG.preferences`


### User Interface (UI) [[Expand]](./User_Interface_UI_.md)
Provides all interactive elements within Blender, including panels, menus, and operators, enabling users to control the add-on's features and visualize its status.


**Related Classes/Methods**:

- `AliceLG.ui`


### Lightfield Processing [[Expand]](./Lightfield_Processing.md)
Encapsulates the core logic for generating, processing, and preparing lightfield data for holographic display, including rendering and data manipulation.


**Related Classes/Methods**:

- <a href="https://github.com/regcs/AliceLG/blob/master/lightfield_render.py" target="_blank" rel="noopener noreferrer">`AliceLG.lightfield_render`</a>


### Viewport Display [[Expand]](./Viewport_Display.md)
Manages the real-time display and interactive representation of lightfield content directly within Blender's 3D viewport, providing visual feedback to the user.


**Related Classes/Methods**:

- `AliceLG.lightfield_viewport`


### External Device Integration [[Expand]](./External_Device_Integration.md)
Handles all communication and data exchange with external holographic display services or hardware, primarily through the pyLightIO library, using protocols like CBOR and RPC.


**Related Classes/Methods**:

- `AliceLG.lib.pylightio`
- `AliceLG.lib.pylightio.external.cbor.cbor`
- `AliceLG.lib.pylightio.external.cbor.cbor_rpc_client`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)