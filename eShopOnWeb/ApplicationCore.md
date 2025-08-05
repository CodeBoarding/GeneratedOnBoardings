```mermaid
graph LR
    ApplicationCore["ApplicationCore"]
    Infrastructure["Infrastructure"]
    Web["Web"]
    PublicApi["PublicApi"]
    BlazorAdmin["BlazorAdmin"]
    ApplicationCore -- "depends on" --> Infrastructure
    Web -- "uses" --> ApplicationCore
    PublicApi -- "uses" --> ApplicationCore
    BlazorAdmin -- "uses" --> ApplicationCore
    click ApplicationCore href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/ApplicationCore.md" "Details"
    click Infrastructure href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Infrastructure.md" "Details"
    click Web href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/Web.md" "Details"
    click PublicApi href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/PublicApi.md" "Details"
    click BlazorAdmin href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/eShopOnWeb/BlazorAdmin.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of a .NET project with identified components and their general relationships.

### ApplicationCore [[Expand]](./ApplicationCore.md)
Core application logic and business rules.


**Related Classes/Methods**: _None_

### Infrastructure [[Expand]](./Infrastructure.md)
Handles data access, external services, and other infrastructure concerns.


**Related Classes/Methods**: _None_

### Web [[Expand]](./Web.md)
Web-facing components, likely ASP.NET Core MVC or Razor Pages.


**Related Classes/Methods**: _None_

### PublicApi [[Expand]](./PublicApi.md)
Provides an API for external consumption.


**Related Classes/Methods**: _None_

### BlazorAdmin [[Expand]](./BlazorAdmin.md)
Administrative interface built with Blazor.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)