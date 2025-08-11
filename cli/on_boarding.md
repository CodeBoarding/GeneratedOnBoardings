```mermaid
graph LR
    CLI_Core["CLI Core"]
    Scan_Analysis_Engine["Scan & Analysis Engine"]
    API_Authentication_Service["API & Authentication Service"]
    Remediation_Engine["Remediation Engine"]
    Reporting_Configuration["Reporting & Configuration"]
    CLI_Core -- "dispatches to" --> Scan_Analysis_Engine
    CLI_Core -- "dispatches to" --> Remediation_Engine
    CLI_Core -- "utilizes" --> API_Authentication_Service
    CLI_Core -- "interacts with" --> Reporting_Configuration
    Scan_Analysis_Engine -- "uses" --> API_Authentication_Service
    Remediation_Engine -- "uses" --> API_Authentication_Service
    API_Authentication_Service -- "relies on" --> Reporting_Configuration
    click CLI_Core href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cli/CLI_Core.md" "Details"
    click Scan_Analysis_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cli/Scan_Analysis_Engine.md" "Details"
    click API_Authentication_Service href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cli/API_Authentication_Service.md" "Details"
    click Remediation_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cli/Remediation_Engine.md" "Details"
    click Reporting_Configuration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/cli/Reporting_Configuration.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Analysis of the Snyk CLI architecture, detailing its core components, their functionalities, and their interdependencies.

### CLI Core [[Expand]](./CLI_Core.md)
The central entry point, responsible for parsing arguments, dispatching commands, and orchestrating the overall execution flow. It interacts with other components to fulfill command-specific tasks.


**Related Classes/Methods**:

- <a href="https://github.com/snyk/cli/blob/main/src/cli/" target="_blank" rel="noopener noreferrer">`src/cli/`</a>
- <a href="https://github.com/snyk/cli/blob/main/src/cli/commands/" target="_blank" rel="noopener noreferrer">`src/cli/commands/`</a>


### Scan & Analysis Engine [[Expand]](./Scan_Analysis_Engine.md)
Detects project ecosystems, loads and manages plugins for dependency extraction and code analysis, and applies security policies to scan results. It includes specialized capabilities for Infrastructure as Code (IaC) analysis.


**Related Classes/Methods**:

- <a href="https://github.com/snyk/cli/blob/main/src/lib/snyk-test/" target="_blank" rel="noopener noreferrer">`src/lib/snyk-test/`</a>
- <a href="https://github.com/snyk/cli/blob/main/src/lib/plugins/" target="_blank" rel="noopener noreferrer">`src/lib/plugins/`</a>
- <a href="https://github.com/snyk/cli/blob/main/src/lib/policy/" target="_blank" rel="noopener noreferrer">`src/lib/policy/`</a>
- <a href="https://github.com/snyk/cli/blob/main/src/lib/iac/" target="_blank" rel="noopener noreferrer">`src/lib/iac/`</a>


### API & Authentication Service [[Expand]](./API_Authentication_Service.md)
Manages all external API communications, including request construction, execution, user authentication (API tokens), and authorization checks.


**Related Classes/Methods**:

- <a href="https://github.com/snyk/cli/blob/main/src/lib/request/" target="_blank" rel="noopener noreferrer">`src/lib/request/`</a>


### Remediation Engine [[Expand]](./Remediation_Engine.md)
Identifies fixable vulnerabilities from scan results and applies automated remediation steps (e.g., dependency upgrades, patches) directly to project files.


**Related Classes/Methods**:

- <a href="https://github.com/snyk/cli/blob/main/packages/snyk_fix/src/" target="_blank" rel="noopener noreferrer">`packages/snyk_fix/src/`</a>


### Reporting & Configuration [[Expand]](./Reporting_Configuration.md)
Handles the transformation of raw data into various output formats (console, JSON, SARIF) and centrally manages all CLI configuration settings, including API endpoints and user preferences.


**Related Classes/Methods**:

- <a href="https://github.com/snyk/cli/blob/main/src/lib/formatters/" target="_blank" rel="noopener noreferrer">`src/lib/formatters/`</a>
- <a href="https://github.com/snyk/cli/blob/main/src/lib/config/" target="_blank" rel="noopener noreferrer">`src/lib/config/`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)