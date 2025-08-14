```mermaid
graph LR
    Core_ML_Utilities["Core ML Utilities"]
    Generative_Models_Suite["Generative Models Suite"]
    Reinforcement_Learning_Algorithms["Reinforcement Learning Algorithms"]
    Transformer_Model_Implementations["Transformer Model Implementations"]
    Large_Language_Model_LLM_Specifics["Large Language Model (LLM) Specifics"]
    Graph_Neural_Networks["Graph Neural Networks"]
    Other_Neural_Network_Architectures["Other Neural Network Architectures"]
    Distributed_Training_Scaling["Distributed Training & Scaling"]
    Core_ML_Utilities -- "Provides/Utilizes Training Infrastructure & Data Handling" --> Generative_Models_Suite
    Generative_Models_Suite -- "Utilizes/Provided by Training Infrastructure & Data Handling" --> Core_ML_Utilities
    Core_ML_Utilities -- "Provides/Utilizes Training Infrastructure & Data Handling" --> Reinforcement_Learning_Algorithms
    Reinforcement_Learning_Algorithms -- "Utilizes/Provided by Training Infrastructure & Data Handling" --> Core_ML_Utilities
    Core_ML_Utilities -- "Provides/Utilizes Common Layers & Utilities" --> Transformer_Model_Implementations
    Transformer_Model_Implementations -- "Utilizes/Provided by Common Layers & Utilities" --> Core_ML_Utilities
    Core_ML_Utilities -- "Provides/Utilizes Training Infrastructure & Data Handling" --> Large_Language_Model_LLM_Specifics
    Large_Language_Model_LLM_Specifics -- "Utilizes/Provided by Training Infrastructure & Data Handling" --> Core_ML_Utilities
    Core_ML_Utilities -- "Provides/Utilizes Training Infrastructure & Data Handling" --> Graph_Neural_Networks
    Graph_Neural_Networks -- "Utilizes/Provided by Training Infrastructure & Data Handling" --> Core_ML_Utilities
    Core_ML_Utilities -- "Provides/Utilizes Training Infrastructure & Data Handling" --> Other_Neural_Network_Architectures
    Other_Neural_Network_Architectures -- "Utilizes/Provided by Training Infrastructure & Data Handling" --> Core_ML_Utilities
    Transformer_Model_Implementations -- "Supplies Transformer Building Blocks" --> Generative_Models_Suite
    Transformer_Model_Implementations -- "Provides Foundational Architectures" --> Large_Language_Model_LLM_Specifics
    Large_Language_Model_LLM_Specifics -- "Optimizes/Leverages Distributed Training" --> Distributed_Training_Scaling
    Distributed_Training_Scaling -- "Leveraged by/Optimizes Distributed Training" --> Large_Language_Model_LLM_Specifics
    click Core_ML_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Core_ML_Utilities.md" "Details"
    click Generative_Models_Suite href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Generative_Models_Suite.md" "Details"
    click Reinforcement_Learning_Algorithms href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Reinforcement_Learning_Algorithms.md" "Details"
    click Transformer_Model_Implementations href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Transformer_Model_Implementations.md" "Details"
    click Large_Language_Model_LLM_Specifics href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Large_Language_Model_LLM_Specifics.md" "Details"
    click Graph_Neural_Networks href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Graph_Neural_Networks.md" "Details"
    click Other_Neural_Network_Architectures href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Other_Neural_Network_Architectures.md" "Details"
    click Distributed_Training_Scaling href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/annotated_deep_learning_paper_implementations/Distributed_Training_Scaling.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `annotated_deep_learning_paper_implementations` project is architected as a modular ML toolkit, primarily designed to showcase diverse deep learning model implementations. At its core, the `Core ML Utilities` component provides foundational services such as data handling, training loop management, and common neural network layers, acting as a central backbone for the entire library. Specialized model suites, including `Generative Models Suite`, `Reinforcement Learning Algorithms`, `Transformer Model Implementations`, `Large Language Model (LLM) Specifics`, `Graph Neural Networks`, and `Other Neural Network Architectures`, each represent distinct functional blocks. These model implementations extensively leverage the `Core ML Utilities` for shared functionalities. Furthermore, there are specific inter-component dependencies, such as `Large Language Model (LLM) Specifics` building upon `Transformer Model Implementations` and utilizing `Distributed Training & Scaling` for performance optimization. This component-based architecture facilitates clear data and control flow, making it highly suitable for a flow graph representation where each model type is a primary architectural unit interacting with shared utilities and specialized modules.

### Core ML Utilities [[Expand]](./Core_ML_Utilities.md)
Provides foundational utilities, data handling, training infrastructure, and common neural network building blocks.


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/helpers/trainer.py#L409-L415" target="_blank" rel="noopener noreferrer">`labml_nn.helpers.trainer.run`:409-415</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/helpers/datasets.py" target="_blank" rel="noopener noreferrer">`labml_nn.helpers.datasets`</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/optimizers/adam.py" target="_blank" rel="noopener noreferrer">`labml_nn.optimizers.adam`</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/normalization/batch_norm" target="_blank" rel="noopener noreferrer">`labml_nn.normalization.batch_norm`</a>


### Generative Models Suite [[Expand]](./Generative_Models_Suite.md)
Implementations of various generative models (e.g., Diffusion Models, GANs, SketchRNN).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/diffusion/ddpm/experiment.py#L225-L247" target="_blank" rel="noopener noreferrer">`labml_nn.diffusion.ddpm.experiment.main`:225-247</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/diffusion/stable_diffusion/scripts/text_to_image.py#L104-L153" target="_blank" rel="noopener noreferrer">`labml_nn.diffusion.stable_diffusion.scripts.text_to_image.main`:104-153</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/gan/cycle_gan/__init__.py#L663-L683" target="_blank" rel="noopener noreferrer">`labml_nn.gan.cycle_gan.__init__.train`:663-683</a>


### Reinforcement Learning Algorithms [[Expand]](./Reinforcement_Learning_Algorithms.md)
Implementations of reinforcement learning algorithms (e.g., DQN, PPO, CFR).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/rl/dqn/experiment.py#L254-L285" target="_blank" rel="noopener noreferrer">`labml_nn.rl.dqn.experiment.main`:254-285</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/rl/ppo/experiment.py#L353-L391" target="_blank" rel="noopener noreferrer">`labml_nn.rl.ppo.experiment.main`:353-391</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/cfr/kuhn/__init__.py#L226-L243" target="_blank" rel="noopener noreferrer">`labml_nn.cfr.kuhn.__init__.main`:226-243</a>


### Transformer Model Implementations [[Expand]](./Transformer_Model_Implementations.md)
Core transformer architectures, attention mechanisms, and positional encoding schemes.


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/transformers/mha.py" target="_blank" rel="noopener noreferrer">`labml_nn.transformers.mha`</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/transformers/positional_encoding.py" target="_blank" rel="noopener noreferrer">`labml_nn.transformers.positional_encoding`</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/transformers/gpt/__init__.py#L220-L259" target="_blank" rel="noopener noreferrer">`labml_nn.transformers.gpt.__init__.main`:220-259</a>


### Large Language Model (LLM) Specifics [[Expand]](./Large_Language_Model_LLM_Specifics.md)
Dedicated modules for large-scale language models, including specific architectures (NeoX, RWKV) and fine-tuning techniques (LoRA).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/neox/model.py" target="_blank" rel="noopener noreferrer">`labml_nn.neox.model`</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/neox/utils/trainer.py#L76-L79" target="_blank" rel="noopener noreferrer">`labml_nn.neox.utils.trainer.train`:76-79</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/lora/gpt2.py#L140-L167" target="_blank" rel="noopener noreferrer">`labml_nn.lora.gpt2.__init__`:140-167</a>


### Graph Neural Networks [[Expand]](./Graph_Neural_Networks.md)
Implementations of neural networks for graph-structured data (e.g., GAT, GATv2).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/graphs/gat/experiment.py#L288-L304" target="_blank" rel="noopener noreferrer">`labml_nn.graphs.gat.experiment.main`:288-304</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/graphs/gatv2" target="_blank" rel="noopener noreferrer">`labml_nn.graphs.gatv2`</a>


### Other Neural Network Architectures [[Expand]](./Other_Neural_Network_Architectures.md)
Diverse neural network models not categorized elsewhere (e.g., ResNet, UNet, Capsule Networks).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/capsule_networks/mnist.py#L152-L155" target="_blank" rel="noopener noreferrer">`labml_nn.capsule_networks.mnist.capsule_network_model`:152-155</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/resnet/experiment.py#L54-L77" target="_blank" rel="noopener noreferrer">`labml_nn.resnet.experiment.main`:54-77</a>
- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/unet/experiment.py" target="_blank" rel="noopener noreferrer">`labml_nn.unet/experiment`</a>


### Distributed Training & Scaling [[Expand]](./Distributed_Training_Scaling.md)
Modules for optimizing training of large models, focusing on memory and computational efficiency (e.g., ZeRO-3).


**Related Classes/Methods**:

- <a href="https://github.com/labmlai/annotated_deep_learning_paper_implementations/blob/master/labml_nn/scaling/zero3/__init__.py" target="_blank" rel="noopener noreferrer">`labml_nn.scaling.zero3.__init__`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)