```mermaid
graph LR
    API_Layer["API Layer"]
    SDK_Layer["SDK Layer"]
    Trace_Module["Trace Module"]
    Metric_Module["Metric Module"]
    Log_Module["Log Module"]
    Semantic_Conventions_Layer["Semantic Conventions Layer"]
    API_Layer -- "adheres to definitions from" --> Semantic_Conventions_Layer
    SDK_Layer -- "implements" --> API_Layer
    Trace_Module -- "is part of" --> API_Layer
    Trace_Module -- "defines interfaces for" --> SDK_Layer
    Metric_Module -- "is part of" --> API_Layer
    Metric_Module -- "defines interfaces for" --> SDK_Layer
    Log_Module -- "is part of" --> API_Layer
    Log_Module -- "defines interfaces for" --> SDK_Layer
    Semantic_Conventions_Layer -- "defines standards for" --> API_Layer
    Semantic_Conventions_Layer -- "is referenced by" --> SDK_Layer
    click API_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/opentelemetry-go/API_Layer.md" "Details"
    click SDK_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/opentelemetry-go/SDK_Layer.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### API Layer [[Expand]](./API_Layer.md)
Defines the public, vendor-agnostic interfaces and abstract types for application instrumentation, providing a stable contract for developers. It serves as the primary interaction point for applications integrating the SDK.


**Related Classes/Methods**: _None_

### SDK Layer [[Expand]](./SDK_Layer.md)
Implements the interfaces defined by the API Layer, providing the concrete logic and functionality for telemetry collection and processing.


**Related Classes/Methods**: _None_

### Trace Module
A specialized part of the API Layer, focusing exclusively on interfaces and types related to distributed tracing, such as `Tracer` and `Span`.


**Related Classes/Methods**: _None_

### Metric Module
A specialized part of the API Layer, defining interfaces and abstract types for metric instrumentation, including `Meter` and various instrument types (e.g., counters, gauges).


**Related Classes/Methods**: _None_

### Log Module
A specialized part of the API Layer, providing interfaces and types for structured logging and log record processing.


**Related Classes/Methods**: _None_

### Semantic Conventions Layer
Provides standardized naming and values for telemetry attributes across all signals (traces, metrics, logs), ensuring consistency and interoperability.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)