```mermaid
graph LR
    AliceLG_globals["AliceLG.globals"]
    AliceLG_preferences["AliceLG.preferences"]
    Lightfield_Renderer["Lightfield Renderer"]
    Viewport_Renderer["Viewport Renderer"]
    Blender_Operators["Blender Operators"]
    Lightfield_Renderer -- "reads from" --> AliceLG_globals
    Viewport_Renderer -- "reads from" --> AliceLG_globals
    Blender_Operators -- "reads from" --> AliceLG_globals
    Lightfield_Renderer -- "reads from" --> AliceLG_preferences
    Viewport_Renderer -- "reads from" --> AliceLG_preferences
    Blender_Operators -- "reads from" --> AliceLG_preferences
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### AliceLG.globals
Manages and provides access to global application-wide state variables and data that are not user-configurable but are essential for the add-on's operation. This includes runtime flags, temporary data, or shared resources.


**Related Classes/Methods**:

- <a href="https://github.com/regcs/AliceLG/blob/master/globals.py#L1-L100" target="_blank" rel="noopener noreferrer">`AliceLG.globals` (1:100)</a>


### AliceLG.preferences
Handles the storage, retrieval, and management of user-defined preferences and configurable settings for the add-on. This includes settings persisted across Blender sessions, allowing users to customize default behaviors, paths, or display options.


**Related Classes/Methods**:

- `AliceLG.preferences`


### Lightfield Renderer
Component responsible for rendering lightfields, utilizing global state and user preferences.


**Related Classes/Methods**:

- <a href="https://github.com/regcs/AliceLG/blob/master/lightfield_render.py" target="_blank" rel="noopener noreferrer">`AliceLG.lightfield_render`</a>


### Viewport Renderer
Component responsible for rendering in the viewport, utilizing global state and user preferences.


**Related Classes/Methods**:

- `AliceLG.lightfield_viewport`


### Blender Operators
Components representing Blender operators, utilizing global state and user preferences to adjust their behavior.


**Related Classes/Methods**:

- <a href="https://github.com/regcs/AliceLG/blob/master/lightfield_render.py#L1317-L1918" target="_blank" rel="noopener noreferrer">`AliceLG.lightfield_render.LOOKINGGLASS_OT_render_quilt` (1317:1918)</a>
- <a href="https://github.com/regcs/AliceLG/blob/master/lightfield_viewport.py#L291-L958" target="_blank" rel="noopener noreferrer">`AliceLG.lightfield_viewport.LOOKINGGLASS_OT_render_viewport` (291:958)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)