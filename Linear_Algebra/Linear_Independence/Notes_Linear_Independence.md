# Linear Independence and Linear Dependence

## Definition

### Linear Independence
A set of vectors $\{v_1, v_2, \ldots, v_n\}$ in a vector space $V$ is **linearly independent** if the only solution to the equation:

$$c_1v_1 + c_2v_2 + \cdots + c_nv_n = 0$$

is the **trivial solution**: $c_1 = c_2 = \cdots = c_n = 0$

In other words, no vector in the set can be written as a linear combination of the others.

### Linear Dependence
A set of vectors $\{v_1, v_2, \ldots, v_n\}$ is **linearly dependent** if there exist scalars $c_1, c_2, \ldots, c_n$, **not all zero**, such that:

$$c_1v_1 + c_2v_2 + \cdots + c_nv_n = 0$$

This means at least one vector can be expressed as a linear combination of the others.

---

## Key Intuition

**Linear Independence** = "No redundancy" = "Each vector adds a new direction"

**Linear Dependence** = "Redundancy exists" = "At least one vector is a combination of others"

---

## Testing for Linear Independence

### Method 1: Solve the Homogeneous System
1. Set up the equation: $c_1v_1 + c_2v_2 + \cdots + c_nv_n = 0$
2. Write as a matrix equation: $A\mathbf{c} = 0$ where $A = [v_1 \, v_2 \, \cdots \, v_n]$
3. Find solutions:
   - **Only trivial solution** → Linearly independent
   - **Non-trivial solution exists** → Linearly dependent

### Method 2: Use Determinant (Square Matrices)
For vectors in $\mathbb{R}^n$, if you have exactly $n$ vectors:
- Form matrix $A = [v_1 \, v_2 \, \cdots \, v_n]$
- Calculate $\det(A)$:
  - **$\det(A) \neq 0$** → Linearly independent
  - **$\det(A) = 0$** → Linearly dependent

### Method 3: Row Reduction (Find Rank)
- Form matrix $A = [v_1 \, v_2 \, \cdots \, v_n]$
- Row reduce to echelon form
- Count pivot columns (this is the rank)
- **rank$(A) = n$** → Linearly independent
- **rank$(A) < n$** → Linearly dependent

---

## Important Properties

### Property 1: Zero Vector
Any set containing the **zero vector** is linearly dependent.

**Proof**: If $v_1 = 0$, then $1 \cdot v_1 + 0 \cdot v_2 + \cdots + 0 \cdot v_n = 0$ (non-trivial solution)

### Property 2: Single Vector
A set containing a single non-zero vector is linearly independent.

### Property 3: Two Vectors
Two vectors $v_1, v_2$ are linearly dependent if and only if one is a scalar multiple of the other.

### Property 4: Size Constraint
If you have **more vectors than dimensions**, they must be linearly dependent.

In $\mathbb{R}^n$: Any set of more than $n$ vectors is linearly dependent.

### Property 5: Subset Property
- If a set is **linearly independent**, then every subset is also linearly independent
- If a set is **linearly dependent**, then every superset is also linearly dependent

### Property 6: Extension Property
If $\{v_1, v_2, \ldots, v_n\}$ is linearly independent and $v_{n+1}$ is not in span$\{v_1, v_2, \ldots, v_n\}$, then $\{v_1, v_2, \ldots, v_n, v_{n+1}\}$ is linearly independent.

---

## Geometric Interpretation

### In $\mathbb{R}^2$

**Linearly Independent**: Two non-zero vectors pointing in different directions
- Example: $\begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$

**Linearly Dependent**: Two vectors on the same line through origin
- Example: $\begin{bmatrix} 1 \\ 2 \end{bmatrix}$ and $\begin{bmatrix} 2 \\ 4 \end{bmatrix}$

### In $\mathbb{R}^3$

**Linearly Independent**:
- 2 vectors: Not on the same line through origin
- 3 vectors: Not all in the same plane through origin

