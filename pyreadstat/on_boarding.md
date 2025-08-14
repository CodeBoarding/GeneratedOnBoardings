```mermaid
graph LR
    Pyreadstat_Python_API["Pyreadstat Python API"]
    Cython_Bindings["Cython Bindings"]
    Readstat_C_Core_Library["Readstat C Core Library"]
    Pyreadstat_Utilities["Pyreadstat Utilities"]
    Internal_Data_Representation["Internal Data Representation"]
    Pyreadstat_Python_API -- "Uses" --> Cython_Bindings
    Pyreadstat_Python_API -- "Uses" --> Pyreadstat_Utilities
    Cython_Bindings -- "Delegates to" --> Readstat_C_Core_Library
    Cython_Bindings -- "Interacts with" --> Internal_Data_Representation
    Readstat_C_Core_Library -- "Populates" --> Internal_Data_Representation
    Pyreadstat_Utilities -- "Operates on" --> Internal_Data_Representation
    click Pyreadstat_Python_API href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyreadstat/Pyreadstat_Python_API.md" "Details"
    click Cython_Bindings href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyreadstat/Cython_Bindings.md" "Details"
    click Readstat_C_Core_Library href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyreadstat/Readstat_C_Core_Library.md" "Details"
    click Internal_Data_Representation href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyreadstat/Internal_Data_Representation.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Final architecture analysis for `pyreadstat`, consolidating the insights from the CFG and Source Analysis into a high-level data flow overview. This describes the abstract components and their relationships within the project, including the Python API, Cython bindings, C core library, utilities, and internal data representation.

### Pyreadstat Python API [[Expand]](./Pyreadstat_Python_API.md)
This is the top-level Python interface that users interact with. It provides the primary API functions (e.g., `read_sas7bdat`, `read_sav`, `read_dta`, `write_file`) for reading and writing statistical files, orchestrating the overall data loading and saving process.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/pyreadstat/pyreadstat/__init__.py#L1-L1" target="_blank" rel="noopener noreferrer">`pyreadstat/__init__.py` (1:1)</a>
- `pyreadstat/pyreadstat.py` (1:1)


### Cython Bindings [[Expand]](./Cython_Bindings.md)
These Cython modules serve as the high-performance bridge between the Python layer and the core C `Readstat Core Library`. They handle efficient data type conversions, memory management, and direct calls to the C functions.


**Related Classes/Methods**:

- `pyreadstat/_readstat_parser.pyx` (1:1)
- `pyreadstat/_readstat_writer.pyx` (1:1)
- `pyreadstat/pyreadstat.pyx` (1:1)


### Readstat C Core Library [[Expand]](./Readstat_C_Core_Library.md)
This is the foundational C library that performs the low-level, platform-agnostic operations of reading and writing various statistical file formats. It manages file I/O, handles data decoding, and extracts raw metadata, including format-specific logic for SAS, SPSS, and Stata files.


**Related Classes/Methods**:

- `src/readstat.c` (1:1)
- `src/readstat_parser.c` (1:1)
- `src/readstat_writer.c` (1:1)
- `src/sas/` (1:1)
- `src/spss/` (1:1)
- `src/stata/` (1:1)


### Pyreadstat Utilities
This Python module provides a collection of helper functions that perform post-processing tasks, such as setting catalog information, handling value labels, applying variable formats, and other data manipulation specific to the `pyreadstat` context.


**Related Classes/Methods**:

- <a href="https://github.com/Roche/pyreadstat/pyreadstat/pyfunctions.py#L1-L1" target="_blank" rel="noopener noreferrer">`pyreadstat/pyfunctions.py` (1:1)</a>


### Internal Data Representation [[Expand]](./Internal_Data_Representation.md)
This represents the various internal data models used throughout the system to hold statistical data, variable metadata, value labels, and other file-specific information. This includes both Python objects (e.g., Pandas DataFrames) and C structs used by the `readstat` library.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)