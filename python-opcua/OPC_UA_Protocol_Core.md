```mermaid
graph LR
    UA_Data_Types_Definition["UA Data Types Definition"]
    Binary_Serialization_Deserialization["Binary Serialization/Deserialization"]
    Auto_generated_Protocol_Definitions["Auto-generated Protocol Definitions"]
    OPC_UA_Node_Abstraction["OPC UA Node Abstraction"]
    Node_Management_Operations["Node Management Operations"]
    Subscription_Management["Subscription Management"]
    UA_Data_Types_Definition -- "provides data structures to" --> Binary_Serialization_Deserialization
    UA_Data_Types_Definition -- "provides data structures to" --> Auto_generated_Protocol_Definitions
    UA_Data_Types_Definition -- "provides data structures to" --> OPC_UA_Node_Abstraction
    UA_Data_Types_Definition -- "provides data structures to" --> Node_Management_Operations
    UA_Data_Types_Definition -- "provides data structures to" --> Subscription_Management
    Binary_Serialization_Deserialization -- "consumes/produces instances of" --> UA_Data_Types_Definition
    Binary_Serialization_Deserialization -- "accesses structures from" --> Auto_generated_Protocol_Definitions
    Auto_generated_Protocol_Definitions -- "defines structures for" --> Binary_Serialization_Deserialization
    OPC_UA_Node_Abstraction -- "accesses" --> UA_Data_Types_Definition
    OPC_UA_Node_Abstraction -- "provides operations for" --> Node_Management_Operations
    OPC_UA_Node_Abstraction -- "provides operations for" --> Subscription_Management
    Node_Management_Operations -- "calls methods of" --> OPC_UA_Node_Abstraction
    Node_Management_Operations -- "uses types from" --> UA_Data_Types_Definition
    Subscription_Management -- "references objects from" --> OPC_UA_Node_Abstraction
    Subscription_Management -- "utilizes data types from" --> UA_Data_Types_Definition
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `OPC UA Protocol Core` subsystem forms the bedrock of the `python-opcua` library, encapsulating the fundamental elements required for OPC UA communication. Its boundaries are defined by the core OPC UA data type definitions, binary encoding/decoding mechanisms, auto-generated protocol structures, and common high-level abstractions for interacting with the OPC UA address space.

### UA Data Types Definition
Defines the fundamental OPC UA data types (e.g., NodeId, Variant, StatusCode, QualifiedName) that serve as the basic building blocks for all OPC UA communication and data representation.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/ua/uatypes.py" target="_blank" rel="noopener noreferrer">`opcua.ua.uatypes`</a>


### Binary Serialization/Deserialization
Handles the conversion of complex OPC UA structures and messages to and from their binary wire format, enabling low-level communication over the network.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/ua/ua_binary.py" target="_blank" rel="noopener noreferrer">`opcua.ua.ua_binary`</a>


### Auto-generated Protocol Definitions
Provides structured, high-level Python representations of OPC UA services (requests, responses) and complex data types, often generated from the OPC UA XML specifications. This component is crucial for protocol compliance and maintainability.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/ua/uaprotocol_auto.py" target="_blank" rel="noopener noreferrer">`opcua.ua.uaprotocol_auto`</a>


### OPC UA Node Abstraction
Offers a high-level, object-oriented interface for interacting with individual OPC UA nodes within the address space, abstracting away the underlying protocol details for node attribute access.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/common/node.py" target="_blank" rel="noopener noreferrer">`opcua.common.node`</a>


### Node Management Operations
Simplifies common address space manipulation tasks, such as adding folders, objects, or variables to the OPC UA server's address space.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/common/manage_nodes.py" target="_blank" rel="noopener noreferrer">`opcua.common.manage_nodes`</a>


### Subscription Management
Manages client-side OPC UA subscriptions, handling the creation, modification, and deletion of monitored items and dispatching data change notifications.


**Related Classes/Methods**:

- <a href="https://github.com/FreeOpcUa/python-opcua/blob/master/opcua/common/subscription.py" target="_blank" rel="noopener noreferrer">`opcua.common.subscription`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)