```mermaid
graph LR
    Whisper_Model_Architecture["Whisper Model Architecture"]
    Tokenizer["Tokenizer"]
    Tokenizer -- "Provides Tokens" --> Whisper_Model_Architecture
    Whisper_Model_Architecture -- "Provides Logits for Decoding" --> Tokenizer
    click Tokenizer href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/whisper/Tokenizer.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

One paragraph explaining the functionality which is represented by this graph. What the main flow is and what is its purpose.

### Whisper Model Architecture
A composite component representing the complete encoder-decoder transformer model. It includes the audio encoder, which processes spectrograms, and the text decoder, which generates token sequences. The `Whisper` class acts as the primary facade, orchestrating the interactions between the internal modules like attention blocks and feed-forward networks.


**Related Classes/Methods**:

- `whisper.model`


### Tokenizer [[Expand]](./Tokenizer.md)
A specialized component responsible for converting text into a sequence of integer tokens and vice-versa. It encapsulates the vocabulary and the specific encoding rules (based on `tiktoken`) that the `Whisper Model Architecture` was trained on, including the management of special tokens for timestamps, languages, and tasks.


**Related Classes/Methods**:

- `whisper.tokenizer`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)