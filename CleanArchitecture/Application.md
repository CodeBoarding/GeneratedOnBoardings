```mermaid
graph LR
    Application["Application"]
    Core["Core"]
    Infrastructure["Infrastructure"]
    Web["Web"]
    Application -- "depends on" --> Core
    Application -- "depends on interfaces from" --> Infrastructure
    Web -- "depends on" --> Application
    click Application href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CleanArchitecture/Application.md" "Details"
    click Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CleanArchitecture/Core.md" "Details"
    click Web href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CleanArchitecture/Web.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Application [[Expand]](./Application.md)
The Application Layer (also known as the Use Cases Project) defines application-specific business logic, use cases (commands and queries), Data Transfer Objects (DTOs), and application services. It orchestrates interactions with the Core (Domain) layer and utilizes interfaces (ports) defined in the Core layer, which are then implemented by the Infrastructure layer. It also defines interfaces for Infrastructure services, adhering to the Dependency Inversion Principle.


**Related Classes/Methods**: _None_

### Core [[Expand]](./Core.md)
Core component.


**Related Classes/Methods**: _None_

### Infrastructure
Infrastructure component.


**Related Classes/Methods**: _None_

### Web [[Expand]](./Web.md)
Web component.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)