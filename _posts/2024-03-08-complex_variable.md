---
title: Functions of One Complex Variable
date: 2024-03-08 14:12:00 +0800
categories:
tags:
math: true
---
<style>
  /* 样式适用于<details>标签及其内容 */
  details {
    margin-top: -10px;
    margin-bottom: 20px; /* 设置<details>标签底部的间距 */
  }
  
  /* 如果需要设置<details>标签顶部的间距，可以使用下面的样式 */
  /* details {
       margin-top: 20px; 
     } */

  /* 示例样式，可根据需要调整 */
  summary {
    font-weight: bold;
    cursor: pointer;
  }
</style>

**Theorem.** $\Omega$ simply connected region. If $u,v\in C^2(\Omega,\mathbb{R})$, analytic function

$$f(z):=u(z)+iv(z)\neq 0,\forall z\in\Omega$$

then there exists analytic function $g:\Omega\to\mathbb{C}$, s.t. $e^{g(z)}=f(z)$, for each $z\in\Omega$.

<details open>
<summary>\(Proof.\)</summary>
Set $u_0(z)=\ln|f(z)|$. Check $\Delta u_0(z)=0$. So there exists $v_0$ harmonic s.t. $h=u_0+iv_0$ is analytic on $\Omega$. $\displaystyle\left|\frac{e^{h(z)}}{f(z)}\right|=\left|\frac{e^{u_0(z)}}{f(z)}\right|=1$ on $\Omega\Longrightarrow e^{h(z)}=f(z)e^{ic}$ for some $c\in\mathbb{R}$, so $g=h-ic$. 
</details>

$$n\choose k$$