```mermaid
graph LR
    Error_Diagnostic_Reporting["Error & Diagnostic Reporting"]
    Parser_AST_Representation["Parser & AST Representation"]
    Semantic_Analysis_Engine["Semantic Analysis Engine"]
    LSP_Communication_Layer["LSP Communication Layer"]
    Parser_AST_Representation -- "sends diagnostic information to" --> Error_Diagnostic_Reporting
    Semantic_Analysis_Engine -- "reports errors and warnings to" --> Error_Diagnostic_Reporting
    Error_Diagnostic_Reporting -- "sends formatted diagnostics to" --> LSP_Communication_Layer
    click Error_Diagnostic_Reporting href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/zls/Error_Diagnostic_Reporting.md" "Details"
    click Parser_AST_Representation href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/zls/Parser_AST_Representation.md" "Details"
    click Semantic_Analysis_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/zls/Semantic_Analysis_Engine.md" "Details"
    click LSP_Communication_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/zls/LSP_Communication_Layer.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Abstract Components Overview

### Error & Diagnostic Reporting [[Expand]](./Error_Diagnostic_Reporting.md)
This component is responsible for centralizing the collection and aggregation of syntax and semantic errors, warnings, and other diagnostic messages. It receives raw diagnostic information from the Parser & AST Representation and the Semantic Analysis Engine. Its core function is to then format these diagnostics precisely according to the Language Server Protocol (LSP) specification, preparing them for efficient publication and transmission to the client via the LSP Communication Layer. This ensures that the client receives standardized and actionable feedback on code issues.


**Related Classes/Methods**: _None_

### Parser & AST Representation [[Expand]](./Parser_AST_Representation.md)
This component is responsible for taking the raw source code as input, performing lexical analysis to break it down into tokens, and then syntactic analysis to construct an Abstract Syntax Tree (AST). It identifies and reports syntax errors during this process, sending relevant diagnostic information to the Error & Diagnostic Reporting component. The generated AST serves as the foundational data structure for subsequent analysis phases.


**Related Classes/Methods**: _None_

### Semantic Analysis Engine [[Expand]](./Semantic_Analysis_Engine.md)
Operating on the Abstract Syntax Tree (AST) provided by the Parser & AST Representation, this component performs deeper semantic checks. This includes type checking, variable resolution, scope analysis, and other validations to ensure the code's logical correctness. It identifies semantic errors and warnings, which are then reported to the Error & Diagnostic Reporting component for formatting and transmission.


**Related Classes/Methods**: _None_

### LSP Communication Layer [[Expand]](./LSP_Communication_Layer.md)
This component manages all communication between the language server and the client, adhering strictly to the Language Server Protocol (LSP) specification. It is responsible for sending various messages to the client, including formatted diagnostic information received from the Error & Diagnostic Reporting component. It handles the serialization and deserialization of LSP messages, ensuring reliable and standardized data exchange.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)