```mermaid
graph LR
    Core_Infrastructure["Core Infrastructure"]
    Data_Preprocessing["Data Preprocessing"]
    Modeling_Analysis_Frameworks["Modeling & Analysis Frameworks"]
    Public_API["Public API"]
    Support_Visualization["Support & Visualization"]
    Core_Infrastructure -- "Provides services to" --> Data_Preprocessing
    Core_Infrastructure -- "Provides services to" --> Modeling_Analysis_Frameworks
    Core_Infrastructure -- "Provides services to" --> Public_API
    Core_Infrastructure -- "Provides services to" --> Support_Visualization
    Data_Preprocessing -- "Uses" --> Core_Infrastructure
    Data_Preprocessing -- "Outputs processed data to" --> Modeling_Analysis_Frameworks
    Public_API -- "Orchestrates" --> Data_Preprocessing
    Modeling_Analysis_Frameworks -- "Uses" --> Core_Infrastructure
    Modeling_Analysis_Frameworks -- "Consumes processed data from" --> Data_Preprocessing
    Modeling_Analysis_Frameworks -- "Provides models/results to" --> Public_API
    Public_API -- "Uses" --> Core_Infrastructure
    Public_API -- "Orchestrates" --> Modeling_Analysis_Frameworks
    Support_Visualization -- "Provides example data to" --> Public_API
    Support_Visualization -- "Uses" --> Core_Infrastructure
    Support_Visualization -- "Visualizes results from" --> Public_API
    click Core_Infrastructure href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyemma/Core_Infrastructure.md" "Details"
    click Data_Preprocessing href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyemma/Data_Preprocessing.md" "Details"
    click Modeling_Analysis_Frameworks href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyemma/Modeling_Analysis_Frameworks.md" "Details"
    click Public_API href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyemma/Public_API.md" "Details"
    click Support_Visualization href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyemma/Support_Visualization.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `pyemma` project, a scientific computing library for molecular dynamics data analysis, exhibits a well-structured layered architecture with clear separation of concerns. The core functionality is built upon a robust foundation of utilities and base components, followed by distinct layers for data preprocessing, core modeling, and a user-friendly API. Visualization and example datasets provide essential support for usability and demonstration.

### Core Infrastructure [[Expand]](./Core_Infrastructure.md)
This foundational layer provides essential low-level utilities (e.g., data type validation, linear algebra, file I/O, logging, configuration) and defines abstract base classes and interfaces for estimators, models, and serialization. It ensures consistency, extensibility, and reusability across the entire library.


**Related Classes/Methods**:

- `pyemma.util` (1:1)
- `pyemma._base` (1:1)


### Data Preprocessing [[Expand]](./Data_Preprocessing.md)
This component is responsible for the entire data preparation pipeline. It handles reading various molecular dynamics data formats, extracting physically meaningful features (e.g., distances, angles), performing dimensionality reduction (e.g., PCA, TICA, VAMP), and discretizing continuous trajectories into discrete states through clustering algorithms.


**Related Classes/Methods**:

- `pyemma.coordinates.data` (1:1)
- `pyemma.coordinates.transform` (1:1)
- `pyemma.coordinates.clustering` (1:1)


### Modeling & Analysis Frameworks [[Expand]](./Modeling_Analysis_Frameworks.md)
This core scientific component implements the algorithms for estimating and analyzing kinetic models and thermodynamic properties. It includes functionalities for Markov State Models (MSMs), Hidden Markov State Models (HMSMs), and various thermodynamic reweighting methods (e.g., WHAM, MBAR, DTRAM, TRAM), providing the computational backbone for kinetic and thermodynamic insights.


**Related Classes/Methods**:

- `pyemma.msm` (1:1)
- `pyemma.thermo` (1:1)


### Public API [[Expand]](./Public_API.md)
This layer serves as the primary user-facing interface, abstracting the complexities of the underlying data preprocessing and modeling components. It provides high-level functions and classes that orchestrate workflows, allowing users to easily load data, preprocess it, estimate models, and perform analyses without deep knowledge of the internal implementations.


**Related Classes/Methods**:

- <a href="https://github.com/markovmodel/pyemma/blob/devel/pyemma/coordinates/api.py#L1-L1" target="_blank" rel="noopener noreferrer">`pyemma.coordinates.api` (1:1)</a>
- <a href="https://github.com/markovmodel/pyemma/blob/devel/pyemma/msm/api.py#L1-L1" target="_blank" rel="noopener noreferrer">`pyemma.msm.api` (1:1)</a>
- <a href="https://github.com/markovmodel/pyemma/blob/devel/pyemma/thermo/api.py#L1-L1" target="_blank" rel="noopener noreferrer">`pyemma.thermo.api` (1:1)</a>


### Support & Visualization [[Expand]](./Support_Visualization.md)
This component enhances usability by providing readily available example datasets for tutorials and testing, and offers comprehensive plotting functionalities. It enables users to visualize various aspects of molecular dynamics data analysis, including free energy landscapes, Markov state model networks, and implied timescales, aiding in interpretation and presentation of results.


**Related Classes/Methods**:

- `pyemma.datasets` (1:1)
- `pyemma.plots` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)