---
title: Spacetime algebra
author: Job Feldbrugge
header-includes:
    <link rel = "icon" href = "figures/icon.png" type = "image/x-icon"> 
    <div class="topnav">
      <a href="https://jfeldbrugge.github.io/">Home</a>
      <a href="https://jfeldbrugge.github.io/Projects-and-Codes/">Projects and Code</a>
    </div>
---

To apply the tools of geometric algebra to special relativity, we extend the definitions of multi-vectors and geometric products to spacetime. Spacetime differs from Euclidean space, in that the metric is no-longer positive definite. However, as the positivity of the norm is nowhere assumed in the construction of geometric algebra on Euclidean space, we extend the construction to spacetime without any trouble. 

Special relativity is a physical theory of space and time (in the absence of gravity), describing how different observers in different reference frames relate. It is based on two postulates:

- The laws of physics are identical in all inertial reference frames (frames of reference with constant velocity).
- The speed of light in a vacuum is the same for all observers, regardless of the motion of the light source or observer. 
  
In special relativity, spacetime is described as the collection of spacetime events. In an inertial reference frame $S$, defined by a non-accelerating observer, we describe the spacetime event in the coordinates $x = (t,x,y,z)$. In an alternative inertial frame $S'$, defined by another non-accelerating observer moving with a velocity $\textbf{v}$ with respect to the first reference frame, the event is measured in terms of the coordinates $(t',x', y',z').$ These coordinates are related by the Lorentz transformation

$$\begin{align}
t' &= \gamma(t - \|\textbf{v}\| x / c^2)\,,\\
x' &= \gamma(x - \|\textbf{v}\| t)\,,\\
y' &= y\,,\\
z' &= z\,,
\end{align}$$

assuming the velocity $\textbf{v}$ is oriented in the $x$-direction and with the Lorentz factor 

$$ \gamma = \frac{1}{\sqrt{1-\textbf{v}^2/c^2}}\,,$$

and the speed of light in vacuum $c$. From hereon, we will use units for which the speed of light $c=1$.

The Lorentz transformation is analogous to rotations in Euclidean space. However, there exists a key distinction between rotations and Lorentz transformations. While rotations are defined to preserve the distance between two points,

$$\Delta \textbf{x}^2 = \Delta x^2 + \Delta y^2 + \Delta z^2\,,$$

the Lorentz transformation preserves the spacetime distance 

$$\Delta s^2 = \Delta t^2 - \Delta \textbf{x}^2\,,$$

between events. The minus sign differentiates the temporal from the spatial directions. 

Traditionally, special relativity describes the nature of spacetime using inertial coordinate frames. Geometric algebra attempts to develop a coordinate-free formulation, where the geometry of spacetime is written in terms of the language of multi-vectors.

### Spacetime geometric algebra
First, write the spacetime event in a given inertial reference frame, $x = (t,x^1,x^2,x^3)$, as

$$x = x^\mu \gamma_\mu = t \gamma_0 + x^i \gamma_i\,,$$

using the Einstein summation convention over repeated indices, with the orthonormal spacetime basis $\gamma_\mu$ defined as 

$$\begin{align}
\gamma_0^2=1,\quad \gamma_0 \cdot \gamma_i = 0,\quad \gamma_i \cdot \gamma_j = - \delta_{ij}\,.
\end{align}$$

In this reference frame the vector $\gamma_0$ points in the time direction and the vectors $\gamma_i$ for $i=1,2,3$ point in the space directions. In these notes, we will let Latin and Greek letters respectively run over the spatial $1,2,3$ and spacetime indices $0,1,2,3$. Given these basis vectors, we construct a basis for the spacetime algebra $\mathbb{G}^{3,1}$ using the standard geometric product (which is again anti-symmetric for orthogonal vectors, *i.e.,* $\gamma_\mu \gamma_\nu = - \gamma_\nu \gamma_\mu$ for $\mu \neq \nu$): 

- The basis includes a single scalar $1$, as we saw in the Euclidean algebra.
- The basis includes the four vectors $\gamma_0, \gamma_1, \gamma_2,$ and $\gamma_3$, signifying the temporal and spatial directions. Note that the timelike basis vector squares to one, *i.e.,* $\gamma_0^2=+1$, and the spacial basis vectors square to minus one, *i.e.,* $\gamma_i^2=-1$.
- The basis includes of six bivectors $\gamma_1 \gamma_0, \gamma_2\gamma_0,\gamma_3\gamma_0,\gamma_1\gamma_2,\gamma_1\gamma_3,\gamma_2\gamma_3.$ The first three basis vectors are timelike, *i.e.,* as they square to one $(\gamma_i \gamma_0)^2=+1$ for $i \neq j$. The latter three are spacelike, *i.e.,* they square to minus one $(\gamma_i \gamma_j)^2=-1$.
- The basis includes four trivectors $\gamma_0\gamma_1\gamma_2, \gamma_0\gamma_1\gamma_3, \gamma_0\gamma_2\gamma_3,\gamma_1\gamma_2\gamma_3\,.$ The first three are spacelike, *i.e.,* as they square to one $(\gamma_0 \gamma_i \gamma_j)^2=-1$ for $i \neq j$. The last one is timelike, *i.e.,* it squares to one $(\gamma_1\gamma_2\gamma_3)^2=+1\,.$
- Finally, the basis includes a single four-vector known as the pseudoscalar $I = \gamma_0\gamma_1\gamma_2\gamma_3\,.$ The pseudoscalar is spacelike since $I^2=-1\,.$

