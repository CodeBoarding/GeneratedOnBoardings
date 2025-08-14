```mermaid
graph LR
    WhatsApp_Integration["WhatsApp Integration"]
    Bot_Orchestration["Bot Orchestration"]
    AI_Request_Processing["AI Request Processing"]
    Speech_Processing["Speech Processing"]
    Configuration_Management["Configuration Management"]
    WhatsApp_Integration -- "forwards incoming messages to" --> Bot_Orchestration
    Bot_Orchestration -- "sends outgoing responses to" --> WhatsApp_Integration
    Bot_Orchestration -- "dispatches AI-related queries to" --> AI_Request_Processing
    AI_Request_Processing -- "returns AI-generated content to" --> Bot_Orchestration
    Bot_Orchestration -- "dispatches voice messages for transcription to" --> Speech_Processing
    Speech_Processing -- "returns transcribed text to" --> Bot_Orchestration
    Configuration_Management -- "provides settings to" --> WhatsApp_Integration
    Configuration_Management -- "provides settings to" --> Bot_Orchestration
    Configuration_Management -- "provides settings to" --> AI_Request_Processing
    Configuration_Management -- "provides settings to" --> Speech_Processing
    click WhatsApp_Integration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whatsapp-chatgpt/WhatsApp_Integration.md" "Details"
    click Bot_Orchestration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whatsapp-chatgpt/Bot_Orchestration.md" "Details"
    click AI_Request_Processing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whatsapp-chatgpt/AI_Request_Processing.md" "Details"
    click Speech_Processing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whatsapp-chatgpt/Speech_Processing.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### WhatsApp Integration [[Expand]](./WhatsApp_Integration.md)
Manages the WhatsApp Web client, handles the reception of incoming messages (text, voice, media), and sends outgoing responses back to users. It acts as the primary interface between the bot's internal logic and the WhatsApp platform.


**Related Classes/Methods**:

- `src/index.ts`
- `src/handlers/message.ts`


### Bot Orchestration [[Expand]](./Bot_Orchestration.md)
This is the central intelligence and control hub of the bot. It receives processed messages, analyzes user intent, manages conversation context, and orchestrates the flow of information by dispatching requests to the appropriate AI or Speech processing components, and formats the final AI-generated content into user-friendly responses.


**Related Classes/Methods**:

- `src/handlers/message.ts`
- `src/index.ts`


### AI Request Processing [[Expand]](./AI_Request_Processing.md)
Encapsulates the logic for interacting with external Artificial Intelligence services, specifically OpenAI's GPT (for text) and DALL-E 2 (for images). It handles request formatting, API calls, and parsing of AI-generated responses.


**Related Classes/Methods**:

- `src/handlers/gpt.ts`
- `src/handlers/dalle.ts`
- `src/providers/openai.ts`


### Speech Processing [[Expand]](./Speech_Processing.md)
Dedicated to handling voice messages, this component is responsible for transcribing spoken language into text (speech-to-text) using either an external `speech-rest-api` or a local Whisper model.


**Related Classes/Methods**:

- `src/providers/speech.ts`
- `src/providers/whisper-local.ts`


### Configuration Management
Provides a centralized and secure mechanism for managing all application settings, environment variables, and sensitive information such as API keys, ensuring other components can access necessary configurations without hardcoding.


**Related Classes/Methods**:

- `src/config.ts`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)