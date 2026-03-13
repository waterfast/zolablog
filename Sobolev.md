+++
title="Sobolev Spaces"
date=2025-01-03

[taxonomies]
categories = ["Markdown"]
tags = ["post", "markdown"]

+++
#  概述
这学期分析学上的Sobolev Space，考前临时报一下佛脚（虽然感觉没怎么学）。 若无额外强调，本文都默认$U \subset \mathbb{R}^n$是一个开集。
{% definition(term="Sobolev 空间") %}
Sobolev空间$W^{k,p}(U)$是所有满足下述条件的局部可积函数$u \in L^p(U)$的集合:
$对\forall u \in W^{k,p}(U),\forall 多重微分指标 \left|\alpha \right|\leq k$，
$u的 \alpha 阶弱导数都存在，且 Du^\alpha \in L^p(U)$。
{% end %}

Remark ：在$W^{k,p}(U)$中，我们还可以定义范数：
$$
\vert u\vert_{W^{k,p}(U)} = \sum_{\|\alpha \|\leq k}(\int_{U} |D^{\alpha}u|^p \, dx)^{1/p}     \quad  if \quad  1 \leq p < \infty
$$

$$
\vert u\vert_{W^{k,p}(U)} = \sum_{\|\alpha \|\leq k}esupp_{x \in U} |D^{\alpha}u|     \quad  if  \quad p = \infty
$$
