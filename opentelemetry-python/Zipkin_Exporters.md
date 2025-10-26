```mermaid
graph LR
    Zipkin_JSON_Exporter["Zipkin JSON Exporter"]
    Zipkin_Proto_HTTP_Exporter["Zipkin Proto HTTP Exporter"]
    Zipkin_JSON_Encoder["Zipkin JSON Encoder"]
    Zipkin_Proto_Encoder["Zipkin Proto Encoder"]
    Zipkin_Span_Converter["Zipkin Span Converter"]
    Zipkin_Endpoint["Zipkin Endpoint"]
    Zipkin_JSON_Exporter -- "leverages" --> Zipkin_JSON_Encoder
    Zipkin_JSON_Exporter -- "utilizes" --> Zipkin_Endpoint
    Zipkin_Proto_HTTP_Exporter -- "leverages" --> Zipkin_Proto_Encoder
    Zipkin_Proto_HTTP_Exporter -- "utilizes" --> Zipkin_Endpoint
    Zipkin_JSON_Encoder -- "transforms" --> Zipkin_Span_Converter
    Zipkin_JSON_Encoder -- "consumes" --> Zipkin_Endpoint
    Zipkin_Proto_Encoder -- "transforms" --> Zipkin_Span_Converter
    Zipkin_Proto_Encoder -- "consumes" --> Zipkin_Endpoint
    Zipkin_Span_Converter -- "provides data to" --> Zipkin_JSON_Encoder
    Zipkin_Span_Converter -- "provides data to" --> Zipkin_Proto_Encoder
    Zipkin_Endpoint -- "provides data to" --> Zipkin_JSON_Exporter
    Zipkin_Endpoint -- "provides data to" --> Zipkin_Proto_HTTP_Exporter
    Zipkin_Endpoint -- "provides data to" --> Zipkin_JSON_Encoder
    Zipkin_Endpoint -- "provides data to" --> Zipkin_Proto_Encoder
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The OpenTelemetry Zipkin Exporter subsystem is designed to translate OpenTelemetry trace data into the Zipkin format for external collection and analysis. It comprises specialized exporters for JSON and Protocol Buffer over HTTP, each leveraging dedicated encoders for format-specific serialization. A shared Span Converter component ensures consistent transformation of OpenTelemetry spans into Zipkin-compatible structures, while a dedicated Endpoint component extracts and formats service and network information. This modular design promotes reusability and simplifies the integration of OpenTelemetry with Zipkin tracing systems.

### Zipkin JSON Exporter
Orchestrates the export of OpenTelemetry traces in Zipkin JSON v1 format.


**Related Classes/Methods**:



### Zipkin Proto HTTP Exporter
Orchestrates the export of OpenTelemetry traces in Zipkin Proto HTTP v2 format.


**Related Classes/Methods**:



### Zipkin JSON Encoder
Converts OpenTelemetry spans into Zipkin JSON v1 format.


**Related Classes/Methods**:



### Zipkin Proto Encoder
Converts OpenTelemetry spans into Zipkin Proto HTTP v2 format.


**Related Classes/Methods**:



### Zipkin Span Converter
Provides shared logic for transforming OpenTelemetry Span objects into Zipkin Span objects.


**Related Classes/Methods**:



### Zipkin Endpoint
Generates Zipkin-compatible endpoint information from OpenTelemetry resource attributes.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)