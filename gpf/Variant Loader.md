## Variant Loader Component Overview

The Variant Loader component is responsible for loading variant data from different file formats (VCF, DAE) and transforming them into a common internal representation. It uses specific loaders for each format and interacts with the GRR to access reference genomes and pedigree information.

```mermaid
flowchart LR
    subgraph Variant Loading Subsystem
    VcfLoader--Loads data from-->VCF Files
    SingleVcfLoader--Iterates through-->VcfLoader
    VcfFamiliesGenotypes--Builds from-->SingleVcfLoader
    DenovoLoader--Loads data from-->DAE Denovo Files
    DenovoFamiliesGenotypes--Represents-->DenovoLoader
    DaeTransmittedLoader--Loads data from-->DAE Transmitted Files
    DaeTransmittedFamiliesGenotypes--Represents-->DaeTransmittedLoader
    end

    VCF Files--Provides data-->VcfLoader
    DAE Denovo Files--Provides data-->DenovoLoader
    DAE Transmitted Files--Provides data-->DaeTransmittedLoader

    Variant Loading Subsystem--Uses-->GenomicResource
    GenomicResource--Provides-->ReferenceGenome
    GenomicResource--Provides-->FamiliesData


    style Variant Loading Subsystem fill:#f9f,stroke:#333,stroke-width:2px
```

### Component Details

#### 1. VcfLoader

*   **Description**: Orchestrates the loading of variant data from VCF files, potentially handling multiple files and pedigree information. It initializes `SingleVcfLoader` instances for individual files or batches.
*   **Functionality**: Collects VCF filenames, filters file batches based on regions, initializes `SingleVcfLoader` instances, and handles pedigree intersection or union.
*   **Interaction**: Receives VCF files and regions as input. Creates and uses `SingleVcfLoader` instances. Interacts with `FamiliesData` and `ReferenceGenome` through `SingleVcfLoader`.
*   **Relevant source files**: `dae.variants_loaders.vcf.loader.VcfLoader`

#### 2. SingleVcfLoader

*   **Description**: Loads variant data from a single VCF file, building VCF readers and matching pedigree to samples. It iterates through variants to create summary and family variants.
*   **Functionality**: Initializes VCF readers, matches pedigree to samples, builds VCF iterators, and yields summary and family variants.
*   **Interaction**: Receives families data, VCF files, genome, and regions as input. Uses `pysam` to read VCF files. Creates and uses `VcfFamiliesGenotypes`. Produces `SummaryVariant` and `FamilyVariant`.
*   **Relevant source files**: `dae.variants_loaders.vcf.loader.SingleVcfLoader`

#### 3. VcfFamiliesGenotypes

*   **Description**: Builds family genotypes from VCF variant data, collecting family genotypes and handling missing values.
*   **Functionality**: Collects family genotypes, handles missing values, and iterates through families to yield family, genotype, and best state information.
*   **Interaction**: Receives a `SingleVcfLoader` instance and all genotypes. Iterates through families and yields family genotype information.
*   **Relevant source files**: `dae.variants_loaders.vcf.loader.VcfFamiliesGenotypes`

#### 4. DenovoLoader

*   **Description**: Loads de novo variants from a file, handling different file formats and extracting variant information.
*   **Functionality**: Loads data from a denovo file, parses the file, and produces family variants.
*   **Interaction**: Receives families data, a denovo filename, genome, and regions as input. Produces `SummaryVariant` and `FamilyVariant`.
*   **Relevant source files**: `dae.variants_loaders.dae.loader.DenovoLoader`

#### 5. DenovoFamiliesGenotypes

*   **Description**: Represents family genotypes for de novo variants, storing family, genotype, and best state information.
*   **Functionality**: Holds family, genotype, and best state information and provides an iterator to yield this information.
*   **Interaction**: Receives family, genotype, and best state information. Used by `DenovoLoader` to represent family genotype information.
*   **Relevant source files**: `dae.variants_loaders.dae.loader.DenovoFamiliesGenotypes`

#### 6. DaeTransmittedLoader

*   **Description**: Loads variants from DAE transmitted format, handling summary and 'toomany' files.
*   **Functionality**: Loads data from DAE summary and 'toomany' files, explodes family data, and produces family variants.
*   **Interaction**: Receives families data, a summary filename, genome, and regions as input. Produces `SummaryVariant` and `FamilyVariant`.
*   **Relevant source files**: `dae.variants_loaders.dae.loader.DaeTransmittedLoader`

#### 7. DaeTransmittedFamiliesGenotypes

*   **Description**: Represents family genotypes for DAE transmitted variants, storing families and family data.
*   **Functionality**: Holds families and family data, and iterates through families to yield family, best state, and read counts information.
*   **Interaction**: Receives families data and family data. Used by `DaeTransmittedLoader` to represent family genotype information.
*   **Relevant source files**: `dae.variants_loaders.dae.loader.DaeTransmittedFamiliesGenotypes`
