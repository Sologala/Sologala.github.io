---

layout: post
title: 'Efficient Visual Tracking with Exemplar Transformers'
date: 2024-12-15
author: DawsonWen
cover: 'https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241216221511256.png'
tags: 论文阅读
---

<center class="half">
    <img src="https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241216221511256.png" width="600"/><img src="https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241216221637100.png" width="400"/>
</center>




:house: https://github.com/PinataFarms/FEARTracker

摘要： 在FBNet的基础上，引入了pixel-correlation以及单参数化的dynamic模板更新策，在移动设备上实现效率能耗更优的孪生网络检测器。

- 提出了三个不同尺寸的模型 **XS、M、L**

当前SOTA的方法都太重了

- SiamRPN++、Ocean参数量都很高
- Transformer-based在端侧推理的时候内存峰值更高。
- 在线更新问题的更少参数量实现

轻量BackBone

- 2016 SqueezeNet
- 2018 SqueezeNext 
- 2017 MobileNet （dw卷积）
- 2018 ShuffleNet （分组卷积）
- 2019 FBNet (NAS搜索出来的)

# Method

![image-20241216230725053](https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241216230725053.png)

​    
