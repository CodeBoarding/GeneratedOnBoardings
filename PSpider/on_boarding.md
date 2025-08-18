```mermaid
graph LR
    Task_Orchestrator_ThreadPool_["Task Orchestrator (ThreadPool)"]
    Web_Fetcher["Web Fetcher"]
    HTML_Parser["HTML Parser"]
    Data_Saver["Data Saver"]
    Proxy_Manager["Proxy Manager"]
    URL_Deduplicator["URL Deduplicator"]
    Task_Orchestrator_ThreadPool_ -- "Dispatches TaskFetch" --> Web_Fetcher
    Web_Fetcher -- "Returns Fetched Content" --> Task_Orchestrator_ThreadPool_
    Task_Orchestrator_ThreadPool_ -- "Dispatches Parse Tasks" --> HTML_Parser
    HTML_Parser -- "Returns Parse Results & New URLs" --> Task_Orchestrator_ThreadPool_
    Task_Orchestrator_ThreadPool_ -- "Dispatches Save Tasks" --> Data_Saver
    Data_Saver -- "Returns Save Status" --> Task_Orchestrator_ThreadPool_
    Task_Orchestrator_ThreadPool_ -- "Manages Proxies" --> Proxy_Manager
    Proxy_Manager -- "Provides Proxy Status" --> Task_Orchestrator_ThreadPool_
    Task_Orchestrator_ThreadPool_ -- "Utilizes for URL Filtering" --> URL_Deduplicator
    Web_Fetcher -- "Requests Proxy" --> Proxy_Manager
    Web_Fetcher -- "Checks/Adds URL" --> URL_Deduplicator
    click Task_Orchestrator_ThreadPool_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/PSpider/Task_Orchestrator_ThreadPool_.md" "Details"
    click Web_Fetcher href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/PSpider/Web_Fetcher.md" "Details"
    click Proxy_Manager href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/PSpider/Proxy_Manager.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The PSpider project operates as a concurrent web crawling system, orchestrated by a central `Task Orchestrator (ThreadPool)`. This orchestrator manages the lifecycle of crawling tasks, dispatching them to specialized components like the `Web Fetcher` for content retrieval, the `HTML Parser` for data extraction and URL discovery, and the `Data Saver` for persistence. The system leverages a `Proxy Manager` for robust fetching and a `URL Deduplicator` to ensure efficient and non-redundant processing of URLs. Data flows primarily from the orchestrator to the task-specific components and back, with new URLs discovered during parsing feeding back into the orchestration loop.

### Task Orchestrator (ThreadPool) [[Expand]](./Task_Orchestrator_ThreadPool_.md)
The central coordinator managing task queues, dispatching tasks to workers, and processing results to generate subsequent tasks.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/concurrent/threads_pool.py" target="_blank" rel="noopener noreferrer">`Task Orchestrator (ThreadPool)`</a>


### Web Fetcher [[Expand]](./Web_Fetcher.md)
Responsible for making HTTP requests, retrieving raw web page content, and handling initial network interactions.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_fetch.py" target="_blank" rel="noopener noreferrer">`Web Fetcher`</a>


### HTML Parser
Extracts structured data and identifies new URLs from the raw HTML content.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_parse.py" target="_blank" rel="noopener noreferrer">`HTML Parser`</a>


### Data Saver
Persists the extracted structured data to a designated storage medium.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_save.py" target="_blank" rel="noopener noreferrer">`Data Saver`</a>


### Proxy Manager [[Expand]](./Proxy_Manager.md)
Manages a pool of proxy servers, providing them to the Web Fetcher to ensure anonymity and bypass restrictions.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_proxies.py" target="_blank" rel="noopener noreferrer">`Proxy Manager`</a>


### URL Deduplicator
Prevents redundant processing by tracking already visited or queued URLs.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/utilities/cfilter.py" target="_blank" rel="noopener noreferrer">`URL Deduplicator`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)