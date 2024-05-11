---
pdf: 
module: 
lecture: 
date: 2024-05-10T16:41:00
version:
  - LA-24
last-revision: 
notes-taken: false
tags:
  - LinearAlgebra/EigenVectors LinearAlgebra/EigenValues
---
# Eigen Values and Eigen Vectors

When a matrix $A$ is multiplied by a vector $x$, then are certain possibilities,
1. The vector gets transformed into a new vector.
$$
Ax = b
$$

![[Eigen Values and Eigen Vectors-20240510164558947.webp]]


2. The vector remains in the same direction i.e. the vector is scaled (shrunk or stretched or reversed or remains the same).
$$
Ax = \lambda x
$$

![[Eigen Values and Eigen Vectors-20240510164620740.webp]]


The vector $x$ which remains in the same direction after multiplying with $A$ is called the eigen vector of the matrix $A$. The value $\lambda$ associated with the eigen vector is called the eigen value.

$\lambda$ can be $0$ i.e. $Ax = 0 x$ meaning that the eigen vector is in null space.
Eigen vectors are non-zero vectors by definition.

> [!observation] 
> Eigen vectors makes sense only for square matrices.
> 
> $$
> \underset{m \times n}{A} \cdot \underset{n \times 1}{x} = \lambda \cdot \underset{m \times 1}{x}
> $$
> The vector $x$ on LHS $\in \mathbb{R}^n$, but the resultant vector $x$ on RHS $\in \mathbb{R}^m$. Hence $m = n$ i.e. $A$ is a square matrix.

Identity matrix of any vector space $n$ can have infinitely many eigen vectors, but there are only $n$ LI eigen vectors that can span the entire vector space $\mathbb{R}^n$.
$$
\begin{bmatrix}
1&0&0&\dots&0 \\
0&1&0&\dots&0 \\
0&0&1&\dots&0 \\
\vdots&\vdots&\vdots&\ddots&\vdots \\
0&0&0&\dots&1
\end{bmatrix}
\begin{bmatrix}
a \\
b \\
c \\
\vdots \\
d
\end{bmatrix} = 
\begin{bmatrix}
a \\
b \\
c \\
\vdots \\
d
\end{bmatrix}
$$

> [!interesting] 
> There are infinitely many eigen vectors for any matrix.

If $x$ is an eigen vector for a matrix $A$, then any non-zero multiple of eigen vector $x$ is also an eigen vector for the same matrix $A$, with $\lambda$ being the eigen value.

If $x$ is an eigen vector or $A$, then 
$$
Ax = \lambda x
$$
If $kx$, where $k \in \mathbb{R} - \{0\}$ is a eigen vector of $A$, then 
$$
\begin{equation}
\begin{split}
A (kx) &= k \; Ax\\
&= k \; \lambda x\\
&= \lambda \; (kx)
\end{split}
\end{equation}
$$

## Characteristic Equation
Since both the eigen values and eigen vectors are unknown in the equation $Ax=\lambda x$, characteristic equation is solved to find $\lambda$ and $x$.
$$
\begin{equation} 
\begin{split}
Ax &= \lambda x\\
Ax - \lambda x &= 0\\
(A - \lambda \mathcal{I})\; x &= 0\\
\end{split}
\end{equation}
$$
Since $\lambda$ is a scalar, it is multiplied with identity matrix $\mathcal{I}$ to represent it as a matrix.
In the above homogenous system, only non-trivial solution is possible, since eigen vector $x$ is a non-zero vector i.e. $\exists c_{i} \not= 0$ in $x$. Hence the columns of $(A - \lambda \mathcal{I})$ are LD.

Since the columns of $(A - \lambda \mathcal{I})$ are LD,
$$
\begin{equation}
\mid A - \lambda \mathcal{I} \mid\; = 0
\end{equation}
$$
The above characteristic equation can be solved to obtain the eigen vector $\lambda$ and then $\lambda$ can be substituted back in $(A - \lambda \mathcal{I})\; x = 0$ to obtain the eigen value $x$. 

Since $\mid A - \lambda \mathcal{I} \mid\; = 0$, rank $(A - \lambda \mathcal{I}) \lt n$ and at least one free variable always exists.

![[Eigen Values and Eigen Vectors-20240511093730179.webp|Solve eigen value problem for $n \times n$ problem]]

Eigen vectors from different eigen values are linearly independent.
If $\lambda_{1} \not= \lambda_{2}$, then $e_{1} \not= k \; e_{2}$, where $k \in \mathbb{R}$

## Linearly independent Eigen vectors
Consider the characteristic equation in which eigen values are repeating,
$$
(\lambda - \lambda_{1})^{m_{1}} (\lambda - \lambda_{2})^{m_{2}} \dots (\lambda - \lambda_{k})^{m_{k}} = 0
$$
- At least $k$ LI eigen vectors, since there are $k$ distinct eigen values
- Atmost $(m_{1} + m_{2} + \dots + m_{n})$ number of LI eigen vectors 

For $\lambda = \lambda_{1}$, there are at most $m_{1}$ LI eigen vectors
For $\lambda = \lambda_{2}$, there are at most $m_{2}$ LI eigen vectors
$\vdots$
For $\lambda = \lambda_{k}$, there are at most $m_{k}$ LI eigen vectors

For every eigen value $\lambda$,
1. Geometric Multiplicity: No of LI eigen vectors corresponding to $\lambda$
2. Arithmetic Multiplicity: No of times $\lambda$ is repeating

Consider the eigen value $(\lambda - \lambda_{k})^{p}$, there can be only atmost $p$ LI eigen vectors corresponding to $\lambda = \lambda_{k}$, hence
$$
\text{GM} \le \text{AM}
$$

> [!summary] 

**Case 1**: All $\lambda$'s are distinct. 
There is a corresponding eigen vector for every $\lambda$. There are exactly $n$ LI eigen vectors.
There are no repeating eigen values i.e. $\text{AM} = 1$
Every eigen value has only one LI eigen vector corresponding to it i.e. $\text{GM} = 1$
$$
\text{AM} = \text{GM}
$$

**Case 2**: Some or all of the $\lambda$'s are repeating. 
Some eigen values may repeat i.e. $\text{GM} \gt 1$
For every repeating eigen value, there are at most $\text{AM}$ number of LI eigen vectors i.e. $\text{AM}$ is the maximum number of corresponding LI eigen vectors
$$
\text{GM} \le \text{AM}
$$

> [!foreshadow] 
> Symmetric matrices provide an interesting case scenario regarding the number of LI eigen vectors.

---
## Real Symmetric Matrices
Even when there are one or more repeating eigen values, symmetric matrices of order $n$ have **<mark style="background-color: #fff88f; color: black">exactly</mark>** $n$ LI eigen vectors i.e. $\text{AM} = \text{GM} = n$.

Properties of Real Symmetric matrices,
1. They have $n$ real eigen values.
2. They have exactly $n$ orthogonal LI eigen vectors.

> [!tip] Mutliplying two orthogonal vector gives $\vec{0}$

Even if there are repeating eigen values, all of the $n$ eigen vectors are LI.