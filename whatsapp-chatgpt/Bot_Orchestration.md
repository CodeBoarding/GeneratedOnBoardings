```mermaid
graph LR
    Bot_Orchestration["Bot Orchestration"]
    WhatsApp_Client["WhatsApp Client"]
    ChatGPT_Service["ChatGPT Service"]
    DALL_E_Service["DALL-E Service"]
    Speech_to_Text_Service["Speech-to-Text Service"]
    Configuration_Manager["Configuration Manager"]
    WhatsApp_Client -- "sends IncomingMessage to" --> Bot_Orchestration
    Bot_Orchestration -- "sends OutgoingMessage to" --> WhatsApp_Client
    Bot_Orchestration -- "sends TextPrompt to" --> ChatGPT_Service
    ChatGPT_Service -- "sends TextResponse to" --> Bot_Orchestration
    Bot_Orchestration -- "sends ImageGenerationPrompt to" --> DALL_E_Service
    DALL_E_Service -- "sends GeneratedImageURL to" --> Bot_Orchestration
    Bot_Orchestration -- "sends VoiceMessageAudio to" --> Speech_to_Text_Service
    Speech_to_Text_Service -- "sends TranscribedText to" --> Bot_Orchestration
    Bot_Orchestration -- "requests BotSettings from" --> Configuration_Manager
    Configuration_Manager -- "provides BotSettings to" --> Bot_Orchestration
    click Bot_Orchestration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whatsapp-chatgpt/Bot_Orchestration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Bot Orchestration [[Expand]](./Bot_Orchestration.md)
This is the core intelligence unit. It receives processed messages, analyzes user intent, manages conversation context, and dispatches requests to appropriate AI or speech processing components. It also formats AI-generated content into user-friendly responses.


**Related Classes/Methods**:

- `src/handlers/message.ts`
- `src/index.ts`


### WhatsApp Client
This component is responsible for all interactions with the WhatsApp messaging platform, including receiving incoming messages, sending outgoing responses, and managing the WhatsApp session.


**Related Classes/Methods**:

- `whatsapp-web.js`
- `Puppeteer`
- `src/index.ts`


### ChatGPT Service
This component provides an interface to the ChatGPT AI model, handling requests for text generation based on user prompts and returning the AI's textual responses.


**Related Classes/Methods**:

- `chatgpt-api`
- `src/handlers/gpt.ts`
- `src/providers/openai.ts`


### DALL-E Service
This component manages communication with the DALL-E AI model, facilitating image generation requests from text prompts and returning URLs to the generated images.


**Related Classes/Methods**:

- `OpenAI API`
- `src/handlers/dalle.ts`
- `src/types/dalle-config.ts`


### Speech-to-Text Service
This component is responsible for converting spoken language (e.g., from voice messages) into text, which can then be processed by the `Bot Orchestration` and AI services.


**Related Classes/Methods**:

- `speech-rest-api`
- `src/providers/speech.ts`
- `src/providers/whisper-local.ts`
- `src/types/transcription-mode.ts`


### Configuration Manager
This component centralizes the management and provision of all bot-related configuration settings, such as API keys and operational parameters, ensuring secure and consistent access.


**Related Classes/Methods**:

- `src/config.ts`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)