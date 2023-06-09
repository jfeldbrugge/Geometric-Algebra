---
title: Geometric Algebra
author: Job Feldbrugge
header-includes:
    <link rel = "icon" href = "figures/icon.png" type = "image/x-icon"> 
    <div class="topnav">
      <a href="https://jfeldbrugge.github.io/">Home</a>
      <a href="https://jfeldbrugge.github.io/Projects-and-Codes/">Projects and Code</a>
    </div>
---

Geometric algebra is an extension of vector algebra introducing the notion of a multi-vector, uniting different fields of mathematics in a single language. In these notes, I try to learn the subject following *"A Survey of Geometric Algebra and Geometric Calculus"* by Alan Macdonald.

**Definition:** *The geometric algebra $\mathbb{G}^n$ is an extension of the $n$-dimensional vector space $\mathbb{R}^n$. The geometric algebra $\mathbb{R}^n \subset \mathbb{G}^n$ is an associative algebra with a unit $1$, satisfying the four conditions:*

* G1: $A(B+C) = AB + AC$, $(B+C)A = BA + CA$,
* G2: $(aA)B = A(aB)= a(AB)$,
* G3: $(AB)C = A(BC)$,
* G4: $1A=A1=A$,

*with the scalar $a \in \mathbb{R}$ and the multi-vectors $A, B, C \in \mathbb{G}^n.$ In addition, this geometric product satisfies two conditions linking the geometric algebra $\mathbb{G}^n$ to the vector space $\mathbb{R}^n$:*

* G5: $\boldsymbol{u}\boldsymbol{u}=\boldsymbol{u}\cdot\boldsymbol{u} = \|\boldsymbol{u}\|^2$ *for all vectors* $\boldsymbol{u} \in \mathbb{R}^n$,

*by which nonzero vectors have an inverse in $\mathbb{G}^n$ given by $\boldsymbol{u}^{-1}=\boldsymbol{u}/\|\boldsymbol{u}\|$ and a way to construct the multivectors in $\mathbb{G}^n$ from the vectors in $\mathbb{R}^n$*

* G6: *Every orthonormal basis of $\mathbb{R}^n$ determines a canonical basis for the vector space $\mathbb{G}^n$ (to be constructed below).*

From these simple conditions, the theory develops, leading to a richer way to do geometry and calculus.

In particular, from the condition G5 we obtain an identity relating the inner product to the geometric product for general vectors
$$\begin{align}
\boldsymbol{u}\cdot\boldsymbol{v} 
&= \frac{1}{2}((\boldsymbol{u} +  \boldsymbol{v})\cdot(\boldsymbol{u} +  \boldsymbol{v}) - \boldsymbol{u}\cdot\boldsymbol{u} -\boldsymbol{v} \cdot \boldsymbol{v})\\
&= \frac{1}{2}((\boldsymbol{u} +  \boldsymbol{v})^2- \boldsymbol{u}\boldsymbol{u} -\boldsymbol{v}\boldsymbol{v})\\
&= \frac{1}{2}(\boldsymbol{u} \boldsymbol{v} + \boldsymbol{v}\boldsymbol{u})\,.
\end{align}$$
When two vectors are orthogonal, *i.e.,* $\boldsymbol{u} \cdot \boldsymbol{v}=0$, the geometric product of the vectors is skew-symmetric 
$$ \boldsymbol{u} \boldsymbol{v} = -\boldsymbol{v} \boldsymbol{u}\,.$$

The product of two orthogonal vectors is neither a scalar nor a vector, since its square is negative $(\boldsymbol{u}\boldsymbol{v})^2=\boldsymbol{u}\boldsymbol{v}\boldsymbol{u}\boldsymbol{v}=-\boldsymbol{u}\boldsymbol{u} \boldsymbol{v}\boldsymbol{v}=-\|\boldsymbol{u}\|^2 \|\boldsymbol{v}\|^2$. It is an object known as a bi-vector representing an oriented area element (spanned by $\boldsymbol{u}$ and $\boldsymbol{v}$), the first instance of an element of the geometric algebra $\mathbb{G}^n$ that is not present in vector algebra $\mathbb{R}^n$.

Condition G5 shows how the vector norm ankers the geometric product to $\mathbb{R}^n$, and leads to an alternative definition of the inner product of vectors as the symmetrized product,

$$\boldsymbol{u}\cdot \boldsymbol{v} = \frac{1}{2}(\boldsymbol{u}\boldsymbol{v} + \boldsymbol{v} \boldsymbol{u})\,.$$

The anti-symmetrized product is known as the outer product of the vectors 

$$\boldsymbol{u}\wedge \boldsymbol{v} = \frac{1}{2}(\boldsymbol{u}\boldsymbol{v} - \boldsymbol{v} \boldsymbol{u})\,.$$

We will see that this outer product coincides with the outer product of vector analysis.

From these definitions, it follows that the geometric product of two vectors can be expressed in terms of the more familiar inner and outer products

$$\boldsymbol{u}\boldsymbol{v} = \boldsymbol{u}\cdot\boldsymbol{v} + \boldsymbol{u}\wedge \boldsymbol{v}\,,$$

and

$$\boldsymbol{v}\boldsymbol{u} = \boldsymbol{u}\cdot\boldsymbol{v} - \boldsymbol{u}\wedge \boldsymbol{v}\,.$$

Note that the geometric product of vectors is invertible, unlike the inner or outer products that constitute them. For parallel vectors (with $\boldsymbol{u} = a \boldsymbol{v}$ with $a \in \mathbb{R}$), the geometric product reduces to the inner product $\boldsymbol{u}\boldsymbol{v} = \boldsymbol{u}\cdot \boldsymbol{v}$ (using condition G2). For orthogonal vectors, the geometric product reduces to the outer product $\boldsymbol{u}\boldsymbol{v} = \boldsymbol{u}\wedge \boldsymbol{v}$. For a general set of vectors, the geometric product leads to a multi-vector, where the scalar part represents the inner and the bi-vector part represents the outer product.

To develop intuition, we briefly study the geometric implications of this construction on two- and three-dimensional Euclidean space.

### Two-dimensional plane
Consider the two-dimensional plane $\mathbb{R}^2$ spanned by the orthonormal unit vectors $\boldsymbol{e}_1=\hat{\boldsymbol{x}}$ and $\boldsymbol{e}_2=\hat{\boldsymbol{y}}$. Geometric algebra is spanned by the elements 

$$\{1, \boldsymbol{e}_1, \boldsymbol{e}_2, \boldsymbol{e}_1\boldsymbol{e}_2\}\,,$$ 

where $1$ is the unit scalar, $\boldsymbol{e}_1$ and $\boldsymbol{e}_2$ are the unit vectors and $\boldsymbol{e}_1\boldsymbol{e}_2$ is the unique bi-vector representing an oriented area element. This is the *canonical basis* of the geometric algebra $\mathbb{G}^2$. We cannot generate more bases elements, as the unit vectors $\boldsymbol{e}_1$ and $\boldsymbol{e}_2$ are orthogonal and objects consisting of the geometric product of three or more bases elements of $\mathbb{R}^2$ can be reduced to these four combinations using the anti-commutative property, *e.g.*, $\boldsymbol{e}_1\boldsymbol{e}_2\boldsymbol{e}_1=-\boldsymbol{e}_1\boldsymbol{e}_1\boldsymbol{e}_2=-\boldsymbol{e}_2$. A multi-vector is an object of the form 

$$A = a + b\ \boldsymbol{e}_1 + c\ \boldsymbol{e}_2 + d\ \boldsymbol{e}_1\boldsymbol{e}_2\,,$$

with for real numbers $a,b,c,d \in \mathbb{R}$. The product of two multi-vectors follows from the associative nature of the geometric product and the multiplication table of the bases elements of $\mathbb{R}^2$, $\boldsymbol{e}_1^2=\boldsymbol{e}_2^2=1$ and $\boldsymbol{e}_1\boldsymbol{e}_2=-\boldsymbol{e}_1\boldsymbol{e}_2$, as we saw above. 

Explicitly, the geometric product of two vectors takes the form

$$\begin{align}
\boldsymbol{u} \boldsymbol{v} 
&= (a_1 \boldsymbol{e}_1 + b_1 \boldsymbol{e}_2)(a_2 \boldsymbol{e}_1 + b_2 \boldsymbol{e}_2)\\
&=(a_1 a_2 + b_1 b_2) + (a_1 b_2 - b_1 a_2)\boldsymbol{e}_1\boldsymbol{e}_2\\
&=\boldsymbol{u}\cdot\boldsymbol{v} + \boldsymbol{u}\wedge \boldsymbol{v}\,,
\end{align}$$

where we identify the familiar inner product $\boldsymbol{u}\cdot\boldsymbol{v}=a_1 a_2 + b_1 b_2 = \|\boldsymbol{u}\| \|\boldsymbol{v}\| \cos\theta$ written in terms of the angle between the two vectors $\theta$. The outer product 

$$\begin{align}
\boldsymbol{u}\wedge \boldsymbol{v} &= (a_1 b_2 - b_1 a_2)\boldsymbol{e}_1\boldsymbol{e}_2 \\
&= \|\boldsymbol{u}\| \|\boldsymbol{v}\| \sin \theta \ \boldsymbol{e}_1\boldsymbol{e}_2
\end{align}$$ 

is the signed area of the parallelogram spanned by the two vectors $\boldsymbol{u}$ and $\boldsymbol{v}.$ 

