# Unlocking the Translator's Code - Machine Translation using RetNet
This project was part of my finals project in CS 583 - Deep Learning at Stevens Institute of Technology. It uses a novel decoder model called RetNet from the [torchscale](https://github.com/microsoft/torchscale) library from Microsoft. It uses multi-scale retention as opposed to multi-head attention commonly used in transformer models. By using the retentive network, it allows for transformer like performance with better language modelling, lower memory consumption, higher throughput, and lower latency. 

The model was trained on IWSLT 2017 dataset of English to French sentences (available on [huggingface](https://huggingface.co/datasets/iwslt2017)). The dataset description is as follows:

| | Number of examples |
| --- | --- |
| Train | 232,825 |
| Validation | 890 |
| Test | 8,597 |

Separate encoder and decoder models were created with the following configuration:

### ENCODER
- Embedding dimension = 64
- Number of attention heads = 8
- Feedforward Network embedding dimension = 256
- Number of encoder layers = 8

### RETNET DECODER
- Embedding dimension = 64
- Number of retention heads = 4
- Feedforward Network embedding dimension = 256
- Number of decoder layers = 8

### Hyperparameters
- Optimizer = AdamW with learning rate of 1e-5
- Loss function = Cross-Entropy Loss
- Batch size = 32
- Number of epochs = 20

The model was evaluated using BLEU score and the model achieved a BLEU score of 36.4 on whole dataset.  

I have also published an article on [Medium](https://medium.com/@akshayatam/unlocking-the-translators-code-machine-translation-with-retnet-96e9b6b7d16d).

If you find my work interesting or have any suggestions, let me know. Do cite my work if you find it valuable!