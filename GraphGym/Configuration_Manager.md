```mermaid
graph LR
    Configuration_Core["Configuration Core"]
    Configuration_Generator["Configuration Generator"]
    Configuration_Generator -- "depends on" --> Configuration_Core
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Configuration Manager` subsystem is central to `GraphGym`'s design, embodying the "Configuration as Central Control" and "Reproducibility" architectural patterns. It ensures that all experiment parameters are systematically defined, loaded, and managed, facilitating reproducible and scalable experimentation.

### Configuration Core
This component is the foundational element for managing experiment configurations. It is responsible for loading configuration settings from external sources (e.g., YAML files), ensuring their validity, and preparing the file system environment for experiment outputs. It acts as the gatekeeper for configuration integrity and the organizer of experiment artifacts, aligning with the "Configuration as Central Control" and "Reproducibility" architectural patterns.


**Related Classes/Methods**:

- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L508-L519" target="_blank" rel="noopener noreferrer">`load_cfg`:508-519</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L467-L490" target="_blank" rel="noopener noreferrer">`assert_cfg`:467-490</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L543-L558" target="_blank" rel="noopener noreferrer">`set_out_dir`:543-558</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L561-L575" target="_blank" rel="noopener noreferrer">`set_run_dir`:561-575</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L528-L540" target="_blank" rel="noopener noreferrer">`get_fname`:528-540</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L522-L525" target="_blank" rel="noopener noreferrer">`makedirs_rm_exist`:522-525</a>


### Configuration Generator
This component specializes in programmatically generating diverse sets of configurations, particularly for systematic experimentation like grid searches or controlled sampling. It enables the exploration of a design space for hyperparameter tuning or comparative studies, directly supporting the "Scalability for Experimentation" and "Reproducibility" aspects of the project.


**Related Classes/Methods**:

- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L131-L141" target="_blank" rel="noopener noreferrer">`merge_dict`:131-141</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L171-L213" target="_blank" rel="noopener noreferrer">`gen_grid`:171-213</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L216-L278" target="_blank" rel="noopener noreferrer">`gen_grid_control_sample`:216-278</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L88-L96" target="_blank" rel="noopener noreferrer">`grid2list_sample`:88-96</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L156-L168" target="_blank" rel="noopener noreferrer">`design_space_count`:156-168</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L107-L128" target="_blank" rel="noopener noreferrer">`load_grid`:107-128</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/run/configs_gen.py#L68-L76" target="_blank" rel="noopener noreferrer">`grid2list`:68-76</a>
- <a href="https://github.com/snap-stanford/GraphGym/blob/master/graphgym/config.py#L528-L540" target="_blank" rel="noopener noreferrer">`get_fname`:528-540</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)