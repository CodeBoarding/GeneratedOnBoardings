```mermaid
graph LR
    database_module["database module"]
    insert_payload_function["insert_payload function"]
    insert_url_function["insert_url function"]
    database_module -- "contains" --> insert_payload_function
    database_module -- "contains" --> insert_url_function
```

## Component Details

The Data Storage component is responsible for managing interactions with the database, providing persistent storage for payloads and URLs. It encapsulates the database operations, abstracting them from the rest of the application. The component includes functions for inserting payload and URL data into the database, ensuring data persistence and retrieval.

### database module
The database module provides an abstraction layer for database interactions. It encapsulates the connection details and provides functions for inserting and managing data within the database. This module is the central point for all database operations.
- **Related Classes/Methods**: `WhatWaf.lib.database` (None:None)

### insert_payload function
The insert_payload function is responsible for inserting payload-related data into the database. It receives payload information as input, formats it appropriately, and stores it in the designated database table. This function ensures that payload data is persistently stored for later retrieval and analysis.
- **Related Classes/Methods**: `WhatWaf.lib.database:insert_payload` (54:72)

### insert_url function
The insert_url function handles the insertion of URL-related data into the database. It takes URL information as input, prepares it for storage, and inserts it into the relevant database table. This function ensures that URL data is persistently stored for future use and analysis.
- **Related Classes/Methods**: `WhatWaf.lib.database:insert_url` (75:124)