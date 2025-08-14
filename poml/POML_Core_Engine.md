```mermaid
graph LR
    Parser_Lexer["Parser/Lexer"]
    Interpreter["Interpreter"]
    Templating_Engine["Templating Engine"]
    Styling_Engine["Styling Engine"]
    Parser_Lexer -- "uses" --> Interpreter
    Interpreter -- "uses" --> Templating_Engine
    Templating_Engine -- "applies to" --> Styling_Engine
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the core components of the `poml` project, focusing on parsing, interpretation, templating, and styling functionalities. The analysis aims to rectify source file reference issues for accurate documentation and diagram generation.

### Parser/Lexer
Parses and lexes input.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/poml/blob/main/packages/poml/reader" target="_blank" rel="noopener noreferrer">`packages.poml.reader`</a>


### Interpreter
Interprets parsed input.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/poml/blob/main/packages/poml/reader" target="_blank" rel="noopener noreferrer">`packages.poml.reader`</a>


### Templating Engine
Renders templates.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/poml/blob/main/packages/poml/writer.ts" target="_blank" rel="noopener noreferrer">`packages.poml.writer`</a>


### Styling Engine
Applies styling.


**Related Classes/Methods**:

- <a href="https://github.com/microsoft/poml/blob/main/packages/poml/index.ts" target="_blank" rel="noopener noreferrer">`packages.poml.index`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)