```mermaid
graph LR
    Client_API["Client API"]
    Execution_Runtime["Execution Runtime"]
    Browser_Control_Layer["Browser Control Layer"]
    Serverless_Backend["Serverless Backend"]
    Deployment_Configuration["Deployment & Configuration"]
    Client_API -- "Uses" --> Execution_Runtime
    Client_API -- "Configured by" --> Deployment_Configuration
    Execution_Runtime -- "Controls" --> Browser_Control_Layer
    Execution_Runtime -- "Communicates with" --> Serverless_Backend
    Browser_Control_Layer -- "Controlled by" --> Execution_Runtime
    Browser_Control_Layer -- "Used by" --> Serverless_Backend
    Serverless_Backend -- "Receives commands from" --> Execution_Runtime
    Serverless_Backend -- "Utilizes" --> Browser_Control_Layer
    Serverless_Backend -- "Deployed by" --> Deployment_Configuration
    Deployment_Configuration -- "Deploys" --> Serverless_Backend
    Deployment_Configuration -- "Provides settings to" --> Client_API
    click Client_API href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/chromeless/Client_API.md" "Details"
    click Execution_Runtime href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/chromeless/Execution_Runtime.md" "Details"
    click Browser_Control_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/chromeless/Browser_Control_Layer.md" "Details"
    click Serverless_Backend href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/chromeless/Serverless_Backend.md" "Details"
    click Deployment_Configuration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/chromeless/Deployment_Configuration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Client API [[Expand]](./Client_API.md)
Provides the high-level, fluent interface for users to define browser automation tasks. This is the primary entry point for users interacting with Chromeless.


**Related Classes/Methods**: _None_

### Execution Runtime [[Expand]](./Execution_Runtime.md)
Manages the execution environment for browser automation commands, abstracting whether the commands are run against a local Chrome instance or proxied to a remote serverless environment.


**Related Classes/Methods**: _None_

### Browser Control Layer [[Expand]](./Browser_Control_Layer.md)
Handles the direct interaction with the headless Chrome instance using the Chrome DevTools Protocol, managing browser lifecycle (launch, close) and executing low-level browser commands.


**Related Classes/Methods**: _None_

### Serverless Backend [[Expand]](./Serverless_Backend.md)
Hosts and executes headless Chrome instances as stateless AWS Lambda functions. It receives remote automation commands, processes them, and returns results, optimized for scalability and cold starts.


**Related Classes/Methods**: _None_

### Deployment & Configuration [[Expand]](./Deployment_Configuration.md)
Manages the deployment of serverless resources (Lambda functions, API Gateway) and provides a flexible configuration mechanism for switching between local and remote execution modes, including environment-specific settings.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)