**Linearly Dependent**:
- 2 vectors: On the same line through origin
- 3 vectors: All lie in the same plane through origin

---

## Examples

### Example 1: Testing Independence in $\mathbb{R}^2$

**Question**: Are $v_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 3 \\ 4 \end{bmatrix}$ linearly independent?

**Solution**:
Set up: $c_1\begin{bmatrix} 1 \\ 2 \end{bmatrix} + c_2\begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$

This gives:
- $c_1 + 3c_2 = 0$ → $c_1 = -3c_2$
- $2c_1 + 4c_2 = 0$ → $2(-3c_2) + 4c_2 = -2c_2 = 0$ → $c_2 = 0$

Therefore $c_1 = 0, c_2 = 0$ (only trivial solution)

**Answer**: Linearly independent ✓

**Alternative (Determinant)**:
$$\det\begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix} = 4 - 6 = -2 \neq 0$$

Linearly independent ✓

---

### Example 2: Dependent Vectors

**Question**: Are $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $v_2 = \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$ linearly independent?

**Solution**:
Notice immediately: $v_2 = 2v_1$

We can write: $2v_1 - 1v_2 + 0v_3 = 0$ (non-trivial solution: $c_1 = 2, c_2 = -1, c_3 = 0$)

**Answer**: Linearly dependent

**Alternative (Determinant)**:
$$\det\begin{bmatrix} 1 & 2 & 1 \\ 2 & 4 & 1 \\ 3 & 6 & 1 \end{bmatrix} = 1(4-6) - 2(2-3) + 1(12-12) = -2 + 2 + 0 = 0$$

Linearly dependent ✓

---

### Example 3: Using Row Reduction

**Question**: Are $v_1 = \begin{bmatrix} 1 \\ 2 \\ 1 \end{bmatrix}$, $v_2 = \begin{bmatrix} 2 \\ 5 \\ 3 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 3 \\ 2 \end{bmatrix}$ linearly independent?

**Solution**:
Form matrix and row reduce:
$$A = \begin{bmatrix} 1 & 2 & 1 \\ 2 & 5 & 3 \\ 1 & 3 & 2 \end{bmatrix}$$

$R_2 = R_2 - 2R_1$, $R_3 = R_3 - R_1$:
$$\begin{bmatrix} 1 & 2 & 1 \\ 0 & 1 & 1 \\ 0 & 1 & 1 \end{bmatrix}$$

$R_3 = R_3 - R_2$:
$$\begin{bmatrix} 1 & 2 & 1 \\ 0 & 1 & 1 \\ 0 & 0 & 0 \end{bmatrix}$$

Rank = 2 < 3

**Answer**: Linearly dependent

**Finding the dependency**: From the reduced form, we can see $v_3 = v_1 + v_2$

Verify: $\begin{bmatrix} 1 \\ 2 \\ 1 \end{bmatrix} + \begin{bmatrix} 2 \\ 5 \\ 3 \end{bmatrix} = \begin{bmatrix} 3 \\ 7 \\ 4 \end{bmatrix}$ ✗

Actually, let's solve correctly. Since the third column is free, we have:
$c_1v_1 + c_2v_2 + v_3 = 0$

From row-reduced form: $c_1 = 0, c_2 = -1, c_3 = 1$

So: $v_3 = v_2$? Let's check: No, that's wrong.

Actually solving $Ac = 0$ with $c_3 = 1$:
- $c_1 + 2c_2 + 1 = 0$
- $c_2 + 1 = 0$ → $c_2 = -1$
- $c_1 + 2(-1) + 1 = 0$ → $c_1 = 1$

Therefore: $v_1 - v_2 + v_3 = 0$ or $v_3 = v_2 - v_1$

---

### Example 4: Polynomial Vectors

**Question**: Are $p_1(x) = 1 + x$, $p_2(x) = x + x^2$, $p_3(x) = 1 + x^2$ linearly independent in $P_2$?

