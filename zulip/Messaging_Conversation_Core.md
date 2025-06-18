```mermaid
graph LR
    zerver_views_message_send["zerver.views.message_send"]
    zerver_actions_message_send["zerver.actions.message_send"]
    zerver_views_message_fetch["zerver.views.message_fetch"]
    zerver_models_messages["zerver.models.messages"]
    zerver_lib_message["zerver.lib.message"]
    zerver_lib_narrow["zerver.lib.narrow"]
    zerver_lib_markdown["zerver.lib.markdown"]
    zerver_models_streams["zerver.models.streams"]
    zerver_models_recipients["zerver.models.recipients"]
    zerver_lib_streams["zerver.lib.streams"]
    zerver_views_message_send -- "Delegates message processing" --> zerver_actions_message_send
    zerver_views_message_send -- "Uses for content rendering before sending" --> zerver_lib_markdown
    zerver_actions_message_send -- "Relies on for message content normalization and validation" --> zerver_lib_message
    zerver_actions_message_send -- "Persists message data" --> zerver_models_messages
    zerver_actions_message_send -- "Persists recipient data" --> zerver_models_recipients
    zerver_actions_message_send -- "Interacts with for stream access control" --> zerver_lib_streams
    zerver_actions_message_send -- "Sends message content to for rendering" --> zerver_lib_markdown
    zerver_views_message_fetch -- "Uses to perform message filtering and retrieval" --> zerver_lib_narrow
    zerver_views_message_fetch -- "Receives message data from for formatting and presentation" --> zerver_lib_message
    zerver_lib_message -- "Retrieves and manipulates message data" --> zerver_models_messages
    zerver_lib_message -- "Uses for rendering message content" --> zerver_lib_markdown
    zerver_lib_narrow -- "Interacts with to query message data" --> zerver_models_messages
    zerver_lib_narrow -- "Interacts with to query stream data" --> zerver_models_streams
    zerver_lib_narrow -- "Interacts with to query recipient data" --> zerver_models_recipients
    zerver_lib_streams -- "Interacts with for stream data persistence" --> zerver_models_streams
    zerver_lib_streams -- "Manages recipient creation for streams" --> zerver_models_recipients
    zerver_models_messages -- "Linked to (messages have recipients)" --> zerver_models_recipients
    zerver_models_messages -- "Linked to (messages belong to streams)" --> zerver_models_streams
    zerver_models_recipients -- "Linked to (stream recipients point to streams)" --> zerver_models_streams
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `Messaging & Conversation Core` subsystem in Zulip is the central communication engine, managing the entire lifecycle of messages from sending and editing to displaying them within structured conversations (streams and topics) and direct messages. It also handles message content processing, including Markdown rendering, mentions, and emoji.

### zerver.views.message_send
This component provides the API endpoint that users interact with to send messages. It acts as the initial entry point for all message sending requests, performing preliminary validation and then delegating the core business logic to `zerver.actions.message_send`.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/views/message_send.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/views/message_send.py` (1:1)</a>


### zerver.actions.message_send
This is the core business logic orchestrator for message processing. It handles message validation, content rendering, recipient resolution, persistence to the database, and triggering subsequent actions like notifications.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/actions/message_send.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/actions/message_send.py` (1:1)</a>


### zerver.views.message_fetch
This component exposes API endpoints for retrieving messages. It processes client requests for message history, applying various search and narrowing parameters, and then utilizes `zerver.lib.narrow` to fetch the relevant messages.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/views/message_fetch.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/views/message_fetch.py` (1:1)</a>


### zerver.models.messages
This component defines the Django ORM models for `Message` (the actual message content) and `UserMessage` (user-specific metadata and flags for each message). It is the primary data store for all conversation content.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/models/messages.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/models/messages.py` (1:1)</a>


### zerver.lib.message
This library provides a suite of utility functions for various message-related operations, including content normalization, access control checks, and retrieving message data. It acts as a central library for consistent message handling logic across the application.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/lib/message.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/lib/message.py` (1:1)</a>


### zerver.lib.narrow
This component implements the sophisticated logic for filtering and searching messages based on various criteria (e.g., streams, topics, senders, keywords). It constructs and executes database queries to efficiently retrieve relevant messages.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/lib/narrow.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/lib/narrow.py` (1:1)</a>


### zerver.lib.markdown
Responsible for converting message content from Markdown format into HTML for display. It supports various Markdown extensions and Zulip-specific features like mentions and emoji, ensuring messages are rendered correctly.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/lib/markdown/__init__.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/lib/markdown/__init__.py` (1:1)</a>


### zerver.models.streams
This component defines the Django ORM model for `Stream`, which represents a channel or public/private conversation. It stores metadata about streams, including their name, description, and access policies.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/models/streams.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/models/streams.py` (1:1)</a>


### zerver.models.recipients
This component defines the Django ORM model for `Recipient`, which links messages to their intended destinations (streams, private message groups, or direct messages). It also defines `DirectMessageGroup` for group DMs.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/models/recipients.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/models/recipients.py` (1:1)</a>


### zerver.lib.streams
This library manages all operations related to streams, including their creation, subscription management, access control, and retrieval. It ensures proper permissions and data integrity for stream-based conversations.


**Related Classes/Methods**:

- <a href="https://github.com/zulip/zulip/blob/master/zerver/lib/streams.py#L1-L1" target="_blank" rel="noopener noreferrer">`zerver/lib/streams.py` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)