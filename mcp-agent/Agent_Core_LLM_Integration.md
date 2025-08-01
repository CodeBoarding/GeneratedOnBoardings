```mermaid
graph LR
    Agent_Core["Agent Core"]
    Augmented_LLM_Interface["Augmented LLM Interface"]
    LLM_Selector["LLM Selector"]
    LLM_Provider_Implementations["LLM Provider Implementations"]
    Provider_to_MCP_Converters["Provider to MCP Converters"]
    Agent_Core -- "uses" --> Augmented_LLM_Interface
    Augmented_LLM_Interface -- "uses" --> LLM_Selector
    LLM_Provider_Implementations -- "implements" --> Augmented_LLM_Interface
    LLM_Provider_Implementations -- "uses" --> Provider_to_MCP_Converters
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This subsystem defines the fundamental interface and capabilities of an AI agent, encapsulating interactions with Large Language Models (LLMs), external tools, prompts, and resources. It provides a consistent and extensible model for agent behavior and offers a standardized, augmented interface for interacting with various LLM providers.

### Agent Core
This is the foundational interface for all AI agents within the `mcp-agent` framework. It defines the core capabilities and interaction points of an agent, serving as the base for more specialized agent types. It encapsulates the agent's logic, its interaction with LLMs, and its ability to utilize external tools and resources.


**Related Classes/Methods**:

- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/agents/agent.py#L56-L934" target="_blank" rel="noopener noreferrer">`mcp_agent.agents.agent.Agent` (56:934)</a>


### Augmented LLM Interface
This abstract component provides a unified and enhanced interface for interacting with different LLM providers. It abstracts away the vendor-specific details of LLM APIs, allowing the rest of the framework to interact with LLMs in a consistent manner, regardless of the underlying provider. It supports various LLM operations, including completion and structured completion requests.


**Related Classes/Methods**:

- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm.py#L218-L668" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm.AugmentedLLM` (218:668)</a>


### LLM Selector
This component is responsible for intelligently selecting the most suitable LLM model for a given task. It considers various criteria such as cost, latency, and performance benchmarks to make informed decisions, optimizing resource utilization and response quality.


**Related Classes/Methods**:

- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/llm_selector.py#L96-L413" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.llm_selector.ModelSelector` (96:413)</a>


### LLM Provider Implementations
These are concrete implementations of the `Augmented LLM Interface`, providing the actual connectivity and interaction logic for specific LLM providers (e.g., Anthropic, Azure, Bedrock, Google, OpenAI, Ollama). Each implementation handles the nuances of its respective LLM API and translates requests and responses to and from the framework's internal format.


**Related Classes/Methods**:

- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_anthropic.py#L110-L722" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_anthropic.AnthropicAugmentedLLM` (110:722)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_azure.py#L82-L491" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_azure.AzureAugmentedLLM` (82:491)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_bedrock.py#L48-L349" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_bedrock.BedrockAugmentedLLM` (48:349)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_google.py#L34-L319" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_google.GoogleAugmentedLLM` (34:319)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_ollama.py#L16-L78" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_ollama.OllamaAugmentedLLM` (16:78)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_openai.py#L80-L845" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_openai.OpenAIAugmentedLLM` (80:845)</a>


### Provider to MCP Converters
These utility classes are crucial for ensuring data consistency and interoperability across different LLM providers. They are responsible for converting provider-specific data structures (e.g., Anthropic's messages, OpenAI's chat completions) into the framework's standardized Model Context Protocol (MCP) types.


**Related Classes/Methods**:

- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_anthropic.py#L777-L886" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_anthropic.AnthropicMCPTypeConverter` (777:886)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_azure.py#L524-L614" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_azure.MCPAzureTypeConverter` (524:614)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_bedrock.py#L437-L499" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_bedrock.BedrockMCPTypeConverter` (437:499)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_google.py#L403-L518" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_google.GoogleMCPTypeConverter` (403:518)</a>
- <a href="https://github.com/lastmile-ai/mcp-agent/blob/main/src/mcp_agent/workflows/llm/augmented_llm_openai.py#L949-L1055" target="_blank" rel="noopener noreferrer">`mcp_agent.workflows.llm.augmented_llm_openai.MCPOpenAITypeConverter` (949:1055)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)