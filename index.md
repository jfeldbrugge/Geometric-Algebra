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

Geometric algebra is an extension of vector algebra introducing the notion of a multi-vector, uniting different fields of mathematics in a single language. 

**Definition:** *The geometric algebra $\mathbb{G}^n$ is an extension of the $n$-dimensional vector space $\mathbb{R}^n$. The geometric algebra $\mathbb{R}^n \subset \mathbb{G}^n$ is an associative algebra with a unit $1$, satisfying the four conditions:*

* G1: $A(B+C) = AB + AC$, $(B+C)A = BA + CA$,
* G2: $(aA)B = A(aB)= a(AB)$,
* G3: $(AB)C = A(BC)$,
* G4: $1A=A1=A$,

*with the scalar $a \in \mathbb{R}$ and the multi-vectors $A, B, C \in \mathbb{G}^n.$ In addition, this geometric product satisfies two conditions linking the geometric algebra $\mathbb{G}^n$ to the vector space $\mathbb{R}^n$:*

* G5: $\textbf{u}\textbf{u}=\textbf{u}\cdot\textbf{u} = \|\textbf{u}\|^2$ *for all vectors* $\textbf{u} \in \mathbb{R}^n$,

*by which nonzero vectors have an inverse in $\mathbb{G}^n$ given by $\textbf{u}^{-1}=\textbf{u}/\|\textbf{u}\|$ and a way to construct the multivectors in $\mathbb{G}^n$ from the vectors in $\mathbb{R}^n$*

* G6: *Every orthonormal basis of $\mathbb{R}^n$ determines a canonical basis for the vector space $\mathbb{G}^n$ (to be constructed below).*

From these simple conditions, the theory develops, leading to a richer way to do geometry and calculus.

In particular, from the condition G5 we obtain an identity relating the inner product to the geometric product for general vectors
$$\begin{align}
\textbf{u}\cdot\textbf{v} 
&= \frac{1}{2}((\textbf{u} +  \textbf{v})\cdot(\textbf{u} +  \textbf{v}) - \textbf{u}\cdot\textbf{u} -\textbf{v} \cdot \textbf{v})\\
&= \frac{1}{2}((\textbf{u} +  \textbf{v})^2- \textbf{u}\textbf{u} -\textbf{v}\textbf{v})\\
&= \frac{1}{2}(\textbf{u} \textbf{v} + \textbf{v}\textbf{u})\,.
\end{align}$$
When two vectors are orthogonal, *i.e.,* $\textbf{u} \cdot \textbf{v}=0$, the geometric product of the vectors is skew-symmetric 
$$ \textbf{u} \textbf{v} = -\textbf{v} \textbf{u}\,.$$

The product of two orthogonal vectors is neither a scalar nor a vector, since its square is negative $(\textbf{u}\textbf{v})^2=\textbf{u}\textbf{v}\textbf{u}\textbf{v}=-\textbf{u}\textbf{u} \textbf{v}\textbf{v}=-\|\textbf{u}\|^2 \|\textbf{v}\|^2$. It is an object known as a bi-vector representing an oriented area element (spanned by $\textbf{u}$ and $\textbf{v}$), the first instance of an element of the geometric algebra $\mathbb{G}^n$ that is not present in vector algebra $\mathbb{R}^n$.

Condition G5 shows how the vector norm ankers the geometric product to $\mathbb{R}^n$, and leads to an alternative definition of the inner product of vectors as the symmetrized product,

$$\textbf{u}\cdot \textbf{v} = \frac{1}{2}(\textbf{u}\textbf{v} + \textbf{v} \textbf{u})\,.$$

The anti-symmetrized product is known as the outer product of the vectors 

$$\textbf{u}\wedge \textbf{v} = \frac{1}{2}(\textbf{u}\textbf{v} - \textbf{v} \textbf{u})\,.$$

We will see that this outer product coincides with the outer product of vector analysis.

From these definitions, it follows that the geometric product of two vectors can be expressed in terms of the more familiar inner and outer products

$$\textbf{u}\textbf{v} = \textbf{u}\cdot\textbf{v} + \textbf{u}\wedge \textbf{v}$$

and

$$\textbf{v}\textbf{u} = \textbf{u}\cdot\textbf{v} - \textbf{u}\wedge \textbf{v}\,.$$

