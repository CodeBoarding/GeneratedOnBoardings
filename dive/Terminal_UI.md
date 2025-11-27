```mermaid
graph LR
    UI_Façade_V1UI_["UI Façade (V1UI)"]
    UI_Controller_App_["UI Controller (App)"]
    Layout_Manager["Layout Manager"]
    Key_Binding_Dispatcher["Key‑Binding Dispatcher"]
    LayerSetState_View_Model["LayerSetState View‑Model"]
    FileTree_View_Model["FileTree View‑Model"]
    FileTree_View["FileTree View"]
    LayerDetails_View["LayerDetails View"]
    Unclassified["Unclassified"]
    UI_Façade_V1UI_ -- "ExploreAnalysis event triggers app.Run; passes v1.Config (analysis data & preferences)" --> UI_Controller_App_
    UI_Controller_App_ -- "Creates Layout Manager via layout.NewManager(); registers each view with manager using lm.Add(view, location)" --> Layout_Manager
    UI_Controller_App_ -- "Generates bindings with key.GenerateBindings(); attaches bindings to gocui.Gui" --> Key_Binding_Dispatcher
    UI_Controller_App_ -- "Instantiates LayerSetState view‑model; exposes it for controller read/write selected layer" --> LayerSetState_View_Model
    UI_Controller_App_ -- "Instantiates FileTree view‑model; exposes it for controller updates" --> FileTree_View_Model
    UI_Controller_App_ -- "Provides view‑model reference to view; view registers as observer" --> FileTree_View
    UI_Controller_App_ -- "Provides LayerSetState view‑model to view; view registers for notifications" --> LayerDetails_View
    Key_Binding_Dispatcher -- "Binding OnAction calls controller methods (ToggleView, NextPane); controller updates state" --> UI_Controller_App_
    LayerSetState_View_Model -- "Notifies on layer change; view re‑renders layer statistics" --> LayerDetails_View
    FileTree_View_Model -- "Notifies on tree changes (expand/collapse/filter); view redraws pane" --> FileTree_View
    FileTree_View -- "User cursor movement triggers view‑model Select; view‑model updates selected node" --> FileTree_View_Model
    Layout_Manager -- "Computes geometry for each view; calls view.Layout to set screen rectangle" --> FileTree_View
    Layout_Manager -- "Computes geometry for each view; calls view.Layout to set screen rectangle" --> LayerDetails_View
    FileTree_View -- "Views report RequestedSize hints; layout manager allocates space accordingly" --> Layout_Manager
    LayerDetails_View -- "Views report RequestedSize hints; layout manager allocates space accordingly" --> Layout_Manager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Dive TUI subsystem (cmd/dive/cli/internal/ui/v1) implements a classic MVC architecture wrapped in a terminal‑UI framework (gocui). An event‑driven UI façade (V1UI) listens for the ExploreAnalysis event and launches the UI controller (app.Run). The controller creates the layout manager, registers key‑binding dispatchers, and builds the view‑models (LayerSetState, FileTree). Views (LayerDetails, FileTree, status/footer panes) are attached to their respective view‑models and to the layout manager, which arranges them into header, column, and footer zones. User keystrokes are translated by the key‑binding dispatcher into high‑level controller actions, which mutate view‑model state; the view‑models then push change notifications back to the views, causing a re‑render. The layout manager recomputes geometry on terminal resize, ensuring a responsive split‑pane UI. This tightly‑coupled yet modular arrangement isolates UI rendering, input handling, and state management, making the subsystem easy to reason about, test, and extend.

### UI Façade (V1UI)
UI façade that receives the ExploreAnalysis event and initiates the UI controller.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1.V1UI`</a>


### UI Controller (App)
Entry point that creates the gocui GUI, controller, layout manager, and registers key bindings.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/app/app.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/app`</a>


### Layout Manager
Arranges views into zones and computes geometry for each pane.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/layout/manager.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/layout.Manager`</a>


### Key‑Binding Dispatcher
Generates key bindings from configuration and attaches them to the gocui GUI.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/key/binding.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/key.Binding`</a>
- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/key/config.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/key.Config`</a>


### LayerSetState View‑Model
Observable model representing the currently selected layer and its state.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/viewmodel/layer_set_state.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/viewmodel.LayerSetState`</a>


### FileTree View‑Model
Observable model for the file‑tree data, selection, and filtering.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/viewmodel/filetree.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/viewmodel.FileTree`</a>


### FileTree View
UI view that renders the file‑tree pane and observes the FileTree view‑model.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/view/filetree.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/view.FileTree`</a>


### LayerDetails View
UI view that displays detailed information about the selected layer, observing the LayerSetState view‑model.


**Related Classes/Methods**:

- <a href="https://github.com/wagoodman/dive/blob/main/cmd/dive/cli/internal/ui/v1/view/layer_details.go" target="_blank" rel="noopener noreferrer">`github.com/wagoodman/dive/cmd/dive/cli/internal/ui/v1/view.LayerDetails`</a>


### Unclassified
Component for all unclassified files and utility functions (Utility functions/External Libraries/Dependencies)


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)