```mermaid
graph LR
    ParquetGenotypeStorage["ParquetGenotypeStorage"]
    GenotypeStorage["GenotypeStorage"]
    ParquetLoaderVariants["ParquetLoaderVariants"]
    Schema2DatasetLayout["Schema2DatasetLayout"]
    File_System_Utilities["File System Utilities"]
    ReferenceGenome["ReferenceGenome"]
    GeneModels["GeneModels"]
    ParquetGenotypeStorage -- "implements" --> GenotypeStorage
    ParquetGenotypeStorage -- "uses" --> ParquetLoaderVariants
    ParquetGenotypeStorage -- "uses" --> Schema2DatasetLayout
    ParquetGenotypeStorage -- "creates" --> Schema2DatasetLayout
    ParquetGenotypeStorage -- "uses" --> File_System_Utilities
    ParquetLoaderVariants -- "uses" --> ReferenceGenome
    ParquetLoaderVariants -- "uses" --> GeneModels
    click ParquetGenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/ParquetGenotypeStorage.md" "Details"
    click GenotypeStorage href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/gpf/GenotypeStorage.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Bioinformatics Data Platform / Genomic Data Warehouse

### ParquetGenotypeStorage [[Expand]](./ParquetGenotypeStorage.md)
Manages and interacts with genotype data stored in Parquet files, implementing the GenotypeStorage interface.


**Related Classes/Methods**: _None_

### GenotypeStorage [[Expand]](./GenotypeStorage.md)
Interface for genotype storage solutions.


**Related Classes/Methods**: _None_

### ParquetLoaderVariants
Performs data loading and querying from Parquet files for genomic variant data.


**Related Classes/Methods**: _None_

### Schema2DatasetLayout
Ensures imported data conforms to a standardized Parquet schema and directory structure.


**Related Classes/Methods**: _None_

### File System Utilities
Provides basic file system operations for data management, such as copying files.


**Related Classes/Methods**: _None_

### ReferenceGenome
Represents a reference genome used for interpreting genomic data.


**Related Classes/Methods**: _None_

### GeneModels
Represents gene models used for interpreting genomic data.


**Related Classes/Methods**: _None_



### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)