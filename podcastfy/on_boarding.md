```mermaid
graph LR
    API_Gateway["API Gateway"]
    Orchestration_Pipeline["Orchestration Pipeline"]
    Content_Parser["Content Parser"]
    Script_Generator["Script Generator"]
    Speech_Synthesizer["Speech Synthesizer"]
    Configuration_Service["Configuration Service"]
    API_Gateway -- "Triggers podcast job" --> Orchestration_Pipeline
    Orchestration_Pipeline -- "Returns final audio" --> API_Gateway
    Orchestration_Pipeline -- "Requests text extraction" --> Content_Parser
    Content_Parser -- "Returns raw text" --> Orchestration_Pipeline
    Orchestration_Pipeline -- "Requests script generation" --> Script_Generator
    Script_Generator -- "Returns podcast script" --> Orchestration_Pipeline
    Orchestration_Pipeline -- "Requests audio synthesis" --> Speech_Synthesizer
    Speech_Synthesizer -- "Returns final audio" --> Orchestration_Pipeline
    Content_Parser -- "Reads settings" --> Configuration_Service
    Script_Generator -- "Reads settings" --> Configuration_Service
    Speech_Synthesizer -- "Reads settings" --> Configuration_Service
    click API_Gateway href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/podcastfy/API_Gateway.md" "Details"
    click Orchestration_Pipeline href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/podcastfy/Orchestration_Pipeline.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### API Gateway [[Expand]](./API_Gateway.md)
Exposes the podcast generation service via a RESTful API. It receives user requests and triggers the main orchestration pipeline, returning the final audio file upon completion.


**Related Classes/Methods**:

- `src/podcast_generator/main.py`


### Orchestration Pipeline [[Expand]](./Orchestration_Pipeline.md)
The central coordinator that manages the end-to-end workflow. It sequentially invokes the parser, generator, and synthesizer, passing data between them to ensure a smooth transformation from source content to final audio.


**Related Classes/Methods**:

- `src/podcast_generator/podcast_generator.py`


### Content Parser
A facade responsible for ingesting content from various sources (e.g., websites, PDFs, YouTube). It uses a strategy pattern to select the appropriate extractor and returns clean, raw text to the pipeline.


**Related Classes/Methods**:

- `src/podcast_generator/utils/content_extractor.py`


### Script Generator
Transforms the raw text provided by the Content Parser into a structured, conversational podcast script. It uses LLMs and can employ different strategies to tailor the content's length and format.


**Related Classes/Methods**:

- `src/podcast_generator/utils/text_to_podcast.py`


### Speech Synthesizer
Converts the final podcast script into an audio file. It acts as a facade for various Text-to-Speech (TTS) providers, using a factory to select the appropriate service and manage audio generation.


**Related Classes/Methods**:

- `src/podcast_generator/utils/tts.py`


### Configuration Service
A centralized component that manages and provides access to all application settings. This includes API keys, LLM prompt templates, TTS voice selections, and other operational parameters.


**Related Classes/Methods**:

- `src/podcast_generator/params.py`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)