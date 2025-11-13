# Eigenvalues and Eigenvectors

## Definition

### Eigenvector and Eigenvalue
Let $A$ be an $n \times n$ matrix. A non-zero vector $\mathbf{v}$ is called an **eigenvector** of $A$ if there exists a scalar $\lambda$ such that:

$$A\mathbf{v} = \lambda\mathbf{v}$$

The scalar $\lambda$ is called an **eigenvalue** of $A$ corresponding to the eigenvector $\mathbf{v}$.

### Key Insight
**Eigenvectors are special vectors that don't change direction when the transformation $A$ is applied** — they only get scaled by the factor $\lambda$.

---

## Characteristic Equation

### Deriving the Characteristic Equation
From the eigenvalue equation $A\mathbf{v} = \lambda\mathbf{v}$:

$$A\mathbf{v} = \lambda I\mathbf{v}$$

$$(A - \lambda I)\mathbf{v} = 0$$

For a non-trivial solution (non-zero $\mathbf{v}$) to exist:

$$\det(A - \lambda I) = 0$$

This is called the **characteristic equation** of matrix $A$.

### Characteristic Polynomial
The expression $\det(A - \lambda I)$ is a polynomial in $\lambda$ called the **characteristic polynomial**:

$$p(\lambda) = \det(A - \lambda I)$$

For an $n \times n$ matrix, this is a polynomial of degree $n$.

---

## Finding Eigenvalues and Eigenvectors

### Step-by-Step Process

**Step 1: Find Eigenvalues**
- Compute the characteristic polynomial: $\det(A - \lambda I)$
- Solve $\det(A - \lambda I) = 0$ for $\lambda$
- The solutions are the eigenvalues

**Step 2: Find Eigenvectors**
For each eigenvalue $\lambda_i$:
- Solve the system $(A - \lambda_i I)\mathbf{v} = 0$
- The non-zero solutions $\mathbf{v}$ are the eigenvectors
- The set of all solutions forms the **eigenspace** for $\lambda_i$

### Example 1: $2 \times 2$ Matrix

Let $A = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}$

**Find eigenvalues:**

$$A - \lambda I = \begin{bmatrix} 4-\lambda & 2 \\ 1 & 3-\lambda \end{bmatrix}$$

$$\det(A - \lambda I) = (4-\lambda)(3-\lambda) - 2 = \lambda^2 - 7\lambda + 10 = 0$$

$$(\lambda - 5)(\lambda - 2) = 0$$

Eigenvalues: $\lambda_1 = 5, \lambda_2 = 2$

**Find eigenvector for $\lambda_1 = 5$:**

$$(A - 5I)\mathbf{v} = 0$$

$$\begin{bmatrix} -1 & 2 \\ 1 & -2 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

From first row: $-v_1 + 2v_2 = 0 \Rightarrow v_1 = 2v_2$

Let $v_2 = 1$, then $v_1 = 2$

Eigenvector: $\mathbf{v}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix}$

**Find eigenvector for $\lambda_2 = 2$:**

$$(A - 2I)\mathbf{v} = 0$$

$$\begin{bmatrix} 2 & 2 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

From first row: $2v_1 + 2v_2 = 0 \Rightarrow v_1 = -v_2$

Let $v_2 = 1$, then $v_1 = -1$

Eigenvector: $\mathbf{v}_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$

**Verification:**

$$A\mathbf{v}_1 = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}\begin{bmatrix} 2 \\ 1 \end{bmatrix} = \begin{bmatrix} 10 \\ 5 \end{bmatrix} = 5\begin{bmatrix} 2 \\ 1 \end{bmatrix}$$ ✓

$$A\mathbf{v}_2 = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}\begin{bmatrix} -1 \\ 1 \end{bmatrix} = \begin{bmatrix} -2 \\ 2 \end{bmatrix} = 2\begin{bmatrix} -1 \\ 1 \end{bmatrix}$$ ✓

