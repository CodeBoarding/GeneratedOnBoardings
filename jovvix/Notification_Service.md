```mermaid
graph LR
    Notification_Service["Notification Service"]
    User_Authentication_and_Authorization_Ory_Kratos_["User Authentication and Authorization (Ory Kratos)"]
    Quiz_Creation_and_Management_Module["Quiz Creation and Management Module"]
    SMTP_Server_Mailpit_External_SMTP_["SMTP Server (Mailpit/External SMTP)"]
    User_Authentication_and_Authorization_Ory_Kratos_ -- "Triggers Email Sending" --> Notification_Service
    Quiz_Creation_and_Management_Module -- "Triggers Email Sending" --> Notification_Service
    Notification_Service -- "Sends Email Data To" --> SMTP_Server_Mailpit_External_SMTP_
    SMTP_Server_Mailpit_External_SMTP_ -- "Sends Delivery Feedback To" --> Notification_Service
    click Notification_Service href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/jovvix/Notification_Service.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Notification Service [[Expand]](./Notification_Service.md)
The Notification Service is a dedicated backend component responsible for managing and dispatching all transactional email communications within the application. This includes critical user-facing notifications such as account verification, password reset links, and invitations to quizzes. It abstracts the underlying email sending mechanism, ensuring reliable and timely delivery of essential communications.


**Related Classes/Methods**:

- `api.internal.notification` (1:1)
- `api.pkg.email` (1:1)
- `api.configs.mail` (1:1)


### User Authentication and Authorization (Ory Kratos)
This component handles user registration, login, session management, and authorization flows. It triggers email sending for actions like account verification and password resets.


**Related Classes/Methods**: _None_

### Quiz Creation and Management Module
This module manages the creation, editing, and administration of quizzes. It triggers email notifications for events such as inviting users to a quiz or sending quiz-related updates.


**Related Classes/Methods**: _None_

### SMTP Server (Mailpit/External SMTP)
This represents the external Simple Mail Transfer Protocol (SMTP) server responsible for the actual sending of emails. It receives email data from the Notification Service and may provide delivery feedback.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)