# Projections in Linear Algebra

## Definition

### Projection onto a Subspace
A **projection** of a vector $\mathbf{b}$ onto a subspace $W$ is a vector $\mathbf{p} \in W$ that is closest to $\mathbf{b}$.

The projection satisfies:
$$\mathbf{p} = \text{proj}_W(\mathbf{b})$$

The **error vector** (or residual) is:
$$\mathbf{e} = \mathbf{b} - \mathbf{p}$$

### Key Property: Orthogonality
The error vector $\mathbf{e}$ is **orthogonal** to the subspace $W$:
$$\mathbf{e} \perp W$$

This means $\mathbf{e} \perp \mathbf{w}$ for every $\mathbf{w} \in W$.

---

## Projection onto a Line (1D Subspace)

### Formula
To project vector $\mathbf{b}$ onto vector $\mathbf{a}$ (direction):

$$\text{proj}_{\mathbf{a}}(\mathbf{b}) = \frac{\mathbf{a} \cdot \mathbf{b}}{\mathbf{a} \cdot \mathbf{a}}\mathbf{a} = \frac{\mathbf{a}^T\mathbf{b}}{\mathbf{a}^T\mathbf{a}}\mathbf{a}$$

### Scalar Component
The **scalar projection** (coefficient):
$$\text{comp}_{\mathbf{a}}(\mathbf{b}) = \frac{\mathbf{a} \cdot \mathbf{b}}{|\mathbf{a}|} = \frac{\mathbf{a} \cdot \mathbf{b}}{\sqrt{\mathbf{a} \cdot \mathbf{a}}}$$

### Unit Vector Form
If $\mathbf{u}$ is a unit vector ($|\mathbf{u}| = 1$):
$$\text{proj}_{\mathbf{u}}(\mathbf{b}) = (\mathbf{u} \cdot \mathbf{b})\mathbf{u}$$

---

## Example 1: Projection onto a Line

Project $\mathbf{b} = \begin{bmatrix} 2 \\ 3 \end{bmatrix}$ onto $\mathbf{a} = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$

**Solution**:

$$\mathbf{a}^T\mathbf{b} = 1(2) + 1(3) = 5$$

$$\mathbf{a}^T\mathbf{a} = 1^2 + 1^2 = 2$$

$$\mathbf{p} = \frac{5}{2}\begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 2.5 \\ 2.5 \end{bmatrix}$$

**Error vector**:
$$\mathbf{e} = \mathbf{b} - \mathbf{p} = \begin{bmatrix} 2 \\ 3 \end{bmatrix} - \begin{bmatrix} 2.5 \\ 2.5 \end{bmatrix} = \begin{bmatrix} -0.5 \\ 0.5 \end{bmatrix}$$

**Verify orthogonality**:
$$\mathbf{a}^T\mathbf{e} = 1(-0.5) + 1(0.5) = 0$$ ✓

---

## Projection Matrix for a Line

### Definition
The **projection matrix** $P$ onto the line spanned by $\mathbf{a}$ is:

$$P = \frac{\mathbf{a}\mathbf{a}^T}{\mathbf{a}^T\mathbf{a}}$$

Then: $\mathbf{p} = P\mathbf{b}$

### Properties of Projection Matrix
1. **Symmetric**: $P^T = P$
2. **Idempotent**: $P^2 = P$ (projecting twice = projecting once)
3. **Rank**: $\text{rank}(P) = 1$ (for projection onto a line)
4. **Eigenvalues**: 1 (on the subspace) and 0 (orthogonal to subspace)

### Example 2: Projection Matrix

For $\mathbf{a} = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$:

$$P = \frac{1}{2}\begin{bmatrix} 1 \\ 1 \end{bmatrix}\begin{bmatrix} 1 & 1 \end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}$$

**Verify idempotence**:
$$P^2 = \frac{1}{2}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix} \cdot \frac{1}{2}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix} = \frac{1}{4}\begin{bmatrix} 2 & 2 \\ 2 & 2 \end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix} = P$$ ✓

---

## Projection onto a Subspace (General Case)

### Problem Setup
Given:
- Subspace $W$ with basis $\{\mathbf{a}_1, \mathbf{a}_2, \ldots, \mathbf{a}_k\}$
- Matrix $A = [\mathbf{a}_1 \, \mathbf{a}_2 \, \cdots \, \mathbf{a}_k]$ (columns span $W$)
- Vector $\mathbf{b}$ to be projected