---

### Example 2: $3 \times 3$ Matrix

Let $A = \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{bmatrix}$

**Find eigenvalues:**

$$A - \lambda I = \begin{bmatrix} 2-\lambda & 1 & 0 \\ 0 & 2-\lambda & 0 \\ 0 & 0 & 3-\lambda \end{bmatrix}$$

For upper triangular matrix, determinant is product of diagonal entries:

$$\det(A - \lambda I) = (2-\lambda)^2(3-\lambda) = 0$$

Eigenvalues: $\lambda_1 = 2$ (with multiplicity 2), $\lambda_2 = 3$

**Find eigenvectors for $\lambda_1 = 2$:**

$$\begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

From equations: $v_2 = 0, v_3 = 0, v_1$ is free

Eigenvector: $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}$

**Find eigenvector for $\lambda_2 = 3$:**

$$\begin{bmatrix} -1 & 1 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 0 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

From equations: $v_2 = 0, v_1 = 0, v_3$ is free

Eigenvector: $\mathbf{v}_2 = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$

---

## Eigenspace

### Definition
For each eigenvalue $\lambda_i$, the **eigenspace** $E_{\lambda_i}$ is:

$$E_{\lambda_i} = \text{null}(A - \lambda_i I) = \{\mathbf{v} \mid (A - \lambda_i I)\mathbf{v} = 0\}$$

This is a **subspace** of $\mathbb{R}^n$.

### Geometric Multiplicity
The **geometric multiplicity** of an eigenvalue $\lambda$ is the dimension of its eigenspace:

$$\text{geometric multiplicity} = \dim(E_\lambda) = \text{nullity}(A - \lambda I)$$

### Algebraic Multiplicity
The **algebraic multiplicity** of an eigenvalue $\lambda$ is the number of times $(\lambda - \lambda_i)$ appears as a factor in the characteristic polynomial.

### Important Relationship
For any eigenvalue $\lambda$:

$$1 \leq \text{geometric multiplicity} \leq \text{algebraic multiplicity}$$

---

## Properties of Eigenvalues and Eigenvectors

### Property 1: Scalar Multiples
If $\mathbf{v}$ is an eigenvector of $A$ with eigenvalue $\lambda$, then any scalar multiple $c\mathbf{v}$ (where $c \neq 0$) is also an eigenvector with the same eigenvalue.

**Proof**: $A(c\mathbf{v}) = cA\mathbf{v} = c\lambda\mathbf{v} = \lambda(c\mathbf{v})$

### Property 2: Linear Independence
Eigenvectors corresponding to **distinct eigenvalues** are linearly independent.

### Property 3: Trace and Determinant
For an $n \times n$ matrix $A$ with eigenvalues $\lambda_1, \lambda_2, \ldots, \lambda_n$:

- **Sum of eigenvalues** = $\text{trace}(A)$ = sum of diagonal elements
  $$\sum_{i=1}^n \lambda_i = \text{tr}(A)$$

- **Product of eigenvalues** = $\det(A)$
  $$\prod_{i=1}^n \lambda_i = \det(A)$$

### Property 4: Powers of Matrix
If $\mathbf{v}$ is an eigenvector of $A$ with eigenvalue $\lambda$, then:
- $\mathbf{v}$ is an eigenvector of $A^k$ with eigenvalue $\lambda^k$
- $\mathbf{v}$ is an eigenvector of $A^{-1}$ with eigenvalue $\lambda^{-1}$ (if $A$ is invertible)

### Property 5: Polynomial of Matrix
If $\mathbf{v}$ is an eigenvector of $A$ with eigenvalue $\lambda$, and $p(x) = a_nx^n + \cdots + a_1x + a_0$, then:
- $\mathbf{v}$ is an eigenvector of $p(A)$ with eigenvalue $p(\lambda)$