As $\boldsymbol{e}_1$ and $\boldsymbol{e}_2$ are orthogonal, the bi-vector $\boldsymbol{e}_1\boldsymbol{e}_2$ squares to $-1$, from which it follows that we can identify this bi-vector with the square root of unity $\boldsymbol{e}_1\boldsymbol{e}_2 = \boldsymbol{i}=\sqrt{-1}$. The complete product of basis elements in $\mathbb{R}^n$ is generally an important element in geometric algebra, as it is the only $n$-vector in the canonical basis, denoted as the pseudoscalar of the algebra $\boldsymbol{I}=\boldsymbol{e}_1\boldsymbol{e}_2\dots\boldsymbol{e}_n$. 

In the two-dimensional setting, geometric algebra unifies two-dimensional vector analysis with complex analysis, $A=(a + \boldsymbol{i}\ d) + (b\ \boldsymbol{e}_1 + c\ \boldsymbol{e}_2)$. Two notions of vectors in the plane with a distinct set of products that normally do not communicate with each other. In geometric algebra the interactions between the vectors and complex numbers are central. Writing the outer product of two vectors as $\boldsymbol{u}\wedge \boldsymbol{v} = \|\boldsymbol{u}\|\|\boldsymbol{v}\| \sin\theta\, \boldsymbol{i}$, with the traditional cross-product $\boldsymbol{u}\times \boldsymbol{v} = -\boldsymbol{u}\wedge\boldsymbol{v}\ \boldsymbol{i} = \|\boldsymbol{u}\|\|\boldsymbol{v}\| \sin\theta$, the geometric product of two vectors assumes the form

$$ 
\begin{align}
\boldsymbol{u} \boldsymbol{v} &= \|\boldsymbol{u}\| \|\boldsymbol{v}\| (\cos \theta + \boldsymbol{i} \sin \theta)\\
&= \|\boldsymbol{u}\| \|\boldsymbol{v}\| e^{\boldsymbol{i}\ \theta}\,,
\end{align}
$$

independent of the bases elements, where we define the exponentiation of a bi-vector using Euler's identity $e^{\boldsymbol{i}\ \theta}=\cos\theta + \boldsymbol{i}\sin \theta$. 

#### Rotations
The addition of both complex numbers and vectors acts componentwise. The product of two complex numbers $z_1=a_1 + \boldsymbol{i}\ d_1,$ $z_2=a_2 +\boldsymbol{i}\ d_2$, is implemented as the product of the absolute value and a rotation of the arguments

$$\begin{align}
z_1 z_2 &= (a_1 a_2 - d_1 d_2) + (a_1 d_2 + d_1 a_2)\ \boldsymbol{i}\\
&= |z_1||z_2| e^{\boldsymbol{i}(\theta_1+\theta_2)}\,,
\end{align}$$

with the polar representation $z_1=|z_1|e^{\boldsymbol{i}\ \theta_1},$ $z_2=|z_2|e^{\boldsymbol{i}\ \theta_2}$. The product of two vectors was discussed above. When multiplying a complex number $z=a+\boldsymbol{i}\ d$ with a vector $\boldsymbol{u} = b\ \boldsymbol{e}_1 + c\ \boldsymbol{e}_2$, we find a rotation

$$\begin{align}
z \boldsymbol{u} &= (a + \boldsymbol{i}\ d)(b\ \boldsymbol{e}_1 + c\ \boldsymbol{e}_2)\\
&= (ab + dc)\boldsymbol{e}_1 + (ac- db)\boldsymbol{e}_2\\
&= |z| \left[(b \cos \theta +c \sin\theta)\boldsymbol{e}_1 + (- b \sin\theta + c \cos \theta )\boldsymbol{e}_2\right]\,,
\end{align}$$

writing the complex number in its polar decomposition $z=|z| e^{\boldsymbol{i}\ \theta} = |z|\cos \theta + \boldsymbol{i}\ |z| \sin \theta$. The inverse multiplication $\boldsymbol{u}z$ yields a rotation by the same angle in the opposite direction $\theta \mapsto -\theta$. More generally, we can write a rotation of a vector $\boldsymbol{u}$ by an angle $\theta$ more symmetrically using the conjugation

$$\boldsymbol{u}_{rot} = e^{-\boldsymbol{i}\ \theta/2}\ \boldsymbol{u}\ e^{\boldsymbol{i}\ \theta /2}\,,$$

where the multi-vector $R_\theta = e^{-\boldsymbol{i}\ \theta/2}$ is known as the rotor, with its inverse $R_\theta^{-1}=R_{-\theta}$ as

$$\begin{align}
R_\theta  R_\theta^{-1} 
&= (\cos (\theta/2) - \boldsymbol{i}\ \sin (\theta/2)) (\cos (\theta/2) + \boldsymbol{i}\ \sin (\theta/2))\\
&= \cos^2 (\theta/2) + \sin^2(\theta/2) =1\,.
\end{align}$$

As we will see, this notion of rotation generalizes to higher-dimensional spaces. The conjugation of a vector with a rotor preserves the length of the vector, as

$$\begin{align}
\| R_\theta \boldsymbol{u} R_\theta^{-1}\|^2 &= R_\theta \boldsymbol{u} R_\theta^{-1} R_\theta \boldsymbol{u} R_\theta^{-1}\\
&= R_\theta \boldsymbol{u} \boldsymbol{u} R_\theta^{-1}\\
&=  \|\boldsymbol{u}\|^2 R_\theta  R_\theta^{-1}\\
&=  \|\boldsymbol{u}\|^2\,.
\end{align}$$

Rotors are the multi-vectors resulting from the geometric products of unit vectors.

#### Normals
It follows that the product of a vector with the pseudoscalar yields its normal 

$$\boldsymbol{i} (a \boldsymbol{e}_1 + b \boldsymbol{e}_2)  = a \boldsymbol{e}_1 \boldsymbol{e}_2 \boldsymbol{e}_1 + b \boldsymbol{e}_1 \boldsymbol{e}_2 \boldsymbol{e}_2 = b \boldsymbol{e}_1 - a \boldsymbol{e}_2.$$ 

As normals are very common in geometry, let's write it in terms of the duality operator

$$ \boldsymbol{u}^* = \boldsymbol{u}\ \boldsymbol{i}^{-1}\,,$$

with the inverse of the pseudoscalar $\boldsymbol{i}^{-1} = \boldsymbol{e}_2\boldsymbol{e}_1 = - \boldsymbol{i}$. Using the duality operator, we can rewrite the definition of the cross-product in terms of the outer product

$$\boldsymbol{u}\times \boldsymbol{v} = (\boldsymbol{u}\wedge \boldsymbol{v})^*\,.$$

#### Projections and reflections
Another central operation in geometry is reflections. Given two vectors $\boldsymbol{u}$ and $\boldsymbol{v}$, we can decompose the first one into a component parallel and orthogonal to the second, *i.e.,* $\boldsymbol{u} = \boldsymbol{u}_{\|} + \boldsymbol{u}_\perp$. In the language of geometric algebra, we obtain a very simple construction

$$\begin{align}
\boldsymbol{u}_{\|} &= (\boldsymbol{u}\cdot \boldsymbol{v})\boldsymbol{v}^{-1}\,,\\
\boldsymbol{u}_{\perp} &= (\boldsymbol{u}\wedge \boldsymbol{v})\boldsymbol{v}^{-1}\,,
\end{align}$$

which can be proven by substituting $\boldsymbol{u} = \boldsymbol{u}_{\|} + \boldsymbol{u}_\perp$ in the above equations with the conditions $\boldsymbol{u}_\perp \cdot \boldsymbol{v}=0$ and $\boldsymbol{u}_{\|} \wedge \boldsymbol{v}=0$. The reflection of a vector $\boldsymbol{u}$ through the line spanned by $\boldsymbol{v}$ is given by the conjugation of $\boldsymbol{u}$ by $\boldsymbol{v}$, *i.e.,* given $\boldsymbol{u} = \boldsymbol{u}_{\|} + \boldsymbol{u}_\perp$, the reflection of $\boldsymbol{u}$ in the line associated to $\boldsymbol{v}$ yields

$$\begin{align}
\boldsymbol{u}_{ref} 
&= \boldsymbol{u}_{\|} - \boldsymbol{u}_\perp\\
&= (\boldsymbol{u}\cdot \boldsymbol{v})\boldsymbol{v}^{-1} -(\boldsymbol{u}\wedge \boldsymbol{v})\boldsymbol{v}^{-1}\\
&= (\boldsymbol{u}\cdot \boldsymbol{v} - \boldsymbol{u}\wedge \boldsymbol{v})\boldsymbol{v}^{-1}\\
&= \boldsymbol{v}\boldsymbol{u}\boldsymbol{v}^{-1}\,.
\end{align}$$

We saw above that the rotor $R_\theta$ can be written as the geometric product of two unit vectors $\boldsymbol{v},\boldsymbol{w}$ with an angular separation $-\theta/2$. It thus follows that every rotation is the result of two reflections 

$$ \boldsymbol{u}_{rot} = \boldsymbol{v}(\boldsymbol{w} \boldsymbol{u} \boldsymbol{w}^{-1}) \boldsymbol{v}^{-1}\,.$$

#### Volumes
The area of a bi-vector $\boldsymbol{B}=\boldsymbol{b}_1 \boldsymbol{b}_2$ is defined as the volume of the space spanned by the vectors $\| \boldsymbol{B}\|=\|\boldsymbol{b}_1\|\|\boldsymbol{b}_2\|$.

### Three-dimensional space
Consider the orthonormal basis $\{\boldsymbol{e}_1,\boldsymbol{e}_2,\boldsymbol{e}_3\}$ of the three-dimensional Euclidean plane $\mathbb{R}^3$. The corresponding geometric algebra $\mathbb{G}^3$ is spanned by the elements 