Note that the geometric product of vectors is invertible, unlike the inner or outer products that constitute them. For parallel vectors (with $\textbf{u} = a \textbf{v}$ with $a \in \mathbb{R}$), the geometric product reduces to the inner product $\textbf{u}\textbf{v} = \textbf{u}\cdot \textbf{v}$ (using condition G2). For orthogonal vectors, the geometric product reduces to the outer product $\textbf{u}\textbf{v} = \textbf{u}\wedge \textbf{v}$. For a general set of vectors, the geometric product leads to a multi-vector, where the scalar part represents the inner and the bi-vector part represents the outer product.

To develop intuition, we briefly study the geometric implications of this construction on two- and three-dimensional Euclidean space.

### Two-dimensional plane
Consider the two-dimensional plane $\mathbb{R}^2$ spanned by the orthonormal unit vectors $\textbf{e}_1=\hat{\textbf{x}}$ and $\textbf{e}_2=\hat{\textbf{y}}$. Geometric algebra is spanned by the elements 

$$\{1, \textbf{e}_1, \textbf{e}_2, \textbf{e}_1\textbf{e}_2\}$$ 

where $1$ is the unit scalar, $\textbf{e}_1$ and $\textbf{e}_2$ are the unit vectors and $\textbf{e}_1\textbf{e}_2$ is the unique bi-vector representing an oriented area element. This is the *canonical basis* of the geometric algebra $\mathbb{G}^2$. We cannot generate more bases elements, as the unit vectors $\textbf{e}_1$ and $\textbf{e}_2$ are orthogonal and objects consisting of the geometric product of three or more bases elements of $\mathbb{R}^2$ can be reduced to these four combinations using the anti-commutative property, *e.g.*, $\textbf{e}_1\textbf{e}_2\textbf{e}_1=-\textbf{e}_1\textbf{e}_1\textbf{e}_2=-\textbf{e}_2$. A multi-vector is an object of the form 

$$A = a + b\ \textbf{e}_1 + c\ \textbf{e}_2 + d\ \textbf{e}_1\textbf{e}_2$$

with for real numbers $a,b,c,d \in \mathbb{R}$. The product of two multi-vectors follows from the associative nature of the geometric product and the multiplication table of the bases elements of $\mathbb{R}^2$, $\textbf{e}_1^2=\textbf{e}_2^2=1$ and $\textbf{e}_1\textbf{e}_2=-\textbf{e}_1\textbf{e}_2$, as we saw above. 

Explicitly, the geometric product of two vectors takes the form

$$\begin{align}
\textbf{u} \textbf{v} 
&= (a_1 \textbf{e}_1 + b_1 \textbf{e}_2)(a_2 \textbf{e}_1 + b_2 \textbf{e}_2)\\
&=(a_1 a_2 + b_1 b_2) + (a_1 b_2 - b_1 a_2)\textbf{e}_1\textbf{e}_2\\
&=\textbf{u}\cdot\textbf{v} + \textbf{u}\wedge \textbf{v}\,,
\end{align}$$

where we identify the familiar inner product $\textbf{u}\cdot\textbf{v}=a_1 a_2 + b_1 b_2 = \|\textbf{u}\| \|\textbf{v}\| \cos\theta$ written in terms of the angle between the two vectors $\theta$. The outer product 

$$\begin{align}
\textbf{u}\wedge \textbf{v} &= (a_1 b_2 - b_1 a_2)\textbf{e}_1\textbf{e}_2 \\
&= \|\textbf{u}\| \|\textbf{v}\| \sin \theta \ \textbf{e}_1\textbf{e}_2
\end{align}$$ 

is the signed area of the parallelogram spanned by the two vectors $\textbf{u}$ and $\textbf{v}$. 

As $\textbf{e}_1$ and $\textbf{e}_2$ are orthogonal, the bi-vector $\textbf{e}_1\textbf{e}_2$ squares to $-1$, from which it follows that we can identify this bi-vector with the square root of unity $\textbf{e}_1\textbf{e}_2 = \textbf{i}=\sqrt{-1}$. The complete product of basis elements in $\mathbb{R}^n$ is generally an important element in geometric algebra, as it is the only $n$-vector in the canonical basis, denoted as the pseudoscalar of the algebra $\textbf{I}=\textbf{e}_1\textbf{e}_2\dots\textbf{e}_n$. 

