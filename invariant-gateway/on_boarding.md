Okay, I will generate an onboarding document for the `invariant-gateway` project based on the provided information.

**Project Description**

The `invariant-gateway` project acts as a secure and compliant intermediary for Large Language Model (LLM) requests. It provides a unified interface for interacting with various LLM providers (OpenAI, Gemini, Anthropic), enforces guardrails to ensure responsible AI usage, and integrates with monitoring tools for real-time analysis and auditing. The gateway manages authentication, request routing, guardrail checks, and response instrumentation, offering a robust and manageable solution for organizations leveraging LLMs.

**Flow Diagram**

```mermaid
graph LR
    subgraph Client
    A[Client Application]
    end

    subgraph Invariant Gateway
    B[Request Handling and Routing]
    C[Guardrail Enforcement]
    D[Instrumented Streaming Response]
    E[Configuration Management]
    F[Main Control Program (MCP)]
    end

    subgraph LLM Provider
    G[LLM Provider (OpenAI, Gemini, Anthropic)]
    end

    subgraph Explorer
    H[Explorer Service]
    end

    A--Sends Request-->B
    B--Creates Context-->C
    B--Routes Request-->G
    C--Checks Request-->G
    G--Sends Response-->D
    D--Applies Guardrails-->C
    D--Streams Response-->A
    C--Pushes Traces-->H
    E--Provides Config-->C
    F--Orchestrates-->B
    F--Manages-->C
    F--Handles-->D
```

**Component Descriptions**

*   **Client Application:** The application or system that initiates requests to the LLM providers through the Invariant Gateway. It receives the processed responses from the gateway.
*   **Request Handling and Routing:** This component receives incoming requests, authenticates them, creates a request context, and routes them to the appropriate LLM provider (OpenAI, Gemini, Anthropic). It acts as the entry point for all LLM interactions.
*   **Guardrail Enforcement:** This component is responsible for enforcing guardrails on both incoming requests and outgoing responses. It checks requests against defined guardrails, applies actions based on violations, and integrates with the Explorer service for fetching guardrails and pushing traces.
*   **Instrumented Streaming Response:** This component wraps the streaming responses from the LLM providers. It applies guardrails to the streaming data, pushes traces to the Explorer service for real-time monitoring, and handles the streaming of data back to the client.
*   **Configuration Management:** This component manages the gateway's configuration, including guardrails, API keys, and other settings. It provides a centralized way to configure and update the gateway's behavior.
*   **Main Control Program (MCP):** This component executes the main control loop of the gateway. It handles input, orchestrates guardrail checks, and manages output streaming, acting as the central coordinator for the gateway's operations.
*   **LLM Provider (OpenAI, Gemini, Anthropic):** The actual Large Language Model service that processes the requests and generates responses. The gateway supports multiple providers.
*   **Explorer Service:** A monitoring and analysis service that receives traces and annotations from the gateway, providing insights into the performance and compliance of LLM interactions.