This $16$-dimensional algebra leads to a consistent formulation of special relativity, where the bivectors, trivectors, and the grade-$4$ pseudoscalar play an important role.

#### Spacetime split
Given an event in the spacetime algebra $\mathbb{G}^{3,1}$, we would like to make a spacetime split to recover the three-dimensional space and corresponding geometric algebra $\mathbb{G}^3$. In the coordinate system of an inertial observer, we write the event as the vector $x = x^\mu \gamma_\mu$ and perform the spacetime split with a right multiplication of the time vector

$$\begin{align}
x \gamma_0 &= x \cdot \gamma_0 + x \wedge \gamma_0 \\
&= t + \textbf{x}\,,
\end{align}$$

where the time $t = x \cdot \gamma_0$ is a spacetime scalar and the relative position $\textbf{x} = x \wedge \gamma_0 = x^i \gamma_i \wedge \gamma_0 = x^i \sigma_i$ is a spacetime bivector. This split is motivated by the observation that the norm of a spacetime event is the invariant distance 

$$\begin{align}
x^2 &= x \gamma_0 \gamma_0 x\\
&=(x \cdot \gamma_0  + x \wedge \gamma_0)(x \cdot \gamma_0  - x \wedge \gamma_0)\\
&=(t  + \textbf{x})(t  - \textbf{x})\\
&=t^2 - \textbf{x}^2\,.
\end{align}$$

The temporal bivectors of the spacetime algebra $\sigma_i = \gamma_i \gamma_0$ act as the basis vectors of the induced space algebra $\mathbb{G}^3$. Indeed, the vectors are orthonormal

$$\begin{align}
\sigma_i \cdot \sigma_j &= \langle \gamma_i \gamma_0 \gamma_j \gamma_0 \rangle_0 \\
&= -\langle \gamma_i \gamma_j  \rangle_0 \\
&=  \delta_{ij}\,,
\end{align}$$

anti-commute 

$$\begin{align}
\sigma_i \sigma_j &= \gamma_i \gamma_0 \gamma_j \gamma_0\\
&=-\gamma_j \gamma_0 \gamma_i \gamma_0\\
&=-\sigma_j \sigma_i\,,
\end{align}$$

and generate a geometric algebra with the basis 

$$\{1, \sigma_1, \sigma_2, \sigma_3, \sigma_1 \sigma_2, \sigma_1\sigma_3,\sigma_2\sigma_3,\sigma_1\sigma_2\sigma_3\}\,.$$

The bivectors of the space algebra are the spatial bivectors of the underlying spacetime algebra, 

$$\sigma_i\sigma_j= -\gamma_i\gamma_j\,.$$

The six bivectors of the spacetime algebra nicely capture the vectors and pseudovectors of the induced space algebra. The space pseudoscalar coincides with the pseudoscalar of the spacetime algebra

$$\sigma_1\sigma_2\sigma_3=\gamma_1\gamma_0\gamma_2\gamma_0\gamma_3\gamma_0 = \gamma_0\gamma_1\gamma_2\gamma_0^2\gamma_3=\gamma_0\gamma_1\gamma_2\gamma_3 = I\,.$$

From the space algebra we see that the elements $\sigma_i$ are dual to the elements $\sigma_i \sigma_j$, indeed,

$$\begin{align}
\sigma_i^* &=\sigma_i I^{-1} \\
&= \gamma_i \gamma_0 \gamma_3 \gamma_2 \gamma_1 \gamma_0\\
&=- \gamma_i \gamma_3 \gamma_2 \gamma_1\\
&= \gamma_i \gamma_1 \gamma_2 \gamma_3\,,
\end{align}$$

by which $\sigma_1^* =-\gamma_2 \gamma_3 = \sigma_2 \sigma_3,$ $\sigma_2^*=-\gamma_3 \gamma_1=\sigma_3 \sigma_1$ and $\sigma_3^*=-\gamma_1\gamma_2=\sigma_1\sigma_2\,.$

