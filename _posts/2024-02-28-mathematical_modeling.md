---
classoption: fleqn

title: 数学模型
date: 2024-02-28 11:35:00 +0800
categories:
tags:
math: true
mermaid: true
---
$$\def \dis{\displaystyle}$$
$$\def \dom{\mathrm{dom}\,}$$
$$\def \sgn{\mathrm{sgn}}$$





### 2024/02/26 周一
图 $$G=(V,E)$$，$$V$$ 顶点集

### 2024/02/28 周三
$$L\vec x=\lambda D\vec x$$，这是广义特征值问题，这里 $$L=B^\mathrm{T}B$$，$$D=\mathrm{diag}\{d1,d2,\dots,d_n\}$$ ，$$B$$ 是关联矩阵，$$B=(b_{ei})_{m\times n}$$。

将其化为标准特征值问题：$$(D^{-\frac{1}{2}}LD^{-\frac{1}{2}})(D^{\frac{1}{2}}\vec x)=\lambda(D^{\frac{1}{2}})\vec x$$（$$D^{\frac{1}{2}}=\mathrm{diag}\{\sqrt{d_1},\dots,\sqrt{d_n}\}$$），即 

$$\mathcal L\vec z=\lambda\vec z$$

由实对称阵可对角化，上述特征值问题在记重数的意义下有 $$n$$ 个特征值，从小到大排列为 $$\lambda_1\leq\lambda_2\leq\cdots\leq\lambda_n$$，对应的特征向量为 $$\Phi_1,\Phi_2,\dots,\Phi_n$$。

接下来处理约束 $$\vec x\perp D\vec 1$$。

由于 $$L=D-W$$，而 $$d_i=\sum_{\{j,i\}\in E}w_{ij}$$，所以

$$L\vec 1=\vec 0=0\cdot D\vec x$$

这表明 $$0$$ 是特征值，即 $$\mathcal L\vec 1'=0\cdot\vec 1'$$，这里 $$\vec 1'=D^{\frac{1}{2}}\vec 1$$。下面我们来论证 $$0$$ 就是最小的特征值，即证所有的特征值都非负。

设已有 $$L\vec x=\lambda D\vec x$$，两边和 $$\vec x$$ 做内积，得

$$\vec x^{\mathrm{T}}L\vec x=\lambda\vec x^{\mathrm{T}}D\vec x$$

从而有

$$\sum_{\{i,j\}\in E}(x_i-x_j)^2=\lambda\sum_{i\in V}d_i x_i^2$$

（$$x_i$$ 是 $$\vec x$$ 的第 $$i$$ 个分量），由此得出 $$\lambda\geq 0$$。

$$\vec x\perp D\vec 1$$ 在广义形式下表示投影掉第一个特征向量，在标准形式下为 $$\vec z\perp\vec 1'$$，也为同样的含义。下面我们考虑第一个非平凡的特征值（也就是不为 $$0$$ 的特征值）。



### 2024/03/11 周一
Chang 等式：$$h(G)=\mu_2$$ 这里有两个问题：何为 $$\mu$$，如何相等。  
用 Lagrange 乘子法可以化为特征值问题。同时，由于 $$\dis\frac{I(\vec x)}{N(\vec x)}$$ 是零次齐次的，不妨只在 $$\{\vec x\in\mathbb{R}: \|\vec x\|_{1,d}=1\}$$ 上求其最小值，其中 $$\|\vec x\|_{1,d}=\sum d_i\lvert x_i\rvert$$。

构造 Lagrange 函数：$$F(\vec x,\mu)=I(\vec x)-\mu(\|\vec x\|_{1,d}-1)$$。形式上，我们需要：

$$\frac{\partial F}{\partial\vec x}=0$$

即

$$\partial I(\vec x)=\mu\partial\|\vec x\|_{1,d}$$

问题在于，如何理解我们新定义的这个 $$\partial$$ ？

#### 定义：次梯度
设 $$f$$ 是适当的凸函数，$$\vec x$$ 是其定义域 $$\dom f$$ 中一点，如果向量 $$\vec g\in\mathbb{R}^n$$ 满足 $$\forall\vec y\in\dom f$$，有