In the two-dimensional setting, geometric algebra unifies two-dimensional vector analysis with complex analysis, $A=(a + \textbf{i}\ d) + (b\ \textbf{e}_1 + c\ \textbf{e}_2)$. Two notions of vectors in the plane with a distinct set of products that normally do not communicate with each other. In geometric algebra the interactions between the vectors and complex numbers are central. Writing the outer product of two vectors as $\textbf{u}\wedge \textbf{v} = \|\textbf{u}\|\|\textbf{v}\| \sin\theta\, \textbf{i}$, with the traditional cross-product $\textbf{u}\times \textbf{v} = -\textbf{u}\wedge\textbf{v}\ \textbf{i} = \|\textbf{u}\|\|\textbf{v}\| \sin\theta$, the geometric product of two vectors assumes the form

$$ 
\begin{align}
\textbf{u} \textbf{v} &= \|\textbf{u}\| \|\textbf{v}\| (\cos \theta + \textbf{i} \sin \theta)\\
&= \|\textbf{u}\| \|\textbf{v}\| e^{\textbf{i}\ \theta}\,,
\end{align}
$$

independent of the bases elements, where we define the exponentiation of a bi-vector using Euler's identity $e^{\textbf{i}\ \theta}=\cos\theta + \textbf{i}\sin \theta$. 

#### Rotations
The addition of both complex numbers and vectors acts componentwise. The product of two complex numbers $z_1=a_1 +\textbf{i}\ d_1,$ $z_2=a_2 +\textbf{i}\ d_2$, is implemented as the product of the absolute value and a rotation of the arguments

$$\begin{align}
z_1 z_2 &= (a_1 a_2 - d_1 d_2) + (a_1 d_2 + d_1 a_2)\ \textbf{i}\\
&= |z_1||z_2| e^{\textbf{i}(\theta_1+\theta_2)}\,,
\end{align}$$

with the polar representation $z_1=|z_1|e^{\textbf{i}\ \theta_1},$ $z_2=|z_2|e^{\textbf{i}\ \theta_2}$. The product of two vectors was discussed above. When multiplying a complex number $z=a+\textbf{i}\ d$ with a vector $\textbf{u} = b\ \textbf{e}_1 + c\ \textbf{e}_2$, we find a rotation

$$\begin{align}
z \textbf{u} &= (a + \textbf{i}\ d)(b\ \textbf{e}_1 + c\ \textbf{e}_2)\\
&= (ab + dc)\textbf{e}_1 + (ac- db)\textbf{e}_2\\
&= |z| \left[(b \cos \theta +c \sin\theta)\textbf{e}_1 + (- b \sin\theta + c \cos \theta )\textbf{e}_2\right]
\end{align}$$

writing the complex number in its polar decomposition $z=|z| e^{\textbf{i}\ \theta} = |z|\cos \theta + \textbf{i}\ |z| \sin \theta$. The inverse multiplication $\textbf{u}z$ yields a rotation by the same angle in the opposite direction $\theta \mapsto -\theta$. More generally, we can write a rotation of a vector $\textbf{u}$ by an angle $\theta$ more symmetrically using the conjugation

$$\textbf{u}_{rot} = e^{-\textbf{i}\ \theta/2}\ \textbf{u}\ e^{\textbf{i}\ \theta /2}\,,$$

where the multi-vector $R_\theta = e^{-\textbf{i}\ \theta/2}$ is known as the rotor, with its inverse $R_\theta^{-1}=R_{-\theta}$ as

$$\begin{align}
R_\theta  R_\theta^{-1} 
&= (\cos (\theta/2) - \textbf{i}\ \sin (\theta/2)) (\cos (\theta/2) + \textbf{i}\ \sin (\theta/2))\\
&= \cos^2 (\theta/2) + \sin^2(\theta/2) =1\,.
\end{align}$$

As we will see, this notion of rotation generalizes to higher-dimensional spaces. The conjugation of a vector with a rotor preserves the length of the vector, as

