```mermaid
graph LR
    opcua_crypto_uacrypto["opcua.crypto.uacrypto"]
    opcua_crypto_security_policies_Security_policies["opcua.crypto.security_policies.Security_policies"]
    opcua_client_client["opcua.client.client"]
    opcua_ua_uaprotocol_hand["opcua.ua.uaprotocol_hand"]
    opcua_server_user_manager["opcua.server.user_manager"]
    opcua_crypto_security_policies_Security_policies -- "utilizes" --> opcua_crypto_uacrypto
    opcua_client_client -- "uses" --> opcua_crypto_security_policies_Security_policies
    opcua_ua_uaprotocol_hand -- "uses" --> opcua_crypto_security_policies_Security_policies
    opcua_server_user_manager -- "uses" --> opcua_crypto_security_policies_Security_policies
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The opcua.crypto subsystem is central to securing OPC UA communications, providing a robust framework for data confidentiality, integrity, and authentication. It comprises opcua.crypto.uacrypto, which offers core cryptographic primitives, and opcua.crypto.security_policies.Security_policies, which defines and enforces OPC UA-specific security protocols by orchestrating uacrypto's capabilities. This subsystem is critically integrated into the broader OPC UA architecture, with key modules such as opcua.client.client, opcua.ua.uaprotocol_hand, and opcua.server.user_manager directly interacting with opcua.crypto.security_policies.Security_policies to ensure secure client authentication, protocol handshakes, and server-side user token validation, thereby safeguarding the entire communication flow.

### opcua.crypto.uacrypto
Offers a suite of low-level cryptographic primitives, including functions for encryption, decryption, signing, and hashing.


**Related Classes/Methods**: _None_

### opcua.crypto.security_policies.Security_policies
Orchestrates cryptographic primitives to implement specific OPC UA security policies, defining how messages are secured.


**Related Classes/Methods**: _None_

### opcua.client.client
Responsible for client-side operations and applying security measures.


**Related Classes/Methods**: _None_

### opcua.ua.uaprotocol_hand
Handles the establishment of secure OPC UA connections and negotiates security parameters.


**Related Classes/Methods**: _None_

### opcua.server.user_manager
Manages server-side user authentication and validates incoming user tokens.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)