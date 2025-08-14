```mermaid
graph LR
    ResNet31["ResNet31"]
    FPN["FPN"]
    CTCHead["CTCHead"]
    RecPostProcess["RecPostProcess"]
    ResNet31 -- "passes feature maps to" --> FPN
    FPN -- "feeds enhanced features to" --> CTCHead
    CTCHead -- "outputs character probabilities to" --> RecPostProcess
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Text Recognition Pipeline` subsystem is responsible for transcribing characters within detected text regions into readable text strings. It forms a crucial part of the overall OCR process, taking feature maps from upstream components (e.g., a text detection module) and producing recognized text.

### ResNet31
Acts as the primary feature extractor within the recognition pipeline. It processes the input image or text region to generate a hierarchical set of feature maps, capturing various levels of visual information crucial for text recognition. This component aligns with the "Core Inference Engine" pattern by performing the initial, fundamental feature extraction.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PaddleOCR/blob/main/ppocr/modeling/backbones/rec_resnet_31.py#L101-L318" target="_blank" rel="noopener noreferrer">`ResNet31`:101-318</a>


### FPN
Aggregates and fuses feature maps from different layers of the `ResNet31` backbone. This process creates a more robust and context-rich feature representation by combining high-level semantic information with low-level detailed features, which is vital for accurate text recognition across varying text scales. It enhances the features for subsequent recognition.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PaddleOCR/blob/main/benchmark/PaddleOCR_DBNet/models/neck/FPN.py#L11-L75" target="_blank" rel="noopener noreferrer">`FPN`:11-75</a>


### CTCHead
Translates the aggregated feature map from the `FPN` into character probability distributions. It typically employs a Connectionist Temporal Classification (CTC) loss function, which is well-suited for sequence recognition tasks like text recognition, handling variable-length outputs without explicit alignment. This component represents the core prediction mechanism.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PaddleOCR/blob/main/ppocr/modeling/heads/rec_ctc_head.py#L35-L92" target="_blank" rel="noopener noreferrer">`CTCHead`:35-92</a>


### RecPostProcess
Decodes the raw character probability outputs from the `CTCHead` into readable text strings. This involves operations such as CTC decoding (removing blank tokens and merging repeated characters), converting numerical tokens back to characters, and potentially applying text normalization rules. This component acts as an "Output Handler" for the recognition pipeline.


**Related Classes/Methods**:

- <a href="https://github.com/PaddlePaddle/PaddleOCR/blob/main/ppocr/postprocess/rec_postprocess.py" target="_blank" rel="noopener noreferrer">`RecPostProcess`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)