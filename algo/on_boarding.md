```mermaid
graph LR
    CLI_Orchestrator["CLI Orchestrator"]
    Configuration_Store["Configuration Store"]
    Orchestration_Playbooks["Orchestration Playbooks"]
    Cloud_Provider_Roles["Cloud Provider Roles"]
    Core_Service_Roles["Core Service Roles"]
    CLI_Orchestrator -- "Triggers" --> Orchestration_Playbooks
    CLI_Orchestrator -- "Reads/Updates" --> Configuration_Store
    Configuration_Store -- "Provides variables to" --> Orchestration_Playbooks
    Orchestration_Playbooks -- "Uses" --> Cloud_Provider_Roles
    Orchestration_Playbooks -- "Applies" --> Core_Service_Roles
    click Orchestration_Playbooks href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/algo/Orchestration_Playbooks.md" "Details"
    click Core_Service_Roles href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/algo/Core_Service_Roles.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### CLI Orchestrator
Provides a simplified command-line interface for users to manage the VPN lifecycle. It wraps underlying Ansible commands to handle server deployment, updates, and user management.


**Related Classes/Methods**:

- `algo`


### Configuration Store
Manages all user-defined variables, including cloud provider credentials, server options, and lists of VPN users. This component decouples configuration from execution logic.


**Related Classes/Methods**:

- `config.cfg`
- `configs/`


### Orchestration Playbooks [[Expand]](./Orchestration_Playbooks.md)
Acts as the central controller, defining the high-level sequence of tasks for provisioning servers and deploying client configurations. It coordinates the execution of various roles.


**Related Classes/Methods**:

- `cloud.yml`
- `deploy_client.yml`


### Cloud Provider Roles
A collection of modular roles, each responsible for the specific API interactions required to provision a virtual machine on a supported cloud provider (e.g., AWS, Azure, DigitalOcean).


**Related Classes/Methods**:

- `roles/cloud_digitalocean`
- `roles/cloud_aws`
- `roles/cloud_azure`


### Core Service Roles [[Expand]](./Core_Service_Roles.md)
A set of roles responsible for configuring the server's primary functions. This includes installing and setting up the chosen VPN protocol (WireGuard/IPsec), the firewall, DNS, and user accounts.


**Related Classes/Methods**:

- `roles/wireguard`
- `roles/ipsec`
- `roles/firewall`
- `roles/dns`
- `roles/users`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)