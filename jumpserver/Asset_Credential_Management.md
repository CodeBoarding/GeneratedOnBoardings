```mermaid
graph LR
    Asset_Model["Asset Model"]
    Node_Model["Node Model"]
    Account_Model["Account Model"]
    Secret_Change_Automation_Manager["Secret Change Automation Manager"]
    Vault_Integration_Base["Vault Integration Base"]
    Asset_Model -- "uses" --> Node_Model
    Account_Model -- "accesses" --> Asset_Model
    Node_Model -- "organizes" --> Asset_Model
    Account_Model -- "manages secrets via" --> Secret_Change_Automation_Manager
    Account_Model -- "stores secrets via" --> Vault_Integration_Base
    Secret_Change_Automation_Manager -- "operates on" --> Account_Model
    Secret_Change_Automation_Manager -- "interacts with" --> Asset_Model
    Vault_Integration_Base -- "manages secrets for" --> Account_Model
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `Asset & Credential Management` subsystem in Jumpserver is crucial for defining and managing the IT resources and the credentials used to access them. It establishes the foundational data models and processes for cataloging assets, organizing them hierarchically, and securely managing their associated accounts and secrets.

### Asset Model
This component defines the core `Asset` model, which represents all managed IT resources such as hosts, databases, and cloud assets. It establishes the schema, properties, and connectivity details for these resources, including their associated protocols (e.g., SSH, RDP) and their hierarchical grouping within nodes. It's the central definition of *what* resources Jumpserver manages.


**Related Classes/Methods**: _None_

### Node Model
This component defines the `Node` model, which is responsible for creating and managing the hierarchical structure used to logically group and categorize assets. It provides methods for navigating and querying the node tree, enabling efficient organization and management of resources.


**Related Classes/Methods**: _None_

### Account Model
This component defines the `Account` model, representing the credentials (usernames, passwords, private keys) used to access assets. It stores sensitive account details, manages historical versions of secrets for auditing, and links directly to specific assets, defining *how* Jumpserver accesses resources.


**Related Classes/Methods**: _None_

### Secret Change Automation Manager
This component orchestrates the automated generation, rotation, and verification processes for account secrets. It manages the entire lifecycle of secret changes, including creating records of changes, handling different secret strategies (e.g., custom, random), and sending notifications or reports on the status of these operations.


**Related Classes/Methods**: _None_

### Vault Integration Base
This abstract base class provides a standardized interface for integrating Jumpserver with various external secret management systems (vaults). It defines the core methods for securely storing, retrieving, creating, updating, and deleting sensitive account secrets, ensuring that these credentials are not persistently stored in the local database but rather in a dedicated, secure vault.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)