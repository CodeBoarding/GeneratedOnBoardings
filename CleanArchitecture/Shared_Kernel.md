```mermaid
graph LR
    Shared_Kernel["Shared Kernel"]
    Core_Project["Core Project"]
    Use_Cases_Project["Use Cases Project"]
    Infrastructure_Project["Infrastructure Project"]
    Web_Project["Web Project"]
    Core_Project -- "depends on" --> Shared_Kernel
    Use_Cases_Project -- "depends on" --> Shared_Kernel
    Infrastructure_Project -- "depends on" --> Shared_Kernel
    Use_Cases_Project -- "depends on" --> Core_Project
    Infrastructure_Project -- "depends on" --> Core_Project
    Web_Project -- "depends on" --> Use_Cases_Project
    Web_Project -- "depends on" --> Infrastructure_Project
    click Shared_Kernel href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CleanArchitecture/Shared_Kernel.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Shared Kernel [[Expand]](./Shared_Kernel.md)
Contains common elements, utilities, and shared types (e.g., base classes for entities, common exceptions, value objects) that are used across multiple bounded contexts or layers to avoid duplication and ensure consistency. It acts as an external package.


**Related Classes/Methods**: _None_

### Core Project
Represents the innermost layer, containing the domain model, core business rules, and entities. It has no external dependencies other than the Shared Kernel.


**Related Classes/Methods**: _None_

### Use Cases Project
Defines application-specific business rules, orchestrates the flow of data to and from the entities, and implements application-level services. It depends only on the Core Project and Shared Kernel.


**Related Classes/Methods**: _None_

### Infrastructure Project
Handles external concerns like data persistence (databases), external services, and web framework implementations. It implements interfaces defined in the Core Project and depends on Shared Kernel.


**Related Classes/Methods**: _None_

### Web Project
Acts as the entry point for the application, handling user requests, routing, and presentation. It depends on the Use Cases Project to invoke application logic and the Infrastructure Project for setup and external concerns.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)