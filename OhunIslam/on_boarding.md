```mermaid
graph LR
    API_Gateway["API Gateway"]
    OhunIslam_Web_API["OhunIslam Web API"]
    OhunIslam_Radio_Service["OhunIslam Radio Service"]
    Database["Database"]
    Message_Broker["Message Broker"]
    API_Gateway -- "Routes requests to" --> OhunIslam_Web_API
    API_Gateway -- "Routes requests to" --> OhunIslam_Radio_Service
    OhunIslam_Web_API -- "Manages data in" --> Database
    OhunIslam_Web_API -- "Subscribes to events from" --> Message_Broker
    OhunIslam_Radio_Service -- "Publishes events to" --> Message_Broker
    click OhunIslam_Web_API href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/OhunIslam/OhunIslam_Web_API.md" "Details"
    click Database href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/OhunIslam/Database.md" "Details"
    click Message_Broker href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/OhunIslam/Message_Broker.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### API Gateway
Serves as the single entry point for all client requests. It routes incoming traffic to the appropriate downstream microservice (`OhunIslam Web API` or `OhunIslam Radio Service`), providing a unified and secure interface to the backend system.


**Related Classes/Methods**:

- `OhunIslam.WebAPI/Controllers/MediaController.cs`
- `OhunIslam.Radio/Controllers/RadioController.cs`


### OhunIslam Web API [[Expand]](./OhunIslam_Web_API.md)
The core backend service responsible for all media management. It handles CRUD operations for media assets and their metadata. It also subscribes to events from the `Message Broker` to receive and process real-time updates from other services, such as stream statistics.


**Related Classes/Methods**:

- `OhunIslam.WebAPI/Program.cs`
- `OhunIslam.WebAPI/Controllers/MediaController.cs`


### OhunIslam Radio Service
A dedicated microservice that manages all live radio streaming functionalities. It controls the state of radio streams and publishes status updates and events (e.g., `StreamStatsUpdate`) to the `Message Broker` to inform the rest of the system.


**Related Classes/Methods**:

- `OhunIslam.Radio/Program.cs`
- `OhunIslam.Radio/Controllers/RadioController.cs`


### Database [[Expand]](./Database.md)
The persistence layer for the `OhunIslam Web API`. It stores all core application data, including media metadata like titles, descriptions, and file locations, as defined by the `MediaContext`.


**Related Classes/Methods**:

- `OhunIslam.WebAPI/Infrastructure/MediaContext.cs`


### Message Broker [[Expand]](./Message_Broker.md)
The central communication backbone that facilitates asynchronous, event-driven communication between microservices. It decouples the `OhunIslam Radio Service` from the `OhunIslam Web API`, allowing for resilient and scalable status updates.


**Related Classes/Methods**:

- `OhunIslam.Radio/Services/RabbitMQService.cs`
- `OhunIslam.WebAPI/Services/RadioMessageSubcriber.cs`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)