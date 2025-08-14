```mermaid
graph LR
    Application_Host["Application Host"]
    Service_Defaults["Service Defaults"]
    Application_Host -- "utilizes configurations from" --> Service_Defaults
    Application_Host -- "provisions dependencies from" --> Service_Defaults
    click Application_Host href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShopOnAzure/Application_Host.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

Abstract Components Overview for Application Host & Shared Defaults

### Application Host
This component is responsible for orchestrating the deployment, execution, and lifecycle management of all microservices and client applications within the eShop solution. It acts as the central point for defining how services are launched, configured, and interconnected.


**Related Classes/Methods**:

- `eShop.AppHost/Program.cs` (0:0)


### Service Defaults
This component encapsulates common configurations, extensions, and shared utilities that are consistently applied across multiple microservices. This includes functionalities like authentication, OpenAPI (Swagger) setup, health checks, and other cross-cutting concerns. Its purpose is to promote consistency, reduce duplication, and simplify the development of individual services.


**Related Classes/Methods**:

- `eShop.ServiceDefaults/Extensions.cs` (0:0)
- `eShop.ServiceDefaults/AuthenticationExtensions.cs` (0:0)
- `eShop.ServiceDefaults/OpenApi.Extensions.cs` (0:0)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)