$$\{1, \boldsymbol{e}_1, \boldsymbol{e}_2, \boldsymbol{e}_3, \boldsymbol{e}_1\boldsymbol{e}_2, \boldsymbol{e}_1\boldsymbol{e}_3, \boldsymbol{e}_2\boldsymbol{e}_3, \boldsymbol{e}_1\boldsymbol{e}_2\boldsymbol{e}_3\}$$

consisting of the unit scalar, three vectors corresponding to the three independent directions, three bi-vectors corresponding to the three independent two-dimensional hyperplanes, and a unique tri-vector corresponding to the volume element. 

The product of two vectors takes the form

$$\begin{align}
\boldsymbol{u}\boldsymbol{v} 
&= (a_1 \boldsymbol{e}_1+b_1 \boldsymbol{e}_2+c_1 \boldsymbol{e}_1) (a_2 \boldsymbol{e}_1+b_2 \boldsymbol{e}_2+c_2 \boldsymbol{e}_1) \\
&= (a_1 a_2 + b_1 b_2 + c_1 c_2) + (a_1 b_2 - b_1 a_2) \boldsymbol{e}_1\boldsymbol{e}_2+ (a_1 c_2 - c_1 a_2)\boldsymbol{e}_1\boldsymbol{e}_3+ (b_1 c_2 - c_1 b_2)\boldsymbol{e}_2\boldsymbol{e}_3\\
&=\boldsymbol{u}\cdot\boldsymbol{v} + \boldsymbol{u}\wedge \boldsymbol{v}\,,
\end{align}$$

where we again can identify the inner product $\boldsymbol{u} \cdot \boldsymbol{v} = a_1 a_2 + b_1 b_2 + c_1 c_2$ and the outer product $\boldsymbol{u}\wedge \boldsymbol{v} = (a_1 b_2 - b_1 a_2) \boldsymbol{e}_1\boldsymbol{e}_2+ (a_1 c_2 - c_1 a_2)\boldsymbol{e}_1\boldsymbol{e}_3+ (b_1 c_2 - c_1 b_2)\boldsymbol{e}_2\boldsymbol{e}_3$. 

The bi-vectors, corresponding to oriented area elements, span a space whose elements are known as pseudovectors. A pseudovector is of the form $\boldsymbol{B} = a\ \boldsymbol{B}_1 + b\ \boldsymbol{B}_2 + c\ \boldsymbol{B}_3$ where $\boldsymbol{B}_1=\boldsymbol{e}_2 \boldsymbol{e}_3,$ $\boldsymbol{B}_2 = \boldsymbol{e}_3 \boldsymbol{e}_1$ and $\boldsymbol{B}_3 = \boldsymbol{e}_1 \boldsymbol{e}_2$ with the product $\boldsymbol{B}_i \boldsymbol{B}_j = -\delta_{ij} - \epsilon_{ijk}\boldsymbol{B}_k$ with the Kronneker delta  $\delta_{ij}$ and the Levi-Civita symbol $\epsilon_{ijk}$. This coincides with the pseudovectors known in physics since they are invariant under the parity operation $\boldsymbol{e}_i\mapsto - \boldsymbol{e}_i$. The product of two pseudovectors yields the multi-vector

$$\begin{align}
\boldsymbol{A} \boldsymbol{B} &= (a_1\ \boldsymbol{B}_1 + b_1\ \boldsymbol{B}_2 + c_1\ \boldsymbol{B}_3)(a_2\ \boldsymbol{B}_1 + b_2\ \boldsymbol{B}_2 + c_2\ \boldsymbol{B}_3)\\
&= -(a_1 a_2 + b_1 b_2 + c_1 c_2) - (b_1 c_2 - c_1 b_2) \boldsymbol{B}_1 - (c_1 a_2 - a_1 c_2) \boldsymbol{B}_2  - (a_1 b_2 - b_1 a_2) \boldsymbol{B}_3\,.
\end{align}$$

The bi-vectors can be associated to the quaternions $\boldsymbol{i} = \boldsymbol{B}_1,$ $\boldsymbol{j} = -\boldsymbol{B}_2$, $\boldsymbol{k}=\boldsymbol{B}_3$.

The canonical tri-vector is known as the pseudoscalar $\boldsymbol{I} = \boldsymbol{e}_1 \boldsymbol{e}_2 \boldsymbol{e}_3$, representing the oriented volume element. The exterior product of three vectors 

$$\begin{align}
\boldsymbol{u}\wedge \boldsymbol{v} \wedge \boldsymbol{w} 
&= \boldsymbol{u} \cdot (\boldsymbol{v} \times \boldsymbol{w})\\
&= \alpha\ \boldsymbol{I}\,,
\end{align}$$

with $|\alpha|$ the volume of the parallelepiped spanned by the three vectors (and the cross-product is defined below). The sign is the orientation of the triple $(\boldsymbol{u}, \boldsymbol{v}, \boldsymbol{w})$. 

The geometric product of the pseudoscalar with a vector is a bi-vector, $\boldsymbol{e}_1 \boldsymbol{I} = \boldsymbol{B}_1,$ $\boldsymbol{e}_2 \boldsymbol{I} = \boldsymbol{B}_2,$ and $\boldsymbol{e}_3 \boldsymbol{I} = \boldsymbol{B}_3$. Note that the pseudovector is normal to the original vector (together they span the space $\boldsymbol{I}$). When acting on the pseudovectors, we retrieve the normal vectors, $\boldsymbol{B}_1 \boldsymbol{I}= -\boldsymbol{e}_1,$ $\boldsymbol{B}_2 \boldsymbol{I}= - \boldsymbol{e}_2,$ and $\boldsymbol{B}_3 \boldsymbol{I}= -\boldsymbol{e}_3$. Hence, the pseudoscalar maps the vectors to the pseudovectors and pseudovectors to vectors. This is again nicely implemented by the duality operator

$$\boldsymbol{u}^* = \boldsymbol{u}\ \boldsymbol{I}^{-1}\,,$$

with the inverse $\boldsymbol{I}^{-1}=\boldsymbol{e}_3 \boldsymbol{e}_2 \boldsymbol{e}_1 = -\boldsymbol{I}$.

The multiplication of the bases elements follows the rule

$$\boldsymbol{e}_i \boldsymbol{e}_j = \delta_{ij} + \boldsymbol{I} \epsilon_{ijk}\boldsymbol{e}_k\,,$$

which is known as the Pauli algebra of quantum mechanics. The Pauli spin matrices

$$\begin{align}
\sigma_1=\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix},\
\sigma_2=\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},\
\sigma_3=\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix},
\end{align}$$

thus form a representation of the algebra of three-dimensional space.

#### Rotations
Rotations of vectors can again be implemented with the rotors. Given a vector $\boldsymbol{u}$. Its rotation by an angle $\theta$ in the plane $\boldsymbol{B} = a\ \boldsymbol{B}_1 + b\ \boldsymbol{B}_2 + c\ \boldsymbol{B}_3$ is given by the conjugation

$$\boldsymbol{u}_{rot} = R_\theta \boldsymbol{u} R_\theta^{-1}\,,$$

with the rotor $R_\theta = e^{-\boldsymbol{B} \theta/2}$, where the exponentiation of the pseudovector is defined as $e^{\boldsymbol{B} \theta}=\cos \theta + \boldsymbol{B} \sin \theta$, which makes sense since the pseudovectors $\boldsymbol{B}_1,$ $\boldsymbol{B}_2,$ $\boldsymbol{B}_3$ squares to $-1$ like the bi-vector $\boldsymbol{i}$ in the two-dimensional setting. In $\mathbb{G}^3$, we can also express these rotors in terms of the quaternions. In fact, each pseudovector $\boldsymbol{B}$ represents a two-dimensional plane with an associated geometric subalgebra isomorphic to $\mathbb{G}^2$. The rotor is again the geometric product of two unit vectors spanning the plane with an angle $-\theta/2$. 

When rotating around a unit vector $\boldsymbol{n}$ we obtain the rotor $R=e^{-\boldsymbol{n}\, \boldsymbol{I}\, \theta/2}$. 

#### Normals
The dual of a multi-vector is given by the operation

$$ A^* = A \boldsymbol{I}^{-1}\,. $$

Scalars are dual to pseudoscalars. Vectors are dual to the pseudovectors representing the normal planes. The traditional cross-product of two vectors is the dual of the outer product

$$ \boldsymbol{u} \times \boldsymbol{v} = (\boldsymbol{u} \wedge \boldsymbol{v})^*\,.$$

Note that the cross-product only makes sense in the two- and three-dimensional context. In higher-dimensional spaces, the pseudovectors do not map so neatly on the vectors. The outer product is well-defined for the geometric algebra of $n$-dimensional Euclidean space.

#### Projections and reflections
Just like in the two-dimensional case, we can use the language of geometric algebra to define projections and reflections. Given a vector $\boldsymbol{u}$ we can decompose the vector in a component parallel $\boldsymbol{u}_\|$ and normal $\boldsymbol{u}_\perp$ to another vector $\boldsymbol{v}$. These components again look like

$$\begin{align}
\boldsymbol{u}_{\|} &= (\boldsymbol{u}\cdot \boldsymbol{v})\boldsymbol{v}^{-1}\,,\\
\boldsymbol{u}_{\perp} &= (\boldsymbol{u}\wedge \boldsymbol{v})\boldsymbol{v}^{-1}\,.
\end{align}$$

