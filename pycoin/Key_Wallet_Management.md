```mermaid
graph LR
    pycoin_key_Key["pycoin.key.Key"]
    pycoin_key_BIP32Node["pycoin.key.BIP32Node"]
    pycoin_key_Keychain["pycoin.key.Keychain"]
    pycoin_wallet_SQLite3Persistence["pycoin.wallet.SQLite3Persistence"]
    pycoin_wallet_SQLite3Wallet["pycoin.wallet.SQLite3Wallet"]
    pycoin_encoding_b58["pycoin.encoding.b58"]
    pycoin_networks_ParseAPI["pycoin.networks.ParseAPI"]
    pycoin_key_Key -- "utilizes" --> pycoin_encoding_b58
    pycoin_key_Key -- "provides signing capability to" --> pycoin_wallet_SQLite3Wallet
    pycoin_key_BIP32Node -- "derives" --> pycoin_key_Key
    pycoin_key_BIP32Node -- "provides derivation logic to" --> pycoin_networks_ParseAPI
    pycoin_key_BIP32Node -- "provides derivation logic to" --> pycoin_wallet_SQLite3Wallet
    pycoin_key_Keychain -- "stores metadata for" --> pycoin_key_Key
    pycoin_key_Keychain -- "interacts with" --> pycoin_wallet_SQLite3Persistence
    pycoin_wallet_SQLite3Persistence -- "provides database operations for" --> pycoin_key_Keychain
    pycoin_wallet_SQLite3Persistence -- "serves as data layer for" --> pycoin_wallet_SQLite3Wallet
    pycoin_wallet_SQLite3Wallet -- "relies on" --> pycoin_wallet_SQLite3Persistence
    pycoin_wallet_SQLite3Wallet -- "manages derivation via" --> pycoin_key_BIP32Node
    pycoin_wallet_SQLite3Wallet -- "orchestrates signing using" --> pycoin_key_Key
    pycoin_encoding_b58 -- "provides utilities to" --> pycoin_key_Key
    pycoin_networks_ParseAPI -- "utilizes" --> pycoin_key_BIP32Node
    pycoin_networks_ParseAPI -- "derives" --> pycoin_key_Key
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Key & Wallet Management` subsystem is responsible for the complete lifecycle of cryptographic keys, including generation, hierarchical derivation (BIP32/49/84), serialization, and secure management. It also encompasses the storage and retrieval of wallet-related data such as keys, UTXOs, and blockchain state, primarily utilizing an SQLite database for persistence.

### pycoin.key.Key
Represents a fundamental cryptographic key (private or public). Manages key properties, derives various representations (WIF, SEC, hash160, address), and performs core cryptographic operations like signing and verification.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/key/Key.py" target="_blank" rel="noopener noreferrer">`pycoin.key.Key`</a>


### pycoin.key.BIP32Node
Implements the BIP32 standard for hierarchical deterministic key derivation. Derives child keys (private and public) from a parent node and handles serialization/deserialization of BIP32 nodes.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/key/BIP32Node.py" target="_blank" rel="noopener noreferrer">`pycoin.key.BIP32Node`</a>


### pycoin.key.Keychain
Manages a persistent store for key-related metadata, such as hash160 values, key derivation paths, and P2S scripts. Provides methods for adding, retrieving, and managing these associations.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/key/Keychain.py" target="_blank" rel="noopener noreferrer">`pycoin.key.Keychain`</a>


### pycoin.wallet.SQLite3Persistence
Provides the concrete implementation for persisting various wallet-related data (BIP32 nodes, global settings, UTXOs, keychains) to an SQLite database. It acts as the low-level data access layer.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/wallet/SQLite3Persistence.py" target="_blank" rel="noopener noreferrer">`pycoin.wallet.SQLite3Persistence`</a>


### pycoin.wallet.SQLite3Wallet
The high-level wallet component that orchestrates key management, UTXO tracking, and transaction creation (`create_unsigned_send_tx`). It provides a unified interface for common wallet operations.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/wallet/SQLite3Wallet.py" target="_blank" rel="noopener noreferrer">`pycoin.wallet.SQLite3Wallet`</a>
- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/wallet/SQLite3Wallet.py" target="_blank" rel="noopener noreferrer">`pycoin.wallet.SQLite3Wallet:create_unsigned_send_tx`</a>


### pycoin.encoding.b58
Provides essential Base58Check encoding/decoding utilities (`b2a_hashed_base58`) for representing cryptographic keys, addresses, and other blockchain-related data in a human-readable format.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/encoding/b58.py" target="_blank" rel="noopener noreferrer">`pycoin.encoding.b58`</a>
- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/encoding/b58.py" target="_blank" rel="noopener noreferrer">`pycoin.encoding.b58:b2a_hashed_base58`</a>


### pycoin.networks.ParseAPI
Acts as an entry point for parsing various hierarchical key formats (BIP32, BIP49, BIP84, Electrum seeds/keys) from string representations. It abstracts the parsing logic for different network standards.


**Related Classes/Methods**:

- <a href="https://github.com/richardkiss/pycoin/blob/main/pycoin/networks/ParseAPI.py" target="_blank" rel="noopener noreferrer">`pycoin.networks.ParseAPI`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)