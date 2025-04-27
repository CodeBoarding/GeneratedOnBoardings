## Detection Engine Overview

This component orchestrates the WAF detection process by managing detection scripts, executing requests, and analyzing responses. It leverages tamper scripts to bypass WAF protections and provides formatted output.

Given the complexity and interactions between components, a component diagram is the most suitable visualization technique.

```mermaid
componentDiagram
  SettingsProvider -- Uses --> DetectionQueue : Configures
  ScriptQueue -- Provides --> DetectionMain : Loads Scripts
  TamperScriptManager -- Provides --> DetectionMain : Provides Tampers
  DetectionMain -- Uses --> DetectionQueue : Executes Requests
  DetectionQueue -- Uses --> SettingsProvider : Makes Requests
  DetectionQueue -- Receives --> DetectionMain : Returns Responses
  DetectionMain -- Uses --> OutputFormatter : Formats Output

  classDef internal fill:#f9f,stroke:#333,stroke-width:2px
  classDef external fill:#ccf,stroke:#333,stroke-width:2px
  class SettingsProvider external
  class ScriptQueue internal
  class TamperScriptManager internal
  class DetectionMain internal
  class DetectionQueue internal
  class OutputFormatter external

```

