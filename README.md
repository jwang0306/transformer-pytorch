# Transformer-PyTorch

A PyTorch implementation of the Transformer from the paper [Attention is All You Need](https://arxiv.org/pdf/1706.03762.pdf) in both Post-LN (Post-LayerNorm) and Pre-LN (Pre-LayerNorm).

Pre-LN applies LayerNorm to the input of every sublayers instead of the residual connection part in Post-LN. The proposed model architecture in the paper was in Post-LN, however the [official implementation](https://github.com/tensorflow/tensor2tensor/blob/master/tensor2tensor/models/transformer.py) has been changed into Pre-LN version. The experiment result shows that Pre-LN transformer converges faster while doesn't even need warming up, and is less sensitive to hyperparameters. For more detail about the difference between them, check out the paper [On Layer Normalization in the Transformer Architecture](https://openreview.net/pdf?id=B1x8anVFPr).

### A STAR would be so nice if you like it!

## Dataset

The English-German small-dataset [WMT 2016 multimodal task from torchtext](https://torchtext.readthedocs.io/en/latest/datasets.html#multi30k).

## Prerequisites

- Python3
- PyTorch >= 1.2.0
- torchtext
- spacy
- nltk
- tqdm

## Implementation Notes

- Beam search is not supported.
- Label smoothing is not implemented.
- BPE is not adapted.

## Usage

- Run ```transformer.ipynb``` to download dataset and train the model.
- Change the flag ```pre_lnorm``` to determine which to use.

## Evaluation

<p align="center">
<img src = 'https://i.imgur.com/oNo0GZT.png'>
<img src = 'https://i.imgur.com/AC3dYOf.png'>
</p>

- Parameter settings
  - hidden size: 512
  - feed forward size: 2048
  - num head: 8
  - layer: 6
  - warm-up: 2000
  - batch size: 128

## Generated Examples

Here's an example from test data:

- source
  - ```eine frau verwendet eine bohrmaschine während ein mann sie fotografiert .```
- gold
  - ```a woman uses a drill while another man takes her picture .```
- inference
  - ```a woman uses an electric drill as a man takes a picture .```

## TODO

- Label smoothing
- Attention visualization

## References

- [annotated-transformer](https://nlp.seas.harvard.edu/2018/04/03/attention.html)
- [tunz](https://github.com/tunz/transformer-pytorch)
- [bentrevett](https://github.com/bentrevett/pytorch-seq2seq)
- [huggingface](https://github.com/huggingface/transformers)
- [jadore801120](https://github.com/jadore801120/attention-is-all-you-need-pytorch)