The reflection of the vector $\boldsymbol{u}$ in the line represented by $\boldsymbol{v}$ again yields the conjugation of $\boldsymbol{u}$ by $\boldsymbol{v}$, *i.e.,*

$$\boldsymbol{u}_{ref} = \boldsymbol{u}_{\|} - \boldsymbol{u}_{\perp} = \boldsymbol{v}\boldsymbol{u}\boldsymbol{v}^{-1}.$$

However in the three-dimensional setting, unlike the two-dimensional case, we might want to decompose a vector $\boldsymbol{u}$ into a term parallel and normal to a plane represented by a pseudovector $\boldsymbol{B}$. Geometric algebra beautifully extends this formula with the identities

$$\begin{align}
\boldsymbol{u}_{\|} &= (\boldsymbol{u}\cdot \boldsymbol{B})\boldsymbol{B}^{-1}\,,\\
\boldsymbol{u}_{\perp} &= (\boldsymbol{u}\wedge \boldsymbol{B})\boldsymbol{B}^{-1}\,.
\end{align}$$

A non-zero pseudovector always has an inverse, since $(\boldsymbol{e}_1 \boldsymbol{e}_2)^{-1}=\boldsymbol{e}_2\boldsymbol{e}_1$.

Where the inner and outer product of a vector and a bi-vector $\boldsymbol{A},\boldsymbol{B}$ are defined as the $1$- and $3$-vector part of their geometric product

$$\begin{align}
\boldsymbol{A}\cdot \boldsymbol{B} &= \langle\boldsymbol{A}\boldsymbol{B}\rangle_{1}\,,\\
\boldsymbol{A}\wedge \boldsymbol{B} &= \langle\boldsymbol{A}\boldsymbol{B}\rangle_{3}\,.
\end{align}$$

The reflection of $\boldsymbol{u}$ with respect to the plane represented by $\boldsymbol{B}$ assumes the form

$$\boldsymbol{u}_{ref} = \boldsymbol{u}_{\|} - \boldsymbol{u}_\perp = -\boldsymbol{B} \boldsymbol{u} \boldsymbol{B}^{-1}\,,$$

using the observation that the geometric product of a vector with a bi-vector assumes the form

$$\begin{align}
\boldsymbol{u}\boldsymbol{B} &= \boldsymbol{u}\cdot\boldsymbol{B} + \boldsymbol{u}\wedge \boldsymbol{B}\,,\\
\boldsymbol{B}\boldsymbol{u} &= \boldsymbol{u}\cdot\boldsymbol{B} - \boldsymbol{u}\wedge \boldsymbol{B}\,.
\end{align}$$

This decomposition is not generally true for the geometric product of multi-vectors. 

#### Volumes
The area of a bi-vector $\boldsymbol{B}=\boldsymbol{b}_1 \boldsymbol{b}_2$ is defined as the volume of the space spanned by the vectors $\| \boldsymbol{B}\|=\|\boldsymbol{b}_1\|\|\boldsymbol{b}_2\|$. The volume of a tri-vector $\boldsymbol{T}=\boldsymbol{b}_1 \boldsymbol{b}_2\boldsymbol{b}_3$ is defined as the volume of the space spanned by the vectors $\| \boldsymbol{T}\|=\|\boldsymbol{b}_1\|\|\boldsymbol{b}_2\|\|\boldsymbol{b}_3\|$.


### $n$-dimensional space
These notions neatly generalize to the geometric algebra $\mathbb{G}^n$ extending the vector algebra of the $n$-dimensional Euclidean plane $\mathbb{R}^n$. Given an orthonormal basis $\{\boldsymbol{e}_1,\dots,\boldsymbol{e}_n\}$, the geometric algebra has a canonical basis of the form 

$$\{1, \boldsymbol{e}_1, \boldsymbol{e}_2,\dots,\boldsymbol{e}_1\boldsymbol{e}_2\dots\boldsymbol{e}_n \}$$ 

consisting of a scalar and $m$-vectors with $m=1,\dots,n$. In the space $\mathbb{R}^n$ we can identify $k$-dimensional hyperspace, which that can be identified by a *$k$-blade* consisting of the product of a set of $k$ orthogonal vectors $\boldsymbol{B} = \boldsymbol{b}_1\boldsymbol{b}_2\dots\boldsymbol{b}_k$ spanning the hyperspace. Vectors and bi-vectors are examples of grade $1$ and grande $2$ blades (we use boldface capitals for blades and normal capitals for general multi-vectors). In general, every $n$-vector is a blade as it can be written using a suitable orthogonal basis. A blade is included in another blade, $\boldsymbol{A} \subset \boldsymbol{B},$ when the associated hyperplane is included in the larger hyperplane. 

#### Normals
The pseudoscalar $\boldsymbol{I}=\boldsymbol{e}_1\boldsymbol{e}_2\dots\boldsymbol{e}_n$, associated to the space $\mathbb{R}^n$, is an important element of the geometric algebra as it allows us to relate the multi-vectors to their dual, 

$$A^* = A\ \boldsymbol{I}^{-1}\,,$$

with the inverse pseudoscalar $\boldsymbol{I}^{-1}=\boldsymbol{e}_n\dots\boldsymbol{e}_1$. The *orthogonal complement* of a $j$-blade $\boldsymbol{B}$ is the $(n-1)$-blade $\boldsymbol{B}^*$ consisting of the normal basis vectors.

#### Inner and outer products 
Let $\langle C \rangle_j$ denote the $j$-vector part of $C$. We define the inner and outer product of a $j$- and a $k$-vector $A,B$ as the $(j-k)$- and $(j+k)$-vector part of the geometric product

$$\begin{align}
\boldsymbol{A}\cdot \boldsymbol{B} &= \langle \boldsymbol{A}\boldsymbol{B}\rangle_{k-j}\,,\\
\boldsymbol{A}\wedge \boldsymbol{B} &= \langle \boldsymbol{A}\boldsymbol{B}\rangle_{k+j}\,.
\end{align}$$

The geometric product of a $j$- and a $k$-blade consists of multi-vector with a $(k-j)$-, $(k-j+2)$-, $\dots$, $(j+k)$-vector part. The inner and outer products of general multi-vectors are defined using the products of the blades with linearity. 

The geometric product of a vector with a $k$-blade assumes the form

$$\begin{align}
\boldsymbol{u}\boldsymbol{B} &= \boldsymbol{u}\cdot\boldsymbol{B} + \boldsymbol{u}\wedge \boldsymbol{B}\,.
\end{align}$$

#### Reflections and projections
We can always write a vector $\boldsymbol{u}=\boldsymbol{u}_{\|}+\boldsymbol{u}_\perp$ in terms of a parallel and an orthogonal part with respect to a blade $\boldsymbol{B}$, with

$$\begin{align}
\boldsymbol{u}_{\|} &= (\boldsymbol{u}\cdot \boldsymbol{B})\boldsymbol{B}^{-1}\,,\\
\boldsymbol{u}_{\perp} &= (\boldsymbol{u}\wedge \boldsymbol{B})\boldsymbol{B}^{-1}\,.
\end{align}$$

The reflection of $\boldsymbol{u}$ in $\boldsymbol{B}$ takes the form $\boldsymbol{u}_{ref}=(-1)^{k+1}\boldsymbol{B} \boldsymbol{u} \boldsymbol{B}^{-1}$. When working with the dual $\boldsymbol{b}=\boldsymbol{B}^*$, we obtain the relation $\boldsymbol{u}_{ref} = -\boldsymbol{b}\boldsymbol{u}\boldsymbol{b}^{-1}$.

#### Rotations
Rotations of vectors can again be implemented with the rotors. Given a vector $\boldsymbol{u}$. Its rotation by an angle $\theta$ in the plane $\boldsymbol{B}$ is given by the conjugation

$$\boldsymbol{u}_{rot} = R_\theta \boldsymbol{u} R_\theta^{-1}\,,$$

with the rotor $R_\theta = e^{-\boldsymbol{B} \theta/2}$, where the exponentiation of the blade is defined as $e^{\boldsymbol{B} \theta}=\cos \theta + \boldsymbol{B} \sin \theta.$

Two subsequent rotations $R_1$ and $R_2$ lead to a rotation of the rotor, $R_3 = R_2 R_1$. If $\boldsymbol{u}$ is rotates by $R_1$ and $R_2$ we obtain

$$\boldsymbol{u}_{rot} = R_2 R_1 \boldsymbol{u} R_1^{-1} R_2^{-1} = (R_2 R_1) \boldsymbol{u} (R_2 R_1)^{-1}\,.$$

Given a rotation $R_1 = e^{- \boldsymbol{i}\ \theta/2}$ with a given angle $\boldsymbol{i}\ \theta$ with the bi-vector $\boldsymbol{i}$ and the angle $\theta$ we can rotate the plane of rotation with a rotor $R_2$ to the plane $\boldsymbol{i}' = R_2 \boldsymbol{i} R_2^{-1}$. The resulting rotor transforms as