$$\begin{align}
\| R_\theta \textbf{u} R_\theta^{-1}\|^2 &= R_\theta \textbf{u} R_\theta^{-1} R_\theta \textbf{u} R_\theta^{-1}\\
&= R_\theta \textbf{u} \textbf{u} R_\theta^{-1}\\
&=  \|\textbf{u}\|^2 R_\theta  R_\theta^{-1}\\
&=  \|\textbf{u}\|^2\,.
\end{align}$$

Rotors are the multi-vectors resulting from the geometric products of unit vectors.

#### Normals
It follows that the product of a vector with the pseudoscalar yields its normal 

$$\textbf{i} (a \textbf{e}_1 + b \textbf{e}_2)  = a \textbf{e}_1 \textbf{e}_2 \textbf{e}_1 + b \textbf{e}_1 \textbf{e}_2 \textbf{e}_2 = b \textbf{e}_1 - a \textbf{e}_2.$$ 

As normals are very common in geometry, let's write it in terms of the duality operator

$$ \textbf{u}^* = \textbf{u}\ \textbf{i}^{-1}\,,$$

with the inverse of the pseudoscalar $\textbf{i}^{-1} = \textbf{e}_2\textbf{e}_1 = - \textbf{i}$. Using the duality operator, we can rewrite the definition of the cross-product in terms of the outer product

$$\textbf{u}\times \textbf{v} = (\textbf{u}\wedge \textbf{v})^*\,.$$

#### Projections and reflections
Another central operation in geometry is reflections. Given two vectors $\textbf{u}$ and $\textbf{v}$, we can decompose the first one into a component parallel and orthogonal to the second, *i.e.,* $\textbf{u} = \textbf{u}_{\|} + \textbf{u}_\perp$. In the language of geometric algebra, we obtain a very simple construction

$$\begin{align}
\textbf{u}_{\|} &= (\textbf{u}\cdot \textbf{v})\textbf{v}^{-1}\,,\\
\textbf{u}_{\perp} &= (\textbf{u}\wedge \textbf{v})\textbf{v}^{-1}\,,
\end{align}$$

which can be proven by substituting $\textbf{u} = \textbf{u}_{\|} + \textbf{u}_\perp$ in the above equations with the conditions $\textbf{u}_\perp \cdot \textbf{v}=0$ and $\textbf{u}_{\|} \wedge \textbf{v}=0$. The reflection of a vector $\textbf{u}$ through the line spanned by $\textbf{v}$ is given by the conjugation of $\textbf{u}$ by $\textbf{v}$, *i.e.,* given $\textbf{u} = \textbf{u}_{\|} + \textbf{u}_\perp$, the reflection of $\textbf{u}$ in the line associated to $\textbf{v}$ yields

$$\begin{align}
\textbf{u}_{ref} 
&= \textbf{u}_{\|} - \textbf{u}_\perp\\
&= (\textbf{u}\cdot \textbf{v})\textbf{v}^{-1} -(\textbf{u}\wedge \textbf{v})\textbf{v}^{-1}\\
&= (\textbf{u}\cdot \textbf{v} - \textbf{u}\wedge \textbf{v})\textbf{v}^{-1}\\
&= \textbf{v}\textbf{u}\textbf{v}^{-1}
\end{align}$$

We saw above that the rotor $R_\theta$ can be written as the geometric product of two unit vectors $\textbf{v},\textbf{w}$ with an angular separation $-\theta/2$. It thus follows that every rotation is the result of two reflections 

$$ \textbf{u}_{rot} = \textbf{v}(\textbf{w} \textbf{u} \textbf{w}^{-1}) \textbf{v}^{-1}\,.$$

### Three-dimensional space
Consider the orthonormal basis $\{\textbf{e}_1,\textbf{e}_2,\textbf{e}_3\}$ of the three-dimensional Euclidean plane $\mathbb{R}^3$. The corresponding geometric algebra $\mathbb{G}^3$ is spanned by the elements 

$$\{1, \textbf{e}_1, \textbf{e}_2, \textbf{e}_3, \textbf{e}_1\textbf{e}_2, \textbf{e}_1\textbf{e}_3, \textbf{e}_2\textbf{e}_3, \textbf{e}_1\textbf{e}_2\textbf{e}_3\}$$

