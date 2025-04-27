## Pedigree Loader Overview

This document provides an overview of the Pedigree Loader component, which is responsible for loading and managing pedigree data. The pedigree data represents family relationships and individual attributes, and the loader transforms raw data into a structured format suitable for variant analysis.

### Data Flow Diagram

```mermaid
graph LR
    A["GPFInstance"] -- provides --> B("FamiliesLoader")
    B -- loads --> C("PedigreeReader")
    C -- reads --> D["Pedigree File"] 
    B -- creates --> E("FamiliesData")
    E -- contains --> F("Family")
    F -- contains --> G("Person")


click A href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//GPF Instance.md"
click B href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
click C href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
click D href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
click E href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
click F href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
click G href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf//Pedigree Loader.md"
```
