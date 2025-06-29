```mermaid
graph LR
    Base_Generative_Model_Interface["Base Generative Model Interface"]
    Seq2Seq_Model_Orchestrator["Seq2Seq Model Orchestrator"]
    Seq2Seq_Encoder["Seq2Seq Encoder"]
    Seq2Seq_Decoder_with_Attention["Seq2Seq Decoder with Attention"]
    Transformer_Encoder_Decoder_Orchestrator["Transformer Encoder-Decoder Orchestrator"]
    Transformer_Encoder_Stack["Transformer Encoder Stack"]
    Transformer_Decoder_Stack["Transformer Decoder Stack"]
    Multi_Headed_Attention_Module["Multi-Headed Attention Module"]
    Positional_Encoding_Module["Positional Encoding Module"]
    Base_Generative_Model_Interface -- "implements" --> Seq2Seq_Model_Orchestrator
    Seq2Seq_Model_Orchestrator -- "uses" --> Seq2Seq_Encoder
    Seq2Seq_Model_Orchestrator -- "uses" --> Seq2Seq_Decoder_with_Attention
    Transformer_Encoder_Decoder_Orchestrator -- "uses" --> Transformer_Encoder_Stack
    Transformer_Encoder_Decoder_Orchestrator -- "uses" --> Transformer_Decoder_Stack
    Transformer_Encoder_Stack -- "uses" --> Multi_Headed_Attention_Module
    Transformer_Encoder_Stack -- "uses" --> Positional_Encoding_Module
    Transformer_Decoder_Stack -- "uses" --> Multi_Headed_Attention_Module
    Transformer_Decoder_Stack -- "uses" --> Positional_Encoding_Module
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The Generative Models subsystem implements core neural network architectures for molecular generation, including Seq2Seq and Transformer models, providing foundational building blocks for creating novel molecular structures.

### Base Generative Model Interface
Provides a standardized interface for all generative models, abstracting common functionalities such as model instantiation, loading, saving, and performing molecular generation (inference). This promotes reusability and consistency across different model architectures.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/seq2seq/model.py#L9-L192" target="_blank" rel="noopener noreferrer">`models.seq2seq.model.Model` (9:192)</a>


### Seq2Seq Model Orchestrator
Integrates the Seq2Seq Encoder and Decoder components to form a complete sequence-to-sequence neural network capable of generating molecular sequences.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/seq2seq/seq2seq.py#L268-L282" target="_blank" rel="noopener noreferrer">`models.seq2seq.seq2seq.Seq2Seq` (268:282)</a>


### Seq2Seq Encoder
The recurrent neural network component responsible for processing the input molecular sequence and encoding it into a fixed-size context vector, capturing its essential features.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/seq2seq/seq2seq.py#L11-L136" target="_blank" rel="noopener noreferrer">`models.seq2seq.seq2seq.EncoderRNN` (11:136)</a>


### Seq2Seq Decoder with Attention
The recurrent neural network component that generates the output molecular sequence token by token, utilizing the encoded context vector and an attention mechanism to dynamically focus on relevant parts of the input during generation.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/seq2seq/seq2seq.py#L193-L265" target="_blank" rel="noopener noreferrer">`models.seq2seq.seq2seq.LuongAttnDecoderRNN` (193:265)</a>
- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/seq2seq/seq2seq.py#L139-L190" target="_blank" rel="noopener noreferrer">`models.seq2seq.seq2seq.Attn` (139:190)</a>


### Transformer Encoder-Decoder Orchestrator
The top-level structure of the Transformer model, coordinating the interaction between the Transformer Encoder Stack and Transformer Decoder Stack to perform sequence-to-sequence molecular generation.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/encode_decode/model.py#L14-L72" target="_blank" rel="noopener noreferrer">`models.transformer.encode_decode.model.EncoderDecoder` (14:72)</a>


### Transformer Encoder Stack
The component of the Transformer model responsible for processing the input sequence, consisting of multiple identical encoder layers that learn rich, contextualized representations.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/encode_decode/encoder.py#L6-L19" target="_blank" rel="noopener noreferrer">`models.transformer.encode_decode.encoder.Encoder` (6:19)</a>
- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/encode_decode/encoder_layer.py#L6-L19" target="_blank" rel="noopener noreferrer">`models.transformer.encode_decode.encoder_layer.EncoderLayer` (6:19)</a>


### Transformer Decoder Stack
The component of the Transformer model responsible for generating the output sequence, composed of multiple identical decoder layers that leverage both self-attention and encoder-decoder attention.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/encode_decode/decoder.py#L6-L22" target="_blank" rel="noopener noreferrer">`models.transformer.encode_decode.decoder.Decoder` (6:22)</a>
- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/encode_decode/decoder_layer.py#L5-L26" target="_blank" rel="noopener noreferrer">`models.transformer.encode_decode.decoder_layer.DecoderLayer` (5:26)</a>


### Multi-Headed Attention Module
A fundamental building block within Transformer models that allows the model to jointly attend to information from different representation subspaces at different positions in the sequence.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/module/multi_headed_attention.py#L22-L54" target="_blank" rel="noopener noreferrer">`models.transformer.module.multi_headed_attention.MultiHeadedAttention` (22:54)</a>


### Positional Encoding Module
Injects information about the relative or absolute position of tokens into the input embeddings, as Transformer models inherently lack a mechanism to process sequence order.


**Related Classes/Methods**:

- <a href="https://github.com/MolecularAI/deep-molecular-optimization/blob/main/models/transformer/module/positional_encoding.py#L6-L26" target="_blank" rel="noopener noreferrer">`models.transformer.module.positional_encoding.PositionalEncoding` (6:26)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)