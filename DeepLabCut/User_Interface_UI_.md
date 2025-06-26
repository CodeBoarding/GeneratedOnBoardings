```mermaid
graph LR
    User_Interface_UI_["User Interface (UI)"]
    deeplabcut_gui_window_MainWindow["deeplabcut.gui.window.MainWindow"]
    deeplabcut_gui_components_DefaultTab["deeplabcut.gui.components.DefaultTab"]
    deeplabcut_gui_tabs_create_project_ProjectCreator["deeplabcut.gui.tabs.create_project.ProjectCreator"]
    deeplabcut_gui_tabs_label_frames_LabelFrames["deeplabcut.gui.tabs.label_frames.LabelFrames"]
    deeplabcut_gui_tabs_train_network_TrainNetwork["deeplabcut.gui.tabs.train_network.TrainNetwork"]
    deeplabcut_gui_tabs_analyze_videos_AnalyzeVideos["deeplabcut.gui.tabs.analyze_videos.AnalyzeVideos"]
    deeplabcut_gui_widgets["deeplabcut.gui.widgets"]
    deeplabcut_cli["deeplabcut.cli"]
    deeplabcut_core_engine_Engine["deeplabcut.core.engine.Engine"]
    deeplabcut_utils_auxfun_videos["deeplabcut.utils.auxfun_videos"]
    User_Interface_UI_ -- "uses" --> deeplabcut_gui_window_MainWindow
    User_Interface_UI_ -- "uses" --> deeplabcut_cli
    deeplabcut_gui_window_MainWindow -- "contains" --> deeplabcut_gui_components_DefaultTab
    deeplabcut_gui_window_MainWindow -- "interacts with" --> deeplabcut_core_engine_Engine
    deeplabcut_gui_tabs_create_project_ProjectCreator -- "inherits from" --> deeplabcut_gui_components_DefaultTab
    deeplabcut_gui_components_DefaultTab -- "uses" --> deeplabcut_gui_widgets
    deeplabcut_gui_tabs_create_project_ProjectCreator -- "calls" --> deeplabcut_core_engine_Engine
    deeplabcut_gui_tabs_label_frames_LabelFrames -- "inherits from" --> deeplabcut_gui_components_DefaultTab
    deeplabcut_gui_tabs_label_frames_LabelFrames -- "uses" --> deeplabcut_utils_auxfun_videos
    deeplabcut_gui_tabs_train_network_TrainNetwork -- "inherits from" --> deeplabcut_gui_components_DefaultTab
    deeplabcut_gui_tabs_train_network_TrainNetwork -- "calls" --> deeplabcut_core_engine_Engine
    deeplabcut_gui_tabs_analyze_videos_AnalyzeVideos -- "inherits from" --> deeplabcut_gui_components_DefaultTab
    deeplabcut_gui_tabs_analyze_videos_AnalyzeVideos -- "calls" --> deeplabcut_core_engine_Engine
    deeplabcut_cli -- "calls" --> deeplabcut_core_engine_Engine
    deeplabcut_gui_widgets -- "uses" --> deeplabcut_utils_auxfun_videos
    click User_Interface_UI_ href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/DeepLabCut/User_Interface_UI_.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The User Interface (UI) component in DeepLabCut is designed to provide a seamless interaction layer for users, encompassing both a graphical user interface (GUI) and a command-line interface (CLI).

### User Interface (UI) [[Expand]](./User_Interface_UI_.md)
The primary interaction layer for users, offering both command-line tools (`deeplabcut.cli`) and a comprehensive graphical interface (`deeplabcut.gui`). It translates user commands and actions into calls to the underlying DeepLabCut functionalities, providing a unified entry point for all workflows.


**Related Classes/Methods**:

- `deeplabcut.gui` (1:1)
- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/cli.py#L1-L1" target="_blank" rel="noopener noreferrer">`deeplabcut.cli` (1:1)</a>


### deeplabcut.gui.window.MainWindow
The central window of the DeepLabCut graphical user interface, responsible for initializing and managing all GUI tabs and overall application flow.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/window.py#L83-L740" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.window.MainWindow` (83:740)</a>


### deeplabcut.gui.components.DefaultTab
An abstract base class that provides common structure and functionality for all specific workflow tabs within the DeepLabCut GUI.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/components.py#L291-L327" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.components.DefaultTab` (291:327)</a>


### deeplabcut.gui.tabs.create_project.ProjectCreator
A GUI tab dedicated to guiding users through the process of creating new DeepLabCut projects, including setting up project configurations and initial directories.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/tabs/create_project.py#L184-L538" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.tabs.create_project.ProjectCreator` (184:538)</a>


### deeplabcut.gui.tabs.label_frames.LabelFrames
A GUI tab that provides tools for manually labeling keypoints on extracted video frames, a crucial step in creating training datasets.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/tabs/label_frames.py#L102-L146" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.tabs.label_frames.LabelFrames` (102:146)</a>


### deeplabcut.gui.tabs.train_network.TrainNetwork
A GUI tab for configuring and initiating the training of DeepLabCut's neural network models, allowing users to monitor training progress.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/tabs/train_network.py#L49-L273" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.tabs.train_network.TrainNetwork` (49:273)</a>


### deeplabcut.gui.tabs.analyze_videos.AnalyzeVideos
A GUI tab for applying trained DeepLabCut models to new videos to perform pose estimation and generate analysis results.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/tabs/analyze_videos.py#L32-L372" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.tabs.analyze_videos.AnalyzeVideos` (32:372)</a>


### deeplabcut.gui.widgets
A module containing various custom and reusable PyQt widgets and UI components used throughout the DeepLabCut GUI to enhance user interaction.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/gui/widgets.py#L1-L1" target="_blank" rel="noopener noreferrer">`deeplabcut.gui.widgets` (1:1)</a>


### deeplabcut.cli
The command-line interface for DeepLabCut, providing a scriptable and non-graphical way to access and execute core DeepLabCut functionalities.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/cli.py#L1-L1" target="_blank" rel="noopener noreferrer">`deeplabcut.cli` (1:1)</a>


### deeplabcut.core.engine.Engine
The central processing unit of DeepLabCut, responsible for managing project configurations, orchestrating workflows, and delegating tasks to specific DeepLabCut modules (e.g., for project creation, training, analysis).


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/core/engine.py#L25-L48" target="_blank" rel="noopener noreferrer">`deeplabcut.core.engine.Engine` (25:48)</a>


### deeplabcut.utils.auxfun_videos
A collection of utility functions specifically designed for handling video-related operations, such as reading, writing, and processing video files.


**Related Classes/Methods**:

- <a href="https://github.com/DeepLabCut/DeepLabCut/deeplabcut/utils/auxfun_videos.py#L1-L1" target="_blank" rel="noopener noreferrer">`deeplabcut.utils.auxfun_videos` (1:1)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)