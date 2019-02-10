# LSTM-CRF in PyTorch

A minimal PyTorch implementation of bidirectional LSTM-CRF for sequence tagging, adapted from [the PyTorch tutorial](http://pytorch.org/tutorials/beginner/nlp/advanced_tutorial.html).

Supported features:
- A PyTorch implementation of conditional random field (CRF)
- Vectorized computation of CRF loss
- Vectorized Viterbi decoding
- Mini-batch training with CUDA
- Character and word embeddings in the input layer

## Usage

Training data should be formatted as below:
```
token/tag token/tag token/tag ...
token/tag token/tag token/tag ...
...
```

To prepare data:
```
python prepare.py training_data
```

To train:
```
python train.py model word_to_idx tag_to_idx training_data.csv num_epoch
```

To predict:
```
python predict.py model.epochN word_to_idx tag_to_idx test_data
```

## References

Zhiheng Huang, Wei Xu, Kai Yu. 2015. [Bidirectional LSTM-CRF Models for Sequence Tagging.](https://arxiv.org/abs/1508.01991) arXiv:1508.01991.

Xuezhe Ma, Eduard Hovy. 2016. [End-to-end Sequence Labeling via Bi-directional LSTM-CNNs-CRF.](https://arxiv.org/abs/1603.01354) arXiv:1603.01354.

Shotaro Misawa, Motoki Taniguchi, Yasuhide Miura, Tomoko Ohkuma. 2017. [Character-based Bidirectional LSTM-CRF with Words and Characters for Japanese Named Entity Recognition.](http://www.aclweb.org/anthology/W17-4114) In Proceedings of the First Workshop on Subword and Character Level Models in NLP.

Yan Shao, Christian Hardmeier, Jörg Tiedemann, Joakim Nivre. 2017. [Character-based Joint Segmentation and POS Tagging for Chinese using Bidirectional RNN-CRF.](https://arxiv.org/abs/1704.01314) arXiv:1704.01314.

Zenan Zhai, Dat Quoc Nguyen, Karin Verspoor. 2018. [Comparing CNN and LSTM Character-level Embeddings in BiLSTM-CRF Models for Chemical and Disease Named Entity Recognition.](https://arxiv.org/abs/1808.08450) arXiv:1808.08450.