Find: $\mathbf{p} = $ projection of $\mathbf{b}$ onto $W$

### The Normal Equations

The projection $\mathbf{p}$ is in $W$, so:
$$\mathbf{p} = A\mathbf{x}$$

for some coefficient vector $\mathbf{x}$.

The error $\mathbf{e} = \mathbf{b} - A\mathbf{x}$ must be orthogonal to $W$:
$$A^T\mathbf{e} = 0$$

$$A^T(\mathbf{b} - A\mathbf{x}) = 0$$

$$A^TA\mathbf{x} = A^T\mathbf{b}$$

These are the **normal equations**.

### Solution
If $A$ has linearly independent columns (which it should for a proper basis):
$$\mathbf{x} = (A^TA)^{-1}A^T\mathbf{b}$$

The projection is:
$$\mathbf{p} = A\mathbf{x} = A(A^TA)^{-1}A^T\mathbf{b}$$

### Projection Matrix (General)
$$P = A(A^TA)^{-1}A^T$$

Properties:
- **Symmetric**: $P^T = P$
- **Idempotent**: $P^2 = P$
- **Rank**: $\text{rank}(P) = \text{rank}(A)$

---

## Example 3: Projection onto a Plane

Project $\mathbf{b} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$ onto the plane spanned by $\mathbf{a}_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}$ and $\mathbf{a}_2 = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}$

**Solution**:

Form matrix $A$:
$$A = \begin{bmatrix} 1 & 0 \\ 0 & 1 \\ 0 & 0 \end{bmatrix}$$

Compute $A^TA$:
$$A^TA = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 0 & 1 \\ 0 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} = I$$

Compute $(A^TA)^{-1}A^T$:
$$(A^TA)^{-1}A^T = A^T = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}$$

Projection matrix:
$$P = A(A^TA)^{-1}A^T = \begin{bmatrix} 1 & 0 \\ 0 & 1 \\ 0 & 0 \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{bmatrix}$$

Projection:
$$\mathbf{p} = P\mathbf{b} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{bmatrix}\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 0 \end{bmatrix}$$

**Interpretation**: This projects onto the xy-plane, simply zeroing out the z-component.

---

## Orthogonal Complement

### Definition
The **orthogonal complement** of subspace $W$, denoted $W^\perp$, is:
$$W^\perp = \{\mathbf{v} \mid \mathbf{v} \perp \mathbf{w} \text{ for all } \mathbf{w} \in W\}$$

### Projection onto Orthogonal Complement
If $P$ projects onto $W$, then $I - P$ projects onto $W^\perp$:
$$P_{W^\perp} = I - P$$

### Decomposition
Every vector $\mathbf{b}$ can be uniquely decomposed:
$$\mathbf{b} = \mathbf{p} + \mathbf{e}$$

where:
- $\mathbf{p} \in W$ (component in $W$)
- $\mathbf{e} \in W^\perp$ (component orthogonal to $W$)

---

## Example 4: Orthogonal Complement

Using Example 3, find the projection onto the orthogonal complement (the z-axis).

**Solution**:

$$P_{W^\perp} = I - P = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} - \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{bmatrix} = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

$$\mathbf{e} = P_{W^\perp}\mathbf{b} = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix}\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 3 \end{bmatrix}$$

**Verify**: $\mathbf{b} = \mathbf{p} + \mathbf{e} = \begin{bmatrix} 1 \\ 2 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ 0 \\ 3 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$ ✓

---

## Four Fundamental Subspaces

### The Subspaces
For an $m \times n$ matrix $A$:

1. **Column space** $C(A)$ ⊆ $\mathbb{R}^m$
2. **Row space** $C(A^T)$ ⊆ $\mathbb{R}^n$
3. **Null space** $N(A)$ ⊆ $\mathbb{R}^n$
4. **Left null space** $N(A^T)$ ⊆ $\mathbb{R}^m$

### Orthogonal Pairs
- $C(A^T) \perp N(A)$ (row space ⊥ null space)
- $C(A) \perp N(A^T)$ (column space ⊥ left null space)

### Dimensions
$$\dim(C(A^T)) + \dim(N(A)) = n$$
$$\dim(C(A)) + \dim(N(A^T)) = m$$

---

