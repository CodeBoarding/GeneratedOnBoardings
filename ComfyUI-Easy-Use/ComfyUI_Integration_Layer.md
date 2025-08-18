```mermaid
graph LR
    Prompt_Reception_Orchestration["Prompt Reception & Orchestration"]
    Prompt_Seed_Management["Prompt Seed Management"]
    Workflow_Seed_Application["Workflow Seed Application"]
    Seed_Generation_Utility["Seed Generation Utility"]
    Prompt_Reception_Orchestration -- "initiates calls to" --> Workflow_Seed_Application
    Prompt_Reception_Orchestration -- "initiates calls to" --> Prompt_Seed_Management
    Prompt_Seed_Management -- "interacts with" --> Seed_Generation_Utility
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `py.server` subsystem is central to managing image generation requests within ComfyUI-Easy-Use. It begins with the `Prompt Reception & Orchestration` component, which serves as the primary entry point for incoming prompts. Upon receiving a prompt, it orchestrates two critical subsequent processes: `Prompt Seed Management` and `Workflow Seed Application`. The `Prompt Seed Management` component dynamically updates seed values within the prompt, leveraging the `Seed Generation Utility` to ensure reproducibility and controlled variations in the generative output. Concurrently, the `Workflow Seed Application` component integrates these updated seed values into the overall ComfyUI workflow, ensuring that all generative nodes align with the desired parameters. This coordinated interaction ensures a streamlined and controlled image generation process.

### Prompt Reception & Orchestration
This component acts as the primary entry point for new image generation requests, receiving prompts from the ComfyUI server. It orchestrates the subsequent steps of seed and workflow updates to initiate the generative process.


**Related Classes/Methods**:

- <a href="https://github.com/yolain/ComfyUI-Easy-Use/blob/main/py/server.py#L159-L164" target="_blank" rel="noopener noreferrer">`py.server.onprompt`:159-164</a>


### Prompt Seed Management
Responsible for managing and dynamically updating the specific seed values associated with the current prompt. This is crucial for controlling reproducibility and variations in the generative AI output. It integrates with seed generation utilities and control mechanisms.


**Related Classes/Methods**:

- <a href="https://github.com/yolain/ComfyUI-Easy-Use/blob/main/py/server.py#L62-L124" target="_blank" rel="noopener noreferrer">`py.server.prompt_seed_update`:62-124</a>


### Workflow Seed Application
This component updates the overall ComfyUI workflow configuration based on the provided seed information. Its role is to ensure that the entire generation process, potentially affecting multiple nodes, aligns with the desired parameters.


**Related Classes/Methods**:

- <a href="https://github.com/yolain/ComfyUI-Easy-Use/blob/main/py/server.py#L127-L156" target="_blank" rel="noopener noreferrer">`py.server.workflow_seed_update`:127-156</a>


### Seed Generation Utility
Provides the core logic for generating unique or sequential seed values. These seeds are fundamental for controlling the randomness and ensuring reproducibility of generative AI outputs across different runs.


**Related Classes/Methods**:

- <a href="https://github.com/yolain/ComfyUI-Easy-Use/blob/main/py/server.py#L12-L39" target="_blank" rel="noopener noreferrer">`py.server.SeedGenerator`:12-39</a>
- <a href="https://github.com/yolain/ComfyUI-Easy-Use/blob/main/py/server.py#L42-L59" target="_blank" rel="noopener noreferrer">`py.server.control_seed`:42-59</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)