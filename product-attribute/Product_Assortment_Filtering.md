```mermaid
graph LR
    Product_Assortment_Filtering_Core["Product Assortment & Filtering Core"]
    Product_Template_Management["Product Template Management"]
    Product_Variant_Management["Product Variant Management"]
    Product_Assortment_Filtering_Core -- "Applies Filters To" --> Product_Template_Management
    Product_Assortment_Filtering_Core -- "Applies Filters To" --> Product_Variant_Management
    Product_Template_Management -- "Is Filtered By" --> Product_Assortment_Filtering_Core
    Product_Template_Management -- "Provides Base For" --> Product_Variant_Management
    Product_Variant_Management -- "Is Filtered By" --> Product_Assortment_Filtering_Core
    Product_Variant_Management -- "Extends" --> Product_Template_Management
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

This subsystem focuses on defining and applying rules for product visibility and selection, leveraging Odoo's inherent data models and extensibility.

### Product Assortment & Filtering Core
This is the central component responsible for managing and applying dynamic filtering rules and product assortment logic. It utilizes Odoo's `ir.filters` model to allow users to define custom search and display criteria for products, enabling customer-specific views or dynamic filter applications.


**Related Classes/Methods**:

- `ir.filters` (1:1)


### Product Template Management
Manages the foundational data for generic products. This component defines the common attributes, categories, and sales information for a product before any specific variations are considered. It serves as the base for all product-related operations and is a primary target for assortment and filtering rules.


**Related Classes/Methods**:

- <a href="https://github.com/OCA/product-attribute/blob/18.0/product_code_unique/models/product.py#L1-L1" target="_blank" rel="noopener noreferrer">`product.template` (1:1)</a>


### Product Variant Management
Handles the specific, detailed variations of products, such as different sizes, colors, or configurations. This component extends the base product information from `Product Template Management` with variant-specific attributes and is also subject to the dynamic filtering and assortment rules.


**Related Classes/Methods**:

- `product.product`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)