**Solution**:
Set up: $c_1(1 + x) + c_2(x + x^2) + c_3(1 + x^2) = 0$

Expanding: $(c_1 + c_3) + (c_1 + c_2)x + (c_2 + c_3)x^2 = 0$

For this to be the zero polynomial, all coefficients must be zero:
- $c_1 + c_3 = 0$
- $c_1 + c_2 = 0$
- $c_2 + c_3 = 0$

Matrix form: $\begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{bmatrix}\begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$

$$\det\begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{bmatrix} = 1(1-0) - 0 + 1(1-0) = 2 \neq 0$$

Only trivial solution exists.

**Answer**: Linearly independent ✓

---

### Example 5: Function Spaces

**Question**: Are $f_1(x) = e^x$, $f_2(x) = e^{2x}$, $f_3(x) = e^{3x}$ linearly independent?

**Solution**:
We need: $c_1e^x + c_2e^{2x} + c_3e^{3x} = 0$ for all $x$.

Use the **Wronskian** test for functions:

$$W(f_1, f_2, f_3) = \det\begin{bmatrix} e^x & e^{2x} & e^{3x} \\ e^x & 2e^{2x} & 3e^{3x} \\ e^x & 4e^{2x} & 9e^{3x} \end{bmatrix}$$

Factor out: $e^x \cdot e^{2x} \cdot e^{3x} = e^{6x}$

$$= e^{6x}\det\begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \\ 1 & 4 & 9 \end{bmatrix}$$

$$= e^{6x}[1(18-12) - 1(9-3) + 1(4-2)] = e^{6x}[6 - 6 + 2] = 2e^{6x} \neq 0$$

**Answer**: Linearly independent ✓

---

## Relationship with Basis and Dimension

### Basis
A **basis** for a vector space $V$ is a set of vectors that is:
1. Linearly independent
2. Spans $V$

### Dimension
The **dimension** of a vector space is the number of vectors in any basis.

### Key Facts
- Any linearly independent set in $\mathbb{R}^n$ with $n$ vectors is a basis
- Any spanning set in $\mathbb{R}^n$ with $n$ vectors is a basis
- You cannot have more than $n$ linearly independent vectors in $\mathbb{R}^n$

---

## Common Mistakes to Avoid

### Mistake 1: Confusing Definitions
❌ "Linearly independent means no vector is zero"
✓ Correct: "No vector can be written as a linear combination of others"

### Mistake 2: Wrong Test
❌ Testing if $c_1v_1 + c_2v_2 = v_3$ for independence
✓ Correct: Test if $c_1v_1 + c_2v_2 + c_3v_3 = 0$ has only trivial solution

### Mistake 3: Determinant for Non-Square
❌ Using determinant when number of vectors ≠ dimension
✓ Correct: Use rank or direct method for non-square matrices

### Mistake 4: Forgetting Zero Vector
The zero vector makes ANY set linearly dependent!

### Mistake 5: Arithmetic Errors
Always double-check your calculations, especially in row reduction.

---

## Important Theorems

### Theorem 1: Unique Representation
If $\{v_1, v_2, \ldots, v_n\}$ is linearly independent and $v = c_1v_1 + c_2v_2 + \cdots + c_nv_n$, then the coefficients $c_1, c_2, \ldots, c_n$ are **unique**.

### Theorem 2: Size Theorem
Let $V$ be a vector space with dimension $n$. Then:
- Any set of more than $n$ vectors in $V$ is linearly dependent
- Any set of fewer than $n$ vectors cannot span $V$

### Theorem 3: Basis Extension
Any linearly independent set in a finite-dimensional vector space can be extended to a basis.

### Theorem 4: Rank-Nullity Theorem
For matrix $A$ with $n$ columns:
$$\text{rank}(A) + \text{nullity}(A) = n$$

The columns are linearly independent if and only if nullity$(A) = 0$.

