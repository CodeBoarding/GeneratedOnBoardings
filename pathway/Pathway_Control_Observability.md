```mermaid
graph LR
    pathway_cli["pathway.cli"]
    pathway_internals_monitoring["pathway.internals.monitoring"]
    pathway_debug["pathway.debug"]
    pathway_cli -- "initiates programs which generate data and metrics consumed by" --> pathway_internals_monitoring
    pathway_cli -- "provides execution context for" --> pathway_debug
    pathway_cli -- "displays runtime metrics and operational data exposed by" --> pathway_internals_monitoring
    pathway_internals_monitoring -- "prompts deeper investigation using" --> pathway_debug
    pathway_debug -- "operates within execution context provided by programs launched via" --> pathway_cli
    pathway_debug -- "used to perform detailed analysis and pinpoint root causes for issues initially identified by" --> pathway_internals_monitoring
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Pathway framework's core functionality is orchestrated through three central components: `pathway.cli`, `pathway.internals.monitoring`, and `pathway.debug`. The `pathway.cli` acts as the user's primary interface, responsible for initiating and managing Pathway programs, which in turn generate operational data and metrics. This data is consumed and exposed by `pathway.internals.monitoring`, providing real-time observability into pipeline health and performance. Users can then leverage `pathway.cli` to display these metrics. When issues are identified by the monitoring system, `pathway.debug` provides granular tools for detailed data inspection and analysis, operating within the execution context established by programs launched via `pathway.cli`. This allows developers to pinpoint root causes and verify data transformations, forming a cohesive feedback loop for pipeline development and maintenance.

### pathway.cli
Serves as the primary user interface and orchestration layer for the Pathway framework. It enables users to initiate, manage, and replay Pathway programs, and handles environment setup and repository checkouts. This component is crucial for deploying and controlling data pipelines.


**Related Classes/Methods**:



### pathway.internals.monitoring
Provides real-time observability into the operational status and performance of running Pathway pipelines. It collects and exposes metrics, logs, and statistics related to data connectors, operators, and overall pipeline latency, enabling users to understand pipeline health and identify high-level issues.


**Related Classes/Methods**:



### pathway.debug
Offers granular tools for inspecting, transforming, and visualizing data within Pathway tables. This component is essential for developers to diagnose data-related issues, verify transformations, and understand the internal state of data flowing through the pipelines at a detailed level.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)