```mermaid
graph LR
    itchatmp_controllers_common["itchatmp.controllers.common"]
    itchatmp_controllers_mpapi_base_common["itchatmp.controllers.mpapi.base.common"]
    itchatmp_models_common["itchatmp.models.common"]
    itchatmp_controllers_mpapi_mp["itchatmp.controllers.mpapi.mp"]
    itchatmp_controllers_mpapi_qy["itchatmp.controllers.mpapi.qy"]
    itchatmp_controllers_mpapi_base_common -- "interacts with" --> itchatmp_models_common
    itchatmp_controllers_mpapi_mp -- "depends on" --> itchatmp_controllers_mpapi_base_common
    itchatmp_controllers_mpapi_qy -- "depends on" --> itchatmp_controllers_mpapi_base_common
    itchatmp_controllers_common -- "routes requests to" --> itchatmp_controllers_mpapi_mp
    itchatmp_controllers_common -- "routes requests to" --> itchatmp_controllers_mpapi_qy
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The itchatmp controllers subsystem provides a robust and modular architecture for interacting with WeChat APIs. It is anchored by itchatmp.controllers.mpapi.base.common, which manages essential foundational services like access token handling and WeChat server IP list maintenance, persisting this vital data via itchatmp.models.common. Building on this foundation, itchatmp.controllers.mpapi.mp and itchatmp.controllers.mpapi.qy serve as specialized clients, each dedicated to comprehensive API interactions for WeChat Official Accounts and Enterprise Accounts, respectively. itchatmp.controllers.common acts as the primary entry point and intelligent dispatching layer, dynamically routing incoming API requests to the correct specialized client, thereby ensuring a streamlined and adaptable interface for diverse WeChat API operations.

### itchatmp.controllers.common
Primarily a routing and dispatching layer, acting as a central dispatcher and managing request flow. It is the primary entry point and intelligent dispatching layer for incoming API requests.


**Related Classes/Methods**: _None_

### itchatmp.controllers.mpapi.base.common
Manages essential foundational services like access token handling and WeChat server IP list maintenance, providing core infrastructure for the subsystem.


**Related Classes/Methods**: _None_

### itchatmp.models.common
Provides persistent storage for critical operational data, specifically for access tokens and server IP lists.


**Related Classes/Methods**: _None_

### itchatmp.controllers.mpapi.mp
A specialized API client dedicated to comprehensive API interactions for WeChat Official Accounts.


**Related Classes/Methods**: _None_

### itchatmp.controllers.mpapi.qy
A specialized API client dedicated to comprehensive API interactions for WeChat Enterprise Accounts.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)