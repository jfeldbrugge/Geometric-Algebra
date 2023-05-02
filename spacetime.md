---
title: Space-time algebra
author: Job Feldbrugge
header-includes:
    <link rel = "icon" href = "figures/icon.png" type = "image/x-icon"> 
    <div class="topnav">
      <a href="https://jfeldbrugge.github.io/">Home</a>
      <a href="https://jfeldbrugge.github.io/Projects-and-Codes/">Projects and Code</a>
    </div>
---

In order to apply geometric algebra to relativity, we develop space-time algebra.

Let's consider the orthogonal space-time basis $\gamma_\mu$ with 

$$\begin{align}
\gamma_0^2=1,\quad \gamma_0 \cdot \gamma_i = 0,\quad \gamma_i \cdot \gamma_j = - \delta_{ij}\,.
\end{align}$$

A space-time event is denoted by the vector

$$x = x^\mu \gamma_\mu = t \gamma_0 + x^i \gamma_i\,,$$

with the coordinates $(t,x^1,x^2,x^3)$. The geometric algebra of space-time consists of a scalar $1$. We have four vectors 

$$\gamma_0, \gamma_1,\gamma_2,\gamma_3,$$

representing the space-time directions. We have six bi-vectors 

$$\gamma_1 \gamma_0, \gamma_2\gamma_0,\gamma_3\gamma_0,\gamma_1\gamma_2,\gamma_1\gamma_3,\gamma_2\gamma_3,$$

of which $\sigma_i=\gamma_i \gamma_0$ satisfying 

$$\sigma_i \cdot \sigma_j = \delta_{ij}$$

and $(\gamma_i \gamma_j )^2=-1$. More generally,

$$\gamma_\mu \gamma_\nu + \gamma_\nu \gamma_\mu = 2 \eta_{\mu\nu}\,,$$

with $\eta_{\mu\nu}=\text{diag}(1, -1, -1, -1).$ That is to say, different basis elements anti-commute.

We have four tri-vectors

$$\gamma_0\gamma_1\gamma_2, \gamma_0\gamma_1\gamma_3, \gamma_0\gamma_2\gamma_3,\gamma_1\gamma_2\gamma_3,$$

that are dual to the vectors. Finally, we have a singel grade-$4$ pseudovector

$$I = \gamma_0\gamma_1\gamma_2\gamma_3.$$


Let $x = t \gamma_0 + x^i \gamma_i$, and use $\gamma_0$ to perform a space-time split

$$x \gamma_0 = x \cdot \gamma_0 + x \wedge \gamma_0 = t + \textbf{x}\,,$$

where $t=x \cdot \gamma_0$ is the time and the relative space variable $\textbf{x} = x \wedge \gamma_0 = x^i \gamma_i \wedge \gamma_0 = x^i \sigma_i$ which is a bi-vector. More generally, given a reference frame with four velocity $v$, we have the space-time split $t= x \cdot v$ and $\textbf{x} = x \wedge v$. The bivectors $\sigma_i$ form a basis for three-dimensional space. Note that

$$x^2 = (x \gamma_0)(\gamma_0 x) = (t+\textbf{x})(t-\textbf{x}) = t^2 - \textbf{x}^2\,.$$