$$f(\vec y)\geq f(\vec x)+\langle\vec g,\vec y-\vec x\rangle$$

则称 $$\vec g$$ 为 $$f$$ 在 $$\vec x$$ 处的一个“次梯度”。将所有这样的 $$\vec g$$ 收集在一起，称为 $$f$$ 在 $$\vec x$$ 处的次梯度，记为 $$\partial f(\vec x)$$。

次梯度有如下的性质：
* 设 $$f(\vec x)$$ 是 $$\mathbb{R}^n$$ 上的凸函数，若 $$\vec x_0$$ 满足 $$f(\vec x_0)=\min_{\vec x\in\mathbb{R}^n}f(\vec x)$$，则 $$\vec 0\in\partial f(\vec x_0)$$（实际上是充要的）
* 若 $$f$$ 在 $$\vec x_0$$ 处可微，$$\vec x_0$$ 是 $$\dom f$$ 的内点，则 $$\partial f(\vec x_0)=\{\nabla f(\vec x_0)\}$$
* 对于 $$\alpha\geq 0$$，$$\partial(\alpha f)(\vec x)=\alpha\partial f(\vec x)$$
* 对于 $$\alpha_1,\alpha_2\geq 0$$，$$\partial(\alpha_1 f_1+\alpha_2 f_2)(\vec x)=\alpha_1\partial f_1(\vec x)+\alpha_2\partial f(\vec x)$$
* $$\partial f(\vec x)$$ 是闭的凸集
* 对于 $$\mathbb{R}^n\rightarrow\mathbb{R}$$ 的一次齐次函数 $$f$$，有
  * $$\forall\vec x\in\mathbb{R}^n$$，$$f(\vec x)=\langle\vec s,\vec x\rangle,\vec s\in\partial f(\vec x)$$（即可以线性化）
  * \$$f(\vec x)\geq\langle\vec s,\vec x\rangle,\forall\vec x,\vec y\in\mathbb{R}^n,\forall\vec s\in\partial f(\vec y)$$

> 此性质之证明：  
> a) $$\Longrightarrow$$ b)：$$f(\vec x)\geq f(\vec y)+\langle\vec s,\vec x-\vec y\rangle=\langle\vec s,\vec y\rangle+\langle\vec s,\vec x-\vec y\rangle=\langle\vec s,\vec x\rangle$$。
> 
> a)：$$f(\vec y)\geq f(\vec x)+\langle\vec g,\vec y-\vec x\rangle,\forall \vec x,\vec y\in\mathbb{R}^n,\vec g\in\partial f(\vec x)$$。由于 $$f$$ 是一次齐次函数，在上式中取 $$\vec y=\alpha \vec x,\alpha>0$$，得
>  
> $$f(\alpha\vec x)\geq f(\vec x)+\langle\vec g,\alpha \vec x-\vec x\rangle$$
>  
> 即
> 
> $$(\alpha-1)f(\vec x)\geq(\alpha-1)\langle\vec g,\vec x\rangle$$
> 
> 取 $$\alpha=1+0,1-0$$，即得 $$f(\vec x)=\langle\vec g,\vec x\rangle$$。

<ul> 
 <li>\(\begin{aligned} 
 \partial\lvert x\rvert=\sgn\, x= 
 \begin{cases} 
 \{1\},\quad x&gt;0\\ 
 \{-1\},\quad x&lt;0\\ 
 [-1,1],\quad x=0 
 \end{cases} 
 \end{aligned}\)</li> 
 </ul> 

#### 计算上述 $$\partial\|\vec x\|_{1,d}$$
$$(\partial\|\vec x\|_{1,d})_j=(\partial\sum_{i=1}^nd_i\lvert x_i\rvert)_j=d_j\partial\lvert x_j\rvert=d_j\sgn(x_j)$$，因此，所有分量合在一起，得到

$$
\partial\|\vec x\|_{1,d}=D\sgn\,\vec x
$$

