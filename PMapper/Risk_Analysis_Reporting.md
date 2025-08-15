```mermaid
graph LR
    Risk_Analysis_Orchestrator["Risk Analysis Orchestrator"]
    Finding_Generator_Dispatcher["Finding Generator Dispatcher"]
    Report_Aggregator["Report Aggregator"]
    Report_Presenter["Report Presenter"]
    Finding_Data_Model["Finding Data Model"]
    MFA_Action_Risk_Detector["MFA Action Risk Detector"]
    Admin_MFA_Compliance_Detector["Admin MFA Compliance Detector"]
    Privilege_Escalation_Detector["Privilege Escalation Detector"]
    Risk_Analysis_Orchestrator -- "calls" --> Report_Aggregator
    Risk_Analysis_Orchestrator -- "calls" --> Report_Presenter
    Finding_Generator_Dispatcher -- "calls" --> MFA_Action_Risk_Detector
    Finding_Generator_Dispatcher -- "calls" --> Admin_MFA_Compliance_Detector
    Finding_Generator_Dispatcher -- "calls" --> Privilege_Escalation_Detector
    Report_Aggregator -- "relies on" --> Finding_Generator_Dispatcher
    Report_Aggregator -- "consumes" --> Finding_Data_Model
    Report_Presenter -- "consumes" --> Finding_Data_Model
    MFA_Action_Risk_Detector -- "creates" --> Finding_Data_Model
    Admin_MFA_Compliance_Detector -- "creates" --> Finding_Data_Model
    Privilege_Escalation_Detector -- "creates" --> Finding_Data_Model
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Risk Analysis & Reporting` subsystem is responsible for identifying common AWS IAM security risks and misconfigurations, leveraging the graph structure and policy simulation capabilities to detect vulnerabilities, and generating structured findings and reports.

### Risk Analysis Orchestrator
Serves as the primary entry point for initiating the risk analysis and report generation process. It orchestrates the flow from finding detection to report presentation.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L43-L51" target="_blank" rel="noopener noreferrer">`gen_findings_and_print`:43-51</a>


### Finding Generator Dispatcher
Acts as a central dispatcher, invoking various specialized functions to detect different types of security risks within the IAM graph.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L67-L79" target="_blank" rel="noopener noreferrer">`gen_all_findings`:67-79</a>


### Report Aggregator
Collects and aggregates all identified security findings into a comprehensive report structure.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L54-L64" target="_blank" rel="noopener noreferrer">`gen_report`:54-64</a>


### Report Presenter
Handles the final formatting and display of the generated risk report to the user, typically via the command-line interface.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L519-L548" target="_blank" rel="noopener noreferrer">`print_report`:519-548</a>


### Finding Data Model
Defines the structured data model for individual security findings, encapsulating details such as the type of risk, affected entities, and severity.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/finding.py#L19-L37" target="_blank" rel="noopener noreferrer">`finding`:19-37</a>


### MFA Action Risk Detector
Identifies security risks specifically related to Multi-Factor Authentication (MFA) actions and configurations.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L128-L166" target="_blank" rel="noopener noreferrer">`gen_mfa_actions_findings`:128-166</a>


### Admin MFA Compliance Detector
Detects administrative users within the IAM graph who do not have Multi-Factor Authentication (MFA) enabled, highlighting a common security misconfiguration.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L410-L448" target="_blank" rel="noopener noreferrer">`gen_admin_users_without_mfa_finding`:410-448</a>


### Privilege Escalation Detector
Analyzes the IAM graph to identify potential paths through which an entity could escalate its privileges beyond its intended scope.


**Related Classes/Methods**:

- <a href="https://github.com/nccgroup/PMapper/blob/master/principalmapper/analysis/find_risks.py#L82-L125" target="_blank" rel="noopener noreferrer">`gen_privesc_findings`:82-125</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)