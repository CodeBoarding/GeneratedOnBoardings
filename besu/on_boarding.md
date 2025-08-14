```mermaid
graph LR
    Network_Sync["Network & Sync"]
    Consensus_Engine["Consensus Engine"]
    Blockchain_Core["Blockchain Core"]
    EVM_Execution["EVM Execution"]
    Data_Persistence["Data Persistence"]
    API_CLI_Interface["API & CLI Interface"]
    Network_Sync -- "broadcasts new blocks/transactions to" --> Consensus_Engine
    Consensus_Engine -- "receives broadcasts from" --> Network_Sync
    Network_Sync -- "requests chain data for synchronization from" --> Blockchain_Core
    Blockchain_Core -- "provides chain data to" --> Network_Sync
    Network_Sync -- "persists downloaded data to" --> Data_Persistence
    Data_Persistence -- "provides historical data for synchronization to" --> Network_Sync
    Consensus_Engine -- "validates and updates" --> Blockchain_Core
    Consensus_Engine -- "triggers" --> EVM_Execution
    Blockchain_Core -- "accesses state and delegates smart contract execution to" --> EVM_Execution
    EVM_Execution -- "provides execution results/state changes back to" --> Blockchain_Core
    Blockchain_Core -- "writes data to" --> Data_Persistence
    Data_Persistence -- "reads data from" --> Blockchain_Core
    API_CLI_Interface -- "submits transactions to" --> Network_Sync
    API_CLI_Interface -- "queries" --> Blockchain_Core
    API_CLI_Interface -- "retrieves historical data from" --> Data_Persistence
    click Network_Sync href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Network_Sync.md" "Details"
    click Consensus_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Consensus_Engine.md" "Details"
    click Blockchain_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Blockchain_Core.md" "Details"
    click EVM_Execution href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/EVM_Execution.md" "Details"
    click Data_Persistence href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Data_Persistence.md" "Details"
    click API_CLI_Interface href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/API_CLI_Interface.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

High-level data flow overview of a blockchain client, detailing abstract components and their interactions.

### Network & Sync [[Expand]](./Network_Sync.md)
Manages peer-to-peer connections, node discovery, and orchestrates the synchronization of the local blockchain state with the network, including exchanging blocks and transactions.


**Related Classes/Methods**: _None_

### Consensus Engine [[Expand]](./Consensus_Engine.md)
Implements the blockchain's consensus algorithm to validate new blocks, ensure chain integrity, and achieve agreement among nodes.


**Related Classes/Methods**: _None_

### Blockchain Core [[Expand]](./Blockchain_Core.md)
Manages the fundamental blockchain data structures, including block and transaction validation, chain organization, the overall state of the ledger, and essential cryptographic operations.


**Related Classes/Methods**: _None_

### EVM Execution [[Expand]](./EVM_Execution.md)
Executes smart contract bytecode, manages the state transitions resulting from contract interactions, and ensures deterministic execution within the Ethereum Virtual Machine.


**Related Classes/Methods**: _None_

### Data Persistence [[Expand]](./Data_Persistence.md)
Provides persistent storage for all blockchain data, including blocks, transactions, and the world state, offering efficient retrieval mechanisms.


**Related Classes/Methods**: _None_

### API & CLI Interface [[Expand]](./API_CLI_Interface.md)
Provides external interfaces for users and applications to interact with the blockchain client, including JSON-RPC/WebSockets for programmatic access and a command-line interface for client management.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)