```mermaid
graph LR
    ApplicationCore["ApplicationCore"]
    Infrastructure["Infrastructure"]
    Web["Web"]
    PublicApi["PublicApi"]
    BlazorAdmin["BlazorAdmin"]
    Tests["Tests"]
    Infrastructure -- "depends on" --> ApplicationCore
    Web -- "uses" --> ApplicationCore
    PublicApi -- "uses" --> ApplicationCore
    BlazorAdmin -- "consumes" --> PublicApi
    Tests -- "interacts with" --> ApplicationCore
    Tests -- "interacts with" --> Infrastructure
    Tests -- "interacts with" --> Web
    Tests -- "interacts with" --> PublicApi
    Tests -- "interacts with" --> BlazorAdmin
    click ApplicationCore href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/ApplicationCore.md" "Details"
    click Infrastructure href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Infrastructure.md" "Details"
    click Web href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Web.md" "Details"
    click PublicApi href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/PublicApi.md" "Details"
    click BlazorAdmin href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/BlazorAdmin.md" "Details"
    click Tests href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Tests.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This analysis describes a .NET project architecture. Specific code references could not be provided as the available tools are for Python, and the project context (e.g., package name) was not supplied for a .NET codebase.

### ApplicationCore [[Expand]](./ApplicationCore.md)
Encapsulates the core business logic, domain models, and application services. It defines the interfaces for data access and external services, ensuring the business rules remain independent of infrastructure concerns.


**Related Classes/Methods**: _None_

### Infrastructure [[Expand]](./Infrastructure.md)
Implements data persistence (e.g., Entity Framework Core with SQL Server) and integrates with external services. It provides concrete implementations for interfaces defined in ApplicationCore, adhering to the Dependency Inversion Principle.


**Related Classes/Methods**: _None_

### Web [[Expand]](./Web.md)
The primary presentation layer for the customer-facing e-commerce website, built with ASP.NET Core MVC/Razor Pages. It handles user requests, renders views, and interacts with ApplicationCore to fulfill business operations.


**Related Classes/Methods**: _None_

### PublicApi [[Expand]](./PublicApi.md)
An ASP.NET Core Web API serving as the primary interface for external clients, including the BlazorAdmin application. It exposes RESTful endpoints for various e-commerce functionalities and interacts with ApplicationCore to process requests.


**Related Classes/Methods**: _None_

### BlazorAdmin [[Expand]](./BlazorAdmin.md)
A client-side Blazor WebAssembly application providing a rich administrative user interface. It enables back-office operations such as product management, order processing, and user administration by consuming the PublicApi.


**Related Classes/Methods**: _None_

### Tests [[Expand]](./Tests.md)
A collection of test projects (e.g., unit, integration, and UI tests) that ensure the correctness, reliability, and maintainability of all other components. It covers ApplicationCore, Infrastructure, Web, PublicApi, and BlazorAdmin.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)