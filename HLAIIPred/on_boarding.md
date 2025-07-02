```mermaid
graph LR
    Data_Management["Data Management"]
    Model_Core["Model Core"]
    Training_Evaluation["Training & Evaluation"]
    Prediction_Inference["Prediction & Inference"]
    Application_Orchestration["Application Orchestration"]
    Data_Management -- "Provides Data To" --> Training_Evaluation
    Data_Management -- "Provides Data To" --> Prediction_Inference
    Application_Orchestration -- "Configures" --> Data_Management
    Model_Core -- "Provides Structure To" --> Training_Evaluation
    Model_Core -- "Provides Structure To" --> Prediction_Inference
    Application_Orchestration -- "Configures" --> Model_Core
    Training_Evaluation -- "Provides Trained Model To" --> Prediction_Inference
    Application_Orchestration -- "Triggers & Configures" --> Training_Evaluation
    Prediction_Inference -- "Provides Results To" --> Application_Orchestration
    Application_Orchestration -- "Triggers & Configures" --> Prediction_Inference
    click Data_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/HLAIIPred/Data_Management.md" "Details"
    click Prediction_Inference href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/HLAIIPred/Prediction_Inference.md" "Details"
    click Application_Orchestration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/HLAIIPred/Application_Orchestration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Data Management [[Expand]](./Data_Management.md)
Responsible for loading, preprocessing, and encoding raw biological sequence data into a numerical format suitable for deep learning models. It ensures data integrity and prepares it for consumption by the model training and inference processes.


**Related Classes/Methods**:

- <a href="https://github.com/pfizer-opensource/HLAIIPred/blob/main/hlapred/dataset.py#L1-L1" target="_blank" rel="noopener noreferrer">`hlapred/dataset.py` (1:1)</a>
- <a href="https://github.com/pfizer-opensource/HLAIIPred/blob/main/hlapred/utils.py#L39-L75" target="_blank" rel="noopener noreferrer">`hlapred/utils.py:get_encoding` (39:75)</a>


### Model Core
Defines the neural network architecture, including its various layers, attention mechanisms, and configurable building blocks (e.g., EncoderBlock, DecoderBlock). It provides the blueprint for the deep learning model.


**Related Classes/Methods**:

- <a href="https://github.com/pfizer-opensource/HLAIIPred/blob/main/hlapred/model_modules.py#L1-L1" target="_blank" rel="noopener noreferrer">`hlapred/model_modules.py` (1:1)</a>


### Training & Evaluation
Orchestrates the entire model training lifecycle. This includes instantiating the model, setting up optimizers and loss functions, managing the training loop (forward/backward passes), performing periodic evaluations, and saving trained model states.


**Related Classes/Methods**:

- `hlapred/train.py` (1:1)


### Prediction & Inference [[Expand]](./Prediction_Inference.md)
Manages the process of using a trained model to make predictions on new, unseen data. It handles loading trained model weights, preparing input for inference, executing the forward pass through the model, and outputting the prediction results.


**Related Classes/Methods**:

- <a href="https://github.com/pfizer-opensource/HLAIIPred/blob/main/hlapred/predict.py#L1-L1" target="_blank" rel="noopener noreferrer">`hlapred/predict.py` (1:1)</a>


### Application Orchestration [[Expand]](./Application_Orchestration.md)
Serves as the primary control point for the application. It handles configuration loading, parses command-line arguments, and orchestrates the execution of training or prediction workflows by interacting with other core components.


**Related Classes/Methods**:

- `models/config.yaml` (1:1)
- `cli/HLAIIPred` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)