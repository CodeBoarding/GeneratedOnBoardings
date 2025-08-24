```mermaid
graph LR
    Output_Generation_Engine["Output Generation Engine"]
    Markdown_Generator["Markdown Generator"]
    HTML_Generator["HTML Generator"]
    MDX_Generator["MDX Generator"]
    Sphinx_Generator["Sphinx Generator"]
    HTML_Template_Populator["HTML Template Populator"]
    Output_Generation_Engine -- "orchestrates" --> Markdown_Generator
    Output_Generation_Engine -- "orchestrates" --> HTML_Generator
    Output_Generation_Engine -- "orchestrates" --> MDX_Generator
    Output_Generation_Engine -- "orchestrates" --> Sphinx_Generator
    HTML_Generator -- "provides data to" --> HTML_Template_Populator
    Output_Generation_Engine -- "clones repository" --> Repository_Utilities
    Output_Generation_Engine -- "generates analysis with" --> Diagram_Generator
    click Output_Generation_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Output_Generation_Engine.md" "Details"
    click Markdown_Generator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Markdown_Generator.md" "Details"
    click HTML_Generator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/HTML_Generator.md" "Details"
    click MDX_Generator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/MDX_Generator.md" "Details"
    click Sphinx_Generator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/Sphinx_Generator.md" "Details"
    click HTML_Template_Populator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/CodeBoarding/HTML_Template_Populator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The documentation generation process is orchestrated by the `Output Generation Engine`, primarily implemented in `demo.py`. This engine is responsible for cloning the target Git repository using `Repository Utilities` and then initiating the architectural analysis through the `Diagram Generator`. Once the analysis is complete, the `Output Generation Engine` dispatches the generation of documentation to various specialized generators, including the `Markdown Generator`, `HTML Generator`, `MDX Generator`, and `Sphinx Generator`, based on the desired output format. The `HTML Generator` further interacts with the `HTML Template Populator` to produce interactive HTML documentation. This modular design allows for flexible and extensible documentation generation across different formats.

### Output Generation Engine [[Expand]](./Output_Generation_Engine.md)
The primary component responsible for orchestrating the overall process of generating documentation in various formats. It handles repository cloning, initiates the analysis generation, and dispatches the actual documentation generation to specific format generators based on the desired output.


**Related Classes/Methods**:

- `demo.py`:57-80
- `demo.py`:82-101


### Markdown Generator [[Expand]](./Markdown_Generator.md)
Generates standard Markdown documentation, including embedded Mermaid diagrams and basic component details, making the architectural insights easily readable in Markdown viewers.


**Related Classes/Methods**:



### HTML Generator [[Expand]](./HTML_Generator.md)
Creates standalone HTML documentation, specifically preparing data (e.g., Cytoscape.js compatible JSON) for interactive architectural diagrams.


**Related Classes/Methods**:



### MDX Generator [[Expand]](./MDX_Generator.md)
Produces MDX (Markdown with JSX) files, incorporating Mermaid diagrams and frontmatter for rich, interactive documentation experiences, suitable for modern documentation sites.


**Related Classes/Methods**:



### Sphinx Generator [[Expand]](./Sphinx_Generator.md)
Generates reStructuredText (RST) formatted documentation, including embedded Mermaid diagrams and structured component information, suitable for Sphinx documentation projects.


**Related Classes/Methods**:



### HTML Template Populator [[Expand]](./HTML_Template_Populator.md)
Integrates generated architectural data (like Cytoscape JSON and component-specific HTML snippets) into a predefined HTML template to produce the final, complete, and styled HTML output.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)