这里 $$\sgn\,\vec x=(\sgn\,x_1,\sgn\,x_2,\dots,\sgn\,x_n)$$，$$D=\mathrm{diag}\{d_1,d_2,\dots,d_n\}$$。

再考虑 $$\partial I(\vec x)$$，将 $$\partial I(\vec x)$$ 写成如下形式：

$$
I(\vec x)=h(B\vec x)
$$

其中 $$B$$ 是 $$G$$ 的关联矩阵，

$$h(\vec y)=\sum_{i=1}^n\lvert y_i\rvert=\|\vec y\|,\forall \vec y\in\mathbb{R}^n$$

由作业 2.可知

$$
\partial I(\vec x)=B^T\partial h(B\vec x)=B^T\sgn(B\vec x)
$$



>
例：线图
```mermaid
graph RL;
    B((2)) -->|边1| A((1));
    C((3)) -->|边2| B((2));
    D((4)) -->|边3| C((3));
```
其关联矩阵为
>
> $$
B=\begin{pmatrix}
1 & -1 & 0 & 0\\
0 & 1 & -1 & 0\\
0 & 0 & 1 & -1
\end{pmatrix}
$$
> 
> 则
> 
> $$
B\vec x=\begin{pmatrix}
x_1-x_2\\
x_2-x_3\\
x_3-x_4
\end{pmatrix}
$$
> 
> 取
> 
> $$
\begin{gather}
z_{12}(\vec x)\in\sgn(x_1-x_2)\\
z_{23}(\vec x)\in\sgn(x_2-x_3)\\
z_{34}(\vec x)\in\sgn(x_3-x_4)
\end{gather}
$$
> 
> 则 $$B^T\sgn(B\vec x)$$ 中有元素
> 
> $$
\begin{align}
B^T\begin{pmatrix}
z_{12}(\vec x)\\
z_{23}(\vec x)\\
z_{34}(\vec x)
\end{pmatrix}&=\begin{pmatrix}
1 & 0 & 0\\
-1 & 1 & 0\\
0 & -1 & 1\\
0 & 0 & -1
\end{pmatrix}\begin{pmatrix}
z_{12}(\vec x)\\
z_{23}(\vec x)\\
z_{34}(\vec x)
\end{pmatrix}\\
&=\begin{pmatrix}
z_{12}(\vec x)\\
-z_{12}(\vec x)+z_{23}(\vec x)\\
-z_{23}(\vec x)+z_{34}(\vec x)\\
-z_{34}(\vec x)
\end{pmatrix}=\begin{pmatrix}
z_{12}(\vec x)\\
z_{21}(\vec x)+z_{23}(\vec x)\\
z_{32}(\vec x)+z_{34}(\vec x)\\
z_{43}(\vec x)
\end{pmatrix}
\end{align}
$$
> 
> 这里我们引入 $$z_{12}=-z_{21},z_{23}=-z_{32},z_{34}=-z_{43}$$。所以
> 
> $$
\begin{align}
(\partial I(\vec x))_i&=(B^T\sgn(B\vec x))_i\\
&=\left\{\sum_{j:\{i,j\}\in E}z_{ij}(\vec x):z_{ij}(\vec x)\in\sgn(x_i-x_j) \text{ and } \forall \{i,j\}\in E,z_{ji}(\vec x)=-z_{ij}(\vec x)\right\}
\end{align}
$$

#### 定义：$$\Delta_1$$ 特征值问题
称 $$(\mu,x)$$ 是 $$\mathbb{R}\times X$$ 上的一个 $$\Delta_1$$ 特征对，如果 $$\Delta_1(\vec x)\cap\mu D\sgn(\vec x)\neq\varnothing$$，即存在 $$(z_{ij}(\vec x))_{n\times n}$$ 满足

$$
\sum_{j:\{i,j\}\in E}z_{ij}(\vec x)\in\mu d_i\sgn(x_i), \forall \{i,j\}\in E,z_{ij}(\vec x)=-z_{ji}(\vec x)
$$