---
layout: post
title: 'uaternion-kinimatics'
date: 2024-12-15
author: DawsonWen
cover: 'https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241217225501921.png'
tags: 数学
---

# 旋转的朴素分解


![image-20241217225501921](https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241217225501921.png)

![image-20241217230118436](https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241217230118436.png)



<img src="https://raw.githubusercontent.com/Sologala/imgdb/master/post/image-20241217230036279.png" alt="image-20241217230036279" style="zoom:150%;" />



将$x$向量绕着$u$旋转$\phi$的得到向量$x^{'}$ ，可以通过几何关系表达$x^{'}$为一个 平行与旋转轴的旋转不变分量以及一个正交平面上的2维旋转。

$$
\mathbf{\phi } = \phi u
$$

## 欧拉角转四元数

$$
q = Exp(\phi u) = e^{\frac{\phi u}{2}} = cos \frac{\phi}{2} + u sin \frac{\phi}{2} = \begin{bmatrix} cos\frac{\phi}{2} \\ u sin \frac{\phi} {2} \end{bmatrix}
$$

## 四元数转欧拉角

$$
\phi = 2 arctan(||q_{xyz}||, q_{w}) \\
u = \frac{q_{xyz}}{||q_{xyz}||}
$$

- **值得注意的是，当角度很小的时候，$q_{xyz}$虚部的分量会很小，$u$的计算是会变得无穷大。**

使用如下的方法近似 arctan之后乘上$u$如下：
$$
\theta u \approx 2 \frac{q_{xyz}}{q_w} (1 - \frac{||q_{xyz}||^2}{3 q_{w}^2})
$$


