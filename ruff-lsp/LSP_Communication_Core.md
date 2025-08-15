```mermaid
graph LR
    LSP_Communication_Core["LSP Communication Core"]
    Ruff_Process_Manager["Ruff Process Manager"]
    LSP_Communication_Core -- "orchestrates" --> Ruff_Process_Manager
    Ruff_Process_Manager -- "returns results to" --> LSP_Communication_Core
    click LSP_Communication_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/ruff-lsp/LSP_Communication_Core.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `ruff-lsp` project is structured around two primary architectural components: the `LSP Communication Core` and the `Ruff Process Manager`. The `LSP Communication Core` acts as the central interface for all Language Server Protocol interactions, handling incoming requests from the client, dispatching them to appropriate handlers, and managing the server's lifecycle. It is responsible for parsing LSP messages, maintaining document states, and sending responses and notifications. Complementing this, the `Ruff Process Manager` is dedicated to abstracting and managing the execution of Ruff commands as an external process. It handles the invocation of the Ruff binary, manages its input/output streams, and ensures efficient execution of linting, formatting, and other Ruff-related operations. The `LSP Communication Core` orchestrates the `Ruff Process Manager` to perform code analysis and fixes, with the results being returned to the `LSP Communication Core` for onward transmission to the LSP client. This clear separation of concerns allows for robust LSP communication and efficient, isolated execution of Ruff functionalities.

### LSP Communication Core [[Expand]](./LSP_Communication_Core.md)
The central hub for all Language Server Protocol (LSP) interactions. It manages the server's lifecycle, parses incoming LSP requests, dispatches them to appropriate handlers, and sends responses and notifications back to the LSP client. This component embodies the core client-server communication pattern inherent in LSP.


**Related Classes/Methods**:

- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:initialize`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:did_open`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:did_change`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:hover`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:code_action`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:format_document`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_run_subcommand_on_document`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_lint_document_impl`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_fix_document_impl`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_format_document_impl`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:from_text_document`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:from_cell_or_text_uri`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_update_workspace_settings`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_get_global_defaults`</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.server:_get_settings_by_document`</a>


### Ruff Process Manager
Manages the execution of Ruff commands as an external process and retrieves their results. It abstracts the details of invoking Ruff, handling its input/output streams, and ensuring efficient execution.


**Related Classes/Methods**:

- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/server.py#L1978-L1998" target="_blank" rel="noopener noreferrer">`ruff_lsp.server._run_subcommand_on_document`:1978-1998</a>
- <a href="https://github.com/astral-sh/ruff-lsp/blob/main/ruff_lsp/utils.py" target="_blank" rel="noopener noreferrer">`ruff_lsp.utils.run_path`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)