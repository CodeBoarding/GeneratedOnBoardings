```mermaid
graph LR
    Client_Applications["Client Applications"]
    Core_E_commerce_Services["Core E-commerce Services"]
    Messaging_Eventing_System["Messaging & Eventing System"]
    Data_Storage["Data Storage"]
    Client_Applications -- "interacts with" --> Core_E_commerce_Services
    Core_E_commerce_Services -- "communicates via" --> Messaging_Eventing_System
    Core_E_commerce_Services -- "persists data to" --> Data_Storage
    Messaging_Eventing_System -- "facilitates communication for" --> Core_E_commerce_Services
    Data_Storage -- "stores data for" --> Core_E_commerce_Services
    click Client_Applications href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShopOnAzure/Client_Applications.md" "Details"
    click Core_E_commerce_Services href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShopOnAzure/Core_E_commerce_Services.md" "Details"
    click Messaging_Eventing_System href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShopOnAzure/Messaging_Eventing_System.md" "Details"
    click Data_Storage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShopOnAzure/Data_Storage.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

Final Architecture Overview for eShopOnAzure

### Client Applications
Provides all user-facing interfaces, including the web application, native mobile application, hybrid application, and a dedicated webhook client. These applications are responsible for user interaction, data presentation, and initiating business processes.


**Related Classes/Methods**:

- `src/WebApp/` (1:1)
- `src/ClientApp/` (1:1)
- `src/HybridApp/` (1:1)
- `src/WebhookClient/` (1:1)


### Core E-commerce Services
Encapsulates the primary business logic of the e-commerce system. This includes managing the product catalog, handling shopping baskets, processing orders, managing payments, and dispatching webhooks. It also features a Mobile Backend for Frontend (BFF) to optimize mobile client interactions and a background order processor for specific order-related tasks.


**Related Classes/Methods**:

- `src/Catalog.API/` (1:1)
- `src/Basket.API/` (1:1)
- `src/Ordering.API/` (1:1)
- `src/Ordering.Domain/` (1:1)
- `src/Ordering.Infrastructure/` (1:1)
- `src/PaymentProcessor/` (1:1)
- `src/Webhooks.API/` (1:1)
- `src/Mobile.Bff.Shopping/` (1:1)
- `src/OrderProcessor/` (1:1)


### Messaging & Eventing System
Facilitates asynchronous, event-driven communication between the various microservices. It provides an abstract event bus, an Azure Service Bus implementation for message queuing, and an integration event log to ensure reliable event publishing through a transactional outbox pattern.


**Related Classes/Methods**:

- `src/EventBus/` (1:1)
- `src/EventBusServiceBus/` (1:1)
- `src/IntegrationEventLogEF/` (1:1)


### Data Storage
Provides the persistent storage and caching mechanisms for all application data. This includes relational databases for the product catalog, order details, and webhook subscriptions, as well as a Redis cache for temporary user shopping basket data.


**Related Classes/Methods**:

- `src/Catalog.API/Infrastructure/` (1:1)
- `src/Basket.API/Repositories/` (1:1)
- `src/Ordering.Infrastructure/` (1:1)
- `src/Webhooks.API/Infrastructure/` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)