### Property 6: Similar Matrices
If $B = P^{-1}AP$ (matrices $A$ and $B$ are similar), then:
- $A$ and $B$ have the same eigenvalues
- If $\mathbf{v}$ is an eigenvector of $A$, then $P^{-1}\mathbf{v}$ is an eigenvector of $B$

---

## Special Types of Matrices

### 1. Symmetric Matrices
A real symmetric matrix ($A = A^T$) has:
- **All eigenvalues are real**
- **Eigenvectors corresponding to distinct eigenvalues are orthogonal**
- Always **diagonalizable**

**Example**: $A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$

Eigenvalues: $\lambda_1 = 3, \lambda_2 = 1$

Eigenvectors: $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}, \mathbf{v}_2 = \begin{bmatrix} 1 \\ -1 \end{bmatrix}$

Check orthogonality: $\mathbf{v}_1 \cdot \mathbf{v}_2 = 1(1) + 1(-1) = 0$ ✓

### 2. Triangular Matrices
For upper or lower triangular matrices:
- **Eigenvalues are the diagonal entries**

**Example**: $A = \begin{bmatrix} 3 & 2 & 1 \\ 0 & 5 & 4 \\ 0 & 0 & 7 \end{bmatrix}$

Eigenvalues: $\lambda_1 = 3, \lambda_2 = 5, \lambda_3 = 7$

### 3. Orthogonal Matrices
An orthogonal matrix ($Q^TQ = I$) has:
- **All eigenvalues have absolute value 1** ($|\lambda| = 1$)
- Complex eigenvalues come in conjugate pairs

### 4. Positive Definite Matrices
A positive definite matrix has:
- **All eigenvalues are positive** ($\lambda_i > 0$)

### 5. Diagonal Matrices
A diagonal matrix $D = \text{diag}(d_1, d_2, \ldots, d_n)$ has:
- Eigenvalues: $\lambda_i = d_i$
- Eigenvectors: standard basis vectors $\mathbf{e}_i$

---

## Diagonalization

### Definition
A matrix $A$ is **diagonalizable** if there exists an invertible matrix $P$ and a diagonal matrix $D$ such that:

$$A = PDP^{-1}$$

or equivalently:

$$P^{-1}AP = D$$

### When is a Matrix Diagonalizable?

An $n \times n$ matrix $A$ is diagonalizable if and only if:
- $A$ has $n$ linearly independent eigenvectors

**Sufficient Conditions**:
1. $A$ has $n$ distinct eigenvalues
2. $A$ is a symmetric matrix (real)
3. For each eigenvalue, geometric multiplicity = algebraic multiplicity

### How to Diagonalize

**Step 1**: Find all eigenvalues $\lambda_1, \lambda_2, \ldots, \lambda_n$

**Step 2**: Find corresponding eigenvectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n$

**Step 3**: Form matrices:
- $P = [\mathbf{v}_1 \, \mathbf{v}_2 \, \cdots \, \mathbf{v}_n]$ (eigenvectors as columns)
- $D = \begin{bmatrix} \lambda_1 & 0 & \cdots & 0 \\ 0 & \lambda_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \lambda_n \end{bmatrix}$

**Step 4**: Verify $A = PDP^{-1}$ or $AP = PD$

### Example: Diagonalization

Let $A = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}$ (from Example 1)

We found:
- Eigenvalues: $\lambda_1 = 5, \lambda_2 = 2$
- Eigenvectors: $\mathbf{v}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix}, \mathbf{v}_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$

Form matrices:

$$P = \begin{bmatrix} 2 & -1 \\ 1 & 1 \end{bmatrix}, \quad D = \begin{bmatrix} 5 & 0 \\ 0 & 2 \end{bmatrix}$$

Compute $P^{-1}$:

$$P^{-1} = \frac{1}{3}\begin{bmatrix} 1 & 1 \\ -1 & 2 \end{bmatrix}$$

Verify: $A = PDP^{-1}$

