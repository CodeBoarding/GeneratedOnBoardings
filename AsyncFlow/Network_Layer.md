```mermaid
graph LR
    EdgeRuntime["EdgeRuntime"]
    Network_Transport_Initiator["Network Transport Initiator"]
    Network_Delivery_Mechanism["Network Delivery Mechanism"]
    Network_Transport_Initiator -- "calls and manages" --> Network_Delivery_Mechanism
    Network_Delivery_Mechanism -- "depends on" --> EdgeRuntime
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Network Layer` subsystem is crucial for simulating communication channels within the `AsyncFlow` project, a `Simulation Library/Tool`. It models the transfer of requests between different simulated actors, incorporating realistic network characteristics like latency and bandwidth constraints.

### EdgeRuntime
This is the foundational component of the Network Layer, representing a single, unidirectional communication link. It encapsulates the core logic for simulating network characteristics such as latency, dropout rates, and managing concurrent connections. It acts as the primary building block for all network interactions within the simulation.


**Related Classes/Methods**:

- <a href="https://github.com/AsyncFlow-Sim/AsyncFlow/blob/main/src/asyncflow/runtime/actors/edge.py#L27-L102" target="_blank" rel="noopener noreferrer">`EdgeRuntime`:27-102</a>


### Network Transport Initiator
This component serves as the external interface for sending `RequestState` objects across the simulated network link. It is responsible for initiating the asynchronous process of a request's journey through the network, preparing it for delivery.


**Related Classes/Methods**:

- <a href="https://github.com/AsyncFlow-Sim/AsyncFlow/blob/main/src/asyncflow/runtime/actors/edge.py" target="_blank" rel="noopener noreferrer">`EdgeRuntime:transport`</a>


### Network Delivery Mechanism
This component contains the core simulation logic for the actual transmission and delivery of a request over the network link. It calculates simulated latency, checks for potential request dropouts, and ultimately places the processed request into the destination actor's inbox.


**Related Classes/Methods**:

- <a href="https://github.com/AsyncFlow-Sim/AsyncFlow/blob/main/src/asyncflow/runtime/actors/edge.py" target="_blank" rel="noopener noreferrer">`EdgeRuntime:_deliver`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)