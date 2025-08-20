```mermaid
graph LR
    gaphor_application_Application["gaphor.application.Application"]
    gaphor_main["gaphor.main"]
    gaphor_core_eventmanager_EventManager["gaphor.core.eventmanager.EventManager"]
    gaphor_entrypoint["gaphor.entrypoint"]
    gaphor_plugins["gaphor.plugins"]
    gaphor_main -- "initiates" --> gaphor_application_Application
    gaphor_application_Application -- "dispatches events through" --> gaphor_core_eventmanager_EventManager
    gaphor_application_Application -- "invokes for extension loading" --> gaphor_entrypoint
    gaphor_core_eventmanager_EventManager -- "notifies" --> gaphor_application_Application
    gaphor_entrypoint -- "provides extensions to" --> gaphor_application_Application
    gaphor_entrypoint -- "uses for plugin preparation" --> gaphor_plugins
    gaphor_plugins -- "provides plugin enabling mechanism to" --> gaphor_entrypoint
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Application Core subsystem is central to the Desktop GUI Application, encompassing key modules and functionalities for application lifecycle management, event dispatching, and extension loading.

### gaphor.application.Application
The primary orchestrator and lifecycle manager of the entire application. It represents the core application instance, responsible for initializing services, managing the application state, and coordinating overall application flow.


**Related Classes/Methods**:

- <a href="https://github.com/gaphor/gaphor/blob/main/gaphor/application.py#L48-L185" target="_blank" rel="noopener noreferrer">`gaphor.application.Application`:48-185</a>


### gaphor.main
The bootstrap component responsible for initializing the application environment, setting up the initial configuration, and starting the main application loop. It acts as the initial entry point for the application.


**Related Classes/Methods**:

- <a href="https://github.com/gaphor/gaphor/blob/main/gaphor/main.py" target="_blank" rel="noopener noreferrer">`gaphor.main`</a>


### gaphor.core.eventmanager.EventManager
The central communication bus, crucial for enabling loosely coupled interactions between various application components. It facilitates event-driven communication, allowing components to react to changes without direct dependencies.


**Related Classes/Methods**:

- <a href="https://github.com/gaphor/gaphor/blob/main/gaphor/core/eventmanager.py#L44-L134" target="_blank" rel="noopener noreferrer">`gaphor.core.eventmanager.EventManager`:44-134</a>


### gaphor.entrypoint
Manages the dynamic discovery and loading of application extensions and plugins. This component is vital for the application's extensibility, allowing new functionalities to be integrated seamlessly.


**Related Classes/Methods**:

- <a href="https://github.com/gaphor/gaphor/blob/main/gaphor/entrypoint.py" target="_blank" rel="noopener noreferrer">`gaphor.entrypoint`</a>


### gaphor.plugins
Provides the underlying mechanism for activating and managing discovered plugins. It works in conjunction with `gaphor.entrypoint` to ensure that loaded plugins are properly initialized and integrated into the application.


**Related Classes/Methods**:

- <a href="https://github.com/gaphor/gaphor/blob/main/gaphor/plugins" target="_blank" rel="noopener noreferrer">`gaphor.plugins`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)