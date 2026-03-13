+++
title="Plurisubharmonic Functions"
date=2025-03-12

[taxonomies]
categories = ["Markdown"]
tags = ["post", "markdown","complex analysis in serveral variables"]

[extra]
toc = true

+++
#  概述
多重次调和函数(Plurisubharmonic harmonic functions)  是多变量复变函数里的重要研究对象，在 $\mathbb{C}^{n}$里有类似凸函数在$\mathbb{R}^n$的重要地位。
本文记录学习 Plurisubharmonic functions的笔记。参考用书是 Robert C.Gunning 的那本多复变第一册。

# 定义和基本性质
首先，我们给出多重次调和函数的定义
{% definition(term="Plurisubharmonic Functions") %}
A mapping $u:D \to \[-\infty, +\infty) $ defined in an open subset $D \subset \mathbb{C}^n$ is called plurisubharmonic function if (i)u is upper semicontinuous in D and (ii) the restriction of u to any complex line through any point of D is a subharmonic function on that line in D.
{% end %}

Remark ：u 在D上的上半连续性是必要的，若仅要求复直线上的上半连续，并不等价于 D 上的上半连续。


Plurisubharmonic functions 的一些基本性质可以由 subharmonic functions 的基本性质立即得出:

{% theorem(term="Basic Properties of Plurisubharmonic Functions") %}
(a) A mapping u is plurisubharmonic in D precisely when it is plurisubharmonic in an open neighbourhood of each point of D.

(b) If u is plurisubharmonic in D and if $u(A) = \sup_{z \in D} u(z)$ for some point $A \in D$, then u is
constant in the connected component of D containing A.

(c) If u is plurisubharmonic in D , then $u(A) = \limsup_{z \to D} u(z)$ for each point A in D.

(g) If {$u_{v}$} is a monotonically decreasing sequence of plurrisubharmonic functiongs in D,then the mapping u
defined by $u(z) = lim_{v \to \infty} u_{v}(z)$ is also plurisubharmonic in D.
{% end %}

# Levi Form
Levi 对于判别plurisubharmonc 函数很重要，可以类比成判别凸函数的概念。即二阶导半正定。

{% definition(term="Levi form") %}
If u is a function of class $C^2$ in an open subset $D \subset \mathbb{C}^n$ , the Levi form of u at a point 
$Z \in D$ is the Hermitian form:
$$ 
Lu(X;B,C) = \sum_{j,k}\frac{\partial^2 u(Z)}{\partial z_j \partial \bar{z}_k }  b_j \bar{c}_k 
$$
for any vectors $B,C \in \mathbb{C}^n$.For simplicity of notation also set $Lu(Z;B,B)=Lu(Z;B)$
{% end %}

# 多重次调和的逼近定理
为了更好的研究多重次调和函数，我们可以引进一个磨光算子，帮助我们用光滑的 plurisubharmonic函数来逼近一般的plurisubharmonic 函数。我们可以发掘更多的
plurisubharmonic 函数的性质。

{% definition(term="smooth operator") %}
For any locally Lebesgue integrable mapping $u:D \to [-\infty,\inty)$ in an open subset $D \subset \mathbb{C}^n$ and real constant $\epsilon>0$,let
$$
u_{\epsilon}(Z) = \int_{W \in \mathbb{C}^n}u(Z+\epsilon W)\sigma(W)dV(W)
$$
whenever Z is contained in the open subset 
$D_{\epsilon}=\{Z \in D ; \delta_D(Z)> \epsilon \}  \subseteq D$

{% end %}


{% theorem(term="approximate of plurisubharmonic functions") %}
If u is a plurisubharmonic funtion that  is not identically equal to $-\infty$, in a connected open set 
$   D \subset \mathbb{C}^n$ , the $C^{\infty}$ function $u_{\epsilon}$  are plurisubharmonic in $D_{\epsilon}$ and form a monotonically decreasing family of functions converging to u at each point of D as $\epsilon \to 0$.

{% end %}

{% proof (term = "")%}
First note as a consequence of the above theorem that u is  locally Lebesgue integrable in D,so that the functiongs $u_{\epsilon}$ are well defined and of class $C^{\infty}$ in $D_{\epsilon}$.
To see that $u_{\epsilon}$ is
plurisubharmonic in $D_{\epsilon}$ ,note that whenever the disc {$A+tB: |t| \leq 1$} is contained in $D_{\epsilon}$, then since u is plurisubharmonic ,
$$
\begin{aligned}
\frac{1}{2\pi}\int_{0}^{2\pi} u_{\epsilon}(A+B e^{i\theta}) d\theta =
\frac{1}{2\pi}\int_{W \in \mathbb{C}^n} \int_{0}^{2\pi} u(A+B e^{i\theta}) d\theta  \cdot \sigma(W) dV(W) \\\\
\geq \int_{W \in \mathbb{C}^n} u(A+\epsilon W)\sigma(W) dV(W) = u_{\epsilon}(A) 
\end{aligned}
$$

The interchange of the order of intergration is justified as usual by Fubini's theorem.
the domain of integration really being compact sicne the support of $\sigma$ is contasined in the compact 
polydisc $\bar{\Delta}(0;1)$ and the integrand hence being bounded from above there. Thus,$u_\epsilon$ 
is subharmonic on any line $\{A+tB: |t| \leq 1 \} \cap D$.\\
Next introduce polar coordinates $w_j = r_j e^{i\theta_j}$ and note that the integral above can be written 
$$
u_{\epsilon}(Z) = 
\int_{r = 0}^{\infty}\int_{\theta=0}^{2\pi} u(z_j+\epsilon r_j e^{i\theta_j}) d\theta_{1} ...d\theta_{n} \sigma(r_1)...
\sigma(r_n)dr_1 ...dr_n
$$

