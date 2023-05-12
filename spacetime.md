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
  
In special relativity, spacetime is described as the collection of spacetime events. In an inertial reference frame $S$, defined by a non-accelerating observer, we describe a spacetime event $x$ with the coordinates $x = (t,x,y,z)$. In an alternative inertial frame $S'$, defined by another non-accelerating observer moving with a velocity $\boldsymbol{v}$ with respect to the first observer, the event is described by a second set of coordinates $x = (t',x', y',z').$ These coordinates are related by the Lorentz boost

$$\begin{align}
t' &= \gamma(t - \|\boldsymbol{v}\| x / c^2)\,,\\
x' &= \gamma(x - \|\boldsymbol{v}\| t)\,,\\
y' &= y\,,\\
z' &= z\,,
\end{align}$$

assuming the velocity $\boldsymbol{v}$ is oriented in the $x$-direction and with the Lorentz factor 

$$ \gamma = \frac{1}{\sqrt{1-\boldsymbol{v}^2/c^2}}\,,$$

and the speed of light in vacuum $c$. More general boosts follow by rotating space. We observe that the Lorentz boost transforms space into time and time into space, unlike the more familiar rotations and Galilean transformations in Euclidean space. From hereon, we will use units for which the speed of light $c=1$. Space and time have the same dimensions and velocities are dimensionless.

The Lorentz transformation is analogous to rotations in Euclidean space. However, there exists a key distinction between rotations and Lorentz transformations. While rotations preserve the distance between two points,

$$\Delta \boldsymbol{x}^2 = \Delta x^2 + \Delta y^2 + \Delta z^2\,,$$

the spacetime distance between events

$$\Delta s^2 = \Delta t^2 - \Delta \boldsymbol{x}^2\,,$$

is invariant under the Lorentz transformation. The minus sign differentiates the time and space directions. 

Traditionally, special relativity describes the nature of spacetime using inertial coordinate frames. Geometric algebra attempts to develop a coordinate-free formulation, where the geometry of spacetime is written in terms of the language of multi-vectors.

### Spacetime geometric algebra
First, write the spacetime event $x$ in a given inertial reference frame $S$ as $x = (t,x^1,x^2,x^3)$ or equivalently

$$x = x^\mu \gamma_\mu = t \gamma_0 + x^i \gamma_i\,,$$

with the orthonormal spacetime basis $\gamma_\mu$ defined as 

$$\begin{align}
\gamma_0^2=1,\quad \gamma_0 \cdot \gamma_i = 0,\quad \gamma_i \cdot \gamma_j = - \delta_{ij}\,.
\end{align}$$

In these notes, we use the Einstein summation convention to sum over repeated Latin and Greek indices representing space and spacetime sums, *i.e.,* $x^\mu \gamma_\mu = \sum_{\mu=0}^3 x^\mu \gamma_\mu$ and $x^i \gamma_i = \sum_{i=1}^3 x^i \gamma_i\,.$ In this reference frame the vector $\gamma_0$ points in the time direction and the vectors $\gamma_i$ for $i=1,2,3$ point in the space directions. Given these basis vectors, we construct a basis for the spacetime algebra $\mathbb{G}^{1,3}$ using the standard geometric product (which is again anti-symmetric for orthogonal vectors, *i.e.,* $\gamma_\mu \gamma_\nu = - \gamma_\nu \gamma_\mu$ for $\mu \neq \nu$): 

