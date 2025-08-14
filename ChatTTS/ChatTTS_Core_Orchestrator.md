```mermaid
graph LR
    ChatTTS_core_Chat["ChatTTS.core.Chat"]
    ChatTTS_model_gpt["ChatTTS.model.gpt"]
    ChatTTS_model_dvae["ChatTTS.model.dvae"]
    ChatTTS_model_speaker["ChatTTS.model.speaker"]
    ChatTTS_model_tokenizer["ChatTTS.model.tokenizer"]
    ChatTTS_model_embed["ChatTTS.model.embed"]
    ChatTTS_config_Config["ChatTTS.config.Config"]
    ChatTTS_norm_Normalizer["ChatTTS.norm.Normalizer"]
    ChatTTS_utils["ChatTTS.utils"]
    ChatTTS_model_velocity["ChatTTS.model.velocity"]
    ChatTTS_core_Chat -- "uses" --> ChatTTS_config_Config
    ChatTTS_core_Chat -- "orchestrates" --> ChatTTS_model_gpt
    ChatTTS_core_Chat -- "orchestrates" --> ChatTTS_model_dvae
    ChatTTS_core_Chat -- "orchestrates" --> ChatTTS_model_speaker
    ChatTTS_core_Chat -- "orchestrates" --> ChatTTS_model_tokenizer
    ChatTTS_core_Chat -- "orchestrates" --> ChatTTS_model_embed
    ChatTTS_core_Chat -- "uses" --> ChatTTS_norm_Normalizer
    ChatTTS_core_Chat -- "uses" --> ChatTTS_utils
    ChatTTS_core_Chat -- "integrates with" --> ChatTTS_model_velocity
    ChatTTS_model_gpt -- "uses" --> ChatTTS_model_embed
    ChatTTS_model_gpt -- "uses" --> ChatTTS_model_speaker
    ChatTTS_model_gpt -- "interacts with" --> ChatTTS_model_dvae
    ChatTTS_model_gpt -- "can be optimized by" --> ChatTTS_model_velocity
    ChatTTS_model_dvae -- "interacts with" --> ChatTTS_model_gpt
    ChatTTS_model_speaker -- "provides embeddings to" --> ChatTTS_model_gpt
    ChatTTS_model_tokenizer -- "provides tokens to" --> ChatTTS_model_gpt
    ChatTTS_model_embed -- "provides embeddings to" --> ChatTTS_model_gpt
    ChatTTS_norm_Normalizer -- "processes text for" --> ChatTTS_model_tokenizer
    ChatTTS_utils -- "supports" --> ChatTTS_core_Chat
    ChatTTS_utils -- "supports" --> ChatTTS_model_velocity
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The central control unit and orchestrator of the ChatTTS application. It manages the entire text-to-speech workflow, coordinating model loading, asset management, text pre-processing, model inference, and audio output generation. It serves as the primary interface for user interaction, integrating various sub-components to achieve the final speech synthesis.

### ChatTTS.core.Chat
The central orchestrator of the ChatTTS application, managing the overall text-to-speech workflow.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/core.py#L31-L750" target="_blank" rel="noopener noreferrer">`ChatTTS.core.Chat` (31:750)</a>


### ChatTTS.model.gpt
The generative transformer model responsible for converting processed text and speaker information into latent speech representations. It's the core AI model for speech synthesis.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/model/gpt.py#L0-L0" target="_blank" rel="noopener noreferrer">`ChatTTS.model.gpt` (0:0)</a>


### ChatTTS.model.dvae
The Discrete Variational Autoencoder (DVAE) model. It encodes raw audio into discrete latent codes and decodes these codes back into audio, crucial for handling audio representations within the synthesis pipeline.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/model/dvae.py#L0-L0" target="_blank" rel="noopener noreferrer">`ChatTTS.model.dvae` (0:0)</a>


### ChatTTS.model.speaker
Manages speaker embeddings, allowing the system to generate speech in various voices. It can sample random speaker embeddings or encode speaker characteristics from audio.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/model/speaker.py#L0-L0" target="_blank" rel="noopener noreferrer">`ChatTTS.model.speaker` (0:0)</a>


### ChatTTS.model.tokenizer
Converts raw text input into a sequence of numerical tokens that the GPT model can process. It's a critical component for text pre-processing.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/model/tokenizer.py#L0-L0" target="_blank" rel="noopener noreferrer">`ChatTTS.model.tokenizer` (0:0)</a>


### ChatTTS.model.embed
Responsible for generating various embeddings, such as text embeddings, which serve as crucial inputs for the GPT model.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/model/embed.py#L0-L0" target="_blank" rel="noopener noreferrer">`ChatTTS.model.embed` (0:0)</a>


### ChatTTS.config.Config
Defines and manages application-wide configuration settings and parameters, including model paths and synthesis parameters.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/config/config.py#L124-L133" target="_blank" rel="noopener noreferrer">`ChatTTS.config.Config` (124:133)</a>


### ChatTTS.norm.Normalizer
Handles text normalization, converting raw text into a standardized format suitable for tokenization and speech synthesis, including handling homophones.


**Related Classes/Methods**:

- <a href="https://github.com/2noise/ChatTTS/blob/master/ChatTTS/norm.py#L70-L252" target="_blank" rel="noopener noreferrer">`ChatTTS.norm.Normalizer` (70:252)</a>


### ChatTTS.utils
A collection of general-purpose utility functions supporting various aspects of the application, such as downloading models, managing GPU resources, and file I/O.


**Related Classes/Methods**:

- `ChatTTS.utils` (0:0)


### ChatTTS.model.velocity
A package dedicated to optimizing LLM operations, potentially including components for efficient model loading, running, sampling, and scheduling, especially when `use_vllm` is enabled.


**Related Classes/Methods**:

- `ChatTTS.model.velocity` (0:0)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)