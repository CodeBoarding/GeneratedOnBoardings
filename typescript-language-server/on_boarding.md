```mermaid
graph LR
    LSP_Communication_Layer["LSP Communication Layer"]
    TypeScript_Service_Adapter["TypeScript Service Adapter"]
    Workspace_Document_Management["Workspace & Document Management"]
    Language_Feature_Processors["Language Feature Processors"]
    Diagnostic_Pipeline["Diagnostic Pipeline"]
    LSP_Communication_Layer -- "dispatches requests to" --> Language_Feature_Processors
    Language_Feature_Processors -- "sends results to" --> LSP_Communication_Layer
    LSP_Communication_Layer -- "sends document content to" --> Workspace_Document_Management
    Workspace_Document_Management -- "provides document content to" --> Language_Feature_Processors
    Language_Feature_Processors -- "queries" --> TypeScript_Service_Adapter
    Language_Feature_Processors -- "accesses" --> Workspace_Document_Management
    TypeScript_Service_Adapter -- "notifies" --> LSP_Communication_Layer
    TypeScript_Service_Adapter -- "queries" --> Workspace_Document_Management
    Workspace_Document_Management -- "triggers" --> Diagnostic_Pipeline
    Diagnostic_Pipeline -- "publishes diagnostics to" --> LSP_Communication_Layer
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Updated architectural analysis with verifiable code references and corrected component relationships.

### LSP Communication Layer
Handles all interactions with the LSP client, including receiving requests, dispatching them, and sending responses and notifications.


**Related Classes/Methods**:

- `src/server.ts` (1:1)
- `src/connection.ts` (1:1)
- `src/protocol.ts` (1:1)


### TypeScript Service Adapter
Manages the lifecycle and communication with the external `tsserver` process, including protocol translation between LSP and `tsserver` formats.


**Related Classes/Methods**:

- `src/tsServer.ts` (1:1)
- <a href="https://github.com/typescript-language-server/typescript-language-server/blob/master/src/typescriptService.ts#L1-L1" target="_blank" rel="noopener noreferrer">`src/typescriptService.ts` (1:1)</a>
- `src/protocol.ts` (1:1)


### Workspace & Document Management
Maintains the in-memory representation of open text documents, handles document synchronization, and manages server and workspace-specific configurations.


**Related Classes/Methods**:

- `src/languageFeatures.ts` (1:1)
- `src/configuration.ts` (1:1)
- `src/documents.ts` (1:1)


### Language Feature Processors
Implements the various language features (e.g., completion, hover, refactoring) by orchestrating requests to the `TypeScript Service Adapter` and utilizing data from `Workspace & Document Management`.


**Related Classes/Methods**:

- `src/features/completion.ts` (1:1)
- `src/features/hover.ts` (1:1)
- `src/features/documentSymbol.ts` (1:1)
- `src/features/refactor.ts` (1:1)
- `src/features/codeLens.ts` (1:1)
- `src/features/inlayHints.ts` (1:1)


### Diagnostic Pipeline
Responsible for processing, filtering, and publishing diagnostic information received from the `tsserver` to the LSP client.


**Related Classes/Methods**:

- `src/diagnostics.ts` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)