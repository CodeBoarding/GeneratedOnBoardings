```mermaid
graph LR
    Egress_Ingress_Service["Egress/Ingress Service"]
    Core_Media_Server_SFU_["Core Media Server (SFU)"]
    Egress_Ingress_Service -- "feeds media streams into" --> Core_Media_Server_SFU_
    Core_Media_Server_SFU_ -- "routes media streams to" --> Egress_Ingress_Service
    click Egress_Ingress_Service href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/livekit/Egress_Ingress_Service.md" "Details"
    click Core_Media_Server_SFU_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/livekit/Core_Media_Server_SFU_.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Egress/Ingress Service [[Expand]](./Egress_Ingress_Service.md)
This component encompasses dedicated services for advanced media operations. The Egress functionality, primarily handled by pkg.service.EgressService, manages recording live streams and multi-streaming to various platforms, processing media streams originating from LiveKit rooms. The Ingress functionality, managed by pkg.service.IngressService, handles the ingestion of external media sources (e.g., RTMP, OBS) into LiveKit rooms, acting as a bridge for bringing external content into the LiveKit ecosystem.


**Related Classes/Methods**:

- `pkg.service.EgressService`
- `pkg.service.IngressService`


### Core Media Server (SFU) [[Expand]](./Core_Media_Server_SFU_.md)
The central hub for all media streams within LiveKit rooms, responsible for receiving, processing, and forwarding media. Key responsibilities include managing incoming media tracks via pkg.sfu.Receiver, handling outgoing media distribution to participants through pkg.sfu.DownTrack, and efficiently routing media packets using pkg.sfu.Forwarder. This component ensures real-time media flow and adaptation within the LiveKit environment.


**Related Classes/Methods**:

- `pkg.sfu.Receiver`
- `pkg.sfu.DownTrack`
- `pkg.sfu.Forwarder`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)