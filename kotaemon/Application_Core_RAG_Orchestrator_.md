```mermaid
graph LR
    Application_Orchestrator_make_["Application Orchestrator (make)"]
    Core_Initializer___init___["Core Initializer (__init__)"]
    Public_Event_Declarer_declare_public_events_["Public Event Declarer (declare_public_events)"]
    Public_Event_Subscriber_subscribe_public_events_["Public Event Subscriber (subscribe_public_events)"]
    Event_Registrar_register_events_["Event Registrar (register_events)"]
    Application_Post_Creation_Hook_on_app_created_["Application Post-Creation Hook (on_app_created)"]
    UI_Renderer_render_["UI Renderer (render)"]
    UI_Unrenderer_unrender_["UI Unrenderer (unrender)"]
    Application_Orchestrator_make_ -- "leverages" --> Core_Initializer___init___
    Application_Orchestrator_make_ -- "calls" --> Event_Registrar_register_events_
    Application_Orchestrator_make_ -- "calls" --> Public_Event_Subscriber_subscribe_public_events_
    Application_Orchestrator_make_ -- "calls" --> Public_Event_Declarer_declare_public_events_
    Application_Orchestrator_make_ -- "calls" --> Application_Post_Creation_Hook_on_app_created_
    Application_Orchestrator_make_ -- "enables" --> UI_Renderer_render_
    Application_Orchestrator_make_ -- "enables" --> UI_Unrenderer_unrender_
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Application Core (RAG Orchestrator) subsystem is centered around the libs.ktem.ktem.app module, which serves as the primary control plane for the entire RAG UI framework. Its boundaries are defined by the functionalities encapsulated within this module, specifically its methods responsible for initialization, orchestration, event management, and UI rendering.

### Application Orchestrator (make)
The main entry point for starting the RAG UI application. It orchestrates the entire startup sequence, ensuring all necessary components are initialized and configured, acting as the primary coordinator for the RAG pipeline flow.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:make`</a>


### Core Initializer (__init__)
Initializes the fundamental components of the RAG application, including extensions, data indexing, and reasoning modules. This is where the various pluggable RAG pipeline stages are set up and registered.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:__init__`</a>


### Public Event Declarer (declare_public_events)
Manages the eventing system within the application by defining and making events available for communication and coordination across different RAG pipeline stages and extensions.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:declare_public_events`</a>


### Public Event Subscriber (subscribe_public_events)
Manages the eventing system within the application by handling subscriptions for events that facilitate communication and coordination across different RAG pipeline stages and extensions.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:subscribe_public_events`</a>


### Event Registrar (register_events)
Manages the eventing system within the application by registering events that facilitate communication and coordination across different RAG pipeline stages and extensions.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:register_events`</a>


### Application Post-Creation Hook (on_app_created)
Executes specific tasks immediately after the RAG application has been fully initialized. This allows for final configurations, service startups, or any actions that depend on the complete application state.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:on_app_created`</a>


### UI Renderer (render)
Handles the display and update of the RAG application's user interface, making the RAG pipeline accessible to users.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:render`</a>


### UI Unrenderer (unrender)
Manages the removal and cleanup of UI components, ensuring proper resource management when the UI is no longer needed or is being reconfigured.


**Related Classes/Methods**:

- <a href="https://github.com/Cinnamon/kotaemon/blob/main/libs/ktem/ktem/app.py" target="_blank" rel="noopener noreferrer">`libs.ktem.ktem.app:unrender`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)