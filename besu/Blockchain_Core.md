```mermaid
graph LR
    Blockchain_Core["Blockchain Core"]
    Network_P2P["Network/P2P"]
    Consensus["Consensus"]
    EVM["EVM"]
    Data_Storage["Data/Storage"]
    Crypto["Crypto"]
    Sync["Sync"]
    API_RPC["API/RPC"]
    Network_P2P -- "sends new blocks/transactions to" --> Blockchain_Core
    Blockchain_Core -- "requests block validation from" --> Consensus
    Consensus -- "provides validation results to" --> Blockchain_Core
    Blockchain_Core -- "sends data to broadcast to" --> Network_P2P
    Blockchain_Core -- "requests transaction execution from" --> EVM
    EVM -- "returns execution results and state changes to" --> Blockchain_Core
    Data_Storage -- "stores blockchain data for" --> Blockchain_Core
    Data_Storage -- "retrieves requested data for" --> Blockchain_Core
    Crypto -- "performs cryptographic operations for" --> Blockchain_Core
    Crypto -- "returns cryptographic results to" --> Blockchain_Core
    Sync -- "provides synchronized blockchain data to" --> Blockchain_Core
    Blockchain_Core -- "requests missing blocks/data from" --> Sync
    API_RPC -- "requests blockchain data from" --> Blockchain_Core
    Blockchain_Core -- "sends blockchain data to" --> API_RPC
    click Blockchain_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Blockchain_Core.md" "Details"
    click Sync href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/besu/Sync.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Blockchain Core [[Expand]](./Blockchain_Core.md)
Manages the fundamental blockchain data structures, including block and transaction validation, chain organization, and the overall state of the ledger. It orchestrates the flow of data and operations within the blockchain client.


**Related Classes/Methods**: _None_

### Network/P2P
Handles peer-to-peer communication, including discovering peers, maintaining connections, and broadcasting/receiving blocks and transactions across the network.


**Related Classes/Methods**: _None_

### Consensus
Implements the rules and algorithms necessary to achieve agreement among network participants on the state of the blockchain, primarily focusing on block validation and chain selection.


**Related Classes/Methods**: _None_

### EVM
The runtime environment for executing smart contract code and processing transactions that modify the blockchain state.


**Related Classes/Methods**: _None_

### Data/Storage
Manages the persistent storage of blockchain data, including blocks, transactions, and the world state, ensuring data integrity and efficient retrieval.


**Related Classes/Methods**: _None_

### Crypto
Provides cryptographic primitives and functions, such as hashing, digital signatures, and key management, essential for securing blockchain operations.


**Related Classes/Methods**: _None_

### Sync [[Expand]](./Sync.md)
Manages the process of synchronizing the local blockchain state with the current state of the network, including downloading historical blocks and keeping up with new ones.


**Related Classes/Methods**: _None_

### API/RPC
Exposes interfaces (e.g., RPC, WebSockets) for external applications and users to interact with the blockchain client, query data, and submit transactions.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)