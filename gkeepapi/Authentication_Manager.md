```mermaid
graph LR
    gkeepapi_APIAuth["gkeepapi.APIAuth"]
    gkeepapi___init___login["gkeepapi.__init__.login"]
    gkeepapi___init___authenticate["gkeepapi.__init__.authenticate"]
    gkeepapi___init___refresh["gkeepapi.__init__.refresh"]
    gkeepapi___init___load["gkeepapi.__init__.load"]
    gkeepapi___init___setAuth["gkeepapi.__init__.setAuth"]
    gkeepapi___init___getAuth["gkeepapi.__init__.getAuth"]
    gkeepapi___init___getMasterToken["gkeepapi.__init__.getMasterToken"]
    gkeepapi___init___login -- "stores tokens in" --> gkeepapi_APIAuth
    gkeepapi___init___login -- "calls" --> gkeepapi___init___refresh
    gkeepapi___init___authenticate -- "stores tokens in" --> gkeepapi_APIAuth
    gkeepapi___init___authenticate -- "calls" --> gkeepapi___init___load
    gkeepapi___init___refresh -- "updates tokens in" --> gkeepapi_APIAuth
    gkeepapi___init___load -- "interacts with" --> gkeepapi_APIAuth
    gkeepapi___init___load -- "calls" --> gkeepapi___init___setAuth
    gkeepapi___init___setAuth -- "interacts with" --> gkeepapi_APIAuth
    gkeepapi___init___getAuth -- "retrieves credentials from" --> gkeepapi_APIAuth
    gkeepapi___init___getMasterToken -- "calls" --> gkeepapi___init___getAuth
    gkeepapi_APIAuth -- "provides tokens to" --> gkeepapi___init___getMasterToken
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Authentication Manager` subsystem is dedicated to handling user authentication with Google, including obtaining, storing, and refreshing master and OAuth tokens required for API access. Its boundaries are primarily defined by the `gkeepapi.APIAuth` class and its associated methods within the `gkeepapi` package.

### gkeepapi.APIAuth
This is the core component responsible for maintaining the state of both master and OAuth authentication tokens. It acts as the central data store and manager for all authentication credentials.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py" target="_blank" rel="noopener noreferrer">`gkeepapi.APIAuth`</a>


### gkeepapi.__init__.login
Orchestrates the initial user login process, typically involving external authentication flows to obtain the necessary tokens.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L681-L709" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.login`:681-709</a>


### gkeepapi.__init__.authenticate
Provides an alternative or secondary mechanism for authenticating a session, potentially using pre-existing credentials or a different authentication flow.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L722-L747" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.authenticate`:722-747</a>


### gkeepapi.__init__.refresh
Renews expired master and OAuth tokens to maintain continuous access to the Google Keep API without requiring a full re-login.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L140-L164" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.refresh`:140-164</a>


### gkeepapi.__init__.load
Loads and restores previously saved authentication data, enabling session persistence across application restarts.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L757-L774" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.load`:757-774</a>


### gkeepapi.__init__.setAuth
Applies the retrieved or newly acquired authentication credentials to the system's internal state, preparing for API requests.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L199-L205" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.setAuth`:199-205</a>


### gkeepapi.__init__.getAuth
Retrieves the currently active authentication credentials from `gkeepapi.APIAuth`.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L191-L197" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.getAuth`:191-197</a>


### gkeepapi.__init__.getMasterToken
Specifically retrieves the master token from the authentication manager.


**Related Classes/Methods**:

- <a href="https://github.com/kiwiz/gkeepapi/blob/main/src/gkeepapi/__init__.py#L749-L755" target="_blank" rel="noopener noreferrer">`gkeepapi.__init__.getMasterToken`:749-755</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)