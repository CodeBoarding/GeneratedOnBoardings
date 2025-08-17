```mermaid
graph LR
    ONNX_Runtime_Optimization_Inference_Handler["ONNX Runtime Optimization & Inference Handler"]
    TensorRT_Engine_Builder_Inference_Executor["TensorRT Engine Builder & Inference Executor"]
    ONNX_Runtime_Optimization_Inference_Handler -- "is a peer of" --> TensorRT_Engine_Builder_Inference_Executor
    TensorRT_Engine_Builder_Inference_Executor -- "is a peer of" --> ONNX_Runtime_Optimization_Inference_Handler
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `transformer_deploy` project's backend subsystem focuses on optimizing and executing transformer models using either ONNX Runtime or NVIDIA TensorRT. The `ONNX Runtime Optimization & Inference Handler` component manages the entire ONNX Runtime inference lifecycle, from model preparation and precision handling to session execution. As a peer, the `TensorRT Engine Builder & Inference Executor` component handles the creation, building, loading, and high-speed inference of TensorRT engines, leveraging NVIDIA GPUs for accelerated performance. These two components provide distinct but complementary pathways for deploying and running optimized transformer models, offering flexibility based on hardware and performance requirements.

### ONNX Runtime Optimization & Inference Handler
This component is dedicated to managing the entire lifecycle of ONNX Runtime inference. Its responsibilities include preparing models for ONNX Runtime, handling precision management (e.g., identifying and preserving FP32 nodes for specific operations), mapping input/output tensors, and executing the inference sessions. It serves as the primary interface for deploying and running models via ONNX Runtime.


**Related Classes/Methods**:

- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/ort_utils.py#L55-L85" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.ort_utils.create_model_for_provider`:55-85</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/ort_utils.py#L230-L295" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.ort_utils.inference_onnx_binding`:230-295</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/ort_utils.py#L432-L453" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.ort_utils.get_keep_fp32_nodes`:432-453</a>


### TensorRT Engine Builder & Inference Executor
This component is responsible for the creation, building, loading, and high-speed execution of NVIDIA TensorRT engines. Its functions include defining and generating tensor shapes, optimizing the model into a highly efficient TensorRT engine, and performing accelerated inference on NVIDIA GPUs. This component is crucial for leveraging NVIDIA's hardware acceleration capabilities.


**Related Classes/Methods**:

- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/trt_utils.py#L107-L209" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.trt_utils.build_engine`:107-209</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/trt_utils.py#L240-L279" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.trt_utils.infer_tensorrt`:240-279</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/trt_utils.py#L282-L308" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.trt_utils.load_engine`:282-308</a>
- <a href="https://github.com/ELS-RD/transformer-deploy/blob/main/src/transformer_deploy/backends/trt_utils.py#L67-L78" target="_blank" rel="noopener noreferrer">`transformer_deploy.backends.trt_utils.generate_multiple_shapes`:67-78</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)