# PixelCNN-Paddle

This is an unofficial Paddle implementation of [PixelCNN](https://arxiv.org/pdf/1601.06759v3.pdf) (Van Oord et al. 2016).

## Contents
1. [Introduction](#introduction)
2. [Reproduction Accuracy](#reproduction-accuracy)
3. [Reprod_Log](#reprod-log)
4. [Dataset](#dataset)
5. [Environment](#environment)
6. [Train & Test](#train&test)
7. [Test](#test)
8. [Code Structure](#code-structure)

## Introduction

**Reference Code：**[PixelCNN](https://github.com/EugenHotaj/pytorch-generative/blob/master/pytorch_generative/models/autoregressive/pixel_cnn.py)

**Paper：**[Pixel Recurrent Neural Networks](https://arxiv.org/pdf/1601.06759v3.pdf)


## Reproduction Accuracy
In training, set batch size to 16.

| Index | Raw Paper| Reference Code | Reproduction |
| --- | --- | --- | --- |
| NLL| 81.30 | 85.74 | 86.637246875 |

## Reprod Log
Based on 'reprod_log' model, the following documents are produced.
```
log_reprod
├── forward_paddle.npy
├── forward_torch.npy
├── metric_paddle.npy
├── metric_torch.npy
├── loss_paddle.npy
├── loss_torch.npy
├── bp_align_paddle.npy
├── bp_align_torch.npy
├── train_align_paddle.npy
├── train_align_torch.npy
```

Based on 'ReprodDiffHelper' model, the following five log files are produced.

```
├── forward_diff.log
├── metric_diff.log
├── loss_diff.log
├── bp_align_diff.log
├── train_align_diff.log
```

## Dataset
The authors use MNIST dataset, and it will be auto-download when users training.


## Environment
- Frameworks: 
* [PaddlePaddle](https://paddlepaddle.org.cn/) (2.1.2)
* [NumPy](http://www.numpy.org/) (1.18.4)
* [Pillow](https://pillow.readthedocs.io/en/latest/index.html) (7.2.0)


## Train & Test

```
python train.py
```



## Code Structure

```
├── ckpts  # pdparams and training logs
├── log_reprod
├── src
│   ├── pixel_cnn.py
│   ├── datasets.py
│   ├── base.py
│   ├── convolution.py
│   ├── train.py
│   ├── trainer.py
├── README.md
└── requirements.txt
```