The spacetime vectors and pseudovectors do not appear in this construction. We thus conclude that the even subalgebra of the spacetime algebra $\mathbb{G}^{3,1}$ is isomorphic with the three-dimensional vector algebra $\mathbb{G}^3$.

Given a worldline $x(\tau)$ with the proper time along the worldline $\tau$, define the proper velocity $v= \frac{\mathrm{d}x}{\mathrm{d}\tau}$, where the proper velocity is a unit vector, *i.e.,* $v^2=1$. We can relate the proper velocity to the inertial frame velocity $\textbf{v} = \frac{\mathrm{d}\textbf{x}}{\mathrm{d}t}$ with the spacetime split, 

$$ v \gamma_0 = \frac{\mathrm{d}}{\mathrm{d} \tau}(x \gamma_0) = \frac{\mathrm{d}}{\mathrm{d}\tau}(t+\textbf{x})$$

by which $\frac{\mathrm{d}t}{\mathrm{d}\tau} = v\cdot \gamma_0$ and $\frac{\mathrm{d}\textbf{x}}{\mathrm{d}\tau}= v \wedge \gamma_0$ and thus

$$ \frac{\mathrm{d}\textbf{x}}{\mathrm{d}t} = \frac{\mathrm{d}\textbf{x}}{\mathrm{d}\tau}\frac{\mathrm{d}\tau}{\mathrm{d}t} = \frac{v \wedge \gamma_0}{v\cdot \gamma_0}.$$

This is manifestly invariant under reparametrizations of the worldline.

#### Lorentz transformations
Different observers in different inertial reference frames split spacetime differently. Let's first consider $2$-dimensional spacetime $\mathbb{G}^{1,1}$. In the original reference frame $S$, $\gamma_0$ is the unit vector pointing in the temporal direction. An observer with a relative velocity $\textbf{v}$ in the $x$-direction, defines a reference frame $S'$ where the timelike basis vector is given by the four-velocity $v = \gamma (\gamma_0 +  \|\textbf{v}\|\gamma_1)$, where the Lorentz vector ensures that the norm 

$$\begin{align}
v^2 &= v \gamma_0 \gamma_0 v \\
&=\gamma^2(\gamma_0 \cdot \gamma_0 + \|\textbf{v}\| \gamma_1 \wedge \gamma_0)(\gamma_0 \cdot \gamma_0 - \|\textbf{v}\| \gamma_1 \wedge \gamma_0)\\
&=\gamma^2 (1 - \textbf{v}^2) \\
&= 1\,.
\end{align}$$

The spacetime split in the reference frame $S'$ takes the form 

$$\begin{align}
x v 
&=  x \cdot v + x \wedge v\\
&= t' + \textbf{x}'\,,
\end{align}$$

with the time 

$$\begin{align}
t' &= x \cdot v \\
&=x^\mu \gamma_\mu \cdot v \\
&= \gamma  (x^0 \gamma_0 \cdot \gamma_0 +\|\textbf{v}\| x^1 \gamma_1 \cdot \gamma_1)\\
&= \gamma  (x^0 -\|\textbf{v}\| x^1)\,,
\end{align}$$ 

where $\mu=0,1$, and the relative position 

$$\begin{align}
\textbf{x}' &= x \wedge v\\
&=x^\mu \gamma_\mu \wedge v \\
&= \gamma( x^1 - \|\textbf{v}\| x^0) \sigma_1\,.
\end{align}$$

These are the Lorentz transformations we saw above. As a consequence, in $2$-dimensional spacetime a Lorentz boost corresponds with multiplication by the bivector $\gamma_0 v$, *i.e.,* $(x^0 + x^1 \sigma_1) \gamma_0 = x^0 \gamma_0 + x^1 \gamma_1$ by which $(x^0 + x^1 \sigma_1) \gamma_0 v = t' + \textbf{x}'$. A Lorentz transformation acts as a rotation in $\mathbb{G}^2$.

It follows that in $\mathbb{G}^{3,1}$, the Lorentz transformation in the $x$ direction is implemented using the rotor equation

$$x' = R x R^{-1}$$

with the rotor 

$$R= e^{-\sigma_1 \alpha /2}$$

with the rapidity $\alpha$ defined as $\tanh \alpha = \|\textbf{v}\|\,,$ where $e^{\sigma_1 \alpha} = \cosh \alpha + \sigma_1 \sinh \alpha/2$ since $\sigma_1^2 = 1$. In general, a Lorentz transformation is obtained with a rotor $R=e^{B \alpha /2}$ with a general unit bivector $B$. The spacelike bivectors $\sigma_i$ generate Lorentz boosts. The timelike bivectors $\gamma_1\gamma_2,\gamma_1 \gamma_3, \gamma_2\gamma_3$ generate rotations, since $(\gamma_i \gamma_j)^2=-1$ when $i\neq j$.

#### The Maxwell equations