consisting of the unit scalar, three vectors corresponding to the three independent directions, three bi-vectors corresponding to the three independent two-dimensional hyperplanes, and a unique tri-vector corresponding to the volume element. 

The product of two vectors takes the form

$$\begin{align}
\textbf{u}\textbf{v} 
&= (a_1 \textbf{e}_1+b_1 \textbf{e}_2+c_1 \textbf{e}_1) (a_2 \textbf{e}_1+b_2 \textbf{e}_2+c_2 \textbf{e}_1) \\
&= (a_1 a_2 + b_1 b_2 + c_1 c_2) + (a_1 b_2 - b_1 a_2) \textbf{e}_1\textbf{e}_2+ (a_1 c_2 - c_1 a_2)\textbf{e}_1\textbf{e}_3+ (b_1 c_2 - c_1 b_2)\textbf{e}_2\textbf{e}_3\\
&=\textbf{u}\cdot\textbf{v} + \textbf{u}\wedge \textbf{v}\,,
\end{align}$$

where we again can identify the inner product $\textbf{u} \cdot \textbf{v} = a_1 a_2 + b_1 b_2 + c_1 c_2$ and the outer product $\textbf{u}\wedge \textbf{v} = (a_1 b_2 - b_1 a_2) \textbf{e}_1\textbf{e}_2+ (a_1 c_2 - c_1 a_2)\textbf{e}_1\textbf{e}_3+ (b_1 c_2 - c_1 b_2)\textbf{e}_2\textbf{e}_3$. 

The two-vectors, corresponding to oriented area elements, span a space whose elements are known as pseudovectors. A pseudovector is of the form $\textbf{B} = a\ \textbf{B}_1 + b\ \textbf{B}_2 + c\ \textbf{B}_3$ where $\textbf{B}_1=\textbf{e}_2 \textbf{e}_3,$ $\textbf{B}_2 = \textbf{e}_3 \textbf{e}_1$ and $\textbf{B}_3 = \textbf{e}_1 \textbf{e}_2$ with the product $\textbf{B}_i \textbf{B}_j = -\delta_{ij} - \epsilon_{ijk}\textbf{B}_k$ with the Kronneker delta  $\delta_{ij}$ and the Levi-Civita symbol $\epsilon_{ijk}$. This coincides with the pseudovectors known in physics since they are invariant under the parity operation $\textbf{e}_i \mapsto - \textbf{e}_i$. The product of two pseudovectors yields the multi-vector

$$\begin{align}
\textbf{A} \textbf{B} &= (a_1\ \textbf{B}_1 + b_1\ \textbf{B}_2 + c_1\ \textbf{B}_3)(a_2\ \textbf{B}_1 + b_2\ \textbf{B}_2 + c_2\ \textbf{B}_3)\\
&= -(a_1 a_2 + b_1 b_2 + c_1 c_2) - (b_1 c_2 - c_1 b_2) \textbf{B}_1 - (c_1 a_2 - a_1 c_2) \textbf{B}_2  - (a_1 b_2 - b_1 a_2) \textbf{B}_3\,.
\end{align}$$

The bi-vectors can be associated to the quaternions $\textbf{i} = \textbf{B}_1,$ $\textbf{j} = -\textbf{B}_2$, $\textbf{k}=\textbf{B}_3$.

The canonical tri-vector is known as the pseudoscalar $\textbf{I} = \textbf{e}_1 \textbf{e}_2 \textbf{e}_3$, representing the oriented volume element. The exterior product of three vectors 

$$\begin{align}
\textbf{u}\wedge \textbf{v} \wedge \textbf{w} 
&= \textbf{u} \cdot (\textbf{v} \times \textbf{w})\\
&= \alpha\ \textbf{I}
\end{align}$$

with $|\alpha|$ the volume of the parallelepiped spanned by the three vectors (and the cross-product is defined below). The sign is the orientation of the triple $(\textbf{u}, \textbf{v}, \textbf{w})$. 

