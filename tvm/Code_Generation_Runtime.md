```mermaid
graph LR
    Compilation_Orchestrator["Compilation Orchestrator"]
    Module_Packager["Module Packager"]
    TVM_Virtual_Machine["TVM Virtual Machine"]
    Compilation_Orchestrator -- "produces compiled modules for" --> Module_Packager
    Module_Packager -- "provides packaged modules to" --> TVM_Virtual_Machine
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Code Generation & Runtime` subsystem is responsible for transforming optimized Intermediate Representations (IRs) into executable code for specific hardware targets and providing the necessary runtime environment for their execution, including memory and device context management.

### Compilation Orchestrator
This component is the core of the code generation process. It takes the optimized Intermediate Representation (IR), such as TensorIR or Relax IR, and compiles it into a target-specific executable module. Its fundamental importance lies in embodying the "Compilation Flow Emphasis" by being the critical step that transforms high-level model representations into low-level machine code, tailored for various hardware backends.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/driver/build_module.py#L71-L111" target="_blank" rel="noopener noreferrer">`tvm.driver.build_module.compile`:71-111</a>


### Module Packager
This component handles the serialization and export of the compiled TVM modules into various persistent library formats (e.g., shared libraries, object files, or source code). It is crucial for the "Extensibility for Hardware Backends" pattern, as it prepares the compiled code for deployment and loading by the TVM runtime or external applications. Its role ensures that the compiled artifacts are portable and can be integrated into diverse deployment scenarios.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/module.py#L137-L303" target="_blank" rel="noopener noreferrer">`tvm.runtime.module.export_library`:137-303</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/module.py#L220-L224" target="_blank" rel="noopener noreferrer">`tvm.runtime.module.get_source_format_from_module`:220-224</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/module.py#L133-L135" target="_blank" rel="noopener noreferrer">`tvm.runtime.module._collect_dso_modules`:133-135</a>


### TVM Virtual Machine
This component constitutes the core runtime environment for executing compiled TVM modules. It initializes the virtual machine, sets up device contexts, manages memory, and provides the necessary infrastructure to efficiently run the generated code on the target hardware. This clearly distinguishes the "Runtime" aspect from the compile-time operations, aligning with the "Runtime vs. Compile-time" architectural bias, and serves as the execution engine for the compiled models.


**Related Classes/Methods**:

- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L45-L91" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm.__init__`:45-91</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L93-L124" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm._setup_device`:93-124</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L477-L499" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm.profile`:477-499</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L147-L193" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm.save_function`:147-193</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L253-L279" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm.set_input`:253-279</a>
- <a href="https://github.com/apache/tvm/blob/main/python/tvm/runtime/vm.py#L297-L326" target="_blank" rel="noopener noreferrer">`tvm.runtime.vm.get_outputs`:297-326</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)