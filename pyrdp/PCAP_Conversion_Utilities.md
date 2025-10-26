```mermaid
graph LR
    PCAP_Orchestrator["PCAP Orchestrator"]
    TLS_Decryption_Handler["TLS Decryption Handler"]
    PCAP_Orchestrator -- "uses" --> TLS_Decryption_Handler
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `pyrdp.convert` subsystem is primarily responsible for processing and converting network capture (PCAP) files into a format suitable for RDP analysis and replay. The core of this subsystem revolves around the `PCAP Orchestrator` component, embodied by the `PCAPConverter` class. This orchestrator initiates the analysis by listing and filtering network sessions from a given PCAP file. For encrypted TLS streams, it leverages the `TLS Decryption Handler` component, represented by the `TLSPDUStream` class, to decrypt the traffic. The `PCAP Orchestrator` instantiates `TLSPDUStream` and feeds it the necessary session and master secret information, allowing the `TLS Decryption Handler` to expose the raw RDP data. This decrypted data is then processed further by the `PCAP Orchestrator` to generate the final output, ensuring that both plaintext and encrypted RDP communications can be effectively analyzed.

### PCAP Orchestrator
This component acts as the high-level controller for processing PCAP files. It is responsible for iterating through network streams, identifying distinct sessions, applying filtering rules (e.g., source/destination exclusions), and orchestrating the processing of individual streams. It serves as the primary entry point for initiating PCAP analysis, delegating specific decryption and parsing tasks to other specialized components. Its role is fundamentally about managing the flow of data extraction from the PCAP.


**Related Classes/Methods**:

- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter:process`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter:processStream`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter:listSessions`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter:checkSrcExcluded`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/PCAPConverter.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.PCAPConverter:checkDstExcluded`</a>


### TLS Decryption Handler
This specialized component focuses on the critical task of handling and decrypting TLS-encrypted data streams embedded within PCAP files. Its core function is to expose the underlying RDP traffic by performing the necessary TLS decryption, thereby making the encrypted RDP data accessible for further analysis or replay by other `pyrdp` components. It acts as a vital processing unit for encrypted network data, enabling `pyrdp` to analyze secure RDP communications.


**Related Classes/Methods**:

- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/TLSPDUStream.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.TLSPDUStream`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/TLSPDUStream.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.TLSPDUStream:__iter__`</a>
- <a href="https://github.com/GoSecure/pyrdp/blob/main/pyrdp/convert/TLSPDUStream.py" target="_blank" rel="noopener noreferrer">`pyrdp.convert.TLSPDUStream:decryptTLSStream`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)