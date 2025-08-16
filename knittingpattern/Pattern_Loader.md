```mermaid
graph LR
    Pattern_Data_Abstraction["Pattern Data Abstraction"]
    Loading_Dispatcher["Loading Dispatcher"]
    Public_API_Loaders["Public API Loaders"]
    Pattern_Set_Factory["Pattern Set Factory"]
    Loading_Dispatcher -- "invokes" --> Pattern_Data_Abstraction
    Public_API_Loaders -- "delegates to" --> Loading_Dispatcher
    Pattern_Set_Factory -- "invokes" --> Public_API_Loaders
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Pattern Loader` subsystem is the initial data ingestion layer for the knitting pattern DSL. It is responsible for abstracting various input sources and providing raw pattern data to the subsequent processing stages.

### Pattern Data Abstraction
This component provides a unified, low-level interface for abstracting and retrieving raw knitting pattern data from diverse external sources (files, URLs, strings, in-memory objects, generic paths). It standardizes this raw input into a usable string or object format for subsequent processing stages.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/Loader.py" target="_blank" rel="noopener noreferrer">`knittingpattern.Loader`</a>


### Loading Dispatcher
This component acts as the central coordinator and internal dispatcher for all incoming loading requests. It centralizes the logic for determining the appropriate loading strategy based on the input type, orchestrating the data retrieval by interacting with the `Pattern Data Abstraction`.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L16-L32" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from`:16-32</a>


### Public API Loaders
These functions collectively serve as the public API entry points for users to initiate the loading of knitting patterns from various specific input types (e.g., in-memory object, string, file path, URL). They provide a user-friendly interface, abstracting the underlying loading complexity by delegating to the `Loading Dispatcher`.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L35-L40" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_object`:35-40</a>
- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L43-L48" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_string`:43-48</a>
- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L51-L56" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_file`:51-56</a>
- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L59-L64" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_path`:59-64</a>
- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L67-L72" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_url`:67-72</a>
- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L75-L85" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.load_from_relative_file`:75-85</a>


### Pattern Set Factory
This high-level factory function initiates the entire knitting pattern processing pipeline. Its primary role is to create a new knitting pattern set, and it explicitly highlights that the data loading process is the foundational first step before any parsing, transformation, or other operations occur.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/__init__.py#L123-L129" target="_blank" rel="noopener noreferrer">`knittingpattern.__init__.new_knitting_pattern_set`:123-129</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)