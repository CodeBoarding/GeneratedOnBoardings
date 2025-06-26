```mermaid
graph LR
    Dependency_Management_System["Dependency Management System"]
    Decorator_and_Utility_Functions["Decorator and Utility Functions"]
    Dependency_Checker["Dependency Checker"]
    Dependency_Error_Handler["Dependency Error Handler"]
    Dependency_Configuration["Dependency Configuration"]
    Package_Utilities["Package Utilities"]
    Decorator_Collection["Decorator Collection"]
    Attribute_Dictionary["Attribute Dictionary"]
    Progress_Tracking["Progress Tracking"]
    JAX_Utilities["JAX Utilities"]
    Dependency_Checker -- "Utilizes" --> Dependency_Error_Handler
    Dependency_Checker -- "Utilizes" --> Dependency_Configuration
    Dependency_Error_Handler -- "Consults" --> Dependency_Configuration
    Dependency_Error_Handler -- "Utilizes" --> Package_Utilities
    Attribute_Dictionary -- "Used by" --> scvi_model_base__base_model_BaseModelClass
    Progress_Tracking -- "Interacts with" --> scvi_train_package
    JAX_Utilities -- "Utilized by" --> JAX_based_models_and_training_plans
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `scvi.utils` package serves as a foundational collection of general-purpose helper functions and modules, supporting various tasks across the `scvi-tools` library. Its core purpose is to provide essential utilities that enhance code functionality, readability, and maintainability, ensuring the stability and correct execution of the entire system.

### Dependency Management System
This system is responsible for ensuring that all necessary external Python packages are installed and meet the required version constraints. It centralizes dependency configuration, checks for their presence and compatibility, and provides mechanisms to handle missing or incompatible dependencies gracefully. This is crucial for the stability and correct execution of `scvi-tools`.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies` (1:1)</a>


### Decorator and Utility Functions
This component encompasses a variety of decorators and general utility functions that enhance code functionality, readability, and maintainability across the `scvi-tools` library. These utilities provide common patterns for tasks like deprecation warnings, property caching, and docstring management.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_decorators.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._decorators` (1:1)</a>
- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_attrdict.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._attrdict` (1:1)</a>
- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_docstrings.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._docstrings` (1:1)</a>
- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_track.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._track` (1:1)</a>
- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_jax.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._jax` (1:1)</a>


### Dependency Checker
This component, primarily represented by `scvi.utils._dependencies.dependencies`, acts as a decorator or direct function call to validate dependencies before a function's execution.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L16-L27" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies.dependencies` (16:27)</a>


### Dependency Error Handler
The `scvi.utils._dependencies.error_on_missing_dependencies` function is responsible for raising informative `ImportError` messages when dependencies are not met.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L5-L13" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies.error_on_missing_dependencies` (5:13)</a>


### Dependency Configuration
The internal dictionary `scvi.utils._dependencies._DEPENDENCY_SETTINGS` stores all dependency metadata, including names, required versions, and whether they are optional or required.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies._DEPENDENCY_SETTINGS` (1:1)</a>


### Package Utilities
Functions like `scvi.utils._dependencies._get_imported_package_version` and `scvi.utils._dependencies._check_package_version` are low-level helpers that retrieve and compare package versions.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies._get_imported_package_version` (1:1)</a>
- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_dependencies.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._dependencies._check_package_version` (1:1)</a>


### Decorator Collection
The `scvi.utils._decorators` module contains various decorators (e.g., for deprecation, property caching). These are used by numerous classes and methods throughout `scvi-tools` to modify their behavior without altering their core logic.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_decorators.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._decorators` (1:1)</a>


### Attribute Dictionary
`scvi.utils._attrdict.attrdict` provides a dictionary-like object that allows access to its keys as attributes. This simplifies data access and is used in various models and data management classes.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_attrdict.py#L3-L11" target="_blank" rel="noopener noreferrer">`scvi.utils._attrdict.attrdict` (3:11)</a>


### Progress Tracking
`scvi.utils._track` provides utilities for tracking progress, potentially for long-running operations or training processes.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_track.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._track` (1:1)</a>


### JAX Utilities
`scvi.utils._jax` contains utilities specifically designed to support JAX integration within `scvi-tools`, enabling models and computations to leverage JAX's capabilities.


**Related Classes/Methods**:

- <a href="https://github.com/scverse/scvi-tools/src/scvi/utils/_jax.py#L1-L1" target="_blank" rel="noopener noreferrer">`scvi.utils._jax` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)