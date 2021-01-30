# HRSC2016_SOTA

This repo collects some state-of-the-art results on remote sensing ship dataset HRSC2016 for convenient comparison. 

### Benchmark

 (Ranked according to the mAP(07)). 

|      model      |   backbone   | input_size | mAP(07) | mAP(12) | FPS  |                          paper link                          | code                                                         |
| :-------------: | :----------: | :--------: | :-----: | :-----: | ---- | :----------------------------------------------------------: | ------------------------------------------------------------ |
|      R2CNN      |  ResNet101   |  800x800   |  73.07  |  79.73  | 2    |          [arxiv](https://arxiv.org/abs/1706.09579)           | [tf](https://github.com/yangxue0827/R2CNN_FPN_Tensorflow)    |
|     RC1&RC2     |    VGG16     |     -      |  75.7   |    -    | -    | [ICPRAM](https://www.scitepress.org/Papers/2017/61206/61206.pdf) | -                                                            |
|  Axis Learning  |  ResNet101   |  800x800   |  78.15  |    -    | 14   |  [Remote Sensing](https://www.mdpi.com/2072-4292/12/6/908)   | -                                                            |
|      RRPN       |  ResNet101   |  800x800   |  79.08  |  85.64  | 3.5  |           [TMM](https://arxiv.org/abs/1703.01086)            | -                                                            |
|      TOSO       |  ResNet101   |  800x800   |  79.29  |    -    | 17   | [ICASSP2020](https://ieeexplore.ieee.org/abstract/document/9053562/) | -                                                            |
|       RRD       |    VGG16     |  800x800   |  84.30  |    -    | -    | [CVPR2018](http://openaccess.thecvf.com/content_cvpr_2018/html/Liao_Rotation-Sensitive_Regression_for_CVPR_2018_paper.html) | [C++](https://github.com/MhLiao/RRD)                         |
| RoI-Transformer |  ResNet101   |  512x800   |  86.20  |    -    | 6    | [CVPR2019](https://openaccess.thecvf.com/content_CVPR_2019/html/Ding_Learning_RoI_Transformer_for_Oriented_Object_Detection_in_Aerial_Images_CVPR_2019_paper.html) | [pytorch](https://github.com/dingjiansw101/RoITransformer_DOTA) |
|      RSDet      |   ResNet50   |  800x800   |  86.5   |    -    | -    |         [AAAI2021](https://arxiv.org/abs/1911.08299)         | [tf](https://github.com/Mrqianduoduo/RSDet-8P-4R)            |
| Gliding Vertex  |  ResNet101   |  512×800   |  88.20  |    -    | 10   | [TPAMI](https://ieeexplore.ieee.org/abstract/document/9001201/) | [pytorch](https://github.com/MingtaoFu/gliding_vertex)       |
|      OPLD       |   ResNet50   | 1024x1333  |  88.44  |    -    | 7.3  |    [JSTAR](https://ieeexplore.ieee.org/document/9252176)     | [pytorch](https://github.com/yf19970118/OPLD-Pytorch)        |
|   BBAVectors    |  ResNet101   |  608x608   |  88.60  |    -    | 11.7 | [WACV2021](https://openaccess.thecvf.com/content/WACV2021/html/Yi_Oriented_Object_Detection_in_Aerial_Images_With_Box_Boundary-Aware_Vectors_WACV_2021_paper.html) | [pytorch](https://github.com/yijingru/BBAVectors-Oriented-Object-Detection) |
|       DRN       | Hourglass104 |  768x768   |    -    |  92.70  | 10   | [CVPR2020](https://openaccess.thecvf.com/content_CVPR_2020/html/Pan_Dynamic_Refinement_Network_for_Oriented_and_Densely_Packed_Object_Detection_CVPR_2020_paper.html) | [pytorch](https://github.com/Anymake/DRN_CVPR2020)           |
|       DAL       |  ResNet101   |  416x416   |  88.95  |    -    | 34   |         [AAAI2021](https://arxiv.org/abs/2012.04150)         | [pytorch](https://github.com/ming71/DAL)                     |
|      R3Det      |  ResNet101   |  800x800   |  89.26  |  96.01  | 12   |         [AAAI2021](https://arxiv.org/abs/1908.05612)         | [tf](https://github.com/Thinklab-SJTU/R3Det_Tensorflow), [pytorch](https://github.com/SJTU-Thinklab-Det/r3det-on-mmdetection) |
|       DCL       |  ResNet101   |  800x800   |  89.46  |  96.41  | -    |          [arxiv](https://arxiv.org/abs/2011.09670)           | [tf](https://github.com/Thinklab-SJTU/DCL_RetinaNet_Tensorflow) |
|       CSL       |   ResNet50   |  800x800   |  89.62  |  96.10  | -    |         [ECCV2020](https://arxiv.org/abs/2003.05597)         | [tf](https://github.com/Thinklab-SJTU/CSL_RetinaNet_Tensorflow) |
|     CFC-Net     |  ResNet101   |  800x800   |  89.70  |    -    | 28   |          [arxiv](https://arxiv.org/abs/2101.06849)           | [pytorch](https://github.com/ming71/CFC-Net)                 |
|       GWD       |  ResNet101   |  800x800   |  89.85  |  97.37  | -    |          [arxiv](https://arxiv.org/abs/2101.11952)           | [tf](https://github.com/yangxue0827/RotationDetection)       |
|     S2ANet      |  ResNet101   |  512x800   |  90.17  |  95.01  | 12.7 |          [arxiv](https://arxiv.org/abs/2008.09397)           | [pytorch](https://github.com/csuhan/s2anet)                  |

## Notes

For fair comparison, experiments on the HRSC2016 dataset should meet the following requirements:

* Strictly following the official dataset division. Specifically, training and testing should be performed on the training set and test set respectively. It is unreasonable to use the validation set for training.
* Many previous work used the VOC07 method to calculate mAP, and some recent work used the VOC12 standard to calculate mAP. These two results should not be compared equally.
* All results are obtained at level 1, that is, there is only one class (ship). 