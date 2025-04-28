## GPF Instance Core Overview
The `GPFInstance` and `WGPFInstance` components are central to the GPF system, managing access to datasets, genomic resources, and configurations. `GPFInstance` provides core functionalities, while `WGPFInstance` extends it with web-specific features.

```mermaid
flowchart LR
    subgraph GPFInstanceCore [GPF Instance Core]
        GPFInstance(GPFInstance) -- uses --> GPFConfigParser(GPFConfigParser)
        GPFInstance -- uses --> GenomicResourceRepository(GenomicResourceRepository)
        GPFInstance -- uses --> ReferenceGenome(ReferenceGenome)
        GPFInstance -- uses --> GeneModels(GeneModels)
        GPFInstance -- calls --> Dataset(Dataset)
        GPFInstance -- calls --> DatasetHierarchy(DatasetHierarchy)
        WGPFInstance(WGPFInstance) -- inherits --> GPFInstance
    end
    subgraph Annotation
        ReannotateInstanceTool(ReannotateInstanceTool)
  end
    GPFInstance -- calls --> ReannotateInstanceTool
