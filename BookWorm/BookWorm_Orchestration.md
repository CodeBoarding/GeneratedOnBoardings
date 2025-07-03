```mermaid
graph LR
    BookWorm_AppHost["BookWorm.AppHost"]
    BookWorm_Basket_Service["BookWorm.Basket Service"]
    BookWorm_Catalog_Service["BookWorm.Catalog Service"]
    BookWorm_Ordering_Service["BookWorm.Ordering Service"]
    BookWorm_Rating_Service["BookWorm.Rating Service"]
    PostgreSQL_Database["PostgreSQL Database"]
    Redis_Cache["Redis Cache"]
    Keycloak_Identity_Provider["Keycloak Identity Provider"]
    YARP_API_Gateway["YARP API Gateway"]
    Microservices_Chassis_Shared_Components["Microservices Chassis/Shared Components"]
    BookWorm_AppHost -- "orchestrates" --> BookWorm_Basket_Service
    BookWorm_AppHost -- "orchestrates" --> BookWorm_Catalog_Service
    BookWorm_AppHost -- "orchestrates" --> BookWorm_Ordering_Service
    BookWorm_AppHost -- "orchestrates" --> BookWorm_Rating_Service
    BookWorm_AppHost -- "manages" --> PostgreSQL_Database
    BookWorm_AppHost -- "manages" --> Redis_Cache
    BookWorm_AppHost -- "manages" --> Keycloak_Identity_Provider
    BookWorm_AppHost -- "configures" --> YARP_API_Gateway
    YARP_API_Gateway -- "routes to" --> BookWorm_Basket_Service
    YARP_API_Gateway -- "routes to" --> BookWorm_Catalog_Service
    YARP_API_Gateway -- "routes to" --> BookWorm_Ordering_Service
    YARP_API_Gateway -- "routes to" --> BookWorm_Rating_Service
    BookWorm_Basket_Service -- "uses for persistence" --> PostgreSQL_Database
    BookWorm_Catalog_Service -- "uses for persistence" --> PostgreSQL_Database
    BookWorm_Ordering_Service -- "uses for persistence" --> PostgreSQL_Database
    BookWorm_Rating_Service -- "uses for persistence" --> PostgreSQL_Database
    BookWorm_Basket_Service -- "uses for caching" --> Redis_Cache
    BookWorm_Catalog_Service -- "uses for caching" --> Redis_Cache
    BookWorm_Ordering_Service -- "uses for caching" --> Redis_Cache
    BookWorm_Rating_Service -- "uses for caching" --> Redis_Cache
    BookWorm_Basket_Service -- "interacts with for authentication/authorization" --> Keycloak_Identity_Provider
    BookWorm_Catalog_Service -- "interacts with for authentication/authorization" --> Keycloak_Identity_Provider
    BookWorm_Ordering_Service -- "interacts with for authentication/authorization" --> Keycloak_Identity_Provider
    BookWorm_Rating_Service -- "interacts with for authentication/authorization" --> Keycloak_Identity_Provider
    BookWorm_Basket_Service -- "utilizes" --> Microservices_Chassis_Shared_Components
    BookWorm_Catalog_Service -- "utilizes" --> Microservices_Chassis_Shared_Components
    BookWorm_Ordering_Service -- "utilizes" --> Microservices_Chassis_Shared_Components
    BookWorm_Rating_Service -- "utilizes" --> Microservices_Chassis_Shared_Components
    BookWorm_Ordering_Service -- "interacts with" --> BookWorm_Basket_Service
    BookWorm_Ordering_Service -- "interacts with" --> BookWorm_Catalog_Service
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Component overview for BookWorm Orchestration, focusing on the structure, flow, and purpose of the key components in this .NET Aspire cloud-native microservices application.

### BookWorm.AppHost
The central deployment and management layer for the entire application. It defines, configures, and launches all microservices and their associated infrastructure components (e.g., PostgreSQL, Redis, Keycloak), acting as the single point of entry for running the distributed system.


**Related Classes/Methods**: _None_

### BookWorm.Basket Service
Manages user shopping baskets, allowing users to add, remove, and update items before checkout.


**Related Classes/Methods**: _None_

### BookWorm.Catalog Service
Provides information about available books, including details, pricing, and inventory.


**Related Classes/Methods**: _None_

### BookWorm.Ordering Service
Handles the order placement process, managing order states, and coordinating with other services for fulfillment.


**Related Classes/Methods**: _None_

### BookWorm.Rating Service
Manages user ratings and reviews for books.


**Related Classes/Methods**: _None_

### PostgreSQL Database
The primary relational database used by various microservices for persistent data storage.


**Related Classes/Methods**: _None_

### Redis Cache
A high-performance in-memory data store used for caching, session management, and potentially message brokering.


**Related Classes/Methods**: _None_

### Keycloak Identity Provider
An open-source identity and access management solution providing authentication and authorization services for the application.


**Related Classes/Methods**: _None_

### YARP API Gateway
A reverse proxy that acts as the single entry point for external clients, routing requests to the appropriate microservices.


**Related Classes/Methods**: _None_

### Microservices Chassis/Shared Components
A collection of common infrastructure, cross-cutting concerns, and shared domain models (e.g., logging, metrics, health checks, common data types, event definitions) that all microservices leverage to ensure consistency and reduce boilerplate.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)