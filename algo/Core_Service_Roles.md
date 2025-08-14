```mermaid
graph LR
    common["common"]
    dns["dns"]
    firewall["firewall"]
    wireguard["wireguard"]
    ipsec["ipsec"]
    users["users"]
    common -- "is a prerequisite for" --> dns
    common -- "is a prerequisite for" --> firewall
    dns -- "is a prerequisite for" --> wireguard
    firewall -- "is a prerequisite for" --> wireguard
    dns -- "is a prerequisite for" --> ipsec
    firewall -- "is a prerequisite for" --> ipsec
    users -- "Provides user data to" --> wireguard
    users -- "Provides user data to" --> ipsec
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### common
A foundational role that executes prerequisite tasks for other roles, such as installing common packages, setting up unattended upgrades, and applying OS-level configurations.


**Related Classes/Methods**:

- `roles/common/tasks/main.yml`


### dns
Configures the system's DNS resolver, typically setting up a local caching resolver to enhance privacy and performance for VPN clients.


**Related Classes/Methods**:

- `roles/dns/tasks/main.yml`


### firewall
Manages network security by configuring `iptables`. It secures the server by default and creates specific rules to allow traffic for the selected VPN protocol.


**Related Classes/Methods**:

- `roles/firewall/tasks/main.yml`


### wireguard
Installs and configures the WireGuard VPN service. This includes managing kernel modules, generating cryptographic keys, and setting up network interfaces.


**Related Classes/Methods**:

- `roles/wireguard/tasks/main.yml`


### ipsec
Installs and configures the IPsec VPN service using strongSwan. It handles package installation, certificate setup, and connection profile configuration.


**Related Classes/Methods**:

- `roles/ipsec/tasks/main.yml`


### users
Manages the server-side VPN user accounts and credentials required by the IPsec and WireGuard services.


**Related Classes/Methods**:

- `roles/users/tasks/main.yml`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)