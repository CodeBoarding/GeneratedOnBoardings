```mermaid
graph LR
    Quantitative_Analysis_Core["Quantitative Analysis Core"]
    Rule_Based_Strategy_Engine["Rule-Based Strategy Engine"]
    Rule_Based_Strategy_Engine -- "leverages" --> Quantitative_Analysis_Core
    Rule_Based_Strategy_Engine -- "consumes data from" --> Quantitative_Analysis_Core
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The qstock.stock subsystem is designed around two primary components: the Quantitative Analysis Core and the Rule-Based Strategy Engine. The Quantitative Analysis Core acts as the foundational analytical layer, providing essential calculations such as stock return rankings, Relative Price Strength (RPS), and comprehensive indicator scoring. This core processes raw stock data to generate derived analytical insights. Building upon this foundation, the Rule-Based Strategy Engine leverages the analytical outputs from the Quantitative Analysis Core to implement sophisticated rule-based stock selection strategies. It consumes processed data from the core to identify stocks based on predefined criteria, including price movements, volume changes, and moving average patterns, ultimately managing various stock pools. This clear separation of concerns ensures that the quantitative analysis capabilities are reusable and distinct from the specific strategic implementations, facilitating modularity and maintainability within the stock analysis framework.

### Quantitative Analysis Core
This component provides foundational quantitative analysis capabilities. It is responsible for calculating and ranking stock returns, computing Relative Price Strength (RPS), and assigning scores based on various financial indicators. It serves as a general-purpose analytical engine for raw stock data.


**Related Classes/Methods**:



### Rule-Based Strategy Engine
This component implements specific rule-based stock selection strategies. It orchestrates various algorithms for identifying stocks based on criteria such as price breakouts, significant movements, volume changes, moving average crossovers, price-volume patterns, and 'xzjp' strategies. It also manages and categorizes different stock pools based on these rules.


**Related Classes/Methods**:





### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)