```mermaid
graph LR
    litellm_main["litellm.main"]
    litellm_llms["litellm.llms"]
    litellm_caching["litellm.caching"]
    litellm_litellm_core_utils_litellm_logging["litellm.litellm_core_utils.litellm_logging"]
    litellm_exceptions["litellm.exceptions"]
    litellm_secret_managers_main["litellm.secret_managers.main"]
    litellm_router["litellm.router"]
    litellm_utils["litellm.utils"]
    litellm_litellm_core_utils_fallback_utils["litellm.litellm_core_utils.fallback_utils"]
    litellm_types["litellm.types"]
    litellm_litellm_core_utils_prompt_templates_factory["litellm.litellm_core_utils.prompt_templates.factory"]
    litellm_main -- "dispatches to" --> litellm_llms
    litellm_llms -- "returns responses to" --> litellm_main
    litellm_main -- "integrates with" --> litellm_caching
    litellm_main -- "sends data to" --> litellm_litellm_core_utils_litellm_logging
    litellm_litellm_core_utils_litellm_logging -- "executes" --> litellm_main
    litellm_main -- "raises" --> litellm_exceptions
    litellm_main -- "catches" --> litellm_exceptions
    litellm_main -- "requests secrets from" --> litellm_secret_managers_main
    litellm_main -- "relies on" --> litellm_router
    litellm_main -- "leverages" --> litellm_utils
    litellm_main -- "employs" --> litellm_litellm_core_utils_fallback_utils
    litellm_main -- "depends on" --> litellm_types
    litellm_main -- "uses" --> litellm_litellm_core_utils_prompt_templates_factory
    click litellm_main href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//litellm/litellm_main.md" "Details"
    click litellm_llms href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//litellm/litellm_llms.md" "Details"
    click litellm_router href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//litellm/litellm_router.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The central entry point for all LLM API interactions in LiteLLM. It acts as a facade, abstracting away the complexities of different LLM providers. It handles request pre-processing, provider dispatch, response post-processing, and integrates with core services like caching, logging, and error handling.

### litellm.main
The central entry point for all LLM API interactions in LiteLLM. It acts as a facade, abstracting away the complexities of different LLM providers. It handles request pre-processing, provider dispatch, response post-processing, and integrates with core services like caching, logging, and error handling.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/main.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.main` (1:1)</a>


### litellm.llms
This package contains the concrete implementations for interacting with various LLM providers (e.g., OpenAI, Azure, Bedrock, Cohere). It abstracts away provider-specific API calls and response formats.


**Related Classes/Methods**:

- `litellm.llms` (1:1)


### litellm.caching
Manages the caching of LLM responses to improve performance, reduce latency, and minimize costs by reusing previous results.


**Related Classes/Methods**:

- `litellm.caching` (1:1)


### litellm.litellm_core_utils.litellm_logging
Provides a centralized mechanism for logging events, managing custom callback functions, and tracking metrics throughout the LLM request lifecycle.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/litellm_core_utils/litellm_logging.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.litellm_core_utils.litellm_logging` (1:1)</a>


### litellm.exceptions
Defines a comprehensive set of custom exception classes specific to LiteLLM, enabling structured and informative error management across different LLM providers and internal processes.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/exceptions.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.exceptions` (1:1)</a>


### litellm.secret_managers.main
Securely retrieves and manages API keys and other sensitive credentials required for authenticating with various LLM providers.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/secret_managers/main.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.secret_managers.main` (1:1)</a>


### litellm.router
Directs incoming LLM requests to the most appropriate model or deployment based on configured routing strategies (e.g., load balancing, failover, cost optimization).


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/router.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.router` (1:1)</a>


### litellm.utils
A collection of essential helper functions used throughout the LiteLLM library for tasks such as token counting, parameter validation, response object conversion, and model information retrieval.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/utils.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.utils` (1:1)</a>


### litellm.litellm_core_utils.fallback_utils
Implements the logic for retrying failed LLM requests with alternative models or providers, enhancing the system's resilience and reliability.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/litellm_core_utils/fallback_utils.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.litellm_core_utils.fallback_utils` (1:1)</a>


### litellm.types
Defines the data structures, Pydantic models, and type hints used across the LiteLLM library, ensuring type safety, data validation, and clear API contracts.


**Related Classes/Methods**:

- `litellm.types` (1:1)


### litellm.litellm_core_utils.prompt_templates.factory
Provides utilities for dynamically generating and transforming prompts based on different models and use cases, including handling function calls and system messages.


**Related Classes/Methods**:

- <a href="https://github.com/BerriAI/litellm/blob/master/litellm/litellm_core_utils/prompt_templates/factory.py#L1-L1" target="_blank" rel="noopener noreferrer">`litellm.litellm_core_utils.prompt_templates.factory` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)