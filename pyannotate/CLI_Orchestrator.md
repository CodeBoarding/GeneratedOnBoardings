```mermaid
graph LR
    CLI_Orchestrator["CLI Orchestrator"]
    Code_Modifier["Code Modifier"]
    Annotation_Outputter["Annotation Outputter"]
    CLI_Orchestrator -- "Delegates the task of applying annotations to source files." --> Code_Modifier
    CLI_Orchestrator -- "Delegates the task of dumping collected annotations to a file." --> Annotation_Outputter
    click CLI_Orchestrator href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pyannotate/CLI_Orchestrator.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `CLI Orchestrator` operates within the `pyannotate_tools.annotations` subsystem, which is responsible for the static code transformation phase of `pyannotate`.

### CLI Orchestrator [[Expand]](./CLI_Orchestrator.md)
The central control point for the `pyannotate_tools.annotations` subsystem. It parses command-line arguments, determines the execution mode (either dumping collected type information or applying static annotations to source files), and orchestrates the flow between the different processing stages of the static code transformation phase.


**Related Classes/Methods**:

- <a href="https://github.com/dropbox/pyannotate/blob/master/pyannotate_tools/annotations/__main__.py#L90-L149" target="_blank" rel="noopener noreferrer">`pyannotate_tools.annotations.__main__.main`:90-149</a>


### Code Modifier
Applies type annotations to source code files based on the collected type information. It leverages the `lib2to3` framework for robust code refactoring, ensuring correct and safe modifications.


**Related Classes/Methods**:

- <a href="https://github.com/dropbox/pyannotate/blob/master/pyannotate_tools/annotations/__main__.py#L51-L62" target="_blank" rel="noopener noreferrer">`pyannotate_tools.annotations.__main__.ModifiedRefactoringTool`:51-62</a>
- <a href="https://github.com/dropbox/pyannotate/blob/master/pyannotate_tools/fixes/fix_annotate_json.py" target="_blank" rel="noopener noreferrer">`pyannotate_tools.fixes.fix_annotate_json`</a>
- <a href="https://github.com/dropbox/pyannotate/blob/master/pyannotate_tools/fixes/fix_annotate.py" target="_blank" rel="noopener noreferrer">`pyannotate_tools.fixes.fix_annotate`</a>


### Annotation Outputter
Writes collected type information to a specified output, typically a JSON file, for persistence, debugging, or as an intermediate artifact for other tools.


**Related Classes/Methods**:

- <a href="https://github.com/dropbox/pyannotate/blob/master/pyannotate_tools/annotations/__main__.py#L65-L87" target="_blank" rel="noopener noreferrer">`pyannotate_tools.annotations.__main__.dump_annotations`:65-87</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)