## Least Squares Problem

### The Problem
Given system $A\mathbf{x} = \mathbf{b}$ with **no exact solution** (inconsistent).

Find $\hat{\mathbf{x}}$ that minimizes:
$$\|\mathbf{b} - A\mathbf{x}\|^2$$

### Geometric Interpretation
- $\mathbf{b}$ is not in $C(A)$ (column space of $A$)
- Find closest vector $\mathbf{p}$ in $C(A)$ to $\mathbf{b}$
- $\mathbf{p} = A\hat{\mathbf{x}}$ where $\hat{\mathbf{x}}$ is the least squares solution

### Solution: Normal Equations
$$A^TA\hat{\mathbf{x}} = A^T\mathbf{b}$$

If $A$ has linearly independent columns:
$$\hat{\mathbf{x}} = (A^TA)^{-1}A^T\mathbf{b}$$

The projection onto $C(A)$:
$$\mathbf{p} = A\hat{\mathbf{x}} = A(A^TA)^{-1}A^T\mathbf{b}$$

---

## Example 5: Least Squares Line Fitting

Fit a line $y = C + Dt$ to data points $(0, 6), (1, 0), (2, 0)$.

**Solution**:

Set up overdetermined system:
$$\begin{bmatrix} 1 & 0 \\ 1 & 1 \\ 1 & 2 \end{bmatrix}\begin{bmatrix} C \\ D \end{bmatrix} = \begin{bmatrix} 6 \\ 0 \\ 0 \end{bmatrix}$$

$$A\mathbf{x} = \mathbf{b}$$

Compute $A^TA$:
$$A^TA = \begin{bmatrix} 1 & 1 & 1 \\ 0 & 1 & 2 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 1 & 1 \\ 1 & 2 \end{bmatrix} = \begin{bmatrix} 3 & 3 \\ 3 & 5 \end{bmatrix}$$

Compute $A^T\mathbf{b}$:
$$A^T\mathbf{b} = \begin{bmatrix} 1 & 1 & 1 \\ 0 & 1 & 2 \end{bmatrix}\begin{bmatrix} 6 \\ 0 \\ 0 \end{bmatrix} = \begin{bmatrix} 6 \\ 0 \end{bmatrix}$$

Solve $A^TA\hat{\mathbf{x}} = A^T\mathbf{b}$:
$$\begin{bmatrix} 3 & 3 \\ 3 & 5 \end{bmatrix}\begin{bmatrix} C \\ D \end{bmatrix} = \begin{bmatrix} 6 \\ 0 \end{bmatrix}$$

From first equation: $3C + 3D = 6 \Rightarrow C + D = 2$

From second equation: $3C + 5D = 0$

Substitute: $3(2 - D) + 5D = 0 \Rightarrow 6 + 2D = 0 \Rightarrow D = -3$

Therefore: $C = 2 - D = 2 - (-3) = 5$

**Best fit line**: $y = 5 - 3t$

---

## Gram-Schmidt Orthogonalization

### Purpose
Convert a basis to an **orthogonal** (or **orthonormal**) basis.

### The Process
Given basis $\{\mathbf{a}_1, \mathbf{a}_2, \ldots, \mathbf{a}_n\}$:

**Step 1**: $\mathbf{q}_1 = \mathbf{a}_1$

**Step 2**: $\mathbf{q}_2 = \mathbf{a}_2 - \text{proj}_{\mathbf{q}_1}(\mathbf{a}_2)$

**Step 3**: $\mathbf{q}_3 = \mathbf{a}_3 - \text{proj}_{\mathbf{q}_1}(\mathbf{a}_3) - \text{proj}_{\mathbf{q}_2}(\mathbf{a}_3)$

**General**: 
$$\mathbf{q}_k = \mathbf{a}_k - \sum_{i=1}^{k-1} \text{proj}_{\mathbf{q}_i}(\mathbf{a}_k)$$

### Normalization (Optional)
To get orthonormal basis:
$$\mathbf{u}_i = \frac{\mathbf{q}_i}{\|\mathbf{q}_i\|}$$

---

## Example 6: Gram-Schmidt

Orthogonalize $\mathbf{a}_1 = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}$, $\mathbf{a}_2 = \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}$

**Solution**:

**Step 1**: 
$$\mathbf{q}_1 = \mathbf{a}_1 = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}$$

