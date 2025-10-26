```mermaid
graph LR
    MDF_Core_Library["MDF Core Library"]
    GUI_Application_Orchestrator["GUI Application Orchestrator"]
    GUI_Data_Visualization_Interaction["GUI Data Visualization & Interaction"]
    GUI_File_Batch_Operations["GUI File & Batch Operations"]
    GUI_User_Defined_Logic_Dialogs["GUI User Defined Logic & Dialogs"]
    GUI_Application_Orchestrator -- "Initiates Data Operations" --> MDF_Core_Library
    GUI_Application_Orchestrator -- "Manages Display" --> GUI_Data_Visualization_Interaction
    GUI_Application_Orchestrator -- "Coordinates File Tasks" --> GUI_File_Batch_Operations
    GUI_Application_Orchestrator -- "Manages Dialogs" --> GUI_User_Defined_Logic_Dialogs
    GUI_File_Batch_Operations -- "Requests Data Processing" --> MDF_Core_Library
    GUI_Data_Visualization_Interaction -- "Retrieves Processed Data" --> MDF_Core_Library
    GUI_User_Defined_Logic_Dialogs -- "Provides Processing Rules" --> MDF_Core_Library
    GUI_User_Defined_Logic_Dialogs -- "Influences Display" --> GUI_Data_Visualization_Interaction
    click MDF_Core_Library href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/asammdf/MDF_Core_Library.md" "Details"
    click GUI_Application_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/asammdf/GUI_Application_Orchestrator.md" "Details"
    click GUI_File_Batch_Operations href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/asammdf/GUI_File_Batch_Operations.md" "Details"
    click GUI_User_Defined_Logic_Dialogs href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/asammdf/GUI_User_Defined_Logic_Dialogs.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `asammdf` project is structured around a powerful MDF Core Library that serves as the backbone for all data parsing, manipulation, and storage of automotive measurement data. This core library, optimized for performance, directly interacts with low-level block processors and manages signal data, including specialized handling for bus logging. A distinct GUI Application Orchestrator provides the entry point for the user interface, coordinating interactions between specialized GUI components. User-driven actions, managed by GUI File & Batch Operations and GUI User Defined Logic & Dialogs, are translated into requests for the MDF Core Library to load, process, or transform data. The results are then consumed by the GUI Data Visualization & Interaction component, which renders time-series plots and tabular views, offering interactive exploration. This modular design ensures a clear separation of concerns, allowing the core data processing capabilities to be used independently while providing a rich, extensible graphical environment for data analysis.

### MDF Core Library [[Expand]](./MDF_Core_Library.md)
The central data processing engine responsible for all MDF file I/O, parsing, signal extraction, and data manipulation. It acts as the primary interface for programmatic interaction with MDF data.


**Related Classes/Methods**:

- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/mdf.py" target="_blank" rel="noopener noreferrer">`src/asammdf/mdf.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/blocks/mdf_v3.py" target="_blank" rel="noopener noreferrer">`src/asammdf/blocks/mdf_v3.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/blocks/mdf_v4.py" target="_blank" rel="noopener noreferrer">`src/asammdf/blocks/mdf_v4.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/signal.py" target="_blank" rel="noopener noreferrer">`src/asammdf/signal.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/blocks/bus_logging_utils.py" target="_blank" rel="noopener noreferrer">`src/asammdf/blocks/bus_logging_utils.py`</a>


### GUI Application Orchestrator [[Expand]](./GUI_Application_Orchestrator.md)
The main application component that initializes the graphical user interface, manages the overall application lifecycle, and coordinates interactions between various GUI sub-components.


**Related Classes/Methods**:

- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/app/asammdfgui.py" target="_blank" rel="noopener noreferrer">`src/asammdf/app/asammdfgui.py`</a>


### GUI Data Visualization & Interaction
Handles the visual representation of MDF data, including plotting time-series signals, displaying tabular data, and managing the multi-document interface for multiple views.


**Related Classes/Methods**:

- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/plot.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/plot.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/widgets/mdi_area.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/widgets/mdi_area.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/widgets/tabular.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/widgets/tabular.py`</a>


### GUI File & Batch Operations [[Expand]](./GUI_File_Batch_Operations.md)
Provides user interface elements and logic specifically for managing MDF files (e.g., opening, saving, channel selection) and configuring/executing batch processing tasks on multiple files.


**Related Classes/Methods**:

- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/ui/file_widget.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/ui/file_widget.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/ui/batch_widget.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/ui/batch_widget.py`</a>


### GUI User Defined Logic & Dialogs [[Expand]](./GUI_User_Defined_Logic_Dialogs.md)
Encompasses all user interface components and underlying logic that allow users to define custom computations, conversion rules, and perform various search and filter operations on MDF data.


**Related Classes/Methods**:

- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/dialogs/define_channel.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/dialogs/define_channel.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/dialogs/conversion_editor.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/dialogs/conversion_editor.py`</a>
- <a href="https://github.com/danielhrisca/asammdf/blob/master/src/asammdf/gui/dialogs/simple_search.py" target="_blank" rel="noopener noreferrer">`src/asammdf/gui/dialogs/simple_search.py`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)