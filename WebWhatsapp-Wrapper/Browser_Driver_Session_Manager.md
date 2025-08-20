```mermaid
graph LR
    Browser_Driver_Session_Manager_Facade_["Browser Driver & Session Manager (Facade)"]
    Selenium_Interaction_Layer_Low_Level_Driver_["Selenium Interaction Layer (Low-Level Driver)"]
    Browser_Driver_Session_Manager_Facade_ -- "delegates to" --> Selenium_Interaction_Layer_Low_Level_Driver_
    Selenium_Interaction_Layer_Low_Level_Driver_ -- "returns results to" --> Browser_Driver_Session_Manager_Facade_
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Browser Driver & Session Manager` subsystem is primarily encapsulated within the `webwhatsapi.async_driver` module. This module serves as the core component responsible for orchestrating browser interactions, managing the WebDriver instance, and maintaining the state of the WhatsApp Web session.

### Browser Driver & Session Manager (Facade)
This component, represented by the `webwhatsapi.async_driver` class, acts as a high-level facade for all browser-related operations and session management. It provides a simplified API for users to interact with WhatsApp Web, abstracting away the complexities of direct Selenium WebDriver commands. Its responsibilities include initializing and terminating the browser, managing the active session state (e.g., login, page navigation), and offering methods for common WhatsApp Web actions like file downloads.


**Related Classes/Methods**:

- <a href="https://github.com/mukulhase/WebWhatsapp-Wrapper/blob/master/webwhatsapi/async_driver.py" target="_blank" rel="noopener noreferrer">`webwhatsapi.async_driver`</a>


### Selenium Interaction Layer (Low-Level Driver)
This component, embodied by the `webwhatsapi.async_driver._run_async` method (and potentially other internal methods within `async_driver` that directly interact with Selenium), is responsible for executing raw Selenium WebDriver commands and injecting JavaScript into the browser. It translates the high-level requests from the `Browser Driver & Session Manager` into the specific low-level actions required by the browser automation framework.


**Related Classes/Methods**:

- <a href="https://github.com/mukulhase/WebWhatsapp-Wrapper/blob/master/webwhatsapi/async_driver.py#L52-L61" target="_blank" rel="noopener noreferrer">`webwhatsapi.async_driver._run_async`:52-61</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)