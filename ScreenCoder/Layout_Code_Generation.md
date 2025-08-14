```mermaid
graph LR
    UI_Element_Detector["UI Element Detector"]
    HTML_Generator["HTML Generator"]
    UI_Element_Detector -- "passes detected element data to" --> HTML_Generator
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### UI Element Detector
Processes the input screenshot to identify and classify distinct UI elements. Its core responsibility is to detect components like text, images, and containers, and to output their precise locations (bounding boxes) and classifications. This forms the foundational data for code generation.


**Related Classes/Methods**:

- `UIED.detection.image_box_detection.ImageDetection`


### HTML Generator
Takes the structured data of detected UI elements (including their bounding boxes and classifications) from the UI Element Detector. Its responsibility is to translate this data into a complete HTML file, using the bounding box information to position elements with CSS and the classification to select appropriate HTML tags.


**Related Classes/Methods**:

- `UIED.generation.html_generator.HTMLGenerator`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)