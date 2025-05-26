```mermaid
graph LR
    Controller["Controller"]
    ActionRegistry["ActionRegistry"]
    Registry["Registry"]
    Agent["Agent"]
    ProductTelemetry["ProductTelemetry"]
    time_execution_sync["time_execution_sync"]
    time_execution_async["time_execution_async"]
    match_url_with_domain_pattern["match_url_with_domain_pattern"]
    Agent -- "initializes" --> Controller
    Agent -- "executes actions using" --> Controller
    Controller -- "manages browser state and executes actions" --> Controller
    Controller -- "uses" --> time_execution_sync
    Registry -- "initializes" --> ProductTelemetry
    Registry -- "creates action models using" --> ProductTelemetry
    Registry -- "normalizes action function signatures using" --> Registry
    Registry -- "executes actions using" --> time_execution_async
    Registry -- "replaces sensitive data using" --> match_url_with_domain_pattern
    ActionRegistry -- "matches domains using" --> match_url_with_domain_pattern
    Agent -- "registers actions and executes them" --> Registry
    click Controller href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Controller.md" "Details"
    click ActionRegistry href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/ActionRegistry.md" "Details"
    click Registry href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Registry.md" "Details"
    click Agent href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/Agent.md" "Details"
    click ProductTelemetry href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/ProductTelemetry.md" "Details"
    click time_execution_sync href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/time_execution_sync.md" "Details"
    click time_execution_async href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/time_execution_async.md" "Details"
    click match_url_with_domain_pattern href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/browser-use/match_url_with_domain_pattern.md" "Details"
```

## Component Details

The Action Execution & Registry subsystem is responsible for managing and executing actions within the browser automation framework. It provides a structured way to define, register, and execute actions, ensuring that the agent can interact with web pages effectively. The core components work together to handle action registration, execution, and telemetry, providing a robust and extensible system for browser automation.

### Controller
The Controller service is the central component for managing the browser state and executing actions. It initializes the browser environment, including the accessibility tree and drag-and-drop functionality. The `act` method is the primary interface for performing actions in the browser, coordinating with other components to achieve the desired outcome.
- **Related Classes/Methods**: `browser_use.controller.service.Controller`

### ActionRegistry
The ActionRegistry manages the available actions that can be performed in the browser. It maintains a list of registered actions and provides methods for retrieving action descriptions and matching actions to specific domains and pages. This component is crucial for enabling the agent to discover and select appropriate actions based on the current context.
- **Related Classes/Methods**: `browser_use.controller.registry.views.ActionRegistry`

### Registry
The Registry service handles the registration and execution of actions. It normalizes action function signatures, replaces sensitive data, and logs data usage. It also creates action models for telemetry purposes, providing valuable insights into action performance and usage patterns. The Registry acts as an intermediary between the ActionRegistry and the Controller, ensuring that actions are executed correctly and efficiently.
- **Related Classes/Methods**: `browser_use.controller.registry.service.Registry`

### Agent
The Agent service orchestrates the interaction with the browser. It initializes the Controller and sets up action models. It provides the `step` and `multi_act` methods to execute actions in the browser based on agent logic. The Agent uses the Registry to register and execute actions.
- **Related Classes/Methods**: `browser_use.agent.service.Agent`

### ProductTelemetry
The ProductTelemetry service captures telemetry data related to action execution and registration. It is used by the Registry service to track usage and performance, providing valuable insights for improving the browser automation framework. This component helps to monitor and optimize the system's performance and identify potential issues.
- **Related Classes/Methods**: `browser_use.telemetry.service.ProductTelemetry`

### time_execution_sync
Utility function to measure the execution time of synchronous functions. This is used to measure the performance of different actions.
- **Related Classes/Methods**: `browser_use.utils.time_execution_sync`

### time_execution_async
Utility function to measure the execution time of asynchronous functions. This is used to measure the performance of different actions.
- **Related Classes/Methods**: `browser_use.utils.time_execution_async`

### match_url_with_domain_pattern
Utility function to match a URL with a domain pattern. This is used to determine which actions are available on a given page.
- **Related Classes/Methods**: `browser_use.utils.match_url_with_domain_pattern`