The geometric product of the pseudoscalar with a vector is a bi-vector, $\textbf{e}_1 \textbf{I} = \textbf{B}_1,$ $\textbf{e}_2 \textbf{I} = \textbf{B}_2,$ and $\textbf{e}_3 \textbf{I} = \textbf{B}_3$. Note that the pseudovector is normal to the original vector (together they span the space $\textbf{I}$). When acting on the pseudovectors, we retrieve the normal vectors, $\textbf{B}_1 \textbf{I}= -\textbf{e}_1,$ $\textbf{B}_2 \textbf{I}= - \textbf{e}_2,$ and $\textbf{B}_3 \textbf{I}= -\textbf{e}_3$. Hence, the pseudoscalar maps the vectors to the pseudovectors and pseudovectors to vectors. This is again nicely implemented by the duality operator

$$\textbf{u}^* = \textbf{u}\ \textbf{I}^{-1}\,,$$

with the inverse $\textbf{I}^{-1}=\textbf{e}_3 \textbf{e}_2 \textbf{e}_1 = -\textbf{I}$.

The multiplication of the bases elements follows the rule

$$\textbf{e}_i \textbf{e}_j = \delta_{ij} + \textbf{I} \epsilon_{ijk}\textbf{e}_k$$

which is known as the Pauli algebra of quantum mechanics. The Pauli spin matrices

$$\begin{align}
\sigma_1=\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix},\
\sigma_2=\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},\
\sigma_3=\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix},
\end{align}$$

thus form a representation of the algebra of three-dimensional space.

#### Rotations
Rotations of vectors can again be implemented with the rotors. Given a vector $\textbf{u}$. Its rotation by an angle $\theta$ in the plane $\textbf{B} = a\ \textbf{B}_1 + b\ \textbf{B}_2 + c\ \textbf{B}_3$ is given by the conjugation

$$\textbf{u}_{rot} = R_\theta \textbf{u} R_\theta^{-1}$$

with the rotor $R_\theta = e^{-\textbf{B} \theta/2}$, where the exponentiation of the pseudovector is defined as $e^{\textbf{B} \theta}=\cos \theta + \textbf{B} \sin \theta$, which makes sense since the pseudovectors $\textbf{B}_1,$ $\textbf{B}_2,$ $\textbf{B}_3$ squares to $-1$ like the bi-vector $\textbf{i}$ in the two-dimensional setting. In $\mathbb{G}^3$, we can also express these rotors in terms of the quaternions. In fact, each pseudovector $\textbf{B}$ represents a two-dimensional plane with an associated geometric subalgebra isomorphic to $\mathbb{G}^2$. The rotor is again the geometric product of two unit vectors spanning the plane with an angle $-\theta/2$. 

When rotating around a unit vector $\textbf{n}$ we obtain the rotor $R=e^{-\textbf{n}\, \textbf{I}\, \theta/2}$. 
#### Normals
The dual of a multi-vector is given by the operation

$$ A^* = A \textbf{I}^{-1}\,. $$

Scalars are dual to pseudoscalars. Vectors are dual to the pseudovectors representing the normal planes. The traditional cross-product of two vectors is the dual of the outer product

$$ \textbf{u} \times \textbf{v} = (\textbf{u} \wedge \textbf{v})^*\,.$$

Note that the cross-product only makes sense in the two- and three-dimensional context. In higher-dimensional spaces, the pseudovectors do not map so neatly on the vectors. The outer product is well-defined for the geometric algebra of $n$-dimensional Euclidean space.

#### Projections and reflections
Just like in the two-dimensional case, we can use the language of geometric algebra to define projections and reflections. Given a vector $\textbf{u}$ we can decompose the vector in a component parallel $\textbf{u}_\|$ and normal $\textbf{u}_\perp$ to another vector $\textbf{v}$. These components again look like

$$\begin{align}
\textbf{u}_{\|} &= (\textbf{u}\cdot \textbf{v})\textbf{v}^{-1}\,,\\
\textbf{u}_{\perp} &= (\textbf{u}\wedge \textbf{v})\textbf{v}^{-1}\,.
\end{align}$$

The reflection of the vector $\textbf{u}$ in the line represented by $\textbf{v}$ again yields the conjugation of $\textbf{u}$ by $\textbf{v}$, *i.e.,*

$$\textbf{u}_{ref} = \textbf{u}_{\|} - \textbf{u}_{\perp} = \textbf{v}\textbf{u}\textbf{v}^{-1}.$$

However in the three-dimensional setting, unlike the two-dimensional case, we might want to decompose a vector $\textbf{u}$ into a term parallel and normal to a plane represented by a pseudovector $\textbf{B}$. Geometric algebra beautifully extends this formula with the identities

