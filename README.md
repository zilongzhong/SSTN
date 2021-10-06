# Spectral-Spatial Transformer Network
This repo contians the source codes of spectral-spatial transformer network(SSTN) for hyperspectral image classification, which is the model proposed in the accepted IEEE T-GRS paper:

<br/>

```jason
Zilong Zhong, Ying Li, Lingfei Ma, Jonathan Li, Wei-Shi Zheng. "Spectral-Spatial Transformer Network 
for Hyperspectral Image Classification: A Factorized Architecture Search Framework.” IEEE Transactions 
on Geoscience and Remote Sensing, DOI:10.1109/TGRS.2021.3115699,2021. (Accepted)
```
## Description
Neural networks have dominated the research of hyperspectral image classification, attributing to the feature learning capacity of convolution operations. However, the fixed geometric structure of convolution kernels hinders long-range interaction between features from distant locations.  In this work, we propose a novel spectral-spatial transformer network (SSTN), which consists of spatial attention and spectral association modules, to overcome the constraints of convolution kernels. Extensive experiments conducted on five popular hyperspectral image benchmarks demonstrate the versatility of SSTNs over other state-of-the-art (SOTA) methods. 

<img src="fig_sstn.png" height="450"/>

Fig.1 Spectral-Spatial Transformer Network with the architecture of 'AEAE', in which 'A' and 'E' stand for a spatial attention block and a spectral association block, respectively. 


