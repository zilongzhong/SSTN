# PyTorch Implementation of SSTN for Hyperspectral Image Classification

Paper links: [SSTN published on IEEE T-GRS](https://www.researchgate.net/publication/355117935_Spectral-Spatial_Transformer_Network_for_Hyperspectral_Image_Classification_A_Factorized_Architecture_Search_Framework). Also, you can directly find the implementation of SSTN and SSRN here: [Network Zoos](https://github.com/zilongzhong/SSTN/blob/main/NetworksBlocks.py)

Here is the bibliography info:
<br/>

```jason
Zilong Zhong, Ying Li, Lingfei Ma, Jonathan Li, Wei-Shi Zheng. "Spectral-Spatial Transformer 
Network for Hyperspectral Image Classification: A Factorized Architecture Search Framework.” 
IEEE Transactions on Geoscience and Remote Sensing, DOI:10.1109/TGRS.2021.3115699,2021.
```
## Description
Neural networks have dominated the research of hyperspectral image classification, attributing to the feature learning capacity of convolution operations. However, the fixed geometric structure of convolution kernels hinders long-range interaction between features from distant locations.  In this work, we propose a novel spectral-spatial transformer network (SSTN), which consists of spatial attention and spectral association modules, to overcome the constraints of convolution kernels. Extensive experiments conducted on three popular hyperspectral image benchmarks demonstrate the versatility of SSTNs over other state-of-the-art (SOTA) methods. Most importantly, SSTN obtains comparable accuracy to or outperforms SOTA methods with **only 1.2% of multiply-and-accumulate (MAC) operations** compared to a strong baseline SSRN.

<img src="figures/fig_sstn.png" height="400"/>

Fig.1 Spectral-Spatial Transformer Network (**SSTN**) with the architecture of **'AEAE'**, in which 'A' and 'E' stand for a spatial attention block and a spectral association block, respectively. (a) Search space for unit setting. (b) Search space for block sequence.

<img src="figures/fig3_tfmr.png" height="220"/>

Fig.2 Illustration of **spatial attention module** (left) and **spectral association module** (right). The attention maps **Attn** in the spatial attention module
is produced by multiplying two reshaped tensors **Q** and **K**. Instead, the attention maps **M1** and **M2** in the spectral association module are the direct output of a convolution operation. The spectral association kernels **Asso** represent a compact set of spectral vectors used to reconstruct input feature **X**.

## Prerequisites

- [Miniconda3](https://docs.conda.io/en/latest/miniconda.html)
- [PyTorch 1.10](https://pytorch.org/)

When you create a conda environment, check you have installed the packages in the [package-list](https://github.com/zilongzhong/SSTN-nov/blob/master/package_list.txt). You can also refer to the [managing environments](https://conda.io/docs/user-guide/tasks/manage-environments.html) of conda.

## Usage

HSI data can be downloaded from this website [HyperspectralData](http://www.ehu.eus/ccwintco/index.php/Hyperspectral_Remote_Sensing_Scenes). Before training or evaluating different models, please make sure the datasets are in the correct folder and download the Pavia Center (PC) HSI dataset, which is too large to upload here. For example, the raw HSI imagery and its ground truth map for the PC dataset should be put in the following two paths:

```bash
./dataset/PC/Pavia.mat
./dataset/PC/Pavia_gt.mat 
```

Commands to train SSTNs with widely studied hyperspectral imagery (HSI) datasets:
```bash
$ python train_PC.py
$ python train_IN.py
$ python train_UP.py

```

Commands to train SSRNs with widely studied hyperspectral imagery (HSI) datasets:
```bash
$ python train_PC.py --model SSRN
$ python train_IN.py --model SSRN
$ python train_UP.py --model SSRN

```

Commands to evaluate trained SSTNs and generate classification maps:
```bash
$ python test_IN.py
$ python test_UP.py
$ python test_PC.py

```
Commands to evaluate trained SSRNs and generate classification maps:
```bash
$ python test_IN.py --model SSRN
$ python test_UP.py --model SSRN
$ python test_PC.py --model SSRN

```

## Result of Pavia Center (PC) Dataset 
<img src="figures/PC_Cmaps1.png" height="200"/>

Fig.3 Classification maps of different models with 200 samples for training on the PC dataset. (a) False color image. (b) Ground truth labels. (c) Classification map of SSRN (Overall Accuracy 97.64%) . (d) Classification map of SSTN (Overall Accuracy **98.95%**) .

## Result of Indian Pines (IN) dataset

<img src="figures/IN_Cmaps.png" height="150"/>

Fig.4 Classification maps of different models with 200 samples for training on the IN dataset. (a) False color image. (b) Ground truth labels. (c) Classification map of SSRN (Overall Accuracy 91.75%) . (d) Classification map of SSTN (Overall Accuracy **94.78%**).

## Result of University of Pavia (UP) dataset

<img src="figures/UP_Cmaps.png" height="200"/>

Fig.5 Classification maps of different models with 200 samples for training on the UP dataset. (a) False color image. (b) Ground truth labels. (c) Classification map of SSRN (Overall Accuracy 95.09%) . (d) Classification map of SSTN (Overall Accuracy **98.21%**).

## Reference

1. Tensorflow implementation of SSRN: [https://github.com/zilongzhong/SSRN](https://github.com/zilongzhong/SSRN).
2. Auto-CNN-HSI-Classification: [https://github.com/YushiChen/Auto-CNN-HSI-Classification](https://github.com/YushiChen/Auto-CNN-HSI-Classification)
