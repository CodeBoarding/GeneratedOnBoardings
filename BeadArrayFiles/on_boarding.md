```mermaid
graph LR
    BeadArrayUtility["BeadArrayUtility"]
    BeadPoolManifest_Parser["BeadPoolManifest Parser"]
    ClusterFile_Parser["ClusterFile Parser"]
    GenotypeCalls_Processor["GenotypeCalls Processor"]
    LocusAggregate_Manager["LocusAggregate Manager"]
    BeadArrayUtility -- "provides data reading utilities for" --> BeadPoolManifest_Parser
    BeadArrayUtility -- "provides data reading utilities for" --> ClusterFile_Parser
    BeadArrayUtility -- "provides data reading utilities for" --> GenotypeCalls_Processor
    BeadPoolManifest_Parser -- "parses data for" --> GenotypeCalls_Processor
    ClusterFile_Parser -- "parses data for" --> GenotypeCalls_Processor
    GenotypeCalls_Processor -- "processes data from" --> LocusAggregate_Manager
    LocusAggregate_Manager -- "aggregates data using" --> BeadPoolManifest_Parser
    click BeadArrayUtility href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//BeadArrayFiles/BeadArrayUtility.md" "Details"
    click BeadPoolManifest_Parser href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//BeadArrayFiles/BeadPoolManifest Parser.md" "Details"
    click ClusterFile_Parser href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//BeadArrayFiles/ClusterFile Parser.md" "Details"
    click GenotypeCalls_Processor href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//BeadArrayFiles/GenotypeCalls Processor.md" "Details"
    click LocusAggregate_Manager href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main//BeadArrayFiles/LocusAggregate Manager.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

The `BeadArrayFiles` project is designed to parse and process various binary file formats related to bead array data, such as Bead Pool Manifest (BPM) files, Cluster files, and Genotype Call (GTC) files. It provides low-level utilities for reading binary data, specialized parsers for different file types, and a central component for managing and retrieving genotype call information. Additionally, it includes a component for aggregating locus data across multiple samples.

### BeadArrayUtility
This component provides fundamental utility functions for reading various data types (byte, int, string, float, ushort) from binary files and performing basic operations like DNA complement. It acts as a low-level data access layer for other components that parse specific file formats.


**Related Classes/Methods**:

- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L82-L109" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.read_string` (82:109)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L70-L80" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.read_byte` (70:80)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L46-L56" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.read_int` (46:56)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L58-L68" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.read_float` (58:68)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L5-L20" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.complement` (5:20)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadArrayUtility.py#L34-L44" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadArrayUtility.read_ushort` (34:44)</a>


### BeadPoolManifest Parser
This component is responsible for parsing Bead Pool Manifest (BPM) files. It includes classes for the manifest itself and individual locus entries, handling different versions of the locus entry format. It heavily relies on BeadArrayUtility for reading data.


**Related Classes/Methods**:

- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L21-L44" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.BeadPoolManifest.__init__` (21:44)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L46-L129" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.BeadPoolManifest.__parse_file` (46:129)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L236-L368" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry` (236:368)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L254-L274" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry.__init__` (254:274)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L276-L295" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry.__parse_file` (276:295)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L297-L342" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry.__parse_locus_version_6` (297:342)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L344-L355" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry.__parse_locus_version_7` (344:355)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L357-L368" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.LocusEntry.__parse_locus_version_8` (357:368)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L161-L182" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.SourceStrand.from_string` (161:182)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/BeadPoolManifest.py#L214-L234" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.BeadPoolManifest.RefStrand.from_string` (214:234)</a>


### ClusterFile Parser
This component handles the parsing of Cluster files, which contain information about genotype clusters. It includes classes for the cluster file itself, individual cluster records, and cluster scores, utilizing BeadArrayUtility for data extraction.


**Related Classes/Methods**:

- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L82-L146" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterFile.read_cluster_file` (82:146)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L2-L146" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterFile` (2:146)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L64-L79" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterFile.read_array` (64:79)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L38-L46" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterFile.add_record` (38:46)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L184-L237" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterRecord.read_record` (184:237)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L148-L237" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterRecord` (148:237)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L287-L317" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterStats` (287:317)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L270-L284" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterScore.read_record` (270:284)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/ClusterFile.py#L240-L284" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.ClusterFile.ClusterScore` (240:284)</a>


