# Transformer-PyTorch

A PyTorch implementation of the Transformer from the paper [Attention is All You Need](https://arxiv.org/pdf/1706.03762.pdf) in both Post-LN (Post-LayerNorm) and Pre-LN (Pre-LayerNorm).

The original paper was using Post-LN, however the [official implementation](https://github.com/tensorflow/tensor2tensor/blob/master/tensor2tensor/models/transformer.py) has been changed into Pre-LN version. For more detail about the difference between them, refer to the paper [On Layer Normalization in the Transformer Architecture](https://openreview.net/pdf?id=B1x8anVFPr).

## Prerequisites

- Python3
- PyTorch >= 1.2.0
- torchtext
- spacy
- tqdm

## Implementation Notes

- Beam search is not supported.
- Uses Multi30k from torchtext as dataset.

## Usage

- Run ```transformer.ipynb``` to download dataset and train the model.
- Change the flag ```pre_lnorm``` to determine which to use.

## Evaluation

## Generated Examples
