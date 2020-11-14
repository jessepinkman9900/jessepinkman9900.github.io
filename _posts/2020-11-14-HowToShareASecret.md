---
title: How To Share A Secret
tags:
- Paper Summary
- Cryptography
key: papersummary-cryptography-HowToShareASecret
permalink: /papersummary/cryptography/how-to-share-a-secret
aside:
  toc: true
sidebar:
  nav: sidebar-papersummary
mathjax: true
mathjax_autoNumber: true
---

How To Share A Secret, Shamir

<!--more-->

## Summary
- $(k,n)$ Threshold Scheme
- $n$ users, should be able to recover secret given $k$ users agree to cooperate
- based on polynomial interpolation


## Process

### Selecting $n=2k-1$
- can recover data even when we lose $\lfloor{\frac{n}{2}\rfloor = k-1}$ points
- if adversary gets $\lfloor{\frac{n}{2}\rfloor}$ of remaining $k$ points, after loss of $k-1$ points, the data is still secure

### Sharing
- data $D$, can be converted into a large integer
- select prime $p > max(D, n)$
- create $k-1$ degree polynomial $ q(x) = a_0 + a_1x + ... + a_{k-1}x^{k-1} \text{ st } a_0 = D $
- evaluate $$ y_i = q(x_i) \quad \forall i \in \mathbb{Z_{k+1}} - \{ 0 \} $$
- give each user a unique $(x_i, y_i)$

### Recovery
- **Polynomial Interpolation**: given $k$ points $ (x_1, y_1), ..., (x_k, y_k) $ with distinct $x_i$ there exist unique polynomial $q(x)$ of degree $k-1$ st $q(x_i)=y_i$
- Representing as matrix math $$X = \begin{bmatrix} x_1^0   & \dots     & x_1^{k-1} \\ \vdots  & \ddots    & \vdots    \\ x_k^0   & \dots     & x_k^{k-1} \end{bmatrix}, \quad A = \begin{bmatrix} a_0     \\ \vdots  \\ a_{k-1} \end{bmatrix}, \quad Y = \begin{bmatrix} y_1     \\ \vdots  \\ y_k \end{bmatrix}\\ XA=Y \\ A = X^{-1}Y$$
- $D = a_0$ and $a_0$ is first element in column vector $A$

## References
1. [How To Share A Secret, Shamir](http://web.mit.edu/6.857/OldStuff/Fall03/ref/Shamir-HowToShareASecret.pdf)
