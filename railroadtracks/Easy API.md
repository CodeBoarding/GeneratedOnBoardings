```mermaid
graph LR
    Project_Core["Project Core"]
    Task_Management["Task Management"]
    Task_Graphing["Task Graphing"]
    Task_Set_Orchestration["Task Set Orchestration"]
    Execution_Strategies["Execution Strategies"]
    Reporting_and_Views["Reporting and Views"]
    Project_Core -- "manages tasks for" --> Task_Management
    Task_Management -- "provides tasks to" --> Task_Graphing
    Task_Management -- "organizes tasks into" --> Task_Set_Orchestration
    Task_Set_Orchestration -- "orchestrates execution using" --> Execution_Strategies
    Reporting_and_Views -- "generates reports from" --> Project_Core
    Reporting_and_Views -- "generates reports from" --> Task_Management
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The Easy API component provides a high-level, simplified interface for users to define, manage, and execute bioinformatics projects and tasks. It abstracts away the complexities of the underlying Persistent Task Graph and Unified Execution Core, offering intuitive classes for tasks, task sets, and project views. This component is the primary user-facing interface for workflow definition and interaction, enabling users to define project environments, manage tasks and their dependencies, orchestrate execution, and generate comprehensive reports.

### Project Core
This component establishes the foundational structure of a bioinformatics project, managing its environment, configuration, and core data entities like assets. It provides the primary interface for users to define and interact with projects, including methods for iterating over project assets and querying tasks based on various criteria.


**Related Classes/Methods**:

- `railroadtracks.src.easy.Project.__init__` (100:104)
- `railroadtracks.src.easy.Project.__str__` (full file reference)
- `railroadtracks.src.easy.Project.get_tasksoftype` (full file reference)
- `railroadtracks.src.easy.Project.get_taskswithactivity` (full file reference)
- `railroadtracks.src.easy.Project.iter_srcassets` (full file reference)
- `railroadtracks.src.easy.Project.iter_targetassets` (full file reference)
- `railroadtracks.src.easy.Environment.__init__` (full file reference)
- `railroadtracks.src.easy.FrozenNamespace` (full file reference)
- `railroadtracks.src.easy.Asset` (full file reference)


### Task Management
This component is dedicated to the definition, manipulation, and querying of individual tasks and logical groupings of tasks (TaskSets). It encapsulates task-specific properties, manages inter-task relationships (parent/child), and facilitates the generation of execution commands.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L97-L105" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.__init__` (97:105)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L68-L91" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.get_steplist_up` (68:91)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L124-L129" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.info` (124:129)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L135-L139" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.dirname` (135:139)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L151-L169" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.unifex_cmd` (151:169)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L171-L176" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.unifex_cmdline` (171:176)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L194-L218" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.parent_tasks` (194:218)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L220-L245" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.primordial_tasks` (220:245)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L247-L269" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.child_tasks` (247:269)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L271-L292" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.all_child_tasks` (271:292)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L295-L307" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.status` (295:307)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L317-L320" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.Task.time_points` (317:320)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L336-L341" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.__init__` (336:341)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L361-L370" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.iter_chunks` (361:370)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L372-L374" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.__contains__` (372:374)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L377-L381" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.__str__` (377:381)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L382-L387" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.add` (382:387)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L388-L393" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.remove` (388:393)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L394-L405" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.union` (394:405)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L406-L411" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.update` (406:411)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L413-L421" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.intersection` (413:421)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L422-L430" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.difference` (422:430)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L431-L435" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.isdisjoint` (431:435)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L436-L440" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.issubset` (436:440)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L441-L445" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.issuperset` (441:445)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L459-L465" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.filter_on_status` (459:465)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasks.py#L466-L476" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasks.TaskSet.filter_on_parent_status` (466:476)</a>


### Task Graphing
This component is responsible for the construction and management of the directed acyclic graph (DAG) that represents task dependencies within a project. It provides functionalities to create graph nodes and traverse the graph to identify predecessor tasks.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/taskgraph.py#L61-L123" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.taskgraph.get_digraph` (61:123)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/taskgraph.py#L127-L129" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.taskgraph.TaskGraph.__init__` (127:129)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/taskgraph.py#L135-L151" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.taskgraph.TaskGraph.predecessor_tasks` (135:151)</a>


### Task Set Orchestration
This component orchestrates the organization and execution flow of task sets. It manages the addition of task sets to a graph structure, ensures the uniqueness of tasks, and generates an ordered list of tasks for execution. It also supports the execution of filtered task sets.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasksetgraph.py#L144-L169" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasksetgraph.TaskSetGraph.execute` (144:169)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasksetgraph.py#L58-L114" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasksetgraph.TaskSetGraph.add_taskset` (58:114)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasksetgraph.py#L116-L121" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasksetgraph.TaskSetGraph.add` (116:121)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/tasksetgraph.py#L124-L131" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.tasksetgraph.TaskSetGraph.execution_list` (124:131)</a>


### Execution Strategies
This component provides various strategies for executing tasks, abstracting the underlying execution mechanism. It includes iterative and multiprocessing approaches, responsible for mapping tasks to appropriate execution processes and updating their status throughout the execution lifecycle.


**Related Classes/Methods**:

- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/execution.py#L98-L122" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.execution.IterativeExecution.map` (98:122)</a>
- <a href="https://github.com/Novartis/railroadtracks/blob/master/src/easy/execution.py#L137-L160" target="_blank" rel="noopener noreferrer">`railroadtracks.src.easy.execution.MultiprocessingExecution.map` (137:160)</a>


### Reporting and Views
This component is responsible for generating user-friendly views and reports that summarize the project's status, activities, results, and storage utilization. It aggregates and presents data from various other components to provide a comprehensive overview.


**Related Classes/Methods**:

- `railroadtracks.src.easy.dict_project_view_activities` (full file reference)
- `railroadtracks.src.easy.dict_project_view_results` (full file reference)
- `railroadtracks.src.easy.dict_assetset_view` (full file reference)
- `railroadtracks.src.easy.str_project_view_storage` (full file reference)
- `railroadtracks.src.easy.str_project_view_activities` (full file reference)
- `railroadtracks.src.easy.str_project_view_results` (full file reference)
- `railroadtracks.src.easy.str_project_view` (full file reference)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)