$$PDP^{-1} = \begin{bmatrix} 2 & -1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 5 & 0 \\ 0 & 2 \end{bmatrix}\frac{1}{3}\begin{bmatrix} 1 & 1 \\ -1 & 2 \end{bmatrix}$$

$$= \begin{bmatrix} 10 & -2 \\ 5 & 2 \end{bmatrix}\frac{1}{3}\begin{bmatrix} 1 & 1 \\ -1 & 2 \end{bmatrix} = \frac{1}{3}\begin{bmatrix} 12 & 6 \\ 3 & 9 \end{bmatrix} = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}$$ ✓

---

## Applications of Diagonalization

### 1. Computing Matrix Powers
If $A = PDP^{-1}$, then:

$$A^k = PD^kP^{-1}$$

where $D^k$ is easy to compute (just raise diagonal entries to power $k$).

**Example**: Find $A^{10}$ where $A = \begin{bmatrix} 4 & 2 \\ 1 & 3 \end{bmatrix}$

Using diagonalization:

$$D^{10} = \begin{bmatrix} 5^{10} & 0 \\ 0 & 2^{10} \end{bmatrix} = \begin{bmatrix} 9765625 & 0 \\ 0 & 1024 \end{bmatrix}$$

$$A^{10} = PD^{10}P^{-1} = \begin{bmatrix} 2 & -1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 9765625 & 0 \\ 0 & 1024 \end{bmatrix}\frac{1}{3}\begin{bmatrix} 1 & 1 \\ -1 & 2 \end{bmatrix}$$

### 2. Solving Differential Equations
The system $\frac{d\mathbf{x}}{dt} = A\mathbf{x}$ has solution:

$$\mathbf{x}(t) = e^{At}\mathbf{x}_0 = Pe^{Dt}P^{-1}\mathbf{x}_0$$

where $e^{Dt} = \text{diag}(e^{\lambda_1 t}, e^{\lambda_2 t}, \ldots, e^{\lambda_n t})$

### 3. Recurrence Relations
For $\mathbf{x}_{n+1} = A\mathbf{x}_n$:

$$\mathbf{x}_n = A^n\mathbf{x}_0 = PD^nP^{-1}\mathbf{x}_0$$

### 4. Quadratic Forms
A quadratic form $Q(\mathbf{x}) = \mathbf{x}^TA\mathbf{x}$ can be simplified using eigenvalues:

If $A = PDP^{-1}$, let $\mathbf{y} = P^{-1}\mathbf{x}$:

$$Q(\mathbf{x}) = \mathbf{y}^TD\mathbf{y} = \lambda_1y_1^2 + \lambda_2y_2^2 + \cdots + \lambda_ny_n^2$$

---

## Cayley-Hamilton Theorem

### Statement
Every square matrix satisfies its own characteristic equation.

If $p(\lambda) = \det(A - \lambda I)$ is the characteristic polynomial, then:

$$p(A) = 0$$

### Example
For $A = \begin{bmatrix} 3 & 1 \\ 0 & 2 \end{bmatrix}$

Characteristic polynomial: $p(\lambda) = (3-\lambda)(2-\lambda) = \lambda^2 - 5\lambda + 6$

By Cayley-Hamilton: $A^2 - 5A + 6I = 0$

Verify:

$$A^2 = \begin{bmatrix} 9 & 5 \\ 0 & 4 \end{bmatrix}, \quad 5A = \begin{bmatrix} 15 & 5 \\ 0 & 10 \end{bmatrix}, \quad 6I = \begin{bmatrix} 6 & 0 \\ 0 & 6 \end{bmatrix}$$

$$A^2 - 5A + 6I = \begin{bmatrix} 9-15+6 & 5-5+0 \\ 0-0+0 & 4-10+6 \end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}$$ ✓

### Application
Can be used to find $A^{-1}$ or express high powers of $A$ in terms of lower powers.

---

## Geometric Interpretation

