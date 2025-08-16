```mermaid
graph LR
    finquant_portfolio["finquant.portfolio"]
    finquant_efficient_frontier["finquant.efficient_frontier"]
    finquant_monte_carlo["finquant.monte_carlo"]
    finquant_minimise_fun["finquant.minimise_fun"]
    finquant_portfolio -- "invokes" --> finquant_efficient_frontier
    finquant_portfolio -- "invokes" --> finquant_monte_carlo
    finquant_efficient_frontier -- "utilizes" --> finquant_minimise_fun
    finquant_monte_carlo -- "utilizes" --> finquant_minimise_fun
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Portfolio Optimization subsystem encompasses the core algorithms and utilities responsible for identifying optimal risk-return trade-offs and simulating portfolio performance.

### finquant.portfolio
Serves as the central orchestrator and primary interface for users to access portfolio optimization and simulation capabilities. It manages portfolio data and invokes the specific optimization and simulation engines. This component is fundamental as it embodies the project's architectural bias towards a centralized Portfolio object.


**Related Classes/Methods**:

- <a href="https://github.com/fmilthaler/FinQuant/blob/master/finquant/portfolio.py" target="_blank" rel="noopener noreferrer">`finquant.portfolio`</a>


### finquant.efficient_frontier
Implements algorithms to calculate and visualize the Efficient Frontier. It identifies portfolios that offer the highest expected return for a given level of risk or the lowest risk for a given expected return, a cornerstone of modern portfolio theory. This component is critical for its direct application of optimization principles.


**Related Classes/Methods**:

- <a href="https://github.com/fmilthaler/FinQuant/blob/master/finquant/efficient_frontier.py" target="_blank" rel="noopener noreferrer">`finquant.efficient_frontier`</a>


### finquant.monte_carlo
Provides the functionality for performing Monte Carlo simulations to generate a large number of random portfolios. This component is essential for exploring the risk-return landscape through simulation, complementing deterministic optimization methods.


**Related Classes/Methods**:

- <a href="https://github.com/fmilthaler/FinQuant/blob/master/finquant/monte_carlo.py" target="_blank" rel="noopener noreferrer">`finquant.monte_carlo`</a>


### finquant.minimise_fun
A utility component that encapsulates the mathematical objective functions and constraints required by the optimization algorithms. These functions define what the optimizers aim to minimize (e.g., volatility) or maximize (e.g., Sharpe ratio). It is a foundational component, providing the mathematical backbone for both efficient_frontier and monte_carlo.


**Related Classes/Methods**:

- <a href="https://github.com/fmilthaler/FinQuant/blob/master/finquant/minimise_fun.py" target="_blank" rel="noopener noreferrer">`finquant.minimise_fun`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)