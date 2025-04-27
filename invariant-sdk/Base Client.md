## Component Overview: Base Client

The `BaseClient` component serves as the foundation for interacting with the Invariant APIs. It encapsulates the core logic for handling API requests, including authentication, error handling, and request preparation. It's designed to be inherited by both synchronous and asynchronous client implementations.

```mermaid
classDiagram
    class BaseClient {
        -api_url: str
        -api_key: str
        -timeout_ms: Tuple[int, int]
        __init__(api_url, api_key, timeout_ms)
        _headers: Dict[str, str]
        _handle_http_error(method: str, pathname: str, response)
        _prepare_request_kwargs(request_kwargs: Optional[Mapping]) Dict
        _prepare_push_trace_request(request: PushTracesRequest, request_kwargs: Optional[Mapping]) Dict
        _prepare_get_dataset_metadata_request(request_kwargs: Optional[Mapping]) Dict
        _prepare_update_dataset_metadata_request(request: UpdateDatasetMetadataRequest, request_kwargs: Optional[Mapping]) Dict
        _prepare_append_messages_request(request: AppendMessagesRequest, request_kwargs: Optional[Mapping]) Dict
    }
    class AsyncClient {
        __init__(api_url, api_key, timeout_ms)
        request(method: str, pathname: str, request_kwargs: Optional[Mapping])
        push_trace(request: PushTracesRequest, request_kwargs: Optional[Mapping])
    }
    class Client {
        __init__(api_url, api_key, timeout_ms)
        request(method: str, pathname: str, request_kwargs: Optional[Mapping])
        push_trace(request: PushTracesRequest, request_kwargs: Optional[Mapping])
    }
    BaseClient <|-- AsyncClient : inherits
    BaseClient <|-- Client : inherits
    BaseClient -- utils : uses
    BaseClient -- exceptions : handles



```

### Component Descriptions:

*   **BaseClient**: This is the abstract base class that handles API URL and API Key retrieval from environment variables using the `utils` component. It also defines methods for preparing requests and handling HTTP errors, raising specific exceptions from the `exceptions` component based on the response status code. It is inherited by `AsyncClient` and `Client`.
    *   **Source Files**: `invariant_sdk/base_client.py`
*   **AsyncClient**: Inherits from `BaseClient` and implements asynchronous API requests using the `httpx` library. It overrides the `request` method to perform asynchronous calls. It uses the `BaseClient` methods for request preparation and error handling.
    *   **Source Files**: `invariant_sdk/async_client.py`
*   **Client**: Inherits from `BaseClient` and implements synchronous API requests using the `requests` library. It overrides the `request` method to perform synchronous calls. It uses the `BaseClient` methods for request preparation and error handling.
    *   **Source Files**: `invariant_sdk/client.py`
*   **utils**: Provides utility functions for retrieving the API URL and API Key from environment variables. `BaseClient` uses these utilities during initialization.
    *   **Source Files**: `invariant_sdk/utils.py`
*   **exceptions**: Defines custom exception classes for different API error scenarios. `BaseClient` raises these exceptions in the `_handle_http_error` method.
    *   **Source Files**: `invariant_sdk/types/exceptions.py`
