```mermaid
graph LR
    tvm_target_Target["tvm.target.Target"]
    tvm_runtime_device_Device["tvm.runtime.device.Device"]
    tvm_rpc_client_connect["tvm.rpc.client.connect"]
    tvm_rpc_server__listen_loop["tvm.rpc.server._listen_loop"]
    tvm_rpc_tracker["tvm.rpc.tracker"]
    tvm_rpc_proxy["tvm.rpc.proxy"]
    tvm_target_Target -- "informs" --> tvm_runtime_device_Device
    tvm_rpc_client_connect -- "initiates connection to" --> tvm_rpc_server__listen_loop
    tvm_rpc_client_connect -- "sends programs to" --> tvm_rpc_server__listen_loop
    tvm_rpc_server__listen_loop -- "executes on" --> tvm_runtime_device_Device
    tvm_rpc_tracker -- "manages" --> tvm_rpc_server__listen_loop
    tvm_rpc_client_connect -- "queries" --> tvm_rpc_tracker
    tvm_rpc_server__listen_loop -- "registers with" --> tvm_rpc_tracker
    tvm_rpc_client_connect -- "connects via" --> tvm_rpc_proxy
    tvm_rpc_server__listen_loop -- "connects via" --> tvm_rpc_proxy
    tvm_rpc_client_connect -- "interacts with" --> tvm_runtime_device_Device
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Hardware Abstraction & Deployment` subsystem in TVM provides a unified interface for defining and managing diverse hardware targets and facilitates remote execution and deployment of TVM programs via an RPC system.

### tvm.target.Target
Defines the characteristics and features of a compilation target (e.g., CPU, GPU, DSP, specific hardware configurations). It encapsulates compilation options and target-specific attributes, providing a unified interface for target definition at compile-time.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/target/target.py" target="_blank" rel="noopener noreferrer">`tvm.target.Target`</a>


### tvm.runtime.device.Device
Manages runtime interaction with physical hardware devices. It allows querying device-specific attributes and capabilities, allocating memory, and executing compiled functions on the actual hardware.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/device.py#L29-L334" target="_blank" rel="noopener noreferrer">`tvm.runtime.device.Device`:29-334</a>


### tvm.rpc.client.connect
The primary entry point for establishing a client connection to a remote TVM RPC server or tracker. It enables remote execution of TVM programs, file system operations, and interaction with remote Device contexts.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/rpc/client.py#L481-L549" target="_blank" rel="noopener noreferrer">`tvm.rpc.client.connect`:481-549</a>


### tvm.rpc.server._listen_loop
The core loop of the TVM RPC server, responsible for listening for incoming client connections, dispatching them for processing, and executing received TVM programs on its local hardware.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/rpc/server.py#L179-L279" target="_blank" rel="noopener noreferrer">`tvm.rpc.server._listen_loop`:179-279</a>


### tvm.rpc.tracker
Acts as a central registry for RPC workers (servers). Clients can query the tracker to find available devices, and it manages worker registration and scheduling.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/rpc/tracker.py" target="_blank" rel="noopener noreferrer">`tvm.rpc.tracker`</a>


### tvm.rpc.proxy
Serves as an intermediary for RPC connections, especially useful for traversing network boundaries (e.g., NAT). It handles connection pairing and data forwarding between clients and servers.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/rpc/proxy.py" target="_blank" rel="noopener noreferrer">`tvm.rpc.proxy`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)