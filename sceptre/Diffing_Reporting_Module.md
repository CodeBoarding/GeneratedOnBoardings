```mermaid
graph LR
    Stack_Differ["Stack Differ"]
    Diff_Writer["Diff Writer"]
    Stack_Differ -- "produces data for" --> Diff_Writer
    Diff_Writer -- "consumes data from" --> Stack_Differ
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Diffing & Reporting Module is primarily encapsulated within the `sceptre.diffing` package. Its core functionality is provided by the `sceptre.diffing.stack_differ` and `sceptre.diffing.diff_writer` components, which handle the comparison of stack configurations and templates, and the subsequent formatting and presentation of these differences, respectively.

### Stack Differ
This component is the core engine for identifying discrepancies between the local Sceptre stack configuration and template, and their corresponding deployed state in AWS CloudFormation. Its responsibilities include: Generating the local stack template and configuration, retrieving the deployed stack template and configuration from AWS, performing a detailed comparison of parameters, template body, and other stack properties, and handling specific CloudFormation nuances like NoEcho parameters and default values during comparison to ensure accurate diffs.


**Related Classes/Methods**:

- <a href="https://github.com/Sceptre/sceptre/blob/master/sceptre/diffing/stack_differ.py#L1-L9999" target="_blank" rel="noopener noreferrer">`sceptre.diffing.stack_differ`:1-9999</a>


### Diff Writer
This component is responsible for transforming the raw difference data provided by the `Stack Differ` into a human-readable and visually appealing report. Its responsibilities include: Determining the presence and type of differences (configuration, template, or both), applying formatting, styling, and colorization to highlight changes in the output, orchestrating the presentation of the diff, including new stack details, configuration changes, and template changes, and serializing and dumping complex data structures (like stack configurations) into a readable format for display.


**Related Classes/Methods**:

- <a href="https://github.com/Sceptre/sceptre/blob/master/sceptre/diffing/diff_writer.py#L1-L9999" target="_blank" rel="noopener noreferrer">`sceptre.diffing.diff_writer`:1-9999</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)