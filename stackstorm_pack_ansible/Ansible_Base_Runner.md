```mermaid
graph LR
    AnsibleBaseRunner["AnsibleBaseRunner"]
    Shell_Utility["Shell Utility"]
    AnsibleBaseRunner -- "relies on" --> Shell_Utility
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Ansible Base Runner subsystem is a foundational Python library designed to encapsulate the common logic required for executing various Ansible commands within a StackStorm environment. It promotes code reusability and consistency across different Ansible-related actions.

### AnsibleBaseRunner
This is the core abstract base class of the Ansible Base Runner subsystem. It provides the foundational logic for executing various Ansible commands. Its responsibilities include: Input Parameter Parsing: Specifically handles the transformation of --extra_vars arguments (_parse_extra_vars). Environment Management: Ensures correct Ansible execution by prepending the virtual environment path to the system's PATH (_prepend_venv_path). Command Construction: Dynamically builds the full command-line arguments for Ansible binaries (via the cmd property). Binary Resolution: Locates the correct Ansible binary within the environment (via the binary property). External Command Invocation: Executes the constructed command using subprocess.call and handles exit codes (via the execute method). It acts as an Adapter and Facade for Ansible's command-line interface, abstracting the underlying shell execution details for all specific Ansible actions that inherit from it.


**Related Classes/Methods**:

- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L14-L141" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner` (14:141)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L30-L85" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner:_parse_extra_vars` (30:85)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L88-L97" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner:_prepend_venv_path` (88:97)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L112-L119" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner:cmd` (112:119)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L122-L141" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner:binary` (122:141)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/ansible_base.py#L99-L108" target="_blank" rel="noopener noreferrer">`ansible_base.AnsibleBaseRunner:execute` (99:108)</a>


### Shell Utility
This component provides utility functions specifically designed for processing and manipulating shell command arguments. Its primary role is to assist the AnsibleBaseRunner by applying specific replacement rules to command arguments before they are executed, ensuring proper formatting and handling of shell-specific nuances.


**Related Classes/Methods**:

- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/shell.py#L1-L1" target="_blank" rel="noopener noreferrer">`shell` (1:1)</a>
- <a href="https://github.com/recursionpharma/stackstorm_pack_ansible/blob/trunk/actions/lib/shell.py#L7-L29" target="_blank" rel="noopener noreferrer">`shell:replace_args` (7:29)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)