```mermaid
graph LR
    API_Layer_FastMCP_Server["API Layer – FastMCP Server"]
    Orchestrator_Workflow_Engine["Orchestrator / Workflow Engine"]
    Guardrails_Policy_Layer["Guardrails – Policy Layer"]
    Platform_Connectors_Adapters_["Platform Connectors (Adapters)"]
    Data_Mesh_Manager_Client["Data‑Mesh Manager Client"]
    Unclassified["Unclassified"]
    API_Layer_FastMCP_Server -- "calls" --> Orchestrator_Workflow_Engine
    Orchestrator_Workflow_Engine -- "invokes" --> Guardrails_Policy_Layer
    Orchestrator_Workflow_Engine -- "calls" --> Platform_Connectors_Adapters_
    Orchestrator_Workflow_Engine -- "calls" --> Data_Mesh_Manager_Client
    click API_Layer_FastMCP_Server href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/dataproduct-mcp/API_Layer_FastMCP_Server.md" "Details"
    click Orchestrator_Workflow_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/dataproduct-mcp/Orchestrator_Workflow_Engine.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Data‑Product MCP Server is a FastAPI‑based micro‑service exposing four LLM‑visible tools (search, get, request_access, query) via a FastMCP server. Incoming tool calls are routed to the Orchestrator, which implements a three‑step workflow: discovery of data products via the Data‑Mesh Manager client, policy enforcement through Guardrails (read‑only SQL validation and prompt‑injection sanitisation), and execution of the SQL query on the appropriate data platform using Platform Connectors (Snowflake, Databricks, or BigQuery). The orchestrated result is sanitised and returned to the LLM. This layered architecture isolates external catalogue interaction, security policy enforcement, and platform‑specific execution, facilitating maintainability and extensibility.

### API Layer – FastMCP Server [[Expand]](./API_Layer_FastMCP_Server.md)
Hosts a FastAPI‑style MCP (FastMCP) and registers the LLM‑visible tools (dataproduct_search, dataproduct_get, dataproduct_request_access, dataproduct_query). It forwards request payloads to the Orchestrator.


**Related Classes/Methods**:

- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/server.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.server`</a>


### Orchestrator / Workflow Engine [[Expand]](./Orchestrator_Workflow_Engine.md)
Implements the three‑step workflow (discover → govern → execute). Coordinates the Data‑Mesh Manager client, Guardrails, and Platform Connectors to fulfil tool requests.


**Related Classes/Methods**:

- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/server.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.server`</a>


### Guardrails – Policy Layer
Provides security‑policy enforcement: validates read‑only SQL and sanitises prompt‑injection strings.


**Related Classes/Methods**:

- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/guardrails/__init__.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.guardrails`</a>
- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/guardrails/readonly.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.guardrails.readonly`</a>
- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/guardrails/prompt_injection.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.guardrails.prompt_injection`</a>


### Platform Connectors (Adapters)
Uniform façade for the three supported data platforms. Each adapter parses connection info, builds a client, and runs the supplied SQL query.


**Related Classes/Methods**:

- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/connections/snowflake_client.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.connections.snowflake_client`</a>
- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/connections/databricks_client.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.connections.databricks_client`</a>
- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/connections/bigquery_client.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.connections.bigquery_client`</a>


### Data‑Mesh Manager Client
Thin wrapper around the external Data‑Mesh Manager REST API, providing discovery, metadata, access‑status, request, and evaluation operations.


**Related Classes/Methods**:

- <a href="https://github.com/entropy-data/dataproduct-mcp/blob/main/src/dataproduct_mcp/datameshmanager/datamesh_manager_client.py" target="_blank" rel="noopener noreferrer">`dataproduct_mcp.datameshmanager.datamesh_manager_client`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)