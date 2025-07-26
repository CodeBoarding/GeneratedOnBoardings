```mermaid
graph LR
    Employee_Lifecycle_Management["Employee Lifecycle Management"]
    Payroll_Core_Engine["Payroll Core Engine"]
    Time_Attendance_System["Time & Attendance System"]
    Performance_Incentives["Performance & Incentives"]
    Mobile_Integration_Layer["Mobile Integration Layer"]
    HR_Settings_Configuration["HR Settings & Configuration"]
    Tax_Compliance_Engine["Tax Compliance Engine"]
    Expense_Management["Expense Management"]
    Time_Attendance_System -- "feeds into" --> Payroll_Core_Engine
    Payroll_Core_Engine -- "integrates with" --> Tax_Compliance_Engine
    Payroll_Core_Engine -- "integrates with" --> Expense_Management
    Mobile_Integration_Layer -- "provides notifications for" --> Employee_Lifecycle_Management
    Mobile_Integration_Layer -- "provides notifications for" --> Payroll_Core_Engine
    Mobile_Integration_Layer -- "provides notifications for" --> Time_Attendance_System
    Mobile_Integration_Layer -- "provides notifications for" --> Performance_Incentives
    Employee_Lifecycle_Management -- "relies on" --> HR_Settings_Configuration
    Payroll_Core_Engine -- "relies on" --> HR_Settings_Configuration
    Time_Attendance_System -- "relies on" --> HR_Settings_Configuration
    Performance_Incentives -- "relies on" --> HR_Settings_Configuration
    Mobile_Integration_Layer -- "relies on" --> HR_Settings_Configuration
    Tax_Compliance_Engine -- "relies on" --> HR_Settings_Configuration
    Expense_Management -- "relies on" --> HR_Settings_Configuration
    click Employee_Lifecycle_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Employee_Lifecycle_Management.md" "Details"
    click Payroll_Core_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Payroll_Core_Engine.md" "Details"
    click Time_Attendance_System href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Time_Attendance_System.md" "Details"
    click Performance_Incentives href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Performance_Incentives.md" "Details"
    click Tax_Compliance_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Tax_Compliance_Engine.md" "Details"
    click Expense_Management href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/hrms/Expense_Management.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Updated analysis incorporating missing components and revised relationships. Key changes include explicit tax/expense components, removed invalid inheritance, and clarified mobile layer interactions while maintaining HR settings dependencies.

### Employee Lifecycle Management [[Expand]](./Employee_Lifecycle_Management.md)
Manages recruitment, onboarding, and separation workflows.


**Related Classes/Methods**:

- `hrms.hr.doctype.employee_onboarding.employee_onboarding`
- `hrms.hr.doctype.employee_separation.employee_separation`
- `hrms.hr.doctype.job_applicant.job_applicant`


### Payroll Core Engine [[Expand]](./Payroll_Core_Engine.md)
Central payroll calculations and core financial processing.


**Related Classes/Methods**:

- `hrms.hr.doctype.salary_slip.salary_slip` (180:200)
- `hrms.hr.doctype.employee_tax_exemption_declaration.employee_tax_exemption_declaration` (205:220)


### Time & Attendance System [[Expand]](./Time_Attendance_System.md)
Tracks attendance, leave applications, and shift scheduling.


**Related Classes/Methods**:

- `hrms.hr.doctype.attendance.attendance`
- `hrms.hr.doctype.leave_application.leave_application`
- `hrms.hr.doctype.shift_type.shift_type`


### Performance & Incentives [[Expand]](./Performance_Incentives.md)
Manages appraisals, goals, and employee benefits.


**Related Classes/Methods**:

- `hrms.hr.doctype.appraisal.appraisal`
- `hrms.hr.doctype.employee_benefit_application.employee_benefit_application` (285:300)


### Mobile Integration Layer
Enables PWA notifications and cross-component mobile workflows.


**Related Classes/Methods**:

- `hrms.hr.doctype.pwa_notifications_mixin.pwa_notifications_mixin` (285:300)


### HR Settings & Configuration
Centralized configuration for all HR modules.


**Related Classes/Methods**:

- <a href="https://github.com/frappe/hrms/blob/develop/hrms/hr/doctype/hr_settings/hr_settings.py#L305-L320" target="_blank" rel="noopener noreferrer">`hrms.hr.doctype.hr_settings.hr_settings` (305:320)</a>


### Tax Compliance Engine [[Expand]](./Tax_Compliance_Engine.md)
Handles tax calculations, compliance reporting, and regulatory updates.


**Related Classes/Methods**:

- `hrms.hr.doctype.employee_tax_exemption_declaration.employee_tax_exemption_declaration` (205:220)


### Expense Management [[Expand]](./Expense_Management.md)
Processes expense claims, reimbursement workflows, and policy validation.


**Related Classes/Methods**:

- `hrms.hr.doctype.expense_claim.expense_claim`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)