```mermaid
graph LR
    Server_Initialization["Server Initialization"]
    Environment_Configuration["Environment Configuration"]
    SPA_Development_Proxy["SPA Development Proxy"]
    Server_Initialization -- "uses" --> Environment_Configuration
    Server_Initialization -- "uses" --> SPA_Development_Proxy
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Backend Server Core subsystem is primarily defined by the core server setup and configuration files. Its boundaries encompass the main Express server initialization, environment variable management, and development-time frontend proxying.

### Server Initialization
This component is the heart of the backend server. It initializes the Express application, configures global middleware, and sets up the main request dispatching mechanism. It acts as the central entry point for all incoming HTTP requests, routing them to appropriate handlers.


**Related Classes/Methods**:

- <a href="https://github.com/atlassian/atlassian-connect-example-app-node/blob/main/src/server.ts" target="_blank" rel="noopener noreferrer">`src/server.ts`</a>


### Environment Configuration
Responsible for loading and exposing environment variables required by the application. This ensures that sensitive information and configurable parameters (like PORT, NODE_ENV, ATLASSIAN_CONNECT_BASE_URL) are managed externally and securely.


**Related Classes/Methods**:

- <a href="https://github.com/atlassian/atlassian-connect-example-app-node/blob/main/src/env.ts" target="_blank" rel="noopener noreferrer">`src/env.ts`</a>


### SPA Development Proxy
During the development phase, this component acts as a proxy for requests targeting the frontend Single Page Application (SPA). It forwards requests to the local frontend development server, enabling the backend and frontend to run on separate ports while maintaining a unified origin for browser interactions.


**Related Classes/Methods**:

- <a href="https://github.com/atlassian/atlassian-connect-example-app-node/blob/main/src/spa-proxy.ts" target="_blank" rel="noopener noreferrer">`src/spa-proxy.ts`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)