$$\begin{align}
\textbf{u}_{\|} &= (\textbf{u}\cdot \textbf{B})\textbf{B}^{-1}\,,\\
\textbf{u}_{\perp} &= (\textbf{u}\wedge \textbf{B})\textbf{B}^{-1}\,.
\end{align}$$

A non-zero pseudovector always has an inverse, since $(\textbf{e}_1 \textbf{e}_2)^{-1}=\textbf{e}_2\textbf{e}_1$.

Where the inner and outer product of a vector and a bi-vector $\textbf{A},\textbf{B}$ are defined as the $1$- and $3$-vector part of their geometric product

$$\begin{align}
\textbf{A}\cdot \textbf{B} &= \langle \textbf{A}\textbf{B}\rangle_{1}\,,\\
\textbf{A}\wedge \textbf{B} &= \langle \textbf{A}\textbf{B}\rangle_{3}\,.
\end{align}$$

The reflection of $\textbf{u}$ with respect to the plane represented by $\textbf{B}$ assumes the form

$$\textbf{u}_{ref} = \textbf{u}_{\|} - \textbf{u}_\perp = -\textbf{B} \textbf{u} \textbf{B}^{-1}\,,$$

using the observation that the geometric product of a vector with a bi-vector assumes the form

$$\begin{align}
\textbf{u}\textbf{B} &= \textbf{u}\cdot\textbf{B} + \textbf{u}\wedge \textbf{B}\,,\\
\textbf{B}\textbf{u} &= \textbf{u}\cdot\textbf{B} - \textbf{u}\wedge \textbf{B}\,.
\end{align}$$

This decomposition is not generally true for the geometric product of multi-vectors. 

### $n$-dimensional space
These notions neatly generalize to the geometric algebra $\mathbb{G}^n$ extending the vector algebra of the $n$-dimensional Euclidean plane $\mathbb{R}^n$. Given an orthonormal basis $\{\textbf{e}_1,\dots,\textbf{e}_n\}$, the geometric algebra has a canonical basis of the form 

$$\{1, \textbf{e}_1, \textbf{e}_2,\dots,\textbf{e}_1\textbf{e}_2\dots\textbf{e}_n \}$$ 

consisting of a scalar and $m$-vectors with $m=1,\dots,n$. In the space $\mathbb{R}^n$ we can identify $k$-dimensional hyperspace, which that can be identified by a *$k$-blade* consisting of the product of a set of $k$ orthogonal vectors $\textbf{B} = \textbf{b}_1\textbf{b}_2\dots\textbf{b}_k$ spanning the hyperspace. Vectors and bi-vectors are examples of grade $1$ and grande $2$ blades (we use boldface capitals for blades and normal capitals for general multi-vectors). In general, every $n$-vector is a blade as it can be written using a suitable orthogonal basis. A blade is included in another blade, $\textbf{A} \subset \textbf{B}$, when the associated hyperplane is included in the larger hyperplane. 

#### Normals
The pseudoscalar $\textbf{I}=\textbf{e}_1\textbf{e}_2\dots\textbf{e}_n$, associated to the space $\mathbb{R}^n$, is an important element of the geometric algebra as it allows us to relate the multi-vectors to their dual, 

$$A^* = A\ \textbf{I}^{-1}\,,$$

with the inverse pseudoscalar $\textbf{I}^{-1}=\textbf{e}_n\dots\textbf{e}_1$. The *orthogonal complement* of a $j$-blade $\textbf{B}$ is the $(n-1)$-blade $\textbf{B}^*$ consisting of the normal basis vectors.

#### Inner and outer products 
Let $\langle C \rangle_j$ denote the $j$-vector part of $C$. We define the inner and outer product of a $j$- and a $k$-vector $A,B$ as the $(j-k)$- and $(j+k)$-vector part of the geometric product

$$\begin{align}
\textbf{A}\cdot \textbf{B} &= \langle \textbf{A}\textbf{B}\rangle_{k-j}\,,\\
\textbf{A}\wedge \textbf{B} &= \langle \textbf{A}\textbf{B}\rangle_{k+j}\,.
\end{align}$$

