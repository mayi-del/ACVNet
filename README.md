# ACVNet
This is the implementation of the paper: **Attention Concatenation Volume for Accurate and Efficient Stereo Matching**, CVPR 2022, Gangwei Xu, Junda Cheng, Peng Guo, Xin Yang
[\[Arxiv\]](https://arxiv.org/)

## Introduction

An informative and concise cost volume representation is vital for stereo matching of high accuracy and efficiency. In this paper, we present a novel cost volume construction method which generates attention weights from correlation clues to suppress redundant information and enhance matching-related information in the concatenation volume. To generate reliable attention weights, we propose multi-level adaptive patch matching to improve the distinctiveness of the matching cost at different disparities even for textureless regions.

![image](https://github.com/gangweiX/ACVNet/blob/main/imgs/acv_network.png)

# How to use

## Environment
* python 3.6
* Pytorch >= 0.4.1

## Data Preparation
Download [Scene Flow Datasets](https://lmb.informatik.uni-freiburg.de/resources/datasets/SceneFlowDatasets.en.html), [KITTI 2012](http://www.cvlibs.net/datasets/kitti/eval_stereo_flow.php?benchmark=stereo), [KITTI 2015](http://www.cvlibs.net/datasets/kitti/eval_scene_flow.php?benchmark=stereo)

## Train
As an example, use the following command to train ACVNet on Scene Flow

```
python main.py
```

## Results on KITTI 2015 leaderboard
[Leaderboard Link](http://www.cvlibs.net/datasets/kitti/eval_scene_flow.php?benchmark=stereo)

| Method | D1-bg (All) | D1-fg (All) | D1-all (All) | Runtime (s) |
|---|---|---|---|---|
| ACVNet | 1.37 % | 3.07 % | 1.65 % | 0.20 |
| LEAStereo | 1.40 % | 2.91 % | 1.65 % | 0.30 |
| GwcNet | 1.74 % | 3.93 % | 2.11 % | 0.32 |
| PSMNet | 1.86 % | 4.62 % | 2.32 % | 0.41 |

# Acknowledgements

Thanks to Xiaoyang Guo for opening source of his excellent work GwcNet. Our work is inspired by this work and part of codes are migrated from [GwcNet](https://github.com/xy-guo/GwcNet).
