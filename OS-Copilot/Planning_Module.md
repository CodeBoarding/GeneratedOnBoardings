```mermaid
graph LR
    FridayPlanner["FridayPlanner"]
    BasicPlanner["BasicPlanner"]
    Tool_Integration["Tool Integration"]
    Tool_Graph_Management["Tool Graph Management"]
    FridayPlanner -- "is a strategic alternative to" --> BasicPlanner
    FridayPlanner -- "utilizes" --> Tool_Integration
    BasicPlanner -- "utilizes" --> Tool_Integration
    FridayPlanner -- "internally relies on" --> Tool_Graph_Management
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `planner` subsystem in `oscopilot` is designed to manage and execute complex task plans, primarily through two distinct planning strategies: `FridayPlanner` and `BasicPlanner`. `FridayPlanner` offers advanced capabilities for complex task decomposition, leveraging `Tool Graph Management` to build and resolve dependencies among tools, ensuring a logical and ordered execution flow. In contrast, `BasicPlanner` provides a more streamlined approach for simpler plan adjustments and tool integration. Both planners interact with the `Tool Integration` component, which serves as a common interface for incorporating new tools or steps into an existing plan. This architecture allows for flexible planning strategies, from basic tool addition to sophisticated dependency-aware plan generation, all while maintaining clear component responsibilities and interactions.

### FridayPlanner
Advanced planning engine for complex task decomposition and sophisticated plan revision, handling intricate tool dependencies and ensuring logical execution flow. It builds and manages a tool dependency graph for robust dependency resolution and topological sorting.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:create_tool_graph`</a>
- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:topological_sort`</a>
- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:add_new_tool`</a>


### BasicPlanner
Provides a straightforward and faster mechanism for task replanning and basic plan adjustments, primarily integrating new tools or steps into an existing plan without complex dependency resolution.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/basic_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.basic_planner.BasicPlanner:add_new_tool`</a>


### Tool Integration
Represents the shared mechanism for incorporating new tools or steps into an existing plan, utilized by different planner implementations.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:add_new_tool`</a>
- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/basic_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.basic_planner.BasicPlanner:add_new_tool`</a>


### Tool Graph Management
Encapsulates the logic for building, managing, and resolving dependencies within a tool graph, enabling topological sorting of tools. This functionality is critical for advanced planning.


**Related Classes/Methods**:

- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:create_tool_graph`</a>
- <a href="https://github.com/OS-Copilot/OS-Copilot/blob/main/oscopilot/modules/planner/friday_planner.py" target="_blank" rel="noopener noreferrer">`oscopilot.modules.planner.friday_planner.FridayPlanner:topological_sort`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)