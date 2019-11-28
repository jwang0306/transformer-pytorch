# Transformer-PyTorch

A PyTorch implementation of the Transformer from the paper [Attention is All You Need](https://arxiv.org/pdf/1706.03762.pdf) in both Post-LN (Post-LayerNorm) and Pre-LN (Pre-LayerNorm).

The original paper was using Post-LN, however the [official implementation](https://github.com/tensorflow/tensor2tensor/blob/master/tensor2tensor/models/transformer.py) has been changed into Pre-LN version. For more detail about the difference between them, refer to the paper [On Layer Normalization in the Transformer Architecture](https://openreview.net/pdf?id=B1x8anVFPr).

## Dataset

Uses Multi30k from torchtext as dataset, which is a De En translation task.

## Prerequisites

- Python3
- PyTorch >= 1.2.0
- torchtext
- spacy
- tqdm

## Implementation Notes

- Beam search is not supported.
- Inverse square root learning rate scheduler, which should be adapted with Pre-LN, was not implemented.

## Usage

- Run ```transformer.ipynb``` to download dataset and train the model.
- Change the flag ```pre_lnorm``` to determine which to use.

## Evaluation

<p align="center">
<img src = 'https://i.imgur.com/Vl4FFlk.png'>
<img src = 'https://i.imgur.com/AQlmaFK.png'>
</p>

## Generated Examples

Here's an example from test data:

- source
    - ```eine frau verwendet eine bohrmaschine während ein mann sie fotografiert .```
- gold
    - ```a woman uses a drill while another man takes her picture .```
- inference
    - ```a woman uses an electric drill as a man takes a picture .```

## References

- [tunz](https://github.com/tunz/transformer-pytorch)
- [bentrevett](https://github.com/bentrevett/pytorch-seq2seq)
- [huggingface](https://github.com/huggingface/transformers)
- [jadore801120](https://github.com/jadore801120/attention-is-all-you-need-pytorch)