### Theorem 5: Gram-Schmidt
Any linearly independent set can be converted to an orthonormal set (orthonormal basis) using the Gram-Schmidt process.

---

## Testing Strategies for GATE

### Quick Recognition
1. **Zero vector present** → Immediately dependent
2. **More vectors than dimension** → Immediately dependent
3. **One vector is scalar multiple of another** → Dependent
4. **All vectors parallel** → Dependent

### Efficient Methods
- **2×2 or 3×3**: Use determinant (fastest)
- **Larger matrices**: Row reduction to find rank
- **Special structures**: Look for obvious dependencies first

### Time-Saving Tips
1. Check for obvious dependencies before calculating
2. Use properties (zero vector, size constraint) to eliminate options
3. For MCQs, sometimes you can test specific values

---

## Applications

### 1. Computer Graphics
- Coordinate system representation
- Transformation matrices
- Ensuring non-degenerate transformations

### 2. Machine Learning
- Feature selection (removing redundant features)
- Principal Component Analysis (PCA)
- Avoiding multicollinearity in regression

### 3. Control Systems
- Controllability and observability matrices
- State-space representations
- System stability analysis

### 4. Signal Processing
- Basis functions for signal representation
- Fourier analysis
- Wavelet transforms

### 5. Quantum Computing
- Quantum state representation
- Basis states in Hilbert space
- Quantum gates and operations

---

## Algorithms

### Algorithm 1: Check Linear Independence (Direct Method)

```
Input: Vectors v₁, v₂, ..., vₙ in ℝᵐ
Output: "Independent" or "Dependent"

1. Form matrix A = [v₁ v₂ ... vₙ] (m×n matrix)
2. Solve Ac = 0 using Gaussian elimination
3. If only trivial solution (c = 0):
      Return "Independent"
   Else:
      Return "Dependent"
```

### Algorithm 2: Check Linear Independence (Rank Method)

```
Input: Vectors v₁, v₂, ..., vₙ in ℝᵐ
Output: "Independent" or "Dependent"

1. Form matrix A = [v₁ v₂ ... vₙ] (m×n matrix)
2. Compute rank(A) using row reduction
3. If rank(A) = n:
      Return "Independent"
   Else:
      Return "Dependent"
```

---

## Practice Checklist

✓ Can you state the definition of linear independence?
✓ Can you test a set of 2-3 vectors for independence?
✓ Can you use determinants when applicable?
✓ Can you use row reduction to find rank?
✓ Can you recognize immediately dependent sets?
✓ Do you understand the geometric meaning?
✓ Can you find a dependency relation when vectors are dependent?
✓ Can you relate independence to span and basis?

---

## Summary Table

| Concept | Linearly Independent | Linearly Dependent |
|---------|---------------------|-------------------|
| Definition | $\sum c_iv_i = 0$ only if all $c_i = 0$ | $\sum c_iv_i = 0$ with some $c_i \neq 0$ |
| Geometric | Vectors point in different directions | At least one vector is combination of others |
| Determinant (n×n) | $\det(A) \neq 0$ | $\det(A) = 0$ |
| Rank | rank$(A) = n$ | rank$(A) < n$ |
| Null space | Only zero vector | Contains non-zero vectors |
| Basis property | Can be extended to basis | Contains redundancy |
| In $\mathbb{R}^n$ | At most $n$ vectors | More than $n$ vectors |

---

## Quick Reference Formulas

1. **Test equation**: $c_1v_1 + c_2v_2 + \cdots + c_nv_n = 0$

2. **Matrix form**: $A\mathbf{c} = 0$ where $A = [v_1 \, v_2 \, \cdots \, v_n]$

3. **Rank test**: Independent ⟺ rank$(A) = n$

4. **Determinant test** (square): Independent ⟺ $\det(A) \neq 0$

5. **Wronskian** (functions): $W(f_1, \ldots, f_n) \neq 0$ ⟹ Independent
