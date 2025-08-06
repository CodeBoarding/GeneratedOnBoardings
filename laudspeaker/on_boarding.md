```mermaid
graph LR
    Frontend_Application["Frontend Application"]
    API_Server["API Server"]
    Workflow_Engine["Workflow Engine"]
    Worker_Services["Worker Services"]
    Database["Database"]
    Frontend_Application -- "Sends user requests to manage workflows and view data." --> API_Server
    API_Server -- "Stores and retrieves all application data like user accounts, workflow states, and customer information." --> Database
    API_Server -- "Publishes events (e.g., 'start-campaign') to the workflow engine when triggered by user actions or schedules." --> Workflow_Engine
    Workflow_Engine -- "Consumes data change events (e.g., new users) from the database via Kafka Connect." --> Database
    Workflow_Engine -- "Publishes task-specific messages (e.g., 'send-email') to be handled by workers." --> Worker_Services
    Worker_Services -- "Consume tasks from the message queue and execute them." --> Workflow_Engine
    Worker_Services -- "Read necessary data (e.g., email templates, user details) and update task statuses." --> Database
    click Frontend_Application href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/laudspeaker/Frontend_Application.md" "Details"
    click API_Server href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/laudspeaker/API_Server.md" "Details"
    click Workflow_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/laudspeaker/Workflow_Engine.md" "Details"
    click Worker_Services href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/laudspeaker/Worker_Services.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Frontend Application [[Expand]](./Frontend_Application.md)
A client-side application, likely built with a modern JavaScript framework like React, that provides the user interface for the platform. It is responsible for all user-facing interactions, such as building marketing journeys and viewing analytics.


**Related Classes/Methods**:

- `Dockerfile.dev.client`
- `Dockerfile.prod.client`


### API Server [[Expand]](./API_Server.md)
The central backend service that exposes a REST or GraphQL API. It handles business logic, authentication, and data validation, acting as the primary intermediary between the frontend client and the backend infrastructure.


**Related Classes/Methods**:

- `Dockerfile.dev.server`
- `Dockerfile.prod.server`
- `env-server-example`


### Workflow Engine [[Expand]](./Workflow_Engine.md)
An event-driven system responsible for executing the marketing automation workflows. It uses Apache Kafka to manage and process events, such as user sign-ups or product purchases, triggering corresponding actions like sending emails or SMS messages.


**Related Classes/Methods**:

- `local-env/1a_init_kafka_engine.sql`
- `local-env/kafkaconnect/`


### Worker Services [[Expand]](./Worker_Services.md)
These are background processes that subscribe to topics in the Workflow Engine (Kafka) and perform the actual work of a given task, such as sending emails, SMS, or push notifications. This decouples long-running tasks from the API server, ensuring the system remains responsive.


**Related Classes/Methods**:

- `Procfile`


### Database
A PostgreSQL database that serves as the primary data store for the application. It holds all persistent data, including user information, workflow configurations, customer data, and campaign results.


**Related Classes/Methods**:

- `Dockerfile.postgres`
- `local-env/kafkaconnect/postgres-source-connector.json`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)