### Linear Transformation Perspective
The matrix $A$ represents a linear transformation. An eigenvector $\mathbf{v}$ is a vector whose direction is unchanged by the transformation (only scaled).

### 2D Example: Stretching
Consider $A = \begin{bmatrix} 3 & 0 \\ 0 & 2 \end{bmatrix}$

- Eigenvalues: $\lambda_1 = 3, \lambda_2 = 2$
- Eigenvectors: $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$

**Interpretation**: The transformation stretches the x-direction by factor 3 and y-direction by factor 2.

### 2D Example: Rotation + Scaling
Consider $A = \begin{bmatrix} 0 & -2 \\ 2 & 0 \end{bmatrix}$

Characteristic equation: $\lambda^2 + 4 = 0$

Eigenvalues: $\lambda = \pm 2i$ (complex)

**Interpretation**: This represents a rotation (no real eigenvectors exist because rotation changes all directions).

---

## Important Theorems

### Theorem 1: Eigenvalue Existence
Every $n \times n$ matrix has exactly $n$ eigenvalues (counting multiplicities) in the complex numbers $\mathbb{C}$.

### Theorem 2: Diagonalizability Criterion
An $n \times n$ matrix is diagonalizable if and only if the sum of geometric multiplicities equals $n$.

### Theorem 3: Spectral Theorem (Real Symmetric Matrices)
Every real symmetric matrix is orthogonally diagonalizable:

$$A = QDQ^T$$

where $Q$ is orthogonal ($Q^TQ = I$) and $D$ is diagonal.

### Theorem 4: Determinant and Invertibility
- $\det(A) = \prod \lambda_i$
- $A$ is invertible ⟺ 0 is not an eigenvalue ⟺ $\det(A) \neq 0$

### Theorem 5: Rank and Eigenvalues
$$\text{rank}(A) = n - \text{number of zero eigenvalues}$$

---

## Quick Computation Tricks

### For $2 \times 2$ Matrices
$A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$

**Characteristic equation**: $\lambda^2 - \text{tr}(A)\lambda + \det(A) = 0$

$$\lambda^2 - (a+d)\lambda + (ad-bc) = 0$$

**Quadratic formula**:

$$\lambda = \frac{(a+d) \pm \sqrt{(a+d)^2 - 4(ad-bc)}}{2}$$

### Special $2 \times 2$ Cases

**Diagonal**: $A = \begin{bmatrix} a & 0 \\ 0 & d \end{bmatrix}$ → $\lambda_1 = a, \lambda_2 = d$

**Symmetric**: $A = \begin{bmatrix} a & b \\ b & d \end{bmatrix}$ → Real eigenvalues, orthogonal eigenvectors

**Antisymmetric**: $A = \begin{bmatrix} 0 & b \\ -b & 0 \end{bmatrix}$ → $\lambda = \pm bi$ (purely imaginary)

### For $3 \times 3$ Triangular Matrices
Eigenvalues are diagonal entries!

---

## Common Mistakes to Avoid

### Mistake 1: Zero Eigenvector
❌ "The zero vector is an eigenvector"
✓ Correct: Eigenvectors must be **non-zero** by definition

### Mistake 2: Forgetting Multiplicities
❌ Counting only distinct eigenvalues
✓ Correct: Count with algebraic multiplicities (an $n \times n$ matrix has $n$ eigenvalues)

### Mistake 3: Sign Errors in Characteristic Polynomial
❌ $\det(A - \lambda I) = \det(\lambda I - A)$
✓ Correct: These differ by sign $(-1)^n$ for $n \times n$ matrix

### Mistake 4: Assuming Diagonalizability
❌ "Every matrix is diagonalizable"
✓ Correct: Only if there are $n$ linearly independent eigenvectors

### Mistake 5: Eigenvalue Order in $D$
The eigenvalues in $D$ must match the order of eigenvectors in $P$!

---

## Applications in Data Science and Machine Learning

