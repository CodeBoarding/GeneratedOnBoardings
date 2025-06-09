```mermaid
graph LR
    Style_Guide_Registration["Style Guide Registration"]
    Google_Style_Guide_Enforcement["Google Style Guide Enforcement"]
    Shopify_Style_Guide_Enforcement["Shopify Style Guide Enforcement"]
    AST_Utilities["AST Utilities"]
    Git_and_External_Tool_Integration["Git and External Tool Integration"]
    Style_Guide_Registration -- "registers" --> Google_Style_Guide_Enforcement
    Style_Guide_Registration -- "registers" --> Shopify_Style_Guide_Enforcement
    Google_Style_Guide_Enforcement -- "uses" --> AST_Utilities
    click Style_Guide_Registration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/shopify_python/Style Guide Registration.md" "Details"
    click Google_Style_Guide_Enforcement href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/shopify_python/Google Style Guide Enforcement.md" "Details"
    click Shopify_Style_Guide_Enforcement href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/shopify_python/Shopify Style Guide Enforcement.md" "Details"
    click AST_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/shopify_python/AST Utilities.md" "Details"
    click Git_and_External_Tool_Integration href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/shopify_python/Git and External Tool Integration.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `shopify_python` project serves as a comprehensive code quality and style enforcement system for Python. Its primary purpose is to ensure adherence to both Google Python Style Guide and Shopify-specific coding standards. It integrates with Pylint for static analysis, leverages AST utilities for code inspection, and provides utilities for interacting with Git repositories to process changed files and apply automated formatting with tools like autopep8.

### Style Guide Registration
Central entry point for registering various style checkers (Google and Shopify) with the Pylint linter, enabling the enforcement of coding standards.


**Related Classes/Methods**:

- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/__init__.py#L13-L15" target="_blank" rel="noopener noreferrer">`shopify_python.__init__:register` (13:15)</a>


### Google Style Guide Enforcement
Implements a Pylint checker that enforces the Google Python Style Guide, applying specific style rules by visiting AST nodes.


**Related Classes/Methods**:

- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/google_styleguide.py#L15-L17" target="_blank" rel="noopener noreferrer">`shopify_python.google_styleguide:register_checkers` (15:17)</a>
- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/google_styleguide.py#L20-L352" target="_blank" rel="noopener noreferrer">`shopify_python.google_styleguide.GoogleStyleGuideChecker` (20:352)</a>


### Shopify Style Guide Enforcement
Implements a Pylint checker that enforces Shopify-specific coding style guidelines, validating naming conventions and comment structures.


**Related Classes/Methods**:

- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/shopify_styleguide.py#L12-L14" target="_blank" rel="noopener noreferrer">`shopify_python.shopify_styleguide:register_checkers` (12:14)</a>
- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/shopify_styleguide.py#L17-L83" target="_blank" rel="noopener noreferrer">`shopify_python.shopify_styleguide.ShopifyStyleGuideChecker` (17:83)</a>


### AST Utilities
Provides utility functions for analyzing Abstract Syntax Trees (ASTs) of Python code, primarily for measuring code complexity or size.


**Related Classes/Methods**:

- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/ast.py#L4-L8" target="_blank" rel="noopener noreferrer">`shopify_python.ast:count_tree_size` (4:8)</a>


### Git and External Tool Integration
Provides utilities for interacting with Git repositories to identify changed Python files and integrates with external code analysis tools like `autopep8` and `pylint`.


**Related Classes/Methods**:

- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/git_utils.py#L52-L60" target="_blank" rel="noopener noreferrer">`shopify_python.git_utils:changed_python_files_in_tree` (52:60)</a>
- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/git_utils.py#L86-L107" target="_blank" rel="noopener noreferrer">`shopify_python.git_utils:autopep_files` (86:107)</a>
- <a href="https://github.com/Shopify/shopify_python/blob/master/shopify_python/git_utils.py#L123-L135" target="_blank" rel="noopener noreferrer">`shopify_python.git_utils:pylint_files` (123:135)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)