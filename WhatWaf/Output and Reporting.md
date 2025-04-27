```mermaid
graph LR
    Settings --> Formatter
    Settings --> FirewallFound
    Content --> Formatter
    DetectionQueue --> Formatter
    FirewallFound --> Formatter
    FirewallFound --> Settings
    Formatter --> User[User]

    subgraph Components
        Settings("Settings")
        Formatter("Formatter")
        FirewallFound("FirewallFound")
        Content("Content")
        DetectionQueue("DetectionQueue")
    end

    style User fill:#f9f,stroke:#333,stroke-width:2px

    classDef component fill:#fbf,stroke:#333,stroke-width:2px
    class Settings, Formatter, FirewallFound, Content, DetectionQueue component


```

### Component Descriptions:

*   **Settings**: Handles configuration and global settings for the WhatWaf application. It provides settings to the Formatter and FirewallFound components. Relevant source files: `repos.WhatWaf.lib.settings`

*   **Formatter**: Provides a consistent way to output information to the user, with different levels of verbosity and formatting. It receives data from Settings, Content, DetectionQueue, and FirewallFound, and outputs to the User. Relevant source files: `repos.WhatWaf.lib.formatter`

*   **FirewallFound**: Deals with the logic for when a firewall is detected, including the option to create an issue to request a detection script. It uses the Formatter to display messages and interacts with Settings to potentially create issues. Relevant source files: `repos.WhatWaf.lib.firewall_found`

*   **Content**: Contains the main logic for content processing and detection. It uses the Formatter to output detection information. Relevant source files: `repos.WhatWaf.content`

*   **DetectionQueue**: Handles the queueing and processing of detection requests. It uses the Formatter to output information about the detection process. Relevant source files: `repos.WhatWaf.content.DetectionQueue
