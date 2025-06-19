```mermaid
graph LR
    Client_Applications["Client Applications"]
    ClientApp["ClientApp"]
    WebApp["WebApp"]
    HybridApp["HybridApp"]
    Product_Catalog_API["Product Catalog API"]
    Basket_API["Basket API"]
    Ordering_API["Ordering API"]
    Identity_API["Identity API"]
    Mobile_BFF_Shopping["Mobile BFF Shopping"]
    Client_Applications -- "encompasses" --> ClientApp
    Client_Applications -- "encompasses" --> WebApp
    Client_Applications -- "encompasses" --> HybridApp
    Client_Applications -- "requests product data from" --> Product_Catalog_API
    Client_Applications -- "manages shopping basket with" --> Basket_API
    Client_Applications -- "places orders and retrieves order history from" --> Ordering_API
    Client_Applications -- "authenticates and manages user profiles with" --> Identity_API
    ClientApp -- "utilizes" --> Mobile_BFF_Shopping
    HybridApp -- "utilizes" --> Mobile_BFF_Shopping
    click Client_Applications href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//eShop/Client_Applications.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

This overarching component represents the user-facing applications that serve as the primary interface for end-users to interact with the eShop system. It encompasses three distinct sub-components: a mobile application, a web application, and a hybrid application. Their collective purpose is to provide a seamless and intuitive experience for users to browse products, manage their shopping baskets, place orders, and view their order history.

### Client Applications
This overarching component represents the user-facing applications that serve as the primary interface for end-users to interact with the eShop system. It encompasses three distinct sub-components: a mobile application, a web application, and a hybrid application. Their collective purpose is to provide a seamless and intuitive experience for users to browse products, manage their shopping baskets, place orders, and view their order history.


**Related Classes/Methods**: _None_

### ClientApp
Represents the mobile application.


**Related Classes/Methods**: _None_

### WebApp
Represents the web application.


**Related Classes/Methods**: _None_

### HybridApp
Represents the hybrid application.


**Related Classes/Methods**: _None_

### Product Catalog API
API for retrieving product data.


**Related Classes/Methods**: _None_

### Basket API
API for managing shopping baskets.


**Related Classes/Methods**: _None_

### Ordering API
API for placing orders and retrieving order history.


**Related Classes/Methods**: _None_

### Identity API
API for user authentication and profile management.


**Related Classes/Methods**: _None_

### Mobile BFF Shopping
Backend For Frontend (BFF) for mobile clients, aggregating calls to multiple microservices.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)