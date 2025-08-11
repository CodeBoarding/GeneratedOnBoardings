```mermaid
graph LR
    Metric_Collection_Processing["Metric Collection & Processing"]
    Metrics_Visualization["Metrics Visualization"]
    Metric_Collection_Processing -- "produces metrics for" --> Metrics_Visualization
    Metrics_Visualization -- "visualizes metrics from" --> Metric_Collection_Processing
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The LiveKit project's metric subsystem is primarily composed of two high-level components: `Metric Collection & Processing` and `Metrics Visualization`. The `Metric Collection & Processing` component, residing in the `pkg/metric` directory, is responsible for the entire lifecycle of metric data, from definition and collection to initial aggregation and processing. This foundational layer ensures that all operational data, such as server health, performance, and media quality, is accurately generated. The processed metrics are then consumed by the `Metrics Visualization` component, which leverages Grafana configurations located in `deploy/grafana`. This component provides interactive dashboards and visualizations, enabling real-time operational insights, trend analysis, and efficient debugging of the LiveKit platform by presenting the collected and processed data in an accessible format.

### Metric Collection & Processing
This component, implemented within the `pkg/metric` package, is responsible for the comprehensive definition, collection, aggregation, and initial processing of various real-time metrics across the entire LiveKit platform. It serves as the foundational layer for generating all operational data, including server health, performance, media quality, and API usage.


**Related Classes/Methods**:

- <a href="https://github.com/livekit/livekit/blob/master/pkg/metric/metric_config.go" target="_blank" rel="noopener noreferrer">`pkg/metric/metric_config.go`</a>
- <a href="https://github.com/livekit/livekit/blob/master/pkg/metric/metric_timestamper.go" target="_blank" rel="noopener noreferrer">`pkg/metric/metric_timestamper.go`</a>
- <a href="https://github.com/livekit/livekit/blob/master/pkg/metric/metrics_collector.go" target="_blank" rel="noopener noreferrer">`pkg/metric/metrics_collector.go`</a>
- <a href="https://github.com/livekit/livekit/blob/master/pkg/metric/metrics_reporter.go" target="_blank" rel="noopener noreferrer">`pkg/metric/metrics_reporter.go`</a>


### Metrics Visualization
This component, represented by the `deploy/grafana` configuration and deployment, is responsible for consuming the processed metrics from the `Metric Collection & Processing` component. It provides interactive dashboards and visualizations, enabling real-time operational insights, trend analysis, and efficient debugging of the LiveKit platform.


**Related Classes/Methods**:

- <a href="https://github.com/livekit/livekit/blob/master/deploy/grafana" target="_blank" rel="noopener noreferrer">`deploy/grafana`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)