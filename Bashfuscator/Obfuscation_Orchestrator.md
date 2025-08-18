```mermaid
graph LR
    Obfuscation_Orchestrator["Obfuscation Orchestrator"]
    Obfuscation_Layer_Generator["Obfuscation Layer Generator"]
    Mutator_Stub_Selector["Mutator & Stub Selector"]
    Code_Wrapper["Code Wrapper"]
    Mutator_Sequence_Validator["Mutator Sequence Validator"]
    Obfuscation_Orchestrator -- "calls" --> Obfuscation_Layer_Generator
    Obfuscation_Orchestrator -- "utilizes" --> Mutator_Sequence_Validator
    Obfuscation_Orchestrator -- "employs" --> Code_Wrapper
    Obfuscation_Layer_Generator -- "requests mutator from" --> Mutator_Stub_Selector
    Obfuscation_Layer_Generator -- "uses" --> Code_Wrapper
    Mutator_Stub_Selector -- "provides mutators and stubs to" --> Obfuscation_Layer_Generator
    Mutator_Sequence_Validator -- "returns validation status to" --> Obfuscation_Orchestrator
    click Obfuscation_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/Bashfuscator/Obfuscation_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the Obfuscation Orchestrator subsystem, focusing on its central components and their interactions within the obfuscation pipeline.

### Obfuscation Orchestrator [[Expand]](./Obfuscation_Orchestrator.md)
The central engine of `bashfuscator`. It manages the entire obfuscation pipeline, initiating the process, coordinating the creation of multiple obfuscation layers, validating the chosen mutator sequence, and finalizing the output by applying necessary wrapping. This component embodies the "central engine" aspect.


**Related Classes/Methods**:

- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:generatePayload`</a>


### Obfuscation Layer Generator
Responsible for constructing a single layer of obfuscation within the pipeline. It selects a specific mutator for its layer and ensures proper evaluation wrapping is applied, contributing to the multi-layered obfuscation effect.


**Related Classes/Methods**:

- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:genObfuscationLayer`</a>


### Mutator & Stub Selector
Manages the intelligent selection of mutators and their associated stubs based on predefined preferences and available options. It serves as the primary interface for requesting a mutator and contains the consolidated logic for choosing the most suitable ones from the available modules.


**Related Classes/Methods**:

- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:getMutator`</a>
- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:choosePrefMutator`</a>
- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:getPrefMutators`</a>
- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:getPrefStubs`</a>
- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:choosePrefStub`</a>


### Code Wrapper
Handles the wrapping of obfuscated code, typically to ensure its correct execution, integration, or to add protective layers (e.g., `eval` or `base64` encoding). This is crucial for the final usability of the obfuscated output.


**Related Classes/Methods**:

- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:evalWrap`</a>


### Mutator Sequence Validator
Validates the sequence or list of selected mutators to ensure they adhere to specific rules, constraints, or compatibility requirements before application, preventing invalid or conflicting obfuscation chains.


**Related Classes/Methods**:

- <a href="https://github.com/Bashfuscator/Bashfuscator/blob/master/bashfuscator/core/engine/obfuscation_handler.py" target="_blank" rel="noopener noreferrer">`bashfuscator.core.engine.obfuscation_handler.py:checkMutatorList`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)