# Span and Linear Combinations

## Linear Combinations

### Definition
A **linear combination** of vectors $v_1, v_2, \ldots, v_n$ in a vector space $V$ is an expression of the form:

$$c_1v_1 + c_2v_2 + \cdots + c_nv_n$$

where $c_1, c_2, \ldots, c_n$ are scalars (real or complex numbers).

### Example
If $v_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 3 \\ 4 \end{bmatrix}$, then:

$$2v_1 + 3v_2 = 2\begin{bmatrix} 1 \\ 2 \end{bmatrix} + 3\begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \end{bmatrix} + \begin{bmatrix} 9 \\ 12 \end{bmatrix} = \begin{bmatrix} 11 \\ 16 \end{bmatrix}$$

is a linear combination of $v_1$ and $v_2$.

---

## Span

### Definition
The **span** of a set of vectors $\{v_1, v_2, \ldots, v_n\}$ is the set of all possible linear combinations of these vectors.

$$\text{span}\{v_1, v_2, \ldots, v_n\} = \{c_1v_1 + c_2v_2 + \cdots + c_nv_n \mid c_i \in \mathbb{R}\}$$

In other words, span($S$) is the set of all vectors that can be written as linear combinations of vectors in $S$.

### Key Properties

1. **Span is a Subspace**: The span of any set of vectors forms a subspace of the vector space.

2. **Closure Properties**:
   - Contains the zero vector (when all coefficients are 0)
   - Closed under addition
   - Closed under scalar multiplication

3. **Dimension**: The dimension of span($S$) equals the number of linearly independent vectors in $S$.

---

## Geometric Interpretation

### In $\mathbb{R}^2$

- **Span of one non-zero vector**: A line through the origin
- **Span of two linearly independent vectors**: The entire plane $\mathbb{R}^2$
- **Span of two linearly dependent vectors**: A line through the origin

### In $\mathbb{R}^3$

- **Span of one non-zero vector**: A line through the origin
- **Span of two linearly independent vectors**: A plane through the origin
- **Span of three linearly independent vectors**: The entire space $\mathbb{R}^3$

---

## Important Concepts

### 1. Spanning Set
A set of vectors $\{v_1, v_2, \ldots, v_n\}$ **spans** a vector space $V$ if every vector in $V$ can be written as a linear combination of these vectors.

### 2. Checking if a Vector is in the Span
To check if vector $b$ is in span$\{v_1, v_2, \ldots, v_n\}$:
- Set up the equation: $c_1v_1 + c_2v_2 + \cdots + c_nv_n = b$
- This gives a system of linear equations
- If the system has a solution, then $b$ is in the span

### 3. Basis
A **basis** is a spanning set that is linearly independent. It's the minimal spanning set.

---

## Examples

### Example 1: Span in $\mathbb{R}^2$

Let $v_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$

**Question**: What is span$\{v_1, v_2\}$?

**Solution**: 
$$c_1\begin{bmatrix} 1 \\ 0 \end{bmatrix} + c_2\begin{bmatrix} 0 \\ 1 \end{bmatrix} = \begin{bmatrix} c_1 \\ c_2 \end{bmatrix}$$

Since $c_1$ and $c_2$ can be any real numbers, span$\{v_1, v_2\} = \mathbb{R}^2$ (the entire plane).

### Example 2: Span of Dependent Vectors

Let $v_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 2 \\ 4 \end{bmatrix}$

**Question**: What is span$\{v_1, v_2\}$?

**Solution**: 
Notice that $v_2 = 2v_1$, so these vectors are linearly dependent.

$$c_1\begin{bmatrix} 1 \\ 2 \end{bmatrix} + c_2\begin{bmatrix} 2 \\ 4 \end{bmatrix} = (c_1 + 2c_2)\begin{bmatrix} 1 \\ 2 \end{bmatrix}$$

This can only produce scalar multiples of $v_1$, so span$\{v_1, v_2\}$ is the line through the origin in the direction of $\begin{bmatrix} 1 \\ 2 \end{bmatrix}$.

### Example 3: Testing Membership in Span

Let $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $v_2 = \begin{bmatrix} 0 \\ 1 \\ 2 \end{bmatrix}$, and $b = \begin{bmatrix} 3 \\ 5 \\ 7 \end{bmatrix}$

**Question**: Is $b$ in span$\{v_1, v_2\}$?

**Solution**: 
We need to solve: $c_1v_1 + c_2v_2 = b$

$$c_1\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} + c_2\begin{bmatrix} 0 \\ 1 \\ 2 \end{bmatrix} = \begin{bmatrix} 3 \\ 5 \\ 7 \end{bmatrix}$$

This gives the system:
- $c_1 = 3$
- $2c_1 + c_2 = 5$
- $3c_1 + 2c_2 = 7$

From equation 1: $c_1 = 3$

From equation 2: $2(3) + c_2 = 5 \Rightarrow c_2 = -1$

Check equation 3: $3(3) + 2(-1) = 9 - 2 = 7$ ✓

Yes, $b$ is in span$\{v_1, v_2\}$ with $c_1 = 3$ and $c_2 = -1$.

---

## Common Mistakes to Avoid

1. **Confusing span with the set of vectors**: Span is the set of all linear combinations, not just the original vectors.

2. **Forgetting the zero vector**: Every span includes the zero vector (all coefficients = 0).

3. **Assuming more vectors = larger span**: Adding linearly dependent vectors doesn't increase the span.

4. **Not checking all equations**: When testing membership, all equations in the system must be satisfied.

---

## Key Theorems

### Theorem 1: Span Properties
If $S = \{v_1, v_2, \ldots, v_n\}$ is a set of vectors in vector space $V$, then:
- span($S$) is a subspace of $V$
- span($S$) is the smallest subspace containing all vectors in $S$

### Theorem 2: Span and Linear Independence
A set of vectors $\{v_1, v_2, \ldots, v_n\}$ spans $\mathbb{R}^n$ if and only if the matrix $[v_1 \, v_2 \, \cdots \, v_n]$ is invertible (has full rank).

### Theorem 3: Dimension of Span
$$\dim(\text{span}\{v_1, v_2, \ldots, v_n\}) = \text{rank}([v_1 \, v_2 \, \cdots \, v_n])$$

---

## Applications

1. **Computer Graphics**: Representing transformations and coordinate systems
2. **Machine Learning**: Feature spaces and dimensionality reduction
3. **Control Theory**: Controllability and observability
4. **Signal Processing**: Basis functions for signal representation
5. **Quantum Mechanics**: State spaces and superposition

---

## Summary

- **Linear Combination**: Sum of scalar multiples of vectors
- **Span**: Set of all linear combinations of a given set of vectors
- **Spanning Set**: A set whose span equals the entire vector space
- **To check membership**: Solve a system of linear equations
- **Geometric intuition**: Lines, planes, and hyperplanes through the origin

---

## References for me

- https://youtu.be/tM4TDL9Hj8U
