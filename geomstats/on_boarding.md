```mermaid
graph LR
    Geometry_Core["Geometry Core"]
    Learning_Algorithms["Learning Algorithms"]
    Numerical_Solvers["Numerical Solvers"]
    Backend_Abstraction_Layer["Backend Abstraction Layer"]
    Data_Management["Data Management"]
    Geometric_Distributions["Geometric Distributions"]
    Visualization_Engine["Visualization Engine"]
    Geometry_Core -- "Defines Structures For" --> Learning_Algorithms
    Geometry_Core -- "Defines Problems For" --> Numerical_Solvers
    Geometry_Core -- "Provides Manifolds For" --> Geometric_Distributions
    Geometry_Core -- "Provides Objects For" --> Visualization_Engine
    Geometry_Core -- "Utilizes" --> Backend_Abstraction_Layer
    Learning_Algorithms -- "Processes Data From" --> Data_Management
    Learning_Algorithms -- "Uses" --> Geometry_Core
    Learning_Algorithms -- "Leverages" --> Numerical_Solvers
    Learning_Algorithms -- "Outputs Results To" --> Visualization_Engine
    Learning_Algorithms -- "Utilizes" --> Backend_Abstraction_Layer
    Numerical_Solvers -- "Solves Problems From" --> Geometry_Core
    Numerical_Solvers -- "Supports" --> Learning_Algorithms
    Numerical_Solvers -- "Utilizes" --> Backend_Abstraction_Layer
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Geometry_Core
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Learning_Algorithms
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Numerical_Solvers
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Data_Management
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Geometric_Distributions
    Backend_Abstraction_Layer -- "Provides Primitives To" --> Visualization_Engine
    Data_Management -- "Feeds Data To" --> Learning_Algorithms
    Data_Management -- "Provides Data For" --> Visualization_Engine
    Data_Management -- "Utilizes" --> Backend_Abstraction_Layer
    Geometric_Distributions -- "Defines Distributions On" --> Geometry_Core
    Geometric_Distributions -- "Generates Samples For" --> Learning_Algorithms
    Geometric_Distributions -- "Utilizes" --> Backend_Abstraction_Layer
    Visualization_Engine -- "Renders" --> Geometry_Core
    Visualization_Engine -- "Renders" --> Learning_Algorithms
    Visualization_Engine -- "Renders" --> Data_Management
    Visualization_Engine -- "Utilizes" --> Backend_Abstraction_Layer
    click Geometry_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Geometry_Core.md" "Details"
    click Learning_Algorithms href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Learning_Algorithms.md" "Details"
    click Numerical_Solvers href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Numerical_Solvers.md" "Details"
    click Backend_Abstraction_Layer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Backend_Abstraction_Layer.md" "Details"
    click Data_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Data_Management.md" "Details"
    click Geometric_Distributions href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/geomstats/Geometric_Distributions.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `geomstats` architecture is centered around a robust Geometry Core that defines the fundamental mathematical structures of various manifolds. This core provides the necessary context and operations for Learning Algorithms to perform machine learning tasks directly on geometric data, and for Numerical Solvers to tackle complex mathematical problems inherent to these spaces. Data for these processes is handled by Data Management, and probabilistic modeling is supported by Geometric Distributions. A crucial Backend Abstraction Layer underpins the entire system, providing a unified interface for numerical computations across different libraries, ensuring flexibility and performance. Finally, the Visualization Engine offers essential tools for understanding and presenting the geometric objects, data, and results generated throughout the `geomstats` workflow. This modular design, with its clear component boundaries and backend flexibility, makes `geomstats` a powerful and extensible toolkit for geometric statistics and machine learning.

### Geometry Core [[Expand]](./Geometry_Core.md)
Defines mathematical structures of manifolds and their intrinsic properties.


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/geometry/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.geometry`</a>


### Learning Algorithms [[Expand]](./Learning_Algorithms.md)
Implements machine learning algorithms adapted for geometric spaces.


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/learning/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.learning`</a>


### Numerical Solvers [[Expand]](./Numerical_Solvers.md)
Provides computational methods for solving geometric problems (e.g., geodesics, optimization).


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/numerics/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.numerics`</a>


### Backend Abstraction Layer [[Expand]](./Backend_Abstraction_Layer.md)
Offers a unified API for numerical operations across different backends (NumPy, Autograd, PyTorch).


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/_backend/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats._backend`</a>


### Data Management [[Expand]](./Data_Management.md)
Handles loading, preparation, and management of geometric datasets.


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/datasets/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.datasets`</a>


### Geometric Distributions [[Expand]](./Geometric_Distributions.md)
Defines probability distributions on geometric manifolds.


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/distributions/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.distributions`</a>


### Visualization Engine
Provides tools for graphically representing geometric objects and computational results.


**Related Classes/Methods**:

- <a href="https://github.com/geomstats/geomstats/blob/main/geomstats/visualization/__init__.py" target="_blank" rel="noopener noreferrer">`geomstats.visualization`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)