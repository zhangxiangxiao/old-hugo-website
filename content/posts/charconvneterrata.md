---
title: "Errata for Character-level Convolutional Networks for Text Classification"
date: "2016-04-03"
description: "Errata for technical errors"
categories:
    - "research"
---

This page contains errata for the paper "Xiang Zhang, Junbo Zhao, Yann LeCun. [Character-level Convolutional Networks for Text Classification](http://arxiv.org/abs/1509.01626). Advances in Neural Information Processing Systems 28 (NIPS 2015)". The [paper on arXiv server](http://arxiv.org/abs/1509.01626) will be updated accordingly, but the [paper in NIPS proceedings](http://papers.nips.cc/paper/5782-character-level-convolutional-networks-for-text-classification) may stay as is. Some of the errata may also apply to our earlier technical report "Xiang Zhang, Yann LeCun. [Text Understanding from Scratch](http://arxiv.org/abs/1502.01710). arXiv 1502.01710."

* The upper index for the convolution and max-pooling module should be `\( \lfloor (l-k)/d \rfloor + 1 \)` instead of `\( \lfloor (l-k+1)/d \rfloor \)`.
* The alphabet contains a duplicate minus/hyphen character. In our experiments, the character quantization process ends up always using the last minus/hyphen character index. This means that the network will never see one of the duplicated characters and the first layer weights associated with it do not contribute to the features to the next layer. Therefore, it would not affect the validity of the experiments. See [this issue on github](https://github.com/zhangxiangxiao/Crepe/issues/4) for more information.
