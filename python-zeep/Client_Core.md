```mermaid
graph LR
    zeep_client_Client["zeep.client.Client"]
    zeep_proxy_ServiceProxy["zeep.proxy.ServiceProxy"]
    zeep_proxy_OperationProxy["zeep.proxy.OperationProxy"]
    zeep_proxy_AsyncOperationProxy["zeep.proxy.AsyncOperationProxy"]
    zeep_xsd_types_Factory["zeep.xsd.types.Factory"]
    zeep_client_Client -- "orchestrates service binding and access to" --> zeep_proxy_ServiceProxy
    zeep_client_Client -- "provides access to" --> zeep_xsd_types_Factory
    zeep_proxy_ServiceProxy -- "delegates synchronous operation execution to" --> zeep_proxy_OperationProxy
    zeep_proxy_ServiceProxy -- "delegates asynchronous operation execution to" --> zeep_proxy_AsyncOperationProxy
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `zeep` client subsystem provides a robust framework for interacting with SOAP web services. At its core, the `Client` orchestrates the entire process, from loading WSDL definitions to managing service interactions. It leverages `ServiceProxy` instances to expose callable SOAP operations, which in turn delegate to `OperationProxy` or `AsyncOperationProxy` for synchronous or asynchronous execution, respectively. The `Factory` component, accessible via the `Client`, ensures proper type handling for XML-to-Python data transformations. This design promotes a clear separation of concerns, allowing for flexible and extensible SOAP communication.

### zeep.client.Client
The central orchestrator and primary entry point for interacting with SOAP web services. It is responsible for loading WSDL definitions, managing the overall client configuration, and providing access to services and their operations. It acts as the main facade for the user.


**Related Classes/Methods**:

- <a href="https://github.com/mvantellingen/python-zeep/blob/main/src/zeep/client.py#L38-L222" target="_blank" rel="noopener noreferrer">`zeep.client.Client`:38-222</a>


### zeep.proxy.ServiceProxy
An intermediary component that represents a callable SOAP service or port. It is instantiated by the `Client` and dynamically exposes methods corresponding to the SOAP operations defined in the WSDL, handling the initial preparation and delegation of actual operation invocations. It serves as the user's direct interface to service operations.


**Related Classes/Methods**:

- <a href="https://github.com/mvantellingen/python-zeep/blob/main/src/zeep/proxy.py#L73-L107" target="_blank" rel="noopener noreferrer">`zeep.proxy.ServiceProxy`:73-107</a>


### zeep.proxy.OperationProxy
Responsible for handling the actual synchronous invocation of a specific SOAP operation. It receives the call from `ServiceProxy`, constructs the SOAP request message, sends it via the transport layer, and processes the synchronous response, including merging SOAP headers.


**Related Classes/Methods**:

- <a href="https://github.com/mvantellingen/python-zeep/blob/main/src/zeep/proxy.py#L8-L52" target="_blank" rel="noopener noreferrer">`zeep.proxy.OperationProxy`:8-52</a>


### zeep.proxy.AsyncOperationProxy
Similar to `OperationProxy`, but specifically designed for handling the asynchronous invocation of SOAP operations. It manages non-blocking requests and responses, typically returning futures or similar constructs, and also handles SOAP header merging.


**Related Classes/Methods**:

- <a href="https://github.com/mvantellingen/python-zeep/blob/main/src/zeep/proxy.py#L55-L70" target="_blank" rel="noopener noreferrer">`zeep.proxy.AsyncOperationProxy`:55-70</a>


### zeep.xsd.types.Factory
Manages the creation and resolution of Python types corresponding to the XML Schema (XSD) types defined in the WSDL. It is crucial for the automatic serialization of Python objects to XML and deserialization of XML to Python objects, and is accessed via the `Client`.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)