### 1. Principal Component Analysis (PCA)
- Find eigenvectors of covariance matrix
- Principal components are eigenvectors
- Variance along each component = corresponding eigenvalue
- Used for dimensionality reduction

### 2. Google PageRank Algorithm
- Web pages as nodes in a graph
- Transition matrix represents links
- PageRank = dominant eigenvector (eigenvalue = 1)

### 3. Markov Chains
- Transition matrix eigenvalues determine long-term behavior
- Steady-state distribution = eigenvector for $\lambda = 1$

### 4. Image Compression
- Singular Value Decomposition (SVD) uses eigenvalues
- Keep largest eigenvalues for approximation

### 5. Graph Analysis
- Graph Laplacian eigenvalues reveal connectivity
- Used in spectral clustering

### 6. Stability Analysis
- Eigenvalues of Jacobian matrix determine system stability
- All eigenvalues with negative real parts → stable system

### 7. Recommendation Systems
- Matrix factorization techniques
- Latent factor models

### 8. Quantum Mechanics
- Observable quantities = eigenvalues of Hermitian operators
- Measurement outcomes = eigenvalues

---

## Computational Considerations

### Numerical Methods
For large matrices, direct computation of characteristic polynomial is impractical:

1. **Power Method**: Find dominant eigenvalue
2. **QR Algorithm**: Find all eigenvalues
3. **Jacobi Method**: For symmetric matrices
4. **Lanczos Algorithm**: For sparse matrices

### Software Tools
- **NumPy**: `numpy.linalg.eig(A)`
- **MATLAB**: `[V, D] = eig(A)`
- **R**: `eigen(A)`

### Numerical Stability
- Eigenvalue computation can be numerically unstable
- Small changes in matrix entries can cause large changes in eigenvalues
- Use specialized algorithms for symmetric/Hermitian matrices

---

## Practice Problems

### Problem 1: Basic Computation
Find eigenvalues and eigenvectors of $A = \begin{bmatrix} 5 & 2 \\ 2 & 5 \end{bmatrix}$

### Problem 2: Diagonalization
Diagonalize $A = \begin{bmatrix} 1 & 2 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 4 \end{bmatrix}$

### Problem 3: Matrix Powers
Find $A^{100}$ where $A = \begin{bmatrix} 0.6 & 0.4 \\ 0.3 & 0.7 \end{bmatrix}$ (Markov chain)

### Problem 4: Geometric Multiplicity
For $A = \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{bmatrix}$, find algebraic and geometric multiplicities.

### Problem 5: Orthogonal Diagonalization
Orthogonally diagonalize $A = \begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix}$

---

## Summary

### Key Concepts
| Concept | Formula/Definition |
|---------|-------------------|
| **Eigenvalue equation** | $A\mathbf{v} = \lambda\mathbf{v}$ |
| **Characteristic equation** | $\det(A - \lambda I) = 0$ |
| **Eigenspace** | $E_\lambda = \text{null}(A - \lambda I)$ |
| **Diagonalization** | $A = PDP^{-1}$ |
| **Trace** | $\text{tr}(A) = \sum \lambda_i$ |
| **Determinant** | $\det(A) = \prod \lambda_i$ |

### Quick Reference

**To find eigenvalues**: Solve $\det(A - \lambda I) = 0$

**To find eigenvectors**: Solve $(A - \lambda I)\mathbf{v} = 0$ for each $\lambda$

**To diagonalize**: $P = [\mathbf{v}_1 \, \cdots \, \mathbf{v}_n]$, $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$

**Matrix powers**: $A^k = PD^kP^{-1}$

---

## References

- Gilbert Strang, *Linear Algebra and Its Applications*
- David Lay, *Linear Algebra and Its Applications*
- MIT OCW 18.06: Linear Algebra
- 3Blue1Brown: Eigenvectors and Eigenvalues (YouTube)

---

*Last Updated: November 13, 2025*