**Step 2**: 
$$\text{proj}_{\mathbf{q}_1}(\mathbf{a}_2) = \frac{\mathbf{q}_1^T\mathbf{a}_2}{\mathbf{q}_1^T\mathbf{q}_1}\mathbf{q}_1 = \frac{1}{2}\begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} = \begin{bmatrix} 0.5 \\ 0.5 \\ 0 \end{bmatrix}$$

$$\mathbf{q}_2 = \mathbf{a}_2 - \text{proj}_{\mathbf{q}_1}(\mathbf{a}_2) = \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} - \begin{bmatrix} 0.5 \\ 0.5 \\ 0 \end{bmatrix} = \begin{bmatrix} 0.5 \\ -0.5 \\ 1 \end{bmatrix}$$

**Verify orthogonality**:
$$\mathbf{q}_1^T\mathbf{q}_2 = 1(0.5) + 1(-0.5) + 0(1) = 0$$ ✓

**Normalize**:
$$\mathbf{u}_1 = \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}, \quad \mathbf{u}_2 = \frac{1}{\sqrt{1.5}}\begin{bmatrix} 0.5 \\ -0.5 \\ 1 \end{bmatrix}$$

---

## QR Decomposition

### Definition
Any matrix $A$ with linearly independent columns can be factored as:
$$A = QR$$

where:
- $Q$ has orthonormal columns ($Q^TQ = I$)
- $R$ is upper triangular with positive diagonal

### Connection to Gram-Schmidt
- $Q$ contains the orthonormal vectors from Gram-Schmidt
- $R$ contains the coefficients relating original and orthonormal bases

### Applications
1. Solving least squares: $A^TA\mathbf{x} = A^T\mathbf{b}$ becomes $R\mathbf{x} = Q^T\mathbf{b}$
2. Computing eigenvalues (QR algorithm)
3. Numerical stability in solving linear systems

---

## Properties of Projections

### Property 1: Distance Minimization
The projection $\mathbf{p}$ of $\mathbf{b}$ onto $W$ minimizes $\|\mathbf{b} - \mathbf{w}\|$ over all $\mathbf{w} \in W$.

### Property 2: Pythagorean Theorem
$$\|\mathbf{b}\|^2 = \|\mathbf{p}\|^2 + \|\mathbf{e}\|^2$$

where $\mathbf{e} = \mathbf{b} - \mathbf{p}$.

### Property 3: Linearity
Projection is a linear transformation:
$$\text{proj}_W(\alpha\mathbf{b}_1 + \beta\mathbf{b}_2) = \alpha\text{proj}_W(\mathbf{b}_1) + \beta\text{proj}_W(\mathbf{b}_2)$$

### Property 4: Idempotence
$$P^2 = P$$

Projecting a projected vector gives the same result.

### Property 5: Symmetry
$$P^T = P$$

Projection matrices are always symmetric.

---

## Applications

### 1. Linear Regression
- Fit model $\mathbf{y} = X\boldsymbol{\beta} + \boldsymbol{\epsilon}$
- Minimize $\|\boldsymbol{\epsilon}\|^2 = \|\mathbf{y} - X\boldsymbol{\beta}\|^2$
- Solution: $\hat{\boldsymbol{\beta}} = (X^TX)^{-1}X^T\mathbf{y}$
- Predicted values: $\hat{\mathbf{y}} = X\hat{\boldsymbol{\beta}} = P\mathbf{y}$ (projection onto column space of $X$)

### 2. Principal Component Analysis (PCA)
- Project high-dimensional data onto lower-dimensional subspace
- Subspace defined by principal components (eigenvectors of covariance matrix)

### 3. Computer Graphics
- Project 3D objects onto 2D screen
- Shadow computation (projection onto plane)

### 4. Signal Processing
- Remove noise by projecting onto signal subspace
- Orthogonal projection filters

### 5. Machine Learning
- Feature extraction and dimensionality reduction
- Support Vector Machines (separating hyperplanes)

### 6. Quantum Mechanics
- Measurement as projection onto eigenspaces
- State collapse after measurement

---

## Common Mistakes to Avoid

### Mistake 1: Forgetting Normalization
❌ Using $\frac{\mathbf{a} \cdot \mathbf{b}}{\mathbf{a}}$ instead of $\frac{\mathbf{a} \cdot \mathbf{b}}{\mathbf{a} \cdot \mathbf{a}}\mathbf{a}$

