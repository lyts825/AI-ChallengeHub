# Data
https://drive.grand-challenge.org/
# Requirements
```numpy 1.26.4```

```opencv-python 4.11.0.86```

```torch 2.6.0 (cuda 12.6)```
# Progress
* 3.29 dataset utils.py
* 3.29 尝试通过边缘检测进行预处理, 发现部分细小血管无法检测到
* 3.30 使用 [U-Net](https://arxiv.org/pdf/1505.04597) , 部分代码参考 [Pytorch-UNet](https://github.com/milesial/Pytorch-UNet)
* 4.2 可以较准确预测，但是边缘和中心亮点会被误识别
* 4.2 修改loss计算方法和optimizer,但是细小血管在预测结果中变得不连续
* 4.2 改用 [DiceBCELoss](https://github.com/MilleXi/Retinal-vessel-segmentation/blob/main/loss.py) 作为Loss计算
* 4.5 将unet移至models.py,更新彩色结果图,在loss计算中应用mask,对图片进行直方图均衡化预处理以加强对细小血管的检测,翻转图片以增加训练样本