### GenotypeCalls Processor
This is a central component for processing and retrieving genotype call data from GTC files. It provides methods to access various attributes like sample names, intensities, genotypes, and quality scores. It also includes helper classes for normalization transforms and scanner data. It heavily relies on BeadArrayUtility for low-level data reading and interacts with BeadPoolManifest Parser and ClusterFile Parser to get related file information.


**Related Classes/Methods**:

- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L62-L621" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls` (62:621)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L103-L136" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.__init__` (103:136)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L590-L621" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.is_write_complete` (590:621)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L155-L182" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.__get_generic_array` (155:182)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L184-L207" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.__get_generic_array_numpy` (184:207)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L230-L235" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_sample_name` (230:235)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L138-L153" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.__get_generic` (138:153)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L237-L242" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_slide_identifier` (237:242)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L244-L249" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_sample_plate` (244:249)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L251-L256" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_sample_well` (251:256)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L258-L263" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_cluster_file` (258:263)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L265-L270" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_snp_manifest` (265:270)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L272-L279" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_imaging_date` (272:279)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L281-L288" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_autocall_date` (281:288)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L290-L297" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_autocall_version` (290:297)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L299-L304" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_genotypes` (299:304)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L306-L346" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_base_calls_generic` (306:346)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L348-L361" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_base_calls_plus_strand` (348:361)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L363-L375" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_base_calls_forward_strand` (363:375)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L377-L408" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_base_calls` (377:408)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L223-L228" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_ploidy_type` (223:228)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L410-L415" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_genotype_scores` (410:415)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L417-L422" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_scanner_data` (417:422)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L424-L429" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_control_x_intensities` (424:429)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L431-L436" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_control_y_intensities` (431:436)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L438-L443" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_raw_x_intensities` (438:443)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L445-L450" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_raw_y_intensities` (445:450)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L452-L457" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_call_rate` (452:457)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L459-L465" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_gender` (459:465)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L467-L472" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_logr_dev` (467:472)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L474-L479" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_gc10` (474:479)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L481-L486" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_gc50` (481:486)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L488-L495" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_num_calls` (488:495)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L497-L504" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_num_no_calls` (497:504)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L506-L513" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_num_intensity_only` (506:513)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L515-L523" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_ballele_freqs` (515:523)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L525-L533" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_logr_ratios` (525:533)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L535-L550" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_percentiles_x` (535:550)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L552-L567" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_percentiles_y` (552:567)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L569-L581" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_normalized_intensities` (569:581)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L583-L588" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.GenotypeCalls.get_normalization_transforms` (583:588)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L640-L650" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.NormalizationTransform.read_normalization_transform` (640:650)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L624-L697" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.NormalizationTransform` (624:697)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L733-L748" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.ScannerData.read_scanner_data` (733:748)</a>
- <a href="https://github.com/Illumina/BeadArrayFiles/blob/master/module/GenotypeCalls.py#L700-L748" target="_blank" rel="noopener noreferrer">`BeadArrayFiles.module.GenotypeCalls.ScannerData` (700:748)</a>


### LocusAggregate Manager
This component is responsible for aggregating locus data, potentially from multiple samples. It includes a loader and a generator for locus aggregates, facilitating the grouping and processing of genetic loci.


**Related Classes/Methods**:

- `BeadArrayFiles.module.LocusAggregate.Loader.__call__` (full file reference)
- `BeadArrayFiles.module.LocusAggregate.LocusAggregate` (full file reference)
- `BeadArrayFiles.module.LocusAggregate.GenerateLocusAggregate.__call__` (full file reference)
- `BeadArrayFiles.module.LocusAggregate.LocusAggregate.load_buffer` (full file reference)
- `BeadArrayFiles.module.LocusAggregate.LocusAggregate.aggregate_samples` (full file reference)
- `BeadArrayFiles.module.LocusAggregate.LocusAggregate.group_loci` (full file reference)




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)