$$\begin{align}
R_3 &= e^{-\boldsymbol{i}'\ \theta/2} \\
&= e^{-R_2 \boldsymbol{i} R_2^{-1}\ \theta/2} \\
&= R_2 e^{-\boldsymbol{i} \ \theta/2}R_2^{-1} \\
&= e^{-R_2 \boldsymbol{i} R_2^{-1}\ \theta/2} \\
&= R_2 R_1 R_2^{-1}\,.
\end{align}$$

Hence the rotor transforms in the same way as vectors under rotations.

#### Volumes
The volume (norm) of a $k$-blade $\boldsymbol{B}=\boldsymbol{b}_1 \cdots \boldsymbol{b}_k$ is defined as the volume of the space spanned by the vectors $\| \boldsymbol{B}\|=\|\boldsymbol{b}_1\|\cdots\|\boldsymbol{b}_k\|$.

#### Complex numbers
Each hyperplane in $\mathbb{R}^n$, corresponding to a bi-vector yields a geometric subalgebra isomorphic to $\mathbb{G}^2$. In this space, we identify the complex numbers $\{a+\boldsymbol{i}\ b\}$. Analogously, every three-dimensional hyperspace yields a geometric subalgebra isomorphic to $\mathbb{G}^3$ with a quaternion subalgebra with the complex numbers $\{a + \boldsymbol{i}\ b + \boldsymbol{j}\ c + \boldsymbol{k}\ d \}.$

### Geometric calculus
We now develop calculus in the setting of geometric algebra. In both function and vector calculus, we study both scalar- and vector-valued functions, mapping the points in $\mathbb{R}^n$ to either the real numbers $\mathbb{R}$ or the vectors $\mathbb{R}^n$. In complex analysis, analytic functions map the points in the complex plane $\mathbb{C}$ to the complex plane $\mathbb{C}$ while satisfying the Cauchy-Riemann equations. In calculus, we not only study these functions but also their rate of change through the derivative, and in particular the  gradient operator 

$$\nabla = \boldsymbol{e}_1 \partial_1 + \dots + \boldsymbol{e}_n \partial_n\,.$$

These notions of change are unified and generalized in geometric calculus. 

#### Two-dimensional plane
Let's briefly consider the two-dimensional setting with scalar-valued and vector-valued functions. The gradient operator acting on the real scalar function $f:\mathbb{R}^2\to \mathbb{R}$  yields the standard result

$$\begin{align}
\nabla f &=  \partial_1 f \boldsymbol{e}_1 +  \partial_2 f \boldsymbol{e}_2\,.\\
\end{align}$$

However, when acting on the vector function $\boldsymbol{f} = f_1 \boldsymbol{e}_1 + f_2 \boldsymbol{e}_2:\mathbb{R}^2\to \mathbb{R}$ (which is not allowed in vector calculus), 

$$\begin{align}
\nabla \boldsymbol{f} &= \boldsymbol{e}_1(\partial_1 f_1 \boldsymbol{e}_1 + \partial_1 f_2 \boldsymbol{e}_2) + \boldsymbol{e}_2(\partial_2 f_1 \boldsymbol{e}_1 + \partial_2 f_2 \boldsymbol{e}_2)\\
 &= (\partial_1 f_1 + \partial_2 f_2)  +  (\partial_1 f_2 - \partial_2 f_1)\boldsymbol{e}_1\boldsymbol{e}_2\\
 &= (\partial_1 f_1 + \partial_2 f_2)  +  (\partial_1 f_2 - \partial_2 f_1) \boldsymbol{i}\\
 &= \nabla \cdot \boldsymbol{f} + \nabla \wedge \boldsymbol{f}\,,
\end{align}$$

we obtain both the divergence $\nabla \cdot \boldsymbol{f} = \partial_1 f_1 + \partial_2 f_2$ and the curl $\nabla \wedge \boldsymbol{f} = (\partial_1 f_2 - \partial_2 f_1)\boldsymbol{i}$ or in more traditional notation $\nabla \times \boldsymbol{f} = (\nabla \wedge \boldsymbol{f})^* = \partial_1 f_2 - \partial_2 f_1$. The gradient thus unifies the divergence and the curl, giving the flow of the vector field in or out of a point and the rotation in the plane $\boldsymbol{i}$. Note that the gradient operator on a vector-valued function is invertible unlike the divergence or curl (as we will see below). 

When acting twice on a real scalar function, we obtain the Laplace operator

$$\begin{align}
\nabla^2 f &= (\partial_1^2 f + \partial_2^2 f)  +  (\partial_1 \partial_2 f - \partial_1 \partial_2 f) \boldsymbol{i}\\
&= \partial_1^2 f + \partial_2^2 f\\
&= \Delta f\,,
\end{align}$$
as one might expect. When acting twice on a vector function, we obtain the Laplace operator acting on the components

$$\begin{align}
\nabla^2 \boldsymbol{f} 
&= (\boldsymbol{e}_1 \partial_1 + \boldsymbol{e}_2 \partial_2)\left((\partial_1 f_1 + \partial_2 f_2)  +  (\partial_1 f_2 - \partial_2 f_1) \boldsymbol{i}\right)\\
&= (\partial_1^2 f_1 + \partial_2^2 f_1)\boldsymbol{e}_1 + 
(\partial_2^2 f_2 + \partial_1^2 f_2)\boldsymbol{e}_2\\
&= \Delta f_1 \boldsymbol{e}_1 + \Delta f_2 \boldsymbol{e}_2\\
&= \Delta \boldsymbol{f}\,.
\end{align}$$

We thus see that geometric calculus simplifies vector calculus in several respects. Moreover, these results generalize to the three-dimensional setting, yielding the three-dimensional gradient, divergence, curl, and Laplace operator in terms of the single operator $\nabla$.

However, more remarkably, it also allows us to differentiate complex-valued functions $f = u + \boldsymbol{i}\ v:\mathbb{C} \to \mathbb{C}$, when identifying the vectors $\boldsymbol{e}_1$ and $\boldsymbol{e}_2$ with the real and imaginary directions,

$$\begin{align} 
\nabla f &= \boldsymbol{e}_1( \partial_1 u + \boldsymbol{i}\ \partial_1 v) + \boldsymbol{e}_2(\partial_2 u + \boldsymbol{i}\ \partial_2 v)\\
&= (\partial_1 u - \partial_2 v)\boldsymbol{e}_1 +  (\partial_1 v + \partial_2 u) \boldsymbol{e}_2 \,,
\end{align}$$

which vanishes for analytic function due to the Cauchy-Riemann equations. We generalize this concept by defining the analytic multi-vector-valued functions satisfying the equation 

$$\nabla F = 0\,.$$ 

Acting twice with the gradient operator yields the Laplace operator

$$\begin{align} 
\nabla^2 f 
&= (\boldsymbol{e}_1 \partial_1 + \boldsymbol{e}_2 \partial_2)\left((\partial_1 u - \partial_2 v)\boldsymbol{e}_1 +  (\partial_1 v + \partial_2 u) \boldsymbol{e}_2\right)\\
&= (\partial_1^2 u + \partial_2^2 u) + (\partial_1^2 v + \partial_2^2 v)\boldsymbol{i}\\
&= \Delta u + \Delta v \ \boldsymbol{i}\\
&= \Delta f\,.
\end{align}$$

Hence, analytic functions are harmonic functions for which $\Delta f=0$.

Finally, let's invert the gradient operator. First, consider the gradient acting on a (possibly complex) scalar field $\nabla p = \boldsymbol{f}$ for some given vector field $\boldsymbol{f}$. Acting with the gradient operator, we obtain the Poisson equation $\Delta p=\nabla \boldsymbol{f},$ which can be solved with the Green's function method

$$\begin{align}
p(\boldsymbol{x}_0)
&\sim \frac{1}{2\pi}\int_{\mathbb{R}^2} \nabla \boldsymbol{f}(\boldsymbol{x}) \ln\|\boldsymbol{x}-\boldsymbol{x}_0\|\mathrm{d}^2x\\
&= \frac{1}{2\pi}\int_{\mathbb{R}^2} \nabla \cdot \boldsymbol{f}(\boldsymbol{x}) \ln(\|\boldsymbol{x}-\boldsymbol{x}_0\|)\mathrm{d}^2x+ \frac{1}{2\pi}\int_{\mathbb{R}^2} \nabla \wedge \boldsymbol{f}(\boldsymbol{x}) \ln\|\boldsymbol{x}-\boldsymbol{x}_0\|\mathrm{d}^2x\\
&= \frac{1}{2\pi}\int_{\mathbb{R}^2} \nabla \cdot \boldsymbol{f}(\boldsymbol{x}) \ln\|\boldsymbol{x}-\boldsymbol{x}_0\|\mathrm{d}^2x + \frac{\boldsymbol{i}}{2\pi}\int_{\mathbb{R}^2} \nabla \times \boldsymbol{f}(\boldsymbol{x}) \ln\|\boldsymbol{x}-\boldsymbol{x}_0\|\mathrm{d}^2x\,,
\end{align}$$

upto analytic scalar-valued functions with the familiar two-dimensional integration, assuming $\boldsymbol{f}$ and $\nabla \boldsymbol{f}$ to be well-behaved for large $\|\boldsymbol{x}\|$. The decomposition $\nabla \boldsymbol{f} =\nabla \cdot \boldsymbol{f} + \nabla \wedge \boldsymbol{f}$, shows that the divergence $\nabla \cdot \boldsymbol{f}$ corresponds to the real part of $p$ and the curl $\nabla \wedge \boldsymbol{f}$ corresponds to the imaginary part of $p$. In general, we need both the divergence and the curl to invert the gradient equation.

Second, consider the gradient of a vector field $\nabla \boldsymbol{p} = f$ for some (possibly complex) scalar field $f$. Upon acting with the gradient operator, we find the vector Poisson equation $\Delta \boldsymbol{p}=\nabla f$, yielding the solution

$$\begin{align}
\boldsymbol{p}(\boldsymbol{x}_0) \sim \frac{1}{2\pi}\int_{\mathbb{R}^2} \nabla f(\boldsymbol{x}) \ln\|\boldsymbol{x}-\boldsymbol{x}_0\|\mathrm{d}^2x\,.
\end{align}$$

upto analytic vector-valued functions. It thus follows that for general (suitably well-behaved) multi-vector functions in $\mathbb{G}^2$, satisfying the equation $\nabla A = B$, the inverse gradient, 

$$A(\boldsymbol{x}_0) \sim \nabla^{-1} B (\boldsymbol{x}_0)= \frac{1}{2\pi} \int_{\mathbb{R}^2} \nabla B(\boldsymbol{x}) \ln \|\boldsymbol{x}-\boldsymbol{x}_0\| \mathrm{d}^2x\,,$$

using the multi-vector Poisson equation $\Delta A = \nabla B$, up to analytic functions. That is to say, if $A$ solves $\nabla A = B$ and $F$ is analytic, $\nabla F=0$, and then so does the sum $A+F$.


#### Generalized derivatives
Of course, there is no reason why we would need to restrict ourselves to the two-dimensional case nor to scalar-, vector-, and complex-valued functions. Instead, it is natural to consider multi-vector valued functions $\mathbb{R}^n \to \mathbb{G}^n$ or more generally functions mapping the geometric algebra $\mathbb{G}^n$ to itself.

For these functions, we define the directional derivative with the limit 

$$ \partial_A F(X) = \lim_{\tau \to 0} \frac{F(X + \tau \mathcal{P}_X(A)) - F(X)}{\tau}\,,$$

where $\mathcal{P}_X(A)$ is the projection of $A$ onto the grades of $X$. When $F:\mathbb{R}^n \to \mathbb{G}^n$ the projection forces directional derivatives in multi-vector directions other than the vectors to zero.

Using the partial derivative, we define the multi-vector gradient

$$ \nabla = \sum_J \boldsymbol{e}_J^{-1} \partial_J\,,$$

where we use multi-index notation, *i.e.*, for the set of increasing indices $J=\{j_1,\dots,j_k\}$, with $1 \leq j_a < j_b \leq n$ when $a < b$, we write the canonical bases element $\boldsymbol{e}_J=\boldsymbol{e}_{j_1}\dots \boldsymbol{e}_{j_k}$ and the corresponding directional derivative $\partial_J = \partial_{e_J}$. Note that the inverse of a bases element $\boldsymbol{e}_J^{-1}=(-1)^{(|J|-1)|J|/2} \boldsymbol{e}_J$ with $|J|$ the number of elements in $J$. This generalized gradient enables the study of a multitude of problems that do not naturally fit in traditional vector analysis.

The divergence and curl of a $k$-vector are defined as

$$\begin{align}
\nabla \cdot \boldsymbol{f} = \langle \nabla \boldsymbol{f}\rangle_{k-1}\,,\\
\nabla \wedge \boldsymbol{f} = \langle \nabla \boldsymbol{f}\rangle_{k+1}\,,
\end{align}$$

like the inner and cross-product before. The inner and cross-product of a multi-vector function follow from linearity.

A multi-vector valued function $F$ on $\mathbb{R}^n$ is called analytic when 

$$\nabla F = 0\,,$$

generalizing the Cauchy-Riemann equations.

#### Generalized integrals
Let $M$ be a compact oriented $m$-dimensional manifold in $\mathbb{R}^n$. The integral of a multi-vector $F:\mathbb{R}^n\to \mathbb{G}^n$ is defined as

$$\int_M \mathrm{d}^m\boldsymbol{x}\ F = \int_M \boldsymbol{I}_m(\boldsymbol{x}) \mathrm{d}^m x F(x)\,,$$

where $\mathrm{d}^mx$ is the $m$-volume element of $M$ at the vector $\boldsymbol{x}$ and $\boldsymbol{I}_m(\boldsymbol{x})$ is the pseudoscalar of the tangent space of $M$ at $\boldsymbol{x}$, *i.e.*, $T_\boldsymbol{x}M$.

The fundamental theorem of calculus assumes

$$\int_M \mathrm{d}^m\boldsymbol{x}\ \partial F = \int_{\partial M}\mathrm{d}^{m-1}\boldsymbol{x}\ F\,.$$

where the vector derivative $\partial$ can be seen as a projection of $\nabla$ onto $M$. Given a parametrization $\boldsymbol{x}(u_1,\dots,u_m)$ of $M$ in an neighborhood of $\boldsymbol{x}$, we find the basis $\{\boldsymbol{x}_{u_1},\dots,\boldsymbol{x}_{u_1}\}$ of the tangent space $T_\boldsymbol{x}M$ with $\boldsymbol{x}_{u_j} = \partial_{u_j}\boldsymbol{x}(u_1,\dots,u_m)$ for $j=1,\dots,m$. Defining the dual basis $\{x^{u_j}\}_{j=1,\dots,m}$ of $T_\boldsymbol{x}M$ by the condition $\boldsymbol{x}_{u_j}\cdot \boldsymbol{x}^{u_k}=\delta_{jk}$ for all $j$ and $k=1,\dots,m$, we construct the vector derivative on $M$ as 

$$\partial =\boldsymbol{x}^{u_1} \partial_{u_1} + \dots + \boldsymbol{x}^{u_m} \partial_{u_m}.$$ 

We can show that this definition is equivalent to a projection of $\nabla$ onto the tangent space $T_\boldsymbol{x}M$, making it independent of the parametrization of $M$. An analytic functions on $M$, is defined by the condition

$$\partial F = 0\,.$$ 

The fundamental theorem of gemetric calculus generalizes Cauchy's theorem for analytic functions,

$$\int_{\partial M} \mathrm{d}^{m-1}\boldsymbol{x}\ F = 0\,.$$

More generally, when $F$ is meromorphic and has a set of poles at $\boldsymbol{x}_k$ with the residue $R_k$, that is to say $\partial F(\boldsymbol{x}) = \sum_k \Omega_n R_k \delta(\boldsymbol{x}-\boldsymbol{x}_k)$ with the volume $\Omega_n$ of the $(n-1)$-sphere and the Dirac delta function $\delta$, then the fundamental theorem of calculus yields the $n$-dimensional generalization of the residue theorem

$$\begin{align}
\int_{\partial M} \mathrm{d}^{m-1}\boldsymbol{x}\ F 
&= \int_M \mathrm{d}^m\boldsymbol{x}\ \partial F \\
&= \int_M \mathrm{d}^m x\ \boldsymbol{I}(\boldsymbol{x}) \sum_k \Omega_n R_k \delta(\boldsymbol{x}-\boldsymbol{x}_k)\\
&=\Omega_n \sum_k \boldsymbol{I}(\boldsymbol{x}_k)R_k\,.
\end{align}$$

Now let's consider the more general identity relating the function to its integral

$$ F(\boldsymbol{x}_0) = \frac{(-1)^n}{\Omega_n \boldsymbol{I}} \left[ 
\int_{\partial V} \frac{\boldsymbol{x}-\boldsymbol{x}_0}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^n} \mathrm{d}^{n-1}\boldsymbol{x}\ F(\boldsymbol{x}) - \int_V \frac{\boldsymbol{x}-\boldsymbol{x}_0}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^n} \mathrm{d}^n \boldsymbol{x}\ \nabla F(\boldsymbol{x})\right]\,,$$

