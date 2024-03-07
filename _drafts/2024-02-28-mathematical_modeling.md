---
title: 数学模型
date: 2024-02-28 11:35:00 +0800
categories:
tags:
math: true
---






### 2024/02/26 周一
图 $G=(V,E)$，$V$ 顶点集

### 2024/02/28 周三
$L\vec x=\lambda D\vec x$，这是广义特征值问题，这里 $L=B^\mathrm{T}B$，$$D=\mathrm{diag}\{d1,d2,\dots,d_n\}$$ ，$B$ 是关联矩阵，$B=(b_{ei})_{m\times n}$。

将其化为标准特征值问题：$(D^{-\frac{1}{2}}LD^{-\frac{1}{2}})(D^{\frac{1}{2}}\vec x)=\lambda(D^{\frac{1}{2}})\vec x$（$$D^{\frac{1}{2}}=\mathrm{diag}\{\sqrt{d_1},\dots,\sqrt{d_n}\}$$），即 

$$\mathcal L\vec z=\lambda\vec z$$

由实对称阵可对角化，上述特征值问题在记重数的意义下有 $n$ 个特征值，从小到大排列为 $\lambda_1\leq\lambda_2\leq\cdots\leq\lambda_n$，对应的特征向量为 $\Phi_1,\Phi_2,\dots,\Phi_n$。

接下来处理约束 $\vec x\perp D\vec 1$。

由于 $L=D-W$，而 $$d_i=\sum_{\{j,i\}\in E}w_{ij}$$，所以

$$L\vec 1=\vec 0=0\cdot D\vec x$$

这表明 $0$ 是特征值，即 $\mathcal L\vec 1'=0\cdot\vec 1'$，这里 $\vec 1'=D^{\frac{1}{2}}\vec 1$。下面我们来论证 $0$ 就是最小的特征值，即证所有的特征值都非负。

设已有 $L\vec x=\lambda D\vec x$，两边和 $\vec x$ 做内积，得

$$\vec x^{\mathrm{T}}L\vec x=\lambda\vec x^{\mathrm{T}}D\vec x$$

从而有

$$\sum_{\{i,j\}\in E}(x_i-x_j)^2=\lambda\sum_{i\in V}d_i x_i^2$$

（$x_i$ 是 $\vec x$ 的第 $i$ 个分量），由此得出 $\lambda\geq 0$。

$\vec x\perp D\vec 1$ 在广义形式下表示投影掉第一个特征向量，在标准形式下为 $\vec z\perp\vec 1'$，也为同样的含义。下面我们考虑第一个非平凡的特征值（也就是不为 $0$ 的特征值）。



