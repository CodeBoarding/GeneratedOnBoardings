```mermaid
graph LR
    User_Interface_Remix_Frontend_["User Interface (Remix Frontend)"]
    API_Gateway["API Gateway"]
    Application_Core_ERP_MES_Logic_["Application Core (ERP/MES Logic)"]
    Data_Persistence_Supabase_["Data Persistence (Supabase)"]
    Platform_Services["Platform Services"]
    User_Interface_Remix_Frontend_ -- "requests" --> API_Gateway
    API_Gateway -- "routes to" --> Application_Core_ERP_MES_Logic_
    API_Gateway -- "orchestrates with" --> Platform_Services
    Application_Core_ERP_MES_Logic_ -- "manages data via" --> Data_Persistence_Supabase_
    Application_Core_ERP_MES_Logic_ -- "leverages" --> Platform_Services
    Data_Persistence_Supabase_ -- "serves data to" --> Application_Core_ERP_MES_Logic_
    Data_Persistence_Supabase_ -- "supports" --> Platform_Services
    Platform_Services -- "provides services to" --> API_Gateway
    Platform_Services -- "provides services to" --> Application_Core_ERP_MES_Logic_
    Platform_Services -- "persists data in" --> Data_Persistence_Supabase_
    click API_Gateway href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/carbon/API_Gateway.md" "Details"
    click Application_Core_ERP_MES_Logic_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/carbon/Application_Core_ERP_MES_Logic_.md" "Details"
    click Platform_Services href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/carbon/Platform_Services.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### User Interface (Remix Frontend)
The client-side application providing the user experience, handling user input, and displaying data.


**Related Classes/Methods**:

- `apps/academy/app/root.tsx` (1:1)


### API Gateway [[Expand]](./API_Gateway.md)
The unified entry point for all client and service requests, responsible for routing, validation, and orchestrating interactions with backend logic and services.


**Related Classes/Methods**:

- `packages/database/supabase/functions/lib/api/accounting.ts` (1:1)


### Application Core (ERP/MES Logic) [[Expand]](./Application_Core_ERP_MES_Logic_.md)
Encapsulates the primary business logic for manufacturing operations and enterprise resource planning, including core functionalities like order processing, inventory management, and production scheduling.


**Related Classes/Methods**:

- `packages/database/supabase/functions/lib/scheduling/scheduling-engine.ts` (1:1)


### Data Persistence (Supabase)
Manages all persistent data storage and retrieval for the application, leveraging PostgreSQL and Supabase features like Row-Level Security.


**Related Classes/Methods**:

- `packages/database/supabase/config.toml` (1:1)


### Platform Services [[Expand]](./Platform_Services.md)
A consolidated component providing essential cross-cutting functionalities such as user authentication and authorization, asynchronous job processing, communication (email/notifications), billing, and analytics.


**Related Classes/Methods**:

- `packages/auth/src/services/auth.server.ts` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)