```mermaid
graph LR
    ApplicationCore["ApplicationCore"]
    Infrastructure["Infrastructure"]
    Web["Web"]
    PublicApi["PublicApi"]
    BlazorAdmin["BlazorAdmin"]
    Tests["Tests"]
    SQL_Server["SQL Server"]
    Users["Users"]
    External_API_Consumers["External API Consumers"]
    Administrators["Administrators"]
    Web -- "uses" --> ApplicationCore
    PublicApi -- "uses" --> ApplicationCore
    BlazorAdmin -- "uses" --> PublicApi
    ApplicationCore -- "uses" --> Infrastructure
    Infrastructure -- "interacts with" --> SQL_Server
    Web -- "interacts with" --> Users
    PublicApi -- "interacts with" --> External_API_Consumers
    BlazorAdmin -- "interacts with" --> Administrators
    Tests -- "valida tes" --> ApplicationCore
    Tests -- "validates" --> Infrastructure
    Tests -- "validates" --> Web
    Tests -- "validates" --> PublicApi
    click ApplicationCore href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/ApplicationCore.md" "Details"
    click Infrastructure href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Infrastructure.md" "Details"
    click Web href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Web.md" "Details"
    click PublicApi href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/PublicApi.md" "Details"
    click BlazorAdmin href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/BlazorAdmin.md" "Details"
    click Tests href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Tests.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### ApplicationCore [[Expand]](./ApplicationCore.md)
Encapsulates the core business logic, domain models, and application services. It defines interfaces for data access and orchestrates business operations, acting as the central hub for the application's domain.


**Related Classes/Methods**: _None_

### Infrastructure [[Expand]](./Infrastructure.md)
Implements data access logic (e.g., Entity Framework Core for SQL Server) and integrates with external services (e.g., identity, email). It provides concrete implementations for interfaces defined in `ApplicationCore`.


**Related Classes/Methods**: _None_

### Web [[Expand]](./Web.md)
The primary presentation layer for the main e-commerce website, handling user interface rendering, user input, and presentation logic using ASP.NET Core MVC/Razor Pages. It interacts with `ApplicationCore` to fulfill user requests.


**Related Classes/Methods**: _None_

### PublicApi [[Expand]](./PublicApi.md)
Exposes a RESTful API for external clients or other applications to programmatically interact with the e-commerce system. It acts as a facade, translating API requests into calls to `ApplicationCore`.


**Related Classes/Methods**: _None_

### BlazorAdmin [[Expand]](./BlazorAdmin.md)
A client-side Blazor WebAssembly application providing an administrative user interface for managing the e-commerce system. It primarily communicates with the `PublicApi` to perform administrative tasks.


**Related Classes/Methods**: _None_

### Tests [[Expand]](./Tests.md)
Contains various testing projects (unit, integration, functional) to ensure the quality, correctness, and reliability of the `ApplicationCore`, `Infrastructure`, `Web`, and `PublicApi` components.


**Related Classes/Methods**: _None_

### SQL Server
An external relational database management system used by the `Infrastructure` component for persistent data storage.


**Related Classes/Methods**: _None_

### Users
External human users who interact with the `Web` application (the main e-commerce website).


**Related Classes/Methods**: _None_

### External API Consumers
External applications or services that programmatically interact with the e-commerce system via the `PublicApi`.


**Related Classes/Methods**: _None_

### Administrators
External human users with administrative privileges who manage the e-commerce system through the `BlazorAdmin` application.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)