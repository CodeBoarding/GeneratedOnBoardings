```mermaid
graph LR
    LLM_Orchestrator["LLM Orchestrator"]
    Context_Management_Module["Context Management Module"]
    Memory_Management_Module["Memory Management Module"]
    Condition_Evaluation_Module["Condition Evaluation Module"]
    GPT_Selection_Module["GPT Selection Module"]
    Summarization_Module["Summarization Module"]
    LLM_External_["LLM (External)"]
    LLM_Orchestrator -- "Sends Prompts To" --> LLM_External_
    LLM_External_ -- "Returns Responses To" --> LLM_Orchestrator
    Context_Management_Module -- "Prepares Input For" --> LLM_Orchestrator
    LLM_Orchestrator -- "Sends Output To" --> Condition_Evaluation_Module
    LLM_Orchestrator -- "Sends Output To" --> GPT_Selection_Module
    LLM_Orchestrator -- "Stores Output In" --> Memory_Management_Module
    Memory_Management_Module -- "Provides Context To" --> Context_Management_Module
    Context_Management_Module -- "Sends Text For Summarization To" --> Summarization_Module
    Summarization_Module -- "Provides Summarized Text To" --> Context_Management_Module
    LLM_Orchestrator -- "Receives Evaluation Result From" --> Condition_Evaluation_Module
    LLM_Orchestrator -- "Receives Selected Option From" --> GPT_Selection_Module
    click LLM_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/thinkgpt/LLM_Orchestrator.md" "Details"
    click Memory_Management_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/thinkgpt/Memory_Management_Module.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `thinkgpt` project is structured around an `LLM Orchestrator` that serves as the central hub for interacting with external Large Language Models. This orchestrator is supported by several specialized modules: the `Context Management Module` prepares and optimizes input, integrating information from the `Memory Management Module` and `Summarization Module`. The `Memory Management Module` handles persistent and transient data storage. Post-LLM response, the `Condition Evaluation Module` and `GPT Selection Module` interpret and process the output for specific decision-making and conditional logic. The `Summarization Module` condenses large texts to fit LLM constraints. This modular design ensures efficient, context-aware, and adaptable LLM interactions. The core of the `thinkgpt` architecture revolves around the `LLM Orchestrator`, which acts as the primary interface to external LLMs. Data flow is largely initiated by the `LLM Orchestrator` sending prompts to the `LLM (External)` and receiving responses. Before prompt submission, the `Context Management Module` plays a crucial role in preparing the input, drawing upon historical data from the `Memory Management Module` and condensed information from the `Summarization Module`. After receiving responses from the LLM, the `LLM Orchestrator` dispatches these outputs to specialized modules like the `Condition Evaluation Module` for logical assessment and the `GPT Selection Module` for decision-making, receiving processed results back. This clear separation of concerns facilitates maintainable and scalable LLM application development, with distinct components handling context preparation, memory, summarization, and output interpretation.

### LLM Orchestrator [[Expand]](./LLM_Orchestrator.md)
The central component for direct interaction with the Large Language Model, managing prompt submission, API calls, and raw response retrieval. It acts as the gateway for all LLM-driven operations and integrates basic memory.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/llm.py" target="_blank" rel="noopener noreferrer">`thinkgpt/llm.py:predict`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/llm.py" target="_blank" rel="noopener noreferrer">`thinkgpt/llm.py:generate`</a>


### Context Management Module
Responsible for preparing and optimizing input context for the LLM, including token limit fitting, truncation, and integration of summarized or memorized information.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/helper.py" target="_blank" rel="noopener noreferrer">`thinkgpt/helper.py:fit_context`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/helper.py" target="_blank" rel="noopener noreferrer">`thinkgpt/helper.py:get_n_tokens`</a>


### Memory Management Module [[Expand]](./Memory_Management_Module.md)
Manages the system's persistent and transient memory, storing past interactions, facts, or conversational history to provide crucial context for LLM prompts.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/memory.py" target="_blank" rel="noopener noreferrer">`thinkgpt/memory.py:memorize`</a>


### Condition Evaluation Module
Interprets and evaluates specific conditions or logical statements based on the LLM's output, parsing structured data to determine true/false outcomes or extract values.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/condition.py" target="_blank" rel="noopener noreferrer">`thinkgpt/condition.py:predict`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/condition.py" target="_blank" rel="noopener noreferrer">`thinkgpt/condition.py:ConditionOutputParser`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/condition.py" target="_blank" rel="noopener noreferrer">`thinkgpt/condition.py:parse`</a>


### GPT Selection Module
Facilitates decision-making and option selection processes by formatting choices for the LLM and parsing the LLM's chosen option(s) from its response.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/gpt_select.py" target="_blank" rel="noopener noreferrer">`thinkgpt/gpt_select.py:predict`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/gpt_select.py" target="_blank" rel="noopener noreferrer">`thinkgpt/gpt_select.py:select`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/gpt_select.py" target="_blank" rel="noopener noreferrer">`thinkgpt/gpt_select.py:SelectOutputParser`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/gpt_select.py" target="_blank" rel="noopener noreferrer">`thinkgpt/gpt_select.py:format_options`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/gpt_select.py" target="_blank" rel="noopener noreferrer">`thinkgpt/gpt_select.py:parse`</a>


### Summarization Module
Processes and condenses large blocks of text into shorter, manageable summaries, vital for handling extensive documents or conversations that exceed LLM token limits.


**Related Classes/Methods**:

- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/summarize.py" target="_blank" rel="noopener noreferrer">`thinkgpt/summarize.py:chunked_summarize`</a>
- <a href="https://github.com/jina-ai/thinkgpt/blob/main/thinkgpt/summarize.py" target="_blank" rel="noopener noreferrer">`thinkgpt/summarize.py:summarize`</a>


### LLM (External)
Represents the external Large Language Model service that the `LLM Orchestrator` interacts with for generating predictions and responses. This component is external to the `thinkgpt` codebase.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)