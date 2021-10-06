# SSTN
This repo contians the source codes of spectral-spatial transformer network(SSTN) for hyperspectral image classification, which is the model proposed in the accepted IEEE T-GRS paper:

<br/>

```jason
Zilong Zhong, Ying Li, Lingfei Ma, Jonathan Li, Wei-Shi Zheng. "Spectral-Spatial Transformer Network for Hyperspectral Image
Classification: A Factorized Architecture Search Framework.” IEEE T-GRS, 2021. (Accepted)
```
## Descriptions
In this paper, we designed an end-to-end spectral-spatial residual network (SSRN) that takes raw 3D cubes as input data without feature engineering for hyperspectral image classification. In this network, the spectral and spatial residual blocks consecutively learn discriminative features from abundant spectral signatures and spatial contexts in hyperspectral imagery (HSI).

<img src="fig_sstn.png" height="150"/>

Fig.1 Spectral-Spatial Transformer Network with the architecture of 'AEAE', in which 'A' and 'E' stand for a spatial attention block and a spectral association block, respectively. 
