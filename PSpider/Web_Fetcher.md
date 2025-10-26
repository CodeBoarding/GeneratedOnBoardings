```mermaid
graph LR
    WebFetcherOrchestrator["WebFetcherOrchestrator"]
    URLContentRetriever["URLContentRetriever"]
    WebFetcherOrchestrator -- "invokes" --> URLContentRetriever
    URLContentRetriever -- "returns content to" --> WebFetcherOrchestrator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This subsystem is responsible for the core task of acquiring raw web page content from the internet. It acts as the initial data acquisition layer within the spider framework, feeding raw content into subsequent processing stages.

### WebFetcherOrchestrator
This component serves as the high-level manager for the web fetching process. It orchestrates the overall flow, managing input URLs, handling concurrency, and delegating the actual HTTP request execution. It acts as a producer, feeding URLs to the URLContentRetriever and consuming the raw content returned, preparing it for the next stages of the spider pipeline.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_fetch.py#L27-L40" target="_blank" rel="noopener noreferrer">`spider.instances.inst_fetch.working`:27-40</a>


### URLContentRetriever
This component is the low-level interface to the network, directly responsible for executing HTTP requests, retrieving raw web page content, and managing initial network interactions. Its responsibilities include handling network-specific concerns such as proxies, retries, and timeouts during data acquisition from the web.


**Related Classes/Methods**:

- <a href="https://github.com/xianhu/PSpider/blob/master/spider/instances/inst_fetch.py#L42-L46" target="_blank" rel="noopener noreferrer">`spider.instances.inst_fetch.url_fetch`:42-46</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)