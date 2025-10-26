```mermaid
graph LR
    GitHub_IPC_Handler["GitHub IPC Handler"]
    Vercel_IPC_Handler["Vercel IPC Handler"]
    Supabase_IPC_Handler["Supabase IPC Handler"]
    Neon_IPC_Handler["Neon IPC Handler"]
    Supabase_Management_Client["Supabase Management Client"]
    Neon_Management_Client["Neon Management Client"]
    IPC_Host["IPC Host"]
    Frontend_Connectors["Frontend Connectors"]
    Utility_Modules["Utility Modules"]
    Settings_Module["Settings Module"]
    GitHub_IPC_Handler -- "registers with" --> IPC_Host
    GitHub_IPC_Handler -- "sends data to" --> Frontend_Connectors
    GitHub_IPC_Handler -- "utilizes" --> Utility_Modules
    GitHub_IPC_Handler -- "interacts with" --> Settings_Module
    Vercel_IPC_Handler -- "registers with" --> IPC_Host
    Vercel_IPC_Handler -- "communicates with" --> Frontend_Connectors
    Vercel_IPC_Handler -- "utilizes" --> Utility_Modules
    Vercel_IPC_Handler -- "interacts with" --> Settings_Module
    Supabase_IPC_Handler -- "registers with" --> IPC_Host
    Supabase_IPC_Handler -- "delegates to" --> Supabase_Management_Client
    Supabase_IPC_Handler -- "utilizes" --> Utility_Modules
    Supabase_IPC_Handler -- "interacts with" --> Settings_Module
    Neon_IPC_Handler -- "registers with" --> IPC_Host
    Neon_IPC_Handler -- "leverages" --> Neon_Management_Client
    Neon_IPC_Handler -- "utilizes" --> Utility_Modules
    Neon_IPC_Handler -- "interacts with" --> Settings_Module
    Supabase_Management_Client -- "interacts with" --> Settings_Module
    Supabase_Management_Client -- "utilizes" --> Utility_Modules
    Neon_Management_Client -- "interacts with" --> Settings_Module
    Neon_Management_Client -- "utilizes" --> Utility_Modules
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### GitHub IPC Handler
Manages all Inter-Process Communication (IPC) related to GitHub, including repository connection, creation, listing, branch retrieval, synchronization, and OAuth device flow. It acts as the bridge between the frontend and GitHub-specific operations.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/ipc/handlers/github_handlers.ts" target="_blank" rel="noopener noreferrer">`src/ipc/handlers/github_handlers.ts`</a>


### Vercel IPC Handler
Manages all IPC communications related to Vercel, covering project connections, creation, listing, deployment, and access token validation.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/ipc/handlers/vercel_handlers.ts" target="_blank" rel="noopener noreferrer">`src/ipc/handlers/vercel_handlers.ts`</a>


### Supabase IPC Handler
Handles Supabase project connections and the OAuth return process. It delegates core API interactions to the Supabase Management Client.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/ipc/handlers/supabase_handlers.ts" target="_blank" rel="noopener noreferrer">`src/ipc/handlers/supabase_handlers.ts`</a>


### Neon IPC Handler
Manages Neon project connections, often coordinating with the Neon Management Client for underlying API operations.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/ipc/handlers/neon_handlers.ts" target="_blank" rel="noopener noreferrer">`src/ipc/handlers/neon_handlers.ts`</a>


### Supabase Management Client
Provides a low-level client for direct interaction with the Supabase Management API, handling function deployment/deletion, SQL execution, and authentication token management.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/supabase_admin/supabase_management_client.ts" target="_blank" rel="noopener noreferrer">`src/supabase_admin/supabase_management_client.ts`</a>


### Neon Management Client
Offers a client for interacting with the Neon API, including obtaining client instances, retrieving organization IDs, and refreshing tokens.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/neon_admin/neon_management_client.ts" target="_blank" rel="noopener noreferrer">`src/neon_admin/neon_management_client.ts`</a>


### IPC Host
Manages Inter-Process Communication by listening for and routing requests.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/ipc/ipc_host.ts" target="_blank" rel="noopener noreferrer">`src/ipc/ipc_host.ts`</a>


### Frontend Connectors
Handles communication with the frontend, sending operation results and data.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/components/GitHubConnector.tsx" target="_blank" rel="noopener noreferrer">`src/components/GitHubConnector.tsx`</a>


### Utility Modules
Provides common functionalities such as error handling and concurrency.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/utils/codebase.ts" target="_blank" rel="noopener noreferrer">`src/utils/codebase.ts`</a>


### Settings Module
Manages persistent configuration and token management.


**Related Classes/Methods**:

- <a href="https://github.com/dyad-sh/dyad/blob/main/src/main/settings.ts" target="_blank" rel="noopener noreferrer">`src/main/settings.ts`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)