where $V$ is a $n$-dimensional region of $\mathbb{R}^n$. Note that when $F$ is analytic,

$$ F(\boldsymbol{x}_0) = \frac{(-1)^n}{\Omega_n \boldsymbol{I}} 
\int_{\partial V} \frac{\boldsymbol{x}-\boldsymbol{x}_0}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^n} \mathrm{d}^{n-1}\boldsymbol{x}\ F(\boldsymbol{x})\,,$$

generalizing Cauchy's integral formula.

This relation enables us to invert the gradient operator. Let $\nabla P = F$, we can reconstruct $P$ from $F$ using the relation 

$$ P(\boldsymbol{x}_0) = \frac{1}{(n-2)\Omega_n} \left[ 
\int_{V} \frac{\mathrm{d}^m x}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^{n-2}} \nabla F(\boldsymbol{x}) - \int_{\partial V} \frac{\mathrm{d}^{m-1}x}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^{n-2}} \mathrm{n}(\boldsymbol{x})\ \nabla F(\boldsymbol{x})\right]\,,$$

for $n>2$ where $\boldsymbol{n}(\boldsymbol{x})$ is the unit outward normal to $\partial V$ defined as $\boldsymbol{n}=\boldsymbol{I}^{-1}\boldsymbol{I}(\boldsymbol{x})$ where $\boldsymbol{I}$ is the pseudoscalar of $\mathbb{R}^n$ and $\boldsymbol{I}(\boldsymbol{x})$ is the pseudoscalar of the tangent space $T_\boldsymbol{x}V$.

When the gradient $F$ is well behaved for large $\boldsymbol{x}$, in particular $\lim_{\boldsymbol{x} \to \infty}F(\boldsymbol{x})=0$ and $|\nabla F(\boldsymbol{x})| =  O(\|\boldsymbol{x}\|^{-2}),$ we find the simpler result

$$\begin{align}
P(\boldsymbol{x}_0) &= \frac{1}{(n-2)\Omega_n}
\int_{\mathbb{R}^n} \frac{\mathrm{d}^m x}{\|\boldsymbol{x}-\boldsymbol{x}_0\|^{n-2}} \nabla F(\boldsymbol{x})\,.
\end{align}$$

This result generalizes the Green's functions we saw in the two-dimensional case.

### Aplications in Physics
Geometric algebra is a very natural language for problems in physics. We here go through a few examples.

#### Maxwell equations
The Maxwell equations in vaccuum for electromagnetism are often written as