Since u is plurisubharmonic in D ,we have:
$$
u_\epsilon(Z) \geq \int_{r = 0}^{\infty} (2\pi)^{n} u(Z)\sigma(r_1)...\sigma(r_n)dr_1 ...dr_n
\geq u(Z)\int_{\mathbb{C}^n}\sigma(W)dV(W) = u(Z)
$$
On the other hand,from the theorem of subharmonic functions we have $\int_{0}^{2\pi}u(z_j+\epsilon r_j e^{i\theta_j})d\theta_j $ are monotonically increasing functiongs of $\epsilon$.Thus, the function of $u_\epsilon$
form a monotonically decreasing family of functions as $\epsilon$ tends to zero, and the limit function v satisfies $v(Z)=\lim_{\epsilon \to 0}u_\epsilon(Z) \geq u(Z)$ at each point of D.

Furthermore,sicne the mapping u is upper semicontinuous in D,
we have $u(Z) \geq \limsup_{\epsilon \to 0} u(Z+\epsilon W)$ and sicne the function u is bounded from above on any compact subset of D,if follows from Fatous's lemma that :
$$
\begin{aligned}
u(Z) = \int_{\Delta(0;1)} u(Z)\sigma(W)dV(W)  \\\\
\geq \int_{\Delta(0;1)} \limsup_{\epsilon \to 0 }u(Z+\epsilon W)\sigma(W)dV(W) \\\\
\geq \limsup_{\epsilon \to 0} \int_{\Delta(0;1)} u(Z+\epsilon W)\sigma(W)dV(W) \\\\
\geq \limsup_{\epsilon \to 0} u_\epsilon(Z) = v(Z)
\end{aligned}
$$
then the limit function v must coincide with u at each point of D, and the proof if thereby concluded.
{% end %}


通过这个逼近定理，可以发掘更多的 plurisubharmonic 函数的性质。
{% theorem(term="") %}
If $D \subseteq \mathbb{C}^m$  and $E \subseteq \mathbb{C}^n$  are open subsets, F:$D \to E$ is a holomorphic
mapping from D into E, and u is a plurisubharmonic function in E, then the composite mapping $u \circ F:D \to E$
if a plurisubharmonic function in D.
{% end %}

{% proof (term = "General considerations")%}
First consider u is $C^2$,then it is easy to verify that $u \circ F$ is plurisubharmonic through the Levi form.

For genral case,if u is identically equal to $-\infty$ in D,then $u \circ F$ is plurisubharmonic in D.

otherwise, it follows that {$u_\epsilon$} is a monotonically decreasing family of functions converging to u at each point of D as $\epsilon \to 0$ by the approximate theorem.
Thus, $u_\epsilon \circ F$ is plurisubharmonic in $F^{-1}(E_\epsilon)$ by the first part ot the proof.
and they obviously formed a monotonically decreasing family of functions converging to $u \circ F$ at each point of D as $\epsilon \to 0$. so $u \circ F$ is plurisubharmonic in D.

{% end %}


{% theorem(term="") %}
If $D \subseteq \mathbb{C}^n$ is a tube domain with base $B \subseteq \mathbb{R}^n$,if u: $D \to [-\infty,\infty)$ is not identically equal to $-\infty$ and
on any connected component of D,and if u(Z) depends only on the real part of Z,then u is plurissubharmonic in D precisely when it is convex when viewed as a
function on B.
{% end %}

{% proof (term = "")%}
First if u is a function of class $C^2$ in D,and u is only dependent on the real part of Z,the Levi form of u reduces to the real form:
$$
Lu(Z;B,C) = \sum_{j,k}\frac{\partial^2 u(Z)}{\partial x_j \partial x_k } b_j \bar{c}_k 
$$
THus By theorem of levi form,u is plurisubharmonic in D precisely when the
real matrix $Lu(Z;B,B)$ is positive semidefinite at each point $X \in B$,and
it is well known that is just the condition that u is a convex function on B.
So we proved the theorem for functions of class $C^2$.

Next ,for the general case,if u is plurisubharmonic in D and not identically equal to $-\infty$,then $u_\epsilon$ is plurisubharmonic in $D_{\epsilon}$ and form a monotonically decreasing family of functions converging to u at each point of D as $\epsilon \to 0$.

If,moreover,u(Z) deopend only on the real part of Z,so does $u_\epsilon$(Z),
since:
$$
\begin{aligned}
u_\epsilon(Z+iR) = \int_{\mathbb{C}^n} u(Z+\epsilon W+iR)\sigma(W)dV(W)\\\\
= \int_{\mathbb{C}^n} u(Z+\epsilon W)\sigma(W)dV(W)=u_\epsilon(Z)
\end{aligned}
$$
for any $R \in \mathbb{R}^n$.

It then follows from the first part of the proof that $u_\epsilon$ is convex when viewed as a function on $B_\epsilon$.But it is well known that the limit
of a decreasing sequence of convex functions is also convex;hence,u is convex
when viewed as a function on B as desired.
On the other hand,if u is convex when viewed as a function on B,it is necessary continuous and can be viewed as a continuous function on D,such that u(Z) depends only on the real part of Z.The function $u_\epsilon$ also depends on 
the real part of Z as before and moreover are convex in $B_\epsilon$...
It then follows from the first part of the proof that $u_\epsilon$ is plurisubharmonic in $D_\epsilon$.However,the function $u_\epsilon$ converge uniformly to u on compact subses of D as $\epsilon \to 0$,it follows that u is plurisubharmonic in D.

{% end %}