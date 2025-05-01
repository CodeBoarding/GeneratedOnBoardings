## Plugin Manager Overview

This diagram illustrates the flow of how plugins are loaded and registered within the `MarkItDown` component. The `Plugin Manager` is responsible for discovering, loading, and registering external plugins, which can extend the functionality of the core application by providing additional format converters.

```mermaid
graph LR
    A[MarkItDown] -- calls --> B(enable_plugins)
    B -- calls --> C(_load_plugins)
    C -- discovers --> D[External Plugins]
    D -- provides --> E(Plugin Converters)
    E -- registers --> F(ConverterRegistration)
    F -- uses --> A



```

## Components Description

- **Component:** `MarkItDown`
  - *Description*: The main class that orchestrates the conversion process. It initializes and manages converters and plugins.
  - *Interaction*: `MarkItDown` calls `enable_plugins` to load and register external plugins.
  - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown`

- **Component:** `enable_plugins`
  - *Description*: Enables and registers converters provided by external plugins. It calls the `_load_plugins` function and then iterates through the loaded plugins, calling their `register_converters` method.
  - *Interaction*: `enable_plugins` calls `_load_plugins` to discover and load plugins, then registers the converters provided by those plugins with the `MarkItDown` instance.
  - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.MarkItDown.enable_plugins`

- **Component:** `_load_plugins`
  - *Description*: Loads and enables plugins for the MarkItDown parser using entry points. It iterates through the found plugins and registers their converters.
  - *Interaction*: `_load_plugins` discovers plugins through entry points and loads them. It returns a list of loaded plugins to `enable_plugins`.
  - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown._load_plugins`

- **Component:** `External Plugins`
  - *Description*: Represents the external plugins that provide additional converters.
  - *Interaction*: Provides `Plugin Converters` to `_load_plugins`.
  - *Relevant source files*: N/A (External)

- **Component:** `Plugin Converters`
  - *Description*: The converters provided by the external plugins.
  - *Interaction*: Registers with `ConverterRegistration` through the `MarkItDown` instance.
  - *Relevant source files*: N/A (Defined within plugins)

- **Component:** `ConverterRegistration`
  - *Description*: Registers a DocumentConverter with a given priority. The converters are sorted by priority before conversion attempts.
  - *Interaction*: Stores the `Plugin Converters` and uses them during the conversion process in `MarkItDown`.
  - *Relevant source files*: `repos.markitdown.packages.markitdown.src.markitdown._markitdown.ConverterRegistration`
