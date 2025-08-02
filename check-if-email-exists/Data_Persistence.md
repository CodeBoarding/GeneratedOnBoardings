```mermaid
graph LR
    Email_Verification_Core["Email Verification Core"]
    Data_Persistence["Data Persistence"]
    HTTP_Backend_Service["HTTP Backend Service"]
    CLI_Interface["CLI Interface"]
    Messaging_Queue_Integration["Messaging Queue Integration"]
    Email_Verification_Core -- "stores verification results in" --> Data_Persistence
    HTTP_Backend_Service -- "utilizes" --> Email_Verification_Core
    Email_Verification_Core -- "retrieves data from" --> Data_Persistence
    HTTP_Backend_Service -- "interacts with" --> Data_Persistence
    CLI_Interface -- "utilizes" --> Email_Verification_Core
    CLI_Interface -- "interacts with" --> Data_Persistence
    Messaging_Queue_Integration -- "sends/receives requests/results to/from" --> Email_Verification_Core
    HTTP_Backend_Service -- "utilizes" --> Messaging_Queue_Integration
    click Email_Verification_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/check-if-email-exists/Email_Verification_Core.md" "Details"
    click Data_Persistence href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/check-if-email-exists/Data_Persistence.md" "Details"
    click CLI_Interface href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/check-if-email-exists/CLI_Interface.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Email Verification Core [[Expand]](./Email_Verification_Core.md)
Encapsulates the primary business logic for email verification, including validation rules, external service calls (if any), and core algorithms. It is the central module providing the core utility.


**Related Classes/Methods**:

- `EmailVerificationCore` (1:1)


### Data Persistence [[Expand]](./Data_Persistence.md)
Handles all interactions with the SQL database. This component is responsible for storing and retrieving verification results, application configurations, and managing database schema changes through integrated migration processes using sqlx.


**Related Classes/Methods**:

- `db.mod` (1:1)
- `db.models` (1:1)
- `db.queries` (1:1)
- `db.migrations` (1:1)


### HTTP Backend Service
Provides a RESTful API or similar HTTP interface for external clients to interact with the email verification utility. It handles request parsing, response formatting, and orchestrates calls to the Email Verification Core and Data Persistence.


**Related Classes/Methods**:

- `HttpBackendService` (1:1)


### CLI Interface [[Expand]](./CLI_Interface.md)
Offers a command-line interface for users to perform email verification directly from the terminal, manage configurations, or trigger specific operations.


**Related Classes/Methods**:

- `CliInterface` (1:1)


### Messaging Queue Integration
Manages asynchronous communication with external messaging systems like AWS SQS or RabbitMQ. This component enables processing of verification requests in a decoupled manner, handling message publishing and consumption.


**Related Classes/Methods**:

- `MessagingQueueIntegration` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)