```mermaid
graph LR
    Network_Sync["Network & Sync"]
    Consensus_Engine["Consensus Engine"]
    Blockchain_Core["Blockchain Core"]
    EVM["EVM"]
    Data_Persistence["Data Persistence"]
    API_RPC["API & RPC"]
    Cryptography["Cryptography"]
    Client_Application_CLI["Client Application / CLI"]
    Network_Sync -- "passes new blocks/transactions for validation" --> Blockchain_Core
    Blockchain_Core -- "broadcasts validated blocks/transactions" --> Network_Sync
    Network_Sync -- "queries for current chain state" --> Data_Persistence
    Network_Sync -- "stores peer information" --> Data_Persistence
    Consensus_Engine -- "relies on for current chain state" --> Blockchain_Core
    Consensus_Engine -- "applies consensus rules to new blocks" --> Blockchain_Core
    Blockchain_Core -- "passes transactions for execution" --> EVM
    EVM -- "returns execution results to" --> Blockchain_Core
    Blockchain_Core -- "reads and writes blocks, transactions, and state data" --> Data_Persistence
    EVM -- "reads and writes state data" --> Data_Persistence
    API_RPC -- "queries for blockchain data" --> Blockchain_Core
    API_RPC -- "submits new transactions to" --> Blockchain_Core
    API_RPC -- "may directly query for specific data" --> Data_Persistence
    Cryptography -- "used for transaction and block signing/verification" --> Blockchain_Core
    Cryptography -- "used for secure communication and peer authentication" --> Network_Sync
    Client_Application_CLI -- "uses internal API for operations" --> API_RPC
    click Network_Sync href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Network_Sync.md" "Details"
    click Consensus_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Consensus_Engine.md" "Details"
    click Blockchain_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Blockchain_Core.md" "Details"
    click Data_Persistence href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Data_Persistence.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Network & Sync [[Expand]](./Network_Sync.md)
Manages peer-to-peer connections, node discovery, and orchestrates the synchronization of the local blockchain state with the network, including exchanging blocks and transactions. It ensures the node is up-to-date with the latest chain.


**Related Classes/Methods**: _None_

### Consensus Engine [[Expand]](./Consensus_Engine.md)
Implements the rules and algorithms (e.g., Proof of Work, Proof of Stake) for achieving agreement among nodes on the blockchain's state and the validity of new blocks. It ensures the integrity and security of the ledger.


**Related Classes/Methods**: _None_

### Blockchain Core [[Expand]](./Blockchain_Core.md)
Responsible for the fundamental data structures of the blockchain, including block and transaction validation, chain organization, and fork resolution. It maintains the integrity and order of the ledger.


**Related Classes/Methods**: _None_

### EVM
Provides the runtime environment for executing smart contracts and processing transactions according to the protocol rules. It handles state transitions based on transaction inputs.


**Related Classes/Methods**: _None_

### Data Persistence [[Expand]](./Data_Persistence.md)
Manages the storage, indexing, and retrieval of all blockchain data, such as blocks, transactions, and state data, ensuring data integrity and efficient access.


**Related Classes/Methods**: _None_

### API & RPC
Exposes interfaces (e.g., JSON-RPC, WebSockets) for external applications and users to interact with the blockchain client, allowing them to query data, submit transactions, and manage the node.


**Related Classes/Methods**: _None_

### Cryptography
Provides essential cryptographic functions for secure operations, including hashing, digital signatures, and key management, underpinning the security of transactions and network communication.


**Related Classes/Methods**: _None_

### Client Application / CLI
Handles application startup, configuration loading, and provides a command-line interface for user interaction and node management (e.g., starting/stopping the node, viewing status).


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)