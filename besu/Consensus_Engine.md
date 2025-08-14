```mermaid
graph LR
    Consensus_Engine["Consensus Engine"]
    Blockchain_Core["Blockchain/Core"]
    Network_P2P["Network/P2P"]
    Data_Storage["Data/Storage"]
    EVM["EVM"]
    API_RPC["API/RPC"]
    Sync["Sync"]
    Config["Config"]
    Consensus_Engine -- "validates data for" --> Blockchain_Core
    Blockchain_Core -- "submits data to" --> Consensus_Engine
    Blockchain_Core -- "stores/retrieves data from" --> Data_Storage
    Network_P2P -- "sends/receives blocks/transactions to/from" --> Blockchain_Core
    Network_P2P -- "sends/receives consensus messages to/from" --> Consensus_Engine
    EVM -- "executes transactions for" --> Blockchain_Core
    EVM -- "updates state via" --> Blockchain_Core
    API_RPC -- "queries data from" --> Blockchain_Core
    API_RPC -- "submits transactions to" --> Blockchain_Core
    Sync -- "requests blocks from" --> Network_P2P
    Sync -- "adds blocks to" --> Blockchain_Core
    Config -- "provides configuration to" --> Consensus_Engine
    Config -- "provides configuration to" --> Network_P2P
    click Consensus_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Consensus_Engine.md" "Details"
    click Blockchain_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Blockchain_Core.md" "Details"
    click Sync href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Sync.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Consensus Engine [[Expand]](./Consensus_Engine.md)
Implements the blockchain's consensus algorithm to validate new blocks, ensure chain integrity, and achieve agreement among nodes.


**Related Classes/Methods**: _None_

### Blockchain/Core [[Expand]](./Blockchain_Core.md)
Manages the core blockchain data structure, including blocks, transactions, and the ledger state. Responsible for block creation and chain management.


**Related Classes/Methods**: _None_

### Network/P2P
Handles peer-to-peer communication, including discovering other nodes, propagating transactions and blocks, and maintaining network connections.


**Related Classes/Methods**: _None_

### Data/Storage
Provides persistent storage for the blockchain data, including blocks, transactions, and the world state.


**Related Classes/Methods**: _None_

### EVM
The execution environment for smart contracts and transactions. Processes transaction logic and updates the blockchain state.


**Related Classes/Methods**: _None_

### API/RPC
Exposes an interface (e.g., RPC, WebSockets) for external applications and users to interact with the blockchain client, query data, and submit transactions.


**Related Classes/Methods**: _None_

### Sync [[Expand]](./Sync.md)
Manages the synchronization process, ensuring the local blockchain client is up-to-date with the latest state of the network by fetching missing blocks and transactions from peers.


**Related Classes/Methods**: _None_

### Config
Manages and provides configuration parameters for various components of the blockchain client, such as network settings, database paths, and consensus parameters.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)