$$\begin{align}
\nabla \cdot \boldsymbol{E}  &= \rho/ \epsilon_0 \quad
&&\nabla \times \boldsymbol{E} = -\partial_t \boldsymbol{B}\\
\nabla \cdot \boldsymbol{B} &=0 \quad 
&&\nabla \times \boldsymbol{B} =\mu_0 (\boldsymbol{J}+\epsilon_0 \partial_t \boldsymbol{E})
\end{align}$$

with the electric and the magnetic fields $\boldsymbol{E}$ and $\boldsymbol{B}$, the electric charge density $\rho$, electric current density $\boldsymbol{J}$, the permittivity of free space $\epsilon_0$ and the permeability of free space $\mu_0$. The latter two are related to the speed of light in vacuum by $c = 1/\sqrt{\epsilon_0 \mu_0}\,.$ 

To express these equations in terms of geometric algebra, combine the electric charge and current into a multi-vector

$$J = c \rho - \boldsymbol{J}\,.$$

The electric and magnetic fields form the field strength as a multi-vector

$$ F = \boldsymbol{E} + I c \boldsymbol{B}\,.$$

Note that the magnetic field is introduced as a bivector which is natural as the magnetic field transforms as a pseudovector under parity transformations. The Maxwell equations simplify to

$$\left(\frac{1}{c}\frac{\partial}{\partial t} + \nabla \right)F = \frac{J}{c \epsilon_0}\,.$$

To see this, let's expand the equation and identify terms by their grade. The left-hand side splits off into a scalar, a vector, a bivector, and a trivector part

$$\begin{align}
\left(\frac{1}{c}\frac{\partial}{\partial t} + \nabla \right)(\boldsymbol{E} + I c \boldsymbol{B})
&= \frac{\partial_t \boldsymbol{E}}{c} + \nabla \boldsymbol{E} + I \partial_t \boldsymbol{B} + I c \nabla \boldsymbol{B}\\
&= \frac{\partial_t \boldsymbol{E}}{c} + \nabla \cdot \boldsymbol{E} + \nabla \wedge \boldsymbol{E} + I \partial_t \boldsymbol{B} + I c \nabla \cdot \boldsymbol{B}+ I c \nabla \wedge \boldsymbol{B}\\
&= \left[\nabla \cdot \boldsymbol{E}\right] + \left[\frac{\partial_t \boldsymbol{E}}{c} + I c \nabla \wedge \boldsymbol{B}\right]+ \left[\nabla \wedge \boldsymbol{E} + I \partial_t \boldsymbol{B}\right]+ \left[I c \nabla \cdot \boldsymbol{B}\right]\,.
\end{align}$$

The right-hand side decomposes into a scalar and a vector part

$$\begin{align}
\frac{J}{c \epsilon_0} = \frac{\rho}{\epsilon_0} - \frac{\boldsymbol{J}}{c \epsilon_0}\,.
\end{align}$$

Equating the scalar and pseudoscalar parts yields the divergence of the electric and magnetic fields $\nabla \cdot \boldsymbol{E} = \rho/\epsilon_0$ and $\nabla \cdot \boldsymbol{B}=0$. The vector and bivector parts yield the curl of the electric and magnetic fields $\nabla \times \boldsymbol{E} = - \partial_t \boldsymbol{B}$ and $\nabla \times \boldsymbol{B} = \mu_0(\boldsymbol{J} - \epsilon_0 \partial_t \boldsymbol{E})\,.$ 


Applying the spacetime gradient $c^{-1}\partial_t - \nabla$ to the Maxwell equation 

$$\begin{align}
c^{-2}\partial_t^2 F + \nabla^2 F = \left(c^{-1} \partial_t - \nabla\right) J 
=\left[\partial_t \rho  + \nabla \cdot \boldsymbol{J}\right] - \left[c \nabla \rho + \frac{\partial_t \boldsymbol{J}}{c}\right] + \nabla \wedge \boldsymbol{J}
\end{align}$$

we find the conservation of charge

$$0 = \partial_t \rho + \nabla \cdot \boldsymbol{J} \,,$$

by noting that the left-hand side has a vanishing scalar part, for the Laplacian preserves the grades of a multi-vector.

When the current $J$ vanishes in a region, the field strength $F$ is an analytic function, for $\left(\frac{1}{c}\frac{\partial}{\partial t} + \nabla \right)F = 0$. Indeed, in the absence of a source, we obtain the wave famous equation

$$ c^{-2} \partial_t^2 F - \nabla^2 F = \left(c^{-1} \partial_t - \nabla \right)\left(c^{-1}\partial_t + \nabla \right)F = 0\,,$$

by which $\partial_t^2 \boldsymbol{E}= c^2 \nabla^2 \boldsymbol{E}$ and $\partial_t^2 \boldsymbol{B}= c^2 \nabla^2 \boldsymbol{B}\,.$

#### Rigid body

The motion of a rigid body can be decomposed in the motion of the center of mass $\boldsymbol{x}$ and a rotation $\boldsymbol{Q}$. The configuration space of a rigid body thus consists of the six-dimensional space

$$\mathcal{M} = \mathbb{E}^3 + SO(3)$$

##### Traditional treatment
Traditionally, the orientation $\boldsymbol{Q}$ of a point on the rigid body with respect to the center of mass is written in terms of three Euler angles $(\psi, \theta, \phi)\,.$ The kinetic energy of the rigid body consists of a part associated with the center of mass and a term associated with the rotation

$$\begin{align}
T &= \frac{m}{2} \dot{\boldsymbol{x}}\cdot \dot{\boldsymbol{x}} + \frac{1}{2} \boldsymbol{\omega} \cdot \mathcal{I} \boldsymbol{\omega}\\
&=\frac{m}{2}(\dot{x}^2 + \dot{y}^2 + \dot{z}^2) + \frac{i_1}{2}(\dot{\psi} \sin \phi \sin \theta  + \dot{\theta} \cos \phi)^2 + \frac{i_2}{2}(\dot{\psi} \cos \phi \sin \theta - \dot{\theta} \sin \phi)^2 + \frac{i_3}{2}(\dot{\psi} \cos \theta + \dot{\phi})^2\,.
\end{align}$$

with the mass of the body $m$, the angular velocity $\boldsymbol{\omega} = \dot{\boldsymbol{Q}}$, and the moment of inertia tensor $\mathcal{I}$ and the associated principal moments of inertia $i_1,$ $i_2,$ and $i_3.$ In the equation above we use the principal axis as the reference frame of the body. 

When the rigid body interacts with the external world through the potential $U(\boldsymbol{x},\boldsymbol{Q})$, the rigid body is neatly described by the Lagrangian

$$L = T - U\,.$$

The equations of motion of the rigid body, interacting with the external world follow from the standard Euler-Lagrange equations,

$$\begin{align}
\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \boldsymbol{x}}\right) - \frac{\partial L}{\partial \boldsymbol{x}} &= 0\,,\\
\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \boldsymbol{Q}}\right) - \frac{\partial L}{\partial \boldsymbol{Q}} &= 0\,.
\end{align}$$

##### Geometric algebra treatment
Geometric algebra provides an alternative way of describing the dynamics of a rigid body. Consider a frame of vectors $\{\boldsymbol{f}_k(t)\}$ rotating in space with respect to the fixed orthonormal frame $\{\boldsymbol{e}_k\}\,,$ representing the orientation of the rigid body. The angular velocity $\boldsymbol{\omega}$ is defined by the equation

$$\dot{\boldsymbol{f}}_k = \boldsymbol{\omega} \times \boldsymbol{f}_k\,.$$

The angular velocity $\boldsymbol{\omega}$ is a pseudovector (invariant under parity transformations), represents a rotation in a plane, and is thus most naturally represented by the angular bivector

$$\Omega = I \boldsymbol{\omega}\,.$$

It follows that $\dot{\boldsymbol{f}}_k = \boldsymbol{f}_k \cdot \Omega\,.$

In geometric algebra, the dynamics of the frame $\{\boldsymbol{f}_k\}$ can be captured in a single object using the time-dependent rotor $R(t)$ using the conjugation

$$\boldsymbol{f}_k(t) = R(t) \boldsymbol{e}_k R^{\dagger}(t)\,.$$

The rotor $R(t)$ is a unit even multivector, *i.e.,* $R R^\dagger=1\,,$ with the reverse denoted by the dagger. The angular bivector is related to the rotor, by the equation

$$\dot{R} = -\frac{1}{2} \Omega R\,.$$

To see this, differentiate the definition of the rotor once

$$\dot{\boldsymbol{f}}_k = \dot{R} \boldsymbol{e}_k R^\dagger + R \boldsymbol{e}_k \dot{R}= \dot{R}R^\dagger \boldsymbol{f}_k + \boldsymbol{f}_k R \dot{R}^\dagger\,.$$

Since $RR^\dagger = 1$, we obtain the identity 

$$ 0 = \frac{\mathrm{d}}{\mathrm{d}t}(RR^\dagger) = \dot{R} R^\dagger + R \dot{R}^\dagger\,,$$ 

by which $\dot{R}R^\dagger = -(\dot{R} R^\dagger)^\dagger\,.$ As the product $\dot{R} R^\dagger$ has an even grade and is equal to the negative of its own reverse, it must thus be a bivector. Bivectors commute with vectors from which it follows that

$$\dot{\boldsymbol{f}}_k = (2 \dot{R} R^\dagger)\cdot \boldsymbol{f}_k\,,$$

from which we obtain the identities $\dot{R} = -\frac{1}{2} \Omega R\,,$ $\dot{R}^\dagger = \frac{1}{2} R^\dagger \Omega\,.$ This should not come as a surprise, as for constant angular bivector $\Omega$, we obtain the rotor

