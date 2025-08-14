```mermaid
graph LR
    Python_API_Layer["Python API Layer"]
    Interoperability_Layer_Native_Bindings_["Interoperability Layer (Native Bindings)"]
    Native_Cryptographic_Core["Native Cryptographic Core"]
    Python_API_Layer -- "calls" --> Interoperability_Layer_Native_Bindings_
    Interoperability_Layer_Native_Bindings_ -- "invokes" --> Native_Cryptographic_Core
    Interoperability_Layer_Native_Bindings_ -- "returns results to" --> Python_API_Layer
    Interoperability_Layer_Native_Bindings_ -- "is tightly coupled with" --> Native_Cryptographic_Core
    click Interoperability_Layer_Native_Bindings_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/bcrypt/Interoperability_Layer_Native_Bindings_.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `bcrypt` library's architecture is structured into three distinct layers to provide secure and efficient password hashing. The `Python API Layer` serves as the primary interface for Python applications, offering a high-level abstraction for cryptographic operations. This layer communicates directly with the `Interoperability Layer (Native Bindings)`, which acts as a crucial bridge, handling data translation and exposing native functionalities to Python. The `Interoperability Layer`, in turn, interacts with the `Native Cryptographic Core`, where the performance-critical and security-sensitive hashing algorithms are executed. This layered approach ensures a clear separation of concerns, allowing for optimized native performance while providing a user-friendly Python interface.

### Python API Layer
This layer provides the high-level, user-friendly Python interface for the cryptographic library. It acts as the primary entry point for Python applications, abstracting away the complexities of the underlying native implementation. It makes direct function calls to the Interoperability Layer.


**Related Classes/Methods**:



### Interoperability Layer (Native Bindings) [[Expand]](./Interoperability_Layer_Native_Bindings_.md)
This is the critical bridge between the Python API Layer and the Native Cryptographic Core. It handles data marshalling (converting Python data types to Rust/C compatible types and vice-versa), exposes native functions (like `hash` and `checkpw`) to Python, manages the Global Interpreter Lock (GIL), and performs necessary error handling across the language boundary.


**Related Classes/Methods**:

- <a href="https://github.com/pyca/bcrypt/blob/main/src/_bcrypt/src/lib.rs" target="_blank" rel="noopener noreferrer">`hash`</a>
- <a href="https://github.com/pyca/bcrypt/blob/main/src/bcrypt/__init__.pyi" target="_blank" rel="noopener noreferrer">`checkpw`</a>


### Native Cryptographic Core
This component contains the performance-critical, security-sensitive cryptographic implementations written in Rust (and potentially C). It performs the actual computationally intensive operations, such as password hashing and verification. It is invoked by and tightly coupled with the Interoperability Layer.


**Related Classes/Methods**:

- <a href="https://github.com/pyca/bcrypt/blob/main/src/_bcrypt/src/lib.rs" target="_blank" rel="noopener noreferrer">`NativeCryptographicCore_logic`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)