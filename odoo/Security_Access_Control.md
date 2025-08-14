```mermaid
graph LR
    Authentication_Manager["Authentication Manager"]
    Core_Security_Service["Core Security Service"]
    Authorization_Rule_Engine_IrRule_["Authorization Rule Engine (IrRule)"]
    Rule_Context_Retrieval["Rule Context & Retrieval"]
    Access_Domain_Computation["Access Domain Computation"]
    Access_Violation_Handler["Access Violation Handler"]
    Authentication_Manager -- "provides authenticated user identity to" --> Core_Security_Service
    Core_Security_Service -- "invokes" --> Authorization_Rule_Engine_IrRule_
    Authorization_Rule_Engine_IrRule_ -- "relies on" --> Rule_Context_Retrieval
    Authorization_Rule_Engine_IrRule_ -- "utilizes" --> Access_Domain_Computation
    Authorization_Rule_Engine_IrRule_ -- "communicates with" --> Access_Violation_Handler
    Access_Domain_Computation -- "depends on" --> Rule_Context_Retrieval
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Security & Access Control` subsystem is critical for an ERP system, ensuring data integrity and user permissions. It is fundamentally composed of distinct yet interconnected components handling user identity, policy enforcement, and granular data access.

### Authentication Manager
Manages user login, session creation, and validation. It integrates various authentication mechanisms, including standard password-based login and external providers like OAuth and Passkey, establishing the user's identity within the system.


**Related Classes/Methods**:

- `odoo.service.security`
- `odoo.addons.auth_oauth`
- `odoo.addons.auth_passkey`


### Core Security Service
Acts as the central orchestrator for security operations. It receives authenticated user identities and coordinates with the Authorization Rule Engine to enforce security policies across the application, ensuring all operations adhere to defined access rules.


**Related Classes/Methods**:

- `odoo.service.security`


### Authorization Rule Engine (IrRule)
The core authorization component responsible for defining, storing, and orchestrating the evaluation of all data access rules (ir.rule records). It is the central authority for determining what data a user can access or modify based on configured policies.


**Related Classes/Methods**:

- `odoo.addons.base.models.ir_rule`


### Rule Context & Retrieval
Provides the dynamic operational context (e.g., current user, environment variables, specific record data) required for rule evaluation and efficiently retrieves all relevant access rules that apply to a specific model or operation.


**Related Classes/Methods**:

- `odoo.addons.base.models.ir_rule._eval_context`
- `odoo.addons.base.models.ir_rule._get_rules`


### Access Domain Computation
Computes and validates the final, effective data filtering domain that applies to a user's access request. It combines multiple ir.rule definitions to form the actual data visibility criteria and checks if a proposed data operation is permissible.


**Related Classes/Methods**:

- `odoo.addons.base.models.ir_rule._compute_domain`
- `odoo.addons.base.models.ir_rule._check_domain`


### Access Violation Handler
Generates and formats appropriate error messages when an access violation occurs. It provides clear feedback about the denied operation and potentially the reason for denial, crucial for user experience and debugging.


**Related Classes/Methods**:

- `odoo.addons.base.models.ir_rule._make_access_error`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)