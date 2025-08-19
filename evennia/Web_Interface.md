```mermaid
graph LR
    evennia_web_admin["evennia.web.admin"]
    evennia_web_website["evennia.web.website"]
    evennia_web_webclient["evennia.web.webclient"]
    evennia_web_api["evennia.web.api"]
    evennia_web_admin -- "interacts with" --> evennia_web_api
    evennia_web_website -- "interacts with" --> evennia_web_api
    evennia_web_webclient -- "interacts with" --> evennia_web_api
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The evennia.web subsystem provides the web-based interfaces and functionalities for the Evennia game engine. It encompasses the administrative panel for game management, the public-facing website for general information, a real-time web client for interactive gameplay, and a programmatic API for external integrations. These components collectively enable web-based interaction with the Evennia server, catering to administrators, players, and external applications.

### evennia.web.admin
Provides a web-based administrative interface for game administrators and developers. This component is crucial for managing various Evennia game entities such as accounts, objects, and game configurations through a user-friendly web portal.


**Related Classes/Methods**:

- <a href="https://github.com/evennia/evennia/blob/main/evennia/web/admin" target="_blank" rel="noopener noreferrer">`evennia.web.admin`</a>


### evennia.web.website
Handles the public-facing website of the Evennia game. This component serves as a general information portal, providing news, game lore, community updates, and potentially player statistics or forums.


**Related Classes/Methods**:

- <a href="https://github.com/evennia/evennia/blob/main/evennia/web/website" target="_blank" rel="noopener noreferrer">`evennia.web.website`</a>


### evennia.web.webclient
Manages real-time, persistent connections for the primary web-based game client. This component typically utilizes WebSockets to enable interactive, low-latency gameplay directly from a web browser, offering a modern alternative to traditional telnet clients.


**Related Classes/Methods**:

- <a href="https://github.com/evennia/evennia/blob/main/evennia/web/webclient" target="_blank" rel="noopener noreferrer">`evennia.web.webclient`</a>


### evennia.web.api
Exposes Evennia's internal data and functionality programmatically through a well-defined API. This allows external applications, tools, or services to interact with the game engine, promoting extensibility and integration within the broader game ecosystem.


**Related Classes/Methods**:

- <a href="https://github.com/evennia/evennia/blob/main/evennia/web/api" target="_blank" rel="noopener noreferrer">`evennia.web.api`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)