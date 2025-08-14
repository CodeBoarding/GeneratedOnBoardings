```mermaid
graph LR
    parse_node["parse_node"]
    search_link_node["search_link_node"]
    concat_answers_node["concat_answers_node"]
    graph_iterator_node["graph_iterator_node"]
    conditional_node["conditional_node"]
    parse_node -- "sends data to" --> search_link_node
    parse_node -- "controlled by" --> graph_iterator_node
    search_link_node -- "feeds into" --> concat_answers_node
    search_link_node -- "controlled by" --> graph_iterator_node
    concat_answers_node -- "receives data from" --> search_link_node
    concat_answers_node -- "controlled by" --> graph_iterator_node
    graph_iterator_node -- "controls execution of" --> parse_node
    graph_iterator_node -- "controls execution of" --> search_link_node
    graph_iterator_node -- "controls execution of" --> concat_answers_node
    graph_iterator_node -- "controls execution of" --> conditional_node
    conditional_node -- "directs flow to" --> parse_node
    conditional_node -- "directs flow to" --> search_link_node
    conditional_node -- "directs flow to" --> concat_answers_node
    conditional_node -- "directs flow to" --> graph_iterator_node
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Data Transformation Nodes` subsystem is a core part of the `Scrapegraph-ai` project, responsible for processing raw web content, extracting structured data, and transforming it into a usable format for subsequent steps within the graph pipeline. It encompasses modular components that handle parsing, linking, answer concatenation, graph iteration, and conditional logic.

### parse_node
Responsible for initial data parsing and extraction, specifically identifying and cleaning URLs from raw web content. It acts as the entry point for raw data into the transformation process.


**Related Classes/Methods**:

- <a href="https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/examples/custom_graph/ollama/custom_graph_ollama.py" target="_blank" rel="noopener noreferrer">`parse_node`</a>


### search_link_node
Acts as a data filter and validator, ensuring only relevant and valid links proceed in the scraping process. It refines the output from the `parse_node`.


**Related Classes/Methods**:

- <a href="https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/scrapegraphai/graphs/search_link_graph.py" target="_blank" rel="noopener noreferrer">`search_link_node`</a>


### concat_answers_node
Functions as a data aggregator, combining extracted information into a unified, structured output. This is crucial for consolidating data from various sources or iterative steps.


**Related Classes/Methods**:

- <a href="https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/scrapegraphai/nodes/concat_answers_node.py" target="_blank" rel="noopener noreferrer">`concat_answers_node`</a>


### graph_iterator_node
Manages iterative processing and flow control within complex scraping graphs, enabling multi-page or recursive data extraction. It embodies the orchestration aspect of the pipeline.


**Related Classes/Methods**:

- <a href="https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/scrapegraphai/graphs/document_scraper_multi_graph.py" target="_blank" rel="noopener noreferrer">`graph_iterator_node`</a>


### conditional_node
Implements dynamic decision-making logic, allowing the graph to adapt its execution path based on specified conditions. This provides flexibility and intelligence to the data flow.


**Related Classes/Methods**:

- <a href="https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/scrapegraphai/graphs/smart_scraper_multi_concat_graph.py" target="_blank" rel="noopener noreferrer">`conditional_node`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)