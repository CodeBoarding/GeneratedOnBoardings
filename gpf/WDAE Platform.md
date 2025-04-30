## WDAE Platform Overview

The WDAE Platform serves as the web application layer for the GPF project, providing a REST API, managing user interactions, transforming data for the web interface, and orchestrating communication with the core GPF components. It acts as the primary interface for users to access and interact with the underlying genomic data and analysis capabilities.

```mermaid
componentDiagram
    User_Client [User/Client]
    WDAE_API_Views [WDAE API/Views]
    WDAE_User_Management [WDAE User Management]
    Study_Query_Transformer [Study Query Transformer]
    Remote_Extension_Loading [Remote Extension Loading]
    Core_GPF [Core GPF Components]
    WDAE_CLI [WDAE CLI]
    User_Management_Commands [User Management Commands]
    Import_Tools_CLI [Import Tools CLI]

    User_Client --> WDAE_API_Views : Sends Requests

    WDAE_API_Views --> WDAE_User_Management : Manages Users/Auth
    WDAE_API_Views --> Study_Query_Transformer : Prepares Data Queries

    WDAE_User_Management --> WDAE_API_Views : Provides User Data/Auth Status

    Study_Query_Transformer --> Core_GPF : Queries Data

    Remote_Extension_Loading --> Core_GPF : Registers Extensions

    WDAE_CLI --> WDAE_User_Management : Initializes/Configures
    WDAE_CLI --> Remote_Extension_Loading : Initializes/Configures

    User_Management_Commands --> WDAE_User_Management : Administers Users

    Import_Tools_CLI --> Core_GPF : Imports Data
```

### Component Descriptions:

*   **User/Client**: Represents the end-user interacting with the WDAE platform through a web browser or API client. It initiates requests for data, authentication, account management, and other functionalities provided by the WDAE API/Views.
    *   *Relevant Files*: N/A (External entity)

*   **WDAE API/Views**: This component encompasses the various API endpoints and web views that receive and process incoming HTTP requests from the User/Client. It handles routing requests to the appropriate backend logic, interacts with user management for authentication and authorization, and utilizes the query transformer for data requests.
    *   *Relevant Files*: `repos.gpf.wdae.wdae.genomes_api.views`, `repos.gpf.wdae.wdae.users_api.views`

*   **WDAE User Management**: This component is responsible for handling all aspects of user accounts, including creation, authentication, authorization, password management, and data serialization/deserialization. It provides the core logic and data models for managing users within WDAE.
    *   *Relevant Files*: `repos.gpf.wdae.wdae.users_api.serializers`, `repos.gpf.wdae.wdae.users_api.models`, `repos.gpf.wdae.wdae.users_api.forms`

*   **Study Query Transformer**: This component takes user-provided query parameters from the API/Views and transforms them into a structured format that can be understood and processed by the Core GPF Components for retrieving study data. It handles the translation of web-based filters and criteria into backend queries.
    *   *Relevant Files*: `repos.gpf.wdae.wdae.studies.query_transformer.QueryTransformer`

*   **Remote Extension Loading**: This component is responsible for discovering, loading, and registering remote GPF extensions, such as studies or gene sets, from federated sources. It allows the WDAE platform to access data and functionalities distributed across different GPF instances.
    *   *Relevant Files*: `repos.gpf.federation.federation.remote.remote_extension`

*   **Core GPF Components**: This represents the underlying libraries and data access layers of the GPF project. It is responsible for storing, managing, querying, and analyzing genomic data. WDAE interacts with these components to fulfill user data requests and utilize core GPF functionalities.
    *   *Relevant Files*: `dae.import_tools.cli` (as it interacts with GPF core for import)

*   **WDAE CLI**: The command-line interface entry point for the WDAE application. It is used for initial setup, configuration, and starting the WDAE web server, which in turn initializes other WDAE components.
    *   *Relevant Files*: `repos.gpf.wdae.wdae.wdae.wgpf.cli`

*   **User Management Commands**: A set of command-line tools designed for administrative tasks related to user management, such as importing users or cleaning up user-related data, operating directly on the WDAE User Management models.
    *   *Relevant Files*: `repos.gpf.wdae.wdae.users_api.management.commands.import_base`, `repos.gpf.wdae.wdae.users_api.management.commands.groups_cleanup`

*   **Import Tools CLI**: The command-line interface for importing various types of data into the GPF system. It orchestrates the data loading and transformation process, interacting directly with the Core GPF Components.
    *   *Relevant Files*: `dae.import_tools.cli`
