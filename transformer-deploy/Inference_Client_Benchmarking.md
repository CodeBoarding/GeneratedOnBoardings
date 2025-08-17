```mermaid
graph LR
    Inference_Client["Inference Client"]
    Benchmarking_Data_Generator["Benchmarking Data Generator"]
    Benchmarking_Data_Generator -- "generates input data for" --> Inference_Client
    Inference_Client -- "dispatches requests to" --> Triton_Inference_Server
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This subsystem focuses on the critical process of preparing and dispatching data for model inference, particularly within a benchmarking context. The `Benchmarking Data Generator` component is responsible for creating diverse synthetic input data, which is then utilized by the `Inference Client`. The `Inference Client` serves as the crucial interface, handling the communication protocols and data serialization to efficiently transmit these inference requests to an external Triton Inference Server. This architecture ensures a streamlined flow for evaluating the performance of deployed models by providing controlled input generation and robust request dispatch capabilities.

### Inference Client
This component serves as the primary interface for sending inference requests to a deployed model server, specifically the Triton Inference Server. It handles the communication protocol, data serialization, and deserialization required for efficient model interaction. It is crucial for consuming input data and dispatching it to the server.


**Related Classes/Methods**:

- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/demo/infinity/triton_client.py#L1-L999999" target="_blank" rel="noopener noreferrer">`transformer_deploy.demo.infinity.triton_client.TritonClient`:1-999999</a>


### Benchmarking Data Generator
This component provides utilities for creating synthetic or dummy input data. This generated data is essential for conducting performance evaluations, load testing, and benchmarking of deployed models, ensuring consistent and controlled inputs for measuring inference latency and throughput.


**Related Classes/Methods**:

- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/benchmarks/utils.py#L1-L999999" target="_blank" rel="noopener noreferrer">`transformer_deploy.benchmarks.utils.generate_dummy_inputs`:1-999999</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/benchmarks/utils.py#L91-L108" target="_blank" rel="noopener noreferrer">`transformer_deploy.benchmarks.utils.generate_multiple_inputs`:91-108</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)