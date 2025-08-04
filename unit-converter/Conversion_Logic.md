```mermaid
graph LR
    Unit_Definitions["Unit Definitions"]
    Unit_Registry["Unit Registry"]
    Conversion_Logic["Conversion Logic"]
    UnitConverter["UnitConverter"]
    Extensibility_Mechanism["Extensibility Mechanism"]
    Unit_Definitions -- "provides data to" --> Unit_Registry
    Unit_Definitions -- "supplies properties to" --> Conversion_Logic
    Unit_Registry -- "stores and manages" --> Unit_Definitions
    Unit_Registry -- "serves as source for" --> UnitConverter
    UnitConverter -- "invokes" --> Conversion_Logic
    Conversion_Logic -- "utilizes properties from" --> Unit_Definitions
    UnitConverter -- "queries" --> Unit_Registry
    Extensibility_Mechanism -- "facilitates registration into" --> Unit_Registry
    Extensibility_Mechanism -- "defines contract for" --> Conversion_Logic
    click Conversion_Logic href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/unit-converter/Conversion_Logic.md" "Details"
    click Extensibility_Mechanism href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/unit-converter/Extensibility_Mechanism.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The UnitConverter project is designed as a modular utility library, emphasizing clear interfaces and extensibility. The core subsystem focuses on accurate unit conversions, leveraging Object-Oriented Design principles, particularly the Strategy and Registry patterns.

### Unit Definitions
This component is responsible for formally defining all supported units. It includes their properties (e.g., name, symbol, dimension), relationships to base units, and any necessary conversion factors or offsets. It serves as the foundational data layer for the conversion process.


**Related Classes/Methods**:

- `UnitDefinition` (1:1)


### Unit Registry
Acts as a central repository for all Unit Definitions and their associated conversion rules. It provides efficient lookup mechanisms to retrieve unit information and identify potential conversion paths between different units. This component embodies the Registry Pattern.


**Related Classes/Methods**:

- `UnitRegistry` (1:1)


### Conversion Logic [[Expand]](./Conversion_Logic.md)
Encapsulates the specific algorithms and mathematical rules required to convert values between different units. This component provides various strategies for conversion (e.g., linear transformations, offset-based conversions), applying the Strategy Pattern for modularity and extensibility.


**Related Classes/Methods**:

- `BinaryCalculator` (1:1)


### UnitConverter
This is the primary public-facing component of the library, serving as the orchestrator for all conversion operations. It takes user input (value, source unit, target unit), consults the Unit Registry to validate units and find conversion paths, and then delegates the actual calculation to the appropriate Conversion Logic strategy.


**Related Classes/Methods**:

- `UnitConverter` (1:1)


### Extensibility Mechanism [[Expand]](./Extensibility_Mechanism.md)
This component provides the architectural hooks (e.g., interfaces, abstract classes, registration methods) that allow developers to extend the library's capabilities. This includes adding new custom units, defining new conversion rules, or implementing alternative conversion strategies without altering the core codebase.


**Related Classes/Methods**:

- `UnitInterface` (1:1)
- `ConversionStrategyInterface` (1:1)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)