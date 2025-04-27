```mermaid
graph LR
    Settings --> Formatter: uses
    Content --> Formatter: uses
    DetectionQueue --> Formatter: uses
    FirewallFound --> Formatter: uses
    FirewallFound --> Settings: uses
    Content --> FirewallFound: uses
    Formatter --> User: displays

    classDef componentFill fill:#f9f,stroke:#333,stroke-width:2px
    class Settings, Formatter, FirewallFound, Content, DetectionQueue, User componentFill
```