The geometric product of a $j$- and a $k$-blade consists of multi-vector with a $(k-j)$-, $(k-j+2)$-, $\dots$, $(j+k)$-vector part. The inner and outer products of general multi-vectors are defined using the products of the blades with linearity. 

The geometric product of a vector with a $k$-blade assumes the form

$$\begin{align}
\textbf{u}\textbf{B} &= \textbf{u}\cdot\textbf{B} + \textbf{u}\wedge \textbf{B}\,.
\end{align}$$

#### Reflections and projections
We can always write a vector $\textbf{u}=\textbf{u}_{\|}+\textbf{u}_\perp$ in terms of a parallel and an orthogonal part with respect to a blade $\textbf{B}$, with

$$\begin{align}
\textbf{u}_{\|} &= (\textbf{u}\cdot \textbf{B})\textbf{B}^{-1}\,,\\
\textbf{u}_{\perp} &= (\textbf{u}\wedge \textbf{B})\textbf{B}^{-1}\,.
\end{align}$$

The reflection of $\textbf{u}$ in $\textbf{B}$ takes the form $\textbf{u}_{ref}=(-1)^{k+1}\textbf{B} \textbf{u} \textbf{B}^{-1}$. When working with the dual $\textbf{b}=\textbf{B}^*$, we obtain the relation $\textbf{u}_{ref} = -\textbf{b}\textbf{u}\textbf{b}^{-1}$.

#### Reflections and projections
Rotations of vectors can again be implemented with the rotors. Given a vector $\textbf{u}$. Its rotation by an angle $\theta$ in the plane $\textbf{B}$ is given by the conjugation

$$\textbf{u}_{rot} = R_\theta \textbf{u} R_\theta^{-1}$$

with the rotor $R_\theta = e^{-\textbf{B} \theta/2}$, where the exponentiation of the blade is defined as $e^{\textbf{B} \theta}=\cos \theta + \textbf{B} \sin \theta.$

Two subsequent rotations $R_1$ and $R_2$ lead to a rotation of the rotor, $R_3 = R_2 R_1$. If $\textbf{u}$ is rotates by $R_1$ and $R_2$ we obtain

$$\textbf{u}_{rot} = R_2 R_1 \textbf{u} R_1^{-1} R_2^{-1} = (R_2 R_1) \textbf{u} (R_2 R_1)^{-1}$$


#### Volumes
The volume (norm) of a $k$-blade $\textbf{B}=\textbf{b}_1 \dots \textbf{b}_k$ is defined as the volume of the space spanned by the vectors $\| \textbf{B}\|=\|\textbf{b}_1\|\dots\|\textbf{b}_k\|$.

#### Complex numbers
Each hyperplane in $\mathbb{R}^n$, corresponding to a bi-vector yields a geometric subalgebra isomorphic to $\mathbb{G}^2$. In this space, we identify the complex numbers $\{a+\textbf{i}\ b\}$. Analogously, every three-dimensional hyperspace yields a geometric subalgebra isomorphic to $\mathbb{G}^3$ with a quaternion subalgebra with the complex numbers $\{a + \textbf{i}\ b + \textbf{j}\ c + \textbf{k}\ d \}.$

### Geometric calculus
We can develop calculus on geometric algebra. In geometric calculus, the gradient operator 

$$\nabla = \textbf{e}_1 \partial_1 + \dots + \textbf{e}_n \partial_n$$

on a vector-valued function is defined as

$$\nabla \textbf{f}  = \nabla \cdot \textbf{f} + \nabla \wedge \textbf{f}\,,$$

unifying the divergence and curl.

Working in $\mathbb{G}^2$, the gradient of a complex function $f(x, y) = u(x,y) + \textbf{i}\ v(x,y)$ is defined as

$$\begin{align} 
\nabla f &= \textbf{e}_1(u_x + \textbf{i}\ v_x) + \textbf{e}_2(u_y + \textbf{i}\ v_y)\\
&= \textbf{e}_1(u_x -v_y) + \textbf{e}_2 (v_x + u_y)\,,
\end{align}$$

which vanishes due to the Cauchy-Riemann equations for analytic functions. 

A multi-vector valued function $F$ on $\mathbb{R}^n$ is called analytic when 

$$\nabla F = 0\,.$$