$$R(t) = e^{-\Omega t /2} R_0\,,$$

with $R_0$ the rotor at $t=0\,.$

**Velocity**
Now, consider a point $\boldsymbol{y}$ on a rigid body. We can write the position of the point as

$$\boldsymbol{y}(t) = R(t) \boldsymbol{x}_r R^\dagger(t) + \bar{\boldsymbol{x}}(t)\,,$$

with $\bar{\boldsymbol{x}}(t)$ the center of mass and $\boldsymbol{x}_r$ the position of the reference point with respect to the center of mass in a stationary reference copy of the rigid body. The velocity of the point $\boldsymbol{v}(t)=\dot{y}(t)$ assumes the form

$$\begin{align}
\boldsymbol{v}
&= \dot{R} \boldsymbol{x}_r R^\dagger + R \boldsymbol{x}_r \dot{R}^\dagger + \dot{\bar{\boldsymbol{x}}}\\
&= -\frac{1}{2} \Omega R \boldsymbol{x}_r R^\dagger + \frac{1}{2} R \boldsymbol{x}_r R^\dagger \Omega + \bar{\boldsymbol{v}}\\
&=(R\boldsymbol{x}_r R^\dagger) \cdot \Omega + \bar{\boldsymbol{v}}\,.
\end{align}$$

When rotating the angular velocity to the reference frame $\Omega_B = R^\dagger \Omega R$, we find $\dot{R} = -\frac{1}{2}R\Omega_B$ and $\dot{R}^\dagger = \frac{1}{2} \Omega_B R^\dagger\,.$ The velocity now assumes the form

$$\boldsymbol{v} = R\ \boldsymbol{x}_r \cdot \Omega_B R^\dagger+ \bar{\boldsymbol{v}}\,.$$

**Angular momentum**
The angular momentum bivector (again a pseudovector describing the rotation in a plane) can be written as

$$\begin{align}
L &= \int \mathrm{d}^3 x_r \rho(\boldsymbol{y}- \bar{\boldsymbol{x}}) \wedge (\boldsymbol{v}-\bar{\boldsymbol{v}})\\
&= \int \mathrm{d}^3x_r \rho (R \boldsymbol{x}_r R^\dagger) \wedge (R \boldsymbol{x}_r\cdot \Omega_B R^\dagger )\\
&= R \left(\int \mathrm{d}^3 x_r \rho \boldsymbol{x}_r \wedge (\boldsymbol{x}_r \cdot \Omega_B)\right)R^\dagger\,,
\end{align}$$

with $\rho$ the mass density of the rigid body.

**Inertia tensor**
Now, define the inertia tensor $\mathcal{I}$ as the linear map

$$\mathcal{I}(B) = \int \mathrm{d}^3 x \rho \boldsymbol{x} \wedge (\boldsymbol{x} \cdot B)$$

mapping bivectors to bivectors. Given a bivector $B$ the bivector $\mathcal{I}(B)$ is the angular momentum about the center of mass of the rotation in the $B$ plane. The angular momentum assumes the form 

$$ L = R \mathcal{I}(\Omega_B)R^\dagger\,.$$

Given this map, we can define the familiar matrix representation by projecting it onto a bivector basis 

$$\mathcal{I}_{ij} = -(I \boldsymbol{e}_i)\cdot \mathcal{I}(I \boldsymbol{e}_j)\,.$$

This matrix turns out to be symmetric and positive definite. Its eigenvectors give the principal axes and its eigenvalues $i_1,i_2,i_3$, the associated principal moments of inertia.

**Kinetic energy**
The kinetic energy  of the rigid body reads

$$\begin{align}
T &= \frac{1}{2} \int \mathrm{d}^3 x \rho (R \boldsymbol{x}\cdot \Omega_B R^\dagger +\bar{\boldsymbol{v}})^2\\
&= \frac{1}{2} \int \mathrm{d}^3 x \rho (\boldsymbol{x} \cdot \Omega_B)^2 + \frac{1}{2} M \bar{\boldsymbol{v}}^2\,,
\end{align}$$

with the total mass of the rigid body $M\,.$ In terms of the moment of inertia, we obtain the familiar expression

$$\begin{align}
T &= \frac{1}{2} M \boldsymbol{v}^2 + \frac{1}{2} \Omega_B^\dagger \cdot \mathcal{I}(\Omega_B)\\
&=\frac{1}{2} M \boldsymbol{v}^2 + \frac{1}{2} \Omega^\dagger \cdot L\,,
\end{align}$$

where we for simplicity have dropped the bar over the velocity of the center of mass.

**Torque**
The torque bivector $N$ on the rigid body affects the body by the differential equation

$$\dot{L} = N\,.$$

**Euler-Lagrange equations**
The Lagrangian of the system $\bar{L}$ (not to be confused with the angular momentum bivector $L$) can be written as 

$$\bar{L} = \frac{1}{2} M \boldsymbol{v}^2 + \frac{1}{2} \Omega_B^\dagger \cdot \mathcal{I}(\Omega_B) - U(\boldsymbol{x},R)$$

in the configuration space consisting of the position of the center of mass $\boldsymbol{x}$ and the orientation described by the rotor $R$, with $\Omega_B =-2 R^\dagger \dot{R}\,.$ The restricting on the rotors $RR^\dagger=1$ makes the direct evaluation of the Euler Lagrange equations difficult. For this reason, replace the rotor $R$ with a general even multi-vector $\psi$ and impose the constraint $\psi \psi^\dagger=1$ with a Lagrange multiplier. Note that such a general even multi-vector has four real dimensions ($1$ scalar + $3$ bivectors basis vectors = $4$ dimensions) and is known as a spinor. This spinor is directly related to the $2$ spinor of the Pauli equation for non-relativistic particles with spin $1/2\,.$ The Lagrangian now assumes the form

$$\bar{L} = \frac{1}{2}M \dot{x}^2 - \frac{1}{2} \Omega_B \cdot \mathcal{I(\Omega_B)} - U(\boldsymbol{x},\psi) - \lambda(\psi \psi^\dagger -1)$$

with the angular velocity bivector in the reference system 
$$\Omega_B=-\psi^\dagger \dot{\psi} + \dot{\psi}^\dagger \psi$$

and the Lagrange multiplier $\lambda$. Note that this form for the angular velocity bivector reduces to the earlier definition when $\psi \psi^\dagger=1\,.$ The Euler-Lagrange equation now yields

$$\begin{align}
\partial_{\boldsymbol{x}}\bar{L} - \frac{\mathrm{d}}{\mathrm{d}t}(\partial_{\dot{\boldsymbol{x}}}\bar{L}) &=0\,,\\
\partial_{\psi}\bar{L} - \frac{\mathrm{d}}{\mathrm{d}t}(\partial_{\dot{\psi}}\bar{L}) &=0\,,\\
\partial_\lambda \bar{L} = 0\,.
\end{align}$$

In the absence of a force, the equation of motion for $\psi$ reduces to 

$$\mathcal{I}(\dot{\Omega}_B) - \Omega_B \mathcal{I}(\Omega_B) = \lambda\,.$$

The scalar part provides $\lambda$ and yields the conservation of rotational energy $-\frac{1}{2} \Omega_B \cdot \mathcal{I}(\Omega_B)$. The bivector part yields 

$$\mathcal{I}(\dot{\Omega}_B)- \frac{1}{2}\Omega_B \mathcal{I}(\Omega_B)+  \frac{1}{2}\mathcal{I}(\Omega_B)\Omega_B =\mathcal{I}(\dot{\Omega}_B)- \Omega_B \times \mathcal{I}(\Omega_B) = 0$$

by which the angular momentum bivector is conserved $\dot{L}=0\,.$ When there is a torque, 

$$N = - \partial_\psi U =  R(\mathcal{I}(\dot{\Omega}_B) - \Omega_B \times \mathcal{I}(\Omega_B))R^\dagger\,.$$

In these equations, I used the cross product on bivectors $A\times B = \frac{1}{2}(AB-BA)\,.$

Finally, the Pauli spinor

$$|\psi\rangle = \begin{pmatrix} a^0 + i a^3 \\ -a^2 + i a^1 \end{pmatrix}$$

maps onto the even multi-vectors of $\mathbb{G}^3\,,$

$$\psi = a^0 + \sum_{k=1}^3 a^k I \boldsymbol{e}_k\,,$$

consisting of a scalar and three bivector terms. This object behaves as a spinor under the geometric product as the even subalgebra spanned by $1, \boldsymbol{e}_1, \boldsymbol{e}_2,\boldsymbol{e}_3$ is isomorphic to the Pauli spinor algebra, as

$$\boldsymbol{e}_i \boldsymbol{e}_j = \delta_{ij} +  \epsilon_{ijk}I \boldsymbol{e}_k\,.$$

This algebra is usually represented by the Pauli spin matrices in physics

$$\begin{align}
\text{I} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix},\ 
\sigma_1=\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},\
\sigma_2=\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix},\
\sigma_3=\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix},
\end{align}$$

satisfying

$$\sigma_i \sigma_j = \delta_{ij}\text{I} + i \epsilon_{ijk}\sigma_k\,,$$

These two algebras are isomorphic upon the isomorphism $\boldsymbol{e}_i \leftrightarrow \sigma_i\,,$ as the pseudoscalar is a complex structure, *i.e.,* $I^2=-1$ like $i=\sqrt{-1}\,.$ 

Hence, spinors are not necessarily quantum objects but already play a role in the Lagrangian of rigid bodies describing classical spin.