### Mistake 2: Wrong Order in Normal Equations
❌ $(AA^T)^{-1}$ instead of $(A^TA)^{-1}$

### Mistake 3: Assuming Invertibility
Not checking if $A^TA$ is invertible (requires linearly independent columns)

### Mistake 4: Confusing Projection and Component
- Projection is a vector: $\text{proj}_{\mathbf{a}}(\mathbf{b})$
- Component is a scalar: $\text{comp}_{\mathbf{a}}(\mathbf{b})$

### Mistake 5: Not Verifying Orthogonality
Always check: $\mathbf{e} \perp W$ (i.e., $A^T\mathbf{e} = 0$)

---

## Key Formulas Summary

| Concept | Formula |
|---------|---------|
| **Projection onto line** | $\text{proj}_{\mathbf{a}}(\mathbf{b}) = \frac{\mathbf{a}^T\mathbf{b}}{\mathbf{a}^T\mathbf{a}}\mathbf{a}$ |
| **Projection matrix (line)** | $P = \frac{\mathbf{a}\mathbf{a}^T}{\mathbf{a}^T\mathbf{a}}$ |
| **Normal equations** | $A^TA\mathbf{x} = A^T\mathbf{b}$ |
| **Least squares solution** | $\hat{\mathbf{x}} = (A^TA)^{-1}A^T\mathbf{b}$ |
| **Projection matrix (general)** | $P = A(A^TA)^{-1}A^T$ |
| **Orthogonal complement** | $P_{W^\perp} = I - P$ |
| **Error vector** | $\mathbf{e} = \mathbf{b} - \mathbf{p} = (I - P)\mathbf{b}$ |
| **Pythagorean theorem** | $\|\mathbf{b}\|^2 = \|\mathbf{p}\|^2 + \|\mathbf{e}\|^2$ |

---

## Important Theorems

### Theorem 1: Projection Theorem
For any vector $\mathbf{b}$ and subspace $W$, there exists a unique projection $\mathbf{p} \in W$ such that $\mathbf{b} - \mathbf{p} \perp W$.

### Theorem 2: Best Approximation
The projection $\mathbf{p}$ minimizes $\|\mathbf{b} - \mathbf{w}\|$ over all $\mathbf{w} \in W$.

### Theorem 3: Orthogonal Decomposition
$\mathbb{R}^n = W \oplus W^\perp$ (direct sum), meaning every vector uniquely decomposes as $\mathbf{v} = \mathbf{w} + \mathbf{w}^\perp$.

### Theorem 4: Projection Matrix Properties
If $P$ is a projection matrix:
1. $P^2 = P$ (idempotent)
2. $P^T = P$ (symmetric)
3. Eigenvalues are 0 or 1

### Theorem 5: Least Squares Solution
The vector $\hat{\mathbf{x}} = (A^TA)^{-1}A^T\mathbf{b}$ minimizes $\|A\mathbf{x} - \mathbf{b}\|^2$.

---

## Computational Considerations

### Numerical Stability
- Computing $(A^TA)^{-1}$ can be numerically unstable
- Better: Use QR decomposition
- Even better: Use SVD for least squares

### Complexity
- Normal equations: $O(n^2m + n^3)$ for $m \times n$ matrix
- QR decomposition: $O(mn^2)$
- More efficient for tall matrices ($m \gg n$)

### Software Implementation
- **Python (NumPy)**: `np.linalg.lstsq(A, b)`
- **MATLAB**: `A \ b` (backslash operator)
- **R**: `lm()` for linear models

---

## Practice Checklist

✓ Can you project a vector onto a line?
✓ Can you find a projection matrix?
✓ Can you verify $P^2 = P$ and $P^T = P$?
✓ Can you solve least squares problems?
✓ Can you apply Gram-Schmidt orthogonalization?
✓ Do you understand the normal equations?
✓ Can you decompose a vector into orthogonal components?
✓ Can you identify when $(A^TA)$ is invertible?

---

## References

- Gilbert Strang, *Linear Algebra and Its Applications*
- MIT OCW 18.06: Linear Algebra, Lectures 14-16
- David Lay, *Linear Algebra and Its Applications*, Chapter 6
- 3Blue1Brown: Dot products and duality (YouTube)

---

*Last Updated: November 13, 2025*
