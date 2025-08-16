```mermaid
graph LR
    Knitting_Pattern_to_SVG_Converter["Knitting Pattern to SVG Converter"]
    Instruction_SVG_Converter["Instruction SVG Converter"]
    Instruction_SVG_Cache["Instruction SVG Cache"]
    SVG_Builder["SVG Builder"]
    AYAB_PNG_Dumper["AYAB PNG Dumper"]
    AYAB_PNG_Builder["AYAB PNG Builder"]
    Pattern_Layout_Engine["Pattern Layout Engine"]
    Knitting_Pattern_to_SVG_Converter -- "utilizes" --> Pattern_Layout_Engine
    Knitting_Pattern_to_SVG_Converter -- "queries" --> Instruction_SVG_Cache
    Knitting_Pattern_to_SVG_Converter -- "uses" --> SVG_Builder
    Instruction_SVG_Cache -- "calls" --> Instruction_SVG_Converter
    AYAB_PNG_Dumper -- "delegates to" --> AYAB_PNG_Builder
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Visual Output Converters subsystem is primarily defined by the knittingpattern.convert package, encompassing modules responsible for transforming the internal knitting pattern data model into visual formats.

### Knitting Pattern to SVG Converter
Orchestrates the conversion of an entire knitting pattern into a complete SVG document. It manages the overall SVG structure, registers individual instruction SVGs as definitions, and places them according to the pattern's layout.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/KnittingPatternToSVG.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.KnittingPatternToSVG`</a>


### Instruction SVG Converter
Converts individual knitting instructions into their specific SVG dictionary representations, handling visual styling and geometric details for each instruction type.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/InstructionToSVG.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.InstructionToSVG`</a>


### Instruction SVG Cache
Caches the SVG representations of individual knitting instructions to optimize performance by avoiding redundant generation.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/InstructionSVGCache.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.InstructionSVGCache`</a>


### SVG Builder
A low-level utility component for programmatically constructing and manipulating SVG elements, such as placing `use` tags, defining symbols, and managing layers within an SVG document.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/SVGBuilder.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.SVGBuilder`</a>


### AYAB PNG Dumper
Converts the knitting pattern into a PNG image format specifically tailored for AYAB knitting machines. This is the high-level entry point for AYAB output.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/AYABPNGDumper.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.AYABPNGDumper`</a>


### AYAB PNG Builder
Handles the low-level pixel manipulation, color conversion, and image construction necessary to generate the AYAB PNG image from the pattern data.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/AYABPNGBuilder.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.AYABPNGBuilder`</a>


### Pattern Layout Engine
Manages the spatial arrangement of knitting instructions on a grid, calculating positions, bounding boxes, and handling connections. While a separate component, it is critical for the visual output process by providing spatial information.


**Related Classes/Methods**:

- <a href="https://github.com/fossasia/knittingpattern/blob/master/knittingpattern/convert/Layout.py" target="_blank" rel="noopener noreferrer">`knittingpattern.convert.Layout`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)