- The basis includes a single scalar $1$. The scalar is timelike since $1^2=1$.
- The basis includes the four vectors $\gamma_0, \gamma_1, \gamma_2,$ and $\gamma_3$, signifying the timelike and spacelike directions. Note that the timelike basis vector squares to one, *i.e.,* $\gamma_0^2=+1$, and the spacial basis vectors square to minus one, *i.e.,* $\gamma_i^2=-1$.
- The basis includes of six bivectors $\gamma_1 \gamma_0, \gamma_2\gamma_0,\gamma_3\gamma_0,\gamma_1\gamma_2,\gamma_1\gamma_3,\gamma_2\gamma_3.$ The first three basis vectors are timelike, *i.e.,* as they square to one $(\gamma_i \gamma_0)^2=+1$ for $i=1,2,3$. The latter three are spacelike, *i.e.,* they square to minus one $(\gamma_i \gamma_j)^2=-1$ assuming $i \neq j\,.$
- The basis includes four trivectors $\gamma_0\gamma_1\gamma_2, \gamma_0\gamma_1\gamma_3, \gamma_0\gamma_2\gamma_3,\gamma_1\gamma_2\gamma_3\,.$ The first three are spacelike, *i.e.,* as they square to one $(\gamma_0 \gamma_i \gamma_j)^2=-1$ for $i \neq j$. The last one is timelike, *i.e.,* it squares to one $(\gamma_1\gamma_2\gamma_3)^2=+1\,.$
- Finally, the basis includes a single four-vector known as the pseudoscalar $I = \gamma_0\gamma_1\gamma_2\gamma_3\,.$ The pseudoscalar is spacelike since $I^2=-1\,.$

This $16$-dimensional algebra leads to a consistent formulation of special relativity, where the bivectors, trivectors, and the grade-$4$ pseudoscalar play an important role.

#### Spacetime split
Given an event in the spacetime algebra $\mathbb{G}^{1,3}$, we would like to split spacetime into space and time, recovering three-dimensional space and the corresponding geometric algebra $\mathbb{G}^3$. In the coordinate system of reference frame $S$, we write the event as the vector $x = x^\mu \gamma_\mu$ and perform the spacetime split by right multiplying the time vector by $\gamma_0$,

$$\begin{align}
x \gamma_0 &= x \cdot \gamma_0 + x \wedge \gamma_0 \\
&= t + \boldsymbol{x}\,.
\end{align}$$

We see that the time $t = x \cdot \gamma_0$ is a spacetime scalar and the relative position $\boldsymbol{x} = x \wedge \gamma_0 = x^i \gamma_i \wedge \gamma_0 = x^i \sigma_i$ with $\sigma_i = \gamma_i \gamma_0$ is a spacetime bivector. This split is motivated by the observation that the norm of a spacetime event is the invariant distance 

$$\begin{align}
x^2 &= x \gamma_0 \gamma_0 x\\
&=(x \cdot \gamma_0  + x \wedge \gamma_0)(x \cdot \gamma_0  - x \wedge \gamma_0)\\
&=(t  + \boldsymbol{x})(t  - \boldsymbol{x})\\
&=t^2 - \boldsymbol{x}^2\,.
\end{align}$$

The timelike bivectors of the spacetime algebra $\sigma_i$ act as the basis vectors of the induced space algebra $\mathbb{G}^3$. Indeed, the vectors are orthonormal

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

and thus generate a geometric algebra with the basis 

$$\{1, \sigma_1, \sigma_2, \sigma_3, \sigma_1 \sigma_2, \sigma_1\sigma_3,\sigma_2\sigma_3,\sigma_1\sigma_2\sigma_3\}\,.$$

The bivectors of the space algebra are the spacelike bivectors of the underlying spacetime algebra, 

$$\sigma_i\sigma_j= -\gamma_i\gamma_j\,.$$

The six bivectors of the spacetime algebra nicely capture the vectors and pseudovectors of the induced space algebra. The space pseudoscalar coincides with the pseudoscalar of the spacetime algebra

$$\sigma_1\sigma_2\sigma_3=\gamma_1\gamma_0\gamma_2\gamma_0\gamma_3\gamma_0 = \gamma_0\gamma_1\gamma_2\gamma_0^2\gamma_3=\gamma_0\gamma_1\gamma_2\gamma_3 = I\,.$$

From the space algebra we see that the vectors are dual to the pseudovectors, *i.e.,*

$$\begin{align}
\sigma_i^* &=\sigma_i I^{-1} \\
&= \gamma_i \gamma_0 \gamma_3 \gamma_2 \gamma_1 \gamma_0\\
&=- \gamma_i \gamma_3 \gamma_2 \gamma_1\\
&= \gamma_i \gamma_1 \gamma_2 \gamma_3\,,
\end{align}$$

by which $\sigma_1^* =-\gamma_2 \gamma_3 = \sigma_2 \sigma_3,$ $\sigma_2^*=-\gamma_3 \gamma_1=\sigma_3 \sigma_1$ and $\sigma_3^*=-\gamma_1\gamma_2=\sigma_1\sigma_2\,.$

The spacetime vectors and pseudovectors do not appear in this construction. We thus conclude that the even subalgebra of the spacetime algebra $\mathbb{G}^{1,3}$ is isomorphic with the three-dimensional vector algebra $\mathbb{G}^3$.

Given a worldline $x(\tau)$ with the proper time along the worldline $\tau$, define the proper velocity $v= \frac{\mathrm{d}x}{\mathrm{d}\tau}$, where the proper velocity is a unit vector, *i.e.,* $v^2=1$. We can relate the proper velocity to the inertial frame velocity $\boldsymbol{v} = \frac{\mathrm{d}\boldsymbol{x}}{\mathrm{d}t}$ with the spacetime split, 

$$ v \gamma_0 = \frac{\mathrm{d}}{\mathrm{d} \tau}(x \gamma_0) = \frac{\mathrm{d}}{\mathrm{d}\tau}(t+\boldsymbol{x})$$

by which $\frac{\mathrm{d}t}{\mathrm{d}\tau} = v\cdot \gamma_0$ and $\frac{\mathrm{d}\boldsymbol{x}}{\mathrm{d}\tau}= v \wedge \gamma_0$ and thus

$$\boldsymbol{v} = \frac{\mathrm{d}\boldsymbol{x}}{\mathrm{d}t} = \frac{\mathrm{d}\boldsymbol{x}}{\mathrm{d}\tau}\frac{\mathrm{d}\tau}{\mathrm{d}t} = \frac{v \wedge \gamma_0}{v\cdot \gamma_0}.$$

This construction for the derivative $\boldsymbol{v}$ is manifestly invariant under reparametrizations of the worldline.

#### Lorentz transformations
Different observers in different inertial reference frames split spacetime differently. Let's first consider the $2$-dimensional spacetime algebra $\mathbb{G}^{1,1}$. An observer with a relative velocity $\boldsymbol{v}$ in the $x$-direction, defines a reference frame $S'$ where the timelike basis vector is given by the four-velocity $v = \gamma (\gamma_0 +  \|\boldsymbol{v}\|\gamma_1)$. The Lorentz factor ensures that the proper velocity has unit norm, *i.e.,* 

$$\begin{align}
v^2 &= v \gamma_0 \gamma_0 v \\
&=\gamma^2(\gamma_0 \cdot \gamma_0 + \|\boldsymbol{v}\| \gamma_1 \wedge \gamma_0)(\gamma_0 \cdot \gamma_0 - \|\boldsymbol{v}\| \gamma_1 \wedge \gamma_0)\\
&=\gamma^2 (1 - \boldsymbol{v}^2) \\
&= 1\,.
\end{align}$$

The spacetime split in the reference frame $S'$ takes the form 

$$\begin{align}
x v 
&=  x \cdot v + x \wedge v\\
&= t' + \boldsymbol{x}'\,,
\end{align}$$

with the time 

$$\begin{align}
t' &= x \cdot v \\
&=x^\mu \gamma_\mu \cdot v \\
&= \gamma  (x^0 \gamma_0 \cdot \gamma_0 +\|\boldsymbol{v}\| x^1 \gamma_1 \cdot \gamma_1)\\
&= \gamma  (x^0 -\|\boldsymbol{v}\| x^1)\,,
\end{align}$$ 

where $\mu=0,1$, and the relative position 

$$\begin{align}
\boldsymbol{x}' &= x \wedge v\\
&=x^\mu \gamma_\mu \wedge v \\
&= \gamma \|\boldsymbol{v}\| x^0 \gamma_0 \wedge \gamma_1 + \gamma x^1 \gamma_1 \wedge \gamma_0 \\
&= \gamma( x^1 - \|\boldsymbol{v}\| x^0) \sigma_1\,.
\end{align}$$

These are the Lorentz boosts restricted to the $(t,x)$-plane. As a consequence, a Lorentz boost of a spacetime event in $\mathbb{G}^{1,1}$ is implemented as the multiplication by the multi-vector $\gamma_0 v$, *i.e.,* $(t+\boldsymbol{x}) \gamma_0 v = t' + \boldsymbol{x}'$. A Lorentz boost in $\mathbb{G}^{1,1}$ is analogous to a rotation in the geometric algebra $\mathbb{G}^2$.

In $\mathbb{G}^{1,3}$, the Lorentz boost in the $x$ direction assumes the form

$$x' = R_\alpha x R_{\alpha}^{-1}$$

with the rotor corresponding to the Lorentz boost

$$R_\alpha= e^{-\sigma_1 \alpha /2}$$

where the rapidity $\alpha$, defined by $\tanh \alpha = \|\boldsymbol{v}\|\,,$ is a convenient parametrization of the magnitude of the relative velocity vector. Explicitly, 

$$e^{\sigma_1 \alpha} = \cosh \alpha + \sigma_1 \sinh \alpha$$ 

since $\sigma_1^2 = 1$. Upon expanding the exponentials, we obtain the familiar transformation 

$$\begin{align}
t' &= t \cosh \alpha - x \sinh \alpha\,,\\
x' &= x \cosh \alpha - t \sinh \alpha\,,\\
y' &= y\,,\\
z' &= z\,,
\end{align}$$

using the identities $\sigma_1 \gamma_0= \gamma_1 = - \gamma_0 \sigma_1\,,$ $\sigma_1 \gamma_1= \gamma_0 = - \gamma_1 \sigma_1\,,$ $\sigma_1 \gamma_2 = \gamma_2 \sigma_1\,,$ and $\sigma_1 \gamma_3= \gamma_3 \sigma_1\,.$ A general Lorentz boost is implemented by the equation

$$x' = e^{-\hat{\boldsymbol{v}} \alpha /2} x e^{\hat{\boldsymbol{v}} \alpha /2}\,,$$

with $\tanh \alpha = \|\boldsymbol{v}\|$ and $\hat{\boldsymbol{v}}^2=1$. A Lorentz transformation includes both spacetime boosts and space rotations, implemented by the rotor equation

$$x' = e^{-B \alpha /2} x e^{B \alpha /2} $$

with the general unit bivector $B$ and the magnitude $\alpha$. The timelike bivectors $\sigma_i = \gamma_i \gamma_0$ generate the Lorentz boosts and the spacelike bivectors $\gamma_1\gamma_2,\gamma_1 \gamma_3, \gamma_2\gamma_3$ generate the rotations, as the first are timelike $(\gamma_i \gamma_0)^2=+1$ and the latter are spacelike $(\gamma_i \gamma_j)^2=-1$ for $i\neq j$.

The rotor parametrization of the Lorentz transformation makes it easy to show the invariance of the spacetime interval, *i.e.,*

$$\begin{align}
(x')^2 &= e^{-B \alpha /2 } x e^{B \alpha /2} e^{-B \alpha/2}x e^{B \alpha / 2}\\
&= e^{-B \alpha /2 } x^2 e^{B \alpha / 2}\\
&= x^2\,.
\end{align}$$

#### The Maxwell equations
We can use these considerations to study Maxwell's theory of electromagnetism in spacetime. Firstly, define the vector derivative on spacetime

$$\nabla = \gamma^\mu \partial_\mu\,,$$

with $\partial_\mu = \frac{\partial}{\partial x^\mu}$, in units for which the speed of light in vacuum $c=1$. The spacetime split is achieved by multiplying $\nabla$ on the right by $\gamma_0$ 

$$\nabla \gamma_0 = (\gamma^0 \partial_t + \gamma^i \partial_i)\gamma_0 = \partial_t - \sigma_i \partial_i = \partial_t - \boldsymbol{\nabla}\,,$$

with $\sigma_i = \gamma_i \gamma_0$ and indices are raised and lowered with the Minkowski matric $\eta_{\mu \nu} = \text{diag}(1,-1,-1,-1)\,.$ As we saw in the study of Euclidean geometric algebras, the Maxwell equations assume the neat form

$$\partial_t F + \boldsymbol{\nabla}F = \rho - \boldsymbol{J}\,,$$

with the field strength $F=\boldsymbol{E} + I \boldsymbol{B}$, the electric charge density $\rho$ and the electric current density $\boldsymbol{J}$ in units for which the speed of light in vacuum $c=1$. Note that the field strength is a spacetime bivector, for which the timelike bivectors correspond to the electric and the spacelike bivectors correspond to the magnetic field components. 

Introduce the spacetime current $J = \rho \gamma_0 + J_i \gamma_i$, by the spacetime split, 

$$\rho = J \cdot \gamma_0\,,\quad \boldsymbol{J} = J \wedge \gamma_0\,,$$

we find a very neat covariant formulation of the Maxwell equations in spacetime

$$\nabla F = J\,.$$

Note that this spacetime current differs from the one we used in the formulation of the Maxwell equations in three-dimensional Euclidean space. This formulation is truly on spacetime embedding it manifestly in special relativity (where it belongs).

The Maxwell equation in this form directly leads to the conservation of charge. After applying the vector derivative,

$$\nabla^2 F = \nabla J = \nabla \cdot J + \nabla \wedge J\,,$$

we directly obtain current conservation

$$\nabla \cdot J =\frac{\partial \rho}{\partial t} + \boldsymbol{\nabla}\cdot \boldsymbol{J} = 0\,,$$

by looking for the scalar part. The Laplace operator preserves the grades of multi-vectors.

Also, the equation $\nabla F=J$ leads to the observation 

$$\nabla \cdot F = J \text{ and } \nabla \wedge F = 0\,,$$ 

as the left-hand side is a spacetime vector. In tensor language, these two identities are given by

$$\partial_\mu F^{\mu\nu} = J^\nu \text{ and } \epsilon^{\mu \nu \rho \sigma} \partial_\nu F_{\rho \sigma}=0\,.$$

Geometric algebra describes in one equation what tensor algebra does in two.

As $\nabla \wedge F =0$, we can write the field strength in terms of the vector potential

$$F = \nabla \wedge A\,.$$

In terms of the vector potential, the Maxwell equations read

$$\nabla \cdot (\nabla \wedge A) = \nabla(\nabla \wedge A)= \nabla^2 A - \nabla(\nabla \cdot A) = J\,.$$

Note that $A$ has some residual gauge freedom, since $A \mapsto A + \nabla \lambda$ for a spacetime scalar $\lambda$ leaves the field strength unchanged, *i.e.,*

$$ F \mapsto \nabla \wedge (A + \nabla \lambda)=\nabla \wedge A+ \nabla \wedge \nabla \lambda= F\,.$$

Here, we use the fact that $\nabla^2 \lambda$ is a scalar quantity by which $\nabla \wedge \nabla\lambda =0\,.$

In the Lorentz gauge, 

$$\nabla \cdot A =0\,,$$

the field strength $F = \nabla A$ and the Maxwell equation assumes the form 

$$\nabla F = \nabla^2 A = J\,.$$

Note that the Lorentz condition does not completely fix the gauge, as $A \mapsto A + \nabla \lambda$ with $\nabla^2 \lambda = 0$ satisfies the Lorentz condition and preserves the field strength.

Finally, note that while the electric and magnetic fields in the spacetime split appear as different objects (vectors and pseudovectors), from the perspective of the spacetime algebra, they are treated on the same footing. Both are simply spacetime bivectors. Under a Lorentz boost, $F' = R F R^{-1}\,,$ the electric and magnetic fields rotate into each other. One observer's electric field may appear as a magnetic field to another observer in the appropriate inertial reference frame.