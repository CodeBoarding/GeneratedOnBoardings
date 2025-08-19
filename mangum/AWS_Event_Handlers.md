```mermaid
graph LR
    Mangum_Core_Adapter["Mangum Core Adapter"]
    ALB_Event_Adapter["ALB Event Adapter"]
    API_Gateway_Event_Adapter["API Gateway Event Adapter"]
    Lambda_Edge_Event_Adapter["Lambda@Edge Event Adapter"]
    ASGI_Application["ASGI Application"]
    ALB_Event["ALB Event"]
    API_Gateway_Event["API Gateway Event"]
    Lambda_Edge_Event["Lambda@Edge Event"]
    ASGI_Scope["ASGI Scope"]
    Mangum_Core_Adapter -- "delegates to" --> ALB_Event_Adapter
    Mangum_Core_Adapter -- "delegates to" --> API_Gateway_Event_Adapter
    Mangum_Core_Adapter -- "delegates to" --> Lambda_Edge_Event_Adapter
    Mangum_Core_Adapter -- "invokes" --> ASGI_Application
    ALB_Event_Adapter -- "transforms" --> ALB_Event
    ALB_Event_Adapter -- "produces" --> ASGI_Scope
    API_Gateway_Event_Adapter -- "transforms" --> API_Gateway_Event
    API_Gateway_Event_Adapter -- "produces" --> ASGI_Scope
    Lambda_Edge_Event_Adapter -- "transforms" --> Lambda_Edge_Event
    Lambda_Edge_Event_Adapter -- "produces" --> ASGI_Scope
    ASGI_Application -- "receives from" --> Mangum_Core_Adapter
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The mangum library acts as a bridge between various AWS event sources and ASGI applications, providing a robust and flexible architecture for deploying ASGI applications on AWS Lambda.

### Mangum Core Adapter
The central component responsible for initializing the ASGI application, detecting the incoming AWS event type, and delegating event parsing to the appropriate Event Adapter. It then passes the transformed ASGI scope and receive callable to the ASGI application.


**Related Classes/Methods**: _None_

### ALB Event Adapter
Parses incoming AWS Application Load Balancer (ALB) event JSON structures and transforms them into a compliant ASGI scope dictionary, handling ALB-specific nuances like header casing and query string encoding.


**Related Classes/Methods**: _None_

### API Gateway Event Adapter
Parses diverse AWS API Gateway events (V1 and V2) and converts them into a standardized ASGI scope, managing multi-value headers and API Gateway-specific query string encoding.


**Related Classes/Methods**: _None_

### Lambda@Edge Event Adapter
Parses the unique event structure from CloudFront Lambda@Edge and transforms it into the standardized ASGI scope dictionary, enabling ASGI applications to process requests originating from the CloudFront CDN.


**Related Classes/Methods**: _None_

### ASGI Application
Represents the user's ASGI-compatible application that receives the standardized ASGI scope and receive callable from the Mangum Core Adapter and processes the request.


**Related Classes/Methods**: _None_

### ALB Event
Represents an incoming AWS Application Load Balancer (ALB) event.


**Related Classes/Methods**: _None_

### API Gateway Event
Represents an incoming AWS API Gateway event.


**Related Classes/Methods**: _None_

### Lambda@Edge Event
Represents an incoming AWS CloudFront Lambda@Edge event.


**Related Classes/Methods**: _None_

### ASGI Scope
The standardized ASGI scope dictionary, which is the output of the event adapters.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)