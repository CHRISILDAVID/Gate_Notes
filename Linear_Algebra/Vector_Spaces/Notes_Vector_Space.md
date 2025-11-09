# Vector Spaces

## Definition

A **vector space** (or linear space) **V** over a field **F** (typically real numbers ℝ or complex numbers ℂ) is a set of objects called **vectors**, together with two operations:
- **Vector addition**: u + v
- **Scalar multiplication**: cv

These operations must satisfy specific axioms.

## Axioms of Vector Spaces

For V to be a vector space over field F, the following properties must hold for all vectors **u**, **v**, **w** ∈ V and all scalars c, d ∈ F:

### Closure Properties
1. **Closure under addition**: If **u**, **v** ∈ V, then **u** + **v** ∈ V
2. **Closure under scalar multiplication**: If **v** ∈ V and c ∈ F, then c**v** ∈ V

### Addition Axioms
3. **Associativity of addition**: (**u** + **v**) + **w** = **u** + (**v** + **w**)
4. **Commutativity of addition**: **u** + **v** = **v** + **u**
5. **Additive identity**: There exists **0** ∈ V such that **v** + **0** = **v** for all **v** ∈ V
6. **Additive inverse**: For each **v** ∈ V, there exists **-v** ∈ V such that **v** + (**-v**) = **0**

### Scalar Multiplication Axioms
7. **Distributivity over vector addition**: c(**u** + **v**) = c**u** + c**v**
8. **Distributivity over scalar addition**: (c + d)**v** = c**v** + d**v**
9. **Associativity of scalar multiplication**: c(d**v**) = (cd)**v**
10. **Scalar identity**: 1**v** = **v**, where 1 is the multiplicative identity in F

## Common Examples of Vector Spaces

### 1. Euclidean Space ℝⁿ
- Set of all n-tuples of real numbers: (x₁, x₂, ..., xₙ)
- Standard operations:
  - Addition: (x₁, ..., xₙ) + (y₁, ..., yₙ) = (x₁ + y₁, ..., xₙ + yₙ)
  - Scalar multiplication: c(x₁, ..., xₙ) = (cx₁, ..., cxₙ)

### 2. Matrix Space Mₘₓₙ
- Set of all m×n matrices with entries from F
- Component-wise addition and scalar multiplication

### 3. Polynomial Space Pₙ
- Set of all polynomials of degree ≤ n
- Example: P₂ = {a₀ + a₁x + a₂x² | a₀, a₁, a₂ ∈ ℝ}

### 4. Function Spaces
- C[a, b]: Continuous functions on interval [a, b]
- F(S, ℝ): All real-valued functions on set S

### 5. Zero Vector Space
- Contains only the zero vector: {**0**}

## Important Concepts

### Subspace
A subset W of vector space V is a **subspace** if:
1. **0** ∈ W (contains zero vector)
2. Closed under addition: **u**, **v** ∈ W ⟹ **u** + **v** ∈ W
3. Closed under scalar multiplication: **v** ∈ W, c ∈ F ⟹ c**v** ∈ W

**Note**: Every subspace is itself a vector space.

### Linear Combination
A vector **v** is a **linear combination** of vectors **v₁**, **v₂**, ..., **vₙ** if:
$$\mathbf{v} = c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n$$
where c₁, c₂, ..., cₙ are scalars.

### Span
The **span** of a set of vectors S = {**v₁**, **v₂**, ..., **vₙ**} is the set of all linear combinations of those vectors:
$$\text{span}(S) = \{c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n \mid c_i \in F\}$$

**Properties**:
- span(S) is a subspace
- S spans V if span(S) = V

### Linear Independence
A set of vectors {**v₁**, **v₂**, ..., **vₙ**} is **linearly independent** if:
$$c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n = \mathbf{0} \implies c_1 = c_2 = \cdots = c_n = 0$$

Otherwise, the set is **linearly dependent**.

**Key fact**: A set is linearly dependent if and only if at least one vector can be written as a linear combination of the others.

### Basis
A **basis** for vector space V is a set B of vectors that:
1. Is linearly independent
2. Spans V (every vector in V can be expressed as a linear combination of basis vectors)

**Properties**:
- Every vector in V has a unique representation as a linear combination of basis vectors
- Any two bases of V have the same number of elements

### Dimension
The **dimension** of vector space V, denoted dim(V), is:
- The number of vectors in any basis of V
- If V has a finite basis, V is **finite-dimensional**
- Otherwise, V is **infinite-dimensional**

**Examples**:
- dim(ℝⁿ) = n
- dim(Pₙ) = n + 1
- dim(Mₘₓₙ) = mn

### Standard Basis
**For ℝⁿ**: The standard basis is {**e₁**, **e₂**, ..., **eₙ**} where:
- **e₁** = (1, 0, 0, ..., 0)
- **e₂** = (0, 1, 0, ..., 0)
- **eₙ** = (0, 0, 0, ..., 1)

## Important Theorems

### 1. Unique Representation Theorem
If B = {**v₁**, **v₂**, ..., **vₙ**} is a basis for V, then every vector **v** ∈ V can be uniquely expressed as:
$$\mathbf{v} = c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n$$

### 2. Dimension Theorem
If V is finite-dimensional and dim(V) = n, then:
- Any set of n + 1 or more vectors in V is linearly dependent
- Any linearly independent set of n vectors is a basis
- Any spanning set of n vectors is a basis

### 3. Dimension of Subspaces
If W is a subspace of finite-dimensional vector space V, then:
- dim(W) ≤ dim(V)
- dim(W) = dim(V) if and only if W = V

## Properties and Results

1. **Zero vector is unique**: There is exactly one zero vector in any vector space
2. **Additive inverse is unique**: Each vector has exactly one additive inverse
3. **0v = 0** for any vector **v**
4. **c0 = 0** for any scalar c
5. **(-1)v = -v** for any vector **v**
6. If **cv = 0**, then either c = 0 or **v = 0**

## Applications in GATE DA

Vector spaces are fundamental to:
- **Machine Learning**: Feature spaces, kernel methods
- **Data Analysis**: Principal Component Analysis (PCA)
- **Computer Graphics**: Transformations, coordinate systems
- **Optimization**: Convex optimization, linear programming
- **Signal Processing**: Signal representation, basis functions
- **Statistics**: Random vectors, multivariate analysis

## Key Points for GATE Preparation

1. **Always verify all 10 axioms** when proving something is a vector space
2. **For subspaces**, only need to check 3 conditions (zero vector, closure under addition and scalar multiplication)
3. **Linear independence** can be checked using determinants for finite sets in ℝⁿ
4. **Dimension** is the most important invariant of a finite-dimensional vector space
5. Know standard bases for ℝⁿ, Pₙ, and Mₘₓₙ
6. Practice identifying bases and computing dimensions

## Common Exam Problems

1. Determine if a given set with operations is a vector space
2. Check if a subset is a subspace
3. Find basis and dimension of a subspace
4. Determine linear independence/dependence
5. Express a vector as a linear combination of basis vectors
6. Find span of a set of vectors

---

**Remember**: Understanding vector spaces is crucial for linear algebra and forms the foundation for many advanced topics in data science and analytics!

# Deep Notes on Vector Spaces

## Table of Contents
1. [Span](#span)
2. [Linear Independence](#linear-independence)
3. [Basis](#basis)
4. [Dimension](#dimension)
5. [Standard Basis](#standard-basis)

---

## Span

### Definition
The **span** of a set of vectors {v₁, v₂, ..., vₙ} in a vector space V is the set of all possible linear combinations of these vectors.

**Mathematically:**
```
Span{v₁, v₂, ..., vₙ} = {c₁v₁ + c₂v₂ + ... + cₙvₙ | c₁, c₂, ..., cₙ ∈ ℝ}
```

### Key Properties

1. **Span is a Subspace**: The span of any set of vectors is always a subspace of the vector space V.

2. **Closure Properties**:
   - Contains the zero vector (when all coefficients are 0)
   - Closed under addition
   - Closed under scalar multiplication

3. **Minimal Spanning Set**: If a vector in the set can be written as a linear combination of others, it can be removed without changing the span.

### Examples

**Example 1: R²**
```
v₁ = (1, 0)
v₂ = (0, 1)

Span{v₁, v₂} = R² (all of 2D space)
```

**Example 2: R³**
```
v₁ = (1, 0, 0)
v₂ = (2, 0, 0)

Span{v₁, v₂} = {(x, 0, 0) | x ∈ ℝ} (the x-axis)
```

**Example 3: Single Vector**
```
v = (1, 2, 3)

Span{v} = {t(1, 2, 3) | t ∈ ℝ} (a line through the origin)
```

### Important Results

- **Spanning Set**: A set of vectors spans V if every vector in V can be written as a linear combination of vectors in the set.
- If Span{v₁, v₂, ..., vₙ} = V, we say {v₁, v₂, ..., vₙ} **spans** V.
- Adding more vectors to a spanning set maintains the spanning property.

### Geometric Interpretation

- **One vector**: Spans a line through the origin
- **Two non-parallel vectors in R³**: Span a plane through the origin
- **Three non-coplanar vectors in R³**: Span all of R³

---

## Linear Independence

### Definition
A set of vectors {v₁, v₂, ..., vₙ} is **linearly independent** if the only solution to:
```
c₁v₁ + c₂v₂ + ... + cₙvₙ = 0
```
is c₁ = c₂ = ... = cₙ = 0 (the trivial solution).

If there exists a non-trivial solution (where at least one cᵢ ≠ 0), the vectors are **linearly dependent**.

### Key Properties

1. **Alternative Definition**: Vectors are linearly dependent if and only if at least one vector can be written as a linear combination of the others.

2. **Single Vector**: 
   - A single non-zero vector is linearly independent
   - The zero vector alone is linearly dependent

3. **Subset Property**: If a set contains a linearly dependent subset, the entire set is linearly dependent.

4. **Superset Property**: Any superset of a linearly dependent set is linearly dependent.

### Testing for Linear Independence

#### Method 1: Matrix Method
Write vectors as columns of a matrix A and row reduce to RREF.
- Vectors are **independent** if every column has a pivot
- Vectors are **dependent** if there's at least one free variable

#### Method 2: Direct Computation
Solve c₁v₁ + c₂v₂ + ... + cₙvₙ = 0
- If only solution is all cᵢ = 0, vectors are independent
- If there's a non-trivial solution, vectors are dependent

### Examples

**Example 1: Independent Vectors in R³**
```
v₁ = (1, 0, 0)
v₂ = (0, 1, 0)
v₃ = (0, 0, 1)

These are linearly independent (standard basis vectors).
```

**Example 2: Dependent Vectors in R³**
```
v₁ = (1, 2, 3)
v₂ = (2, 4, 6)

v₂ = 2v₁, so they are linearly dependent.
```

**Example 3: Three Vectors in R²**
```
Any three vectors in R² are always linearly dependent.
(More vectors than dimensions → must be dependent)
```

### Important Theorems

1. **Maximum Independent Set**: In Rⁿ, any set of more than n vectors is linearly dependent.

2. **Minimum Dependent Set**: In Rⁿ, any set of fewer than n vectors cannot span Rⁿ.

3. **Zero Vector**: Any set containing the zero vector is linearly dependent.

4. **Two Vectors**: Two vectors are linearly dependent if and only if they are scalar multiples of each other (parallel).

---

## Basis

### Definition
A **basis** for a vector space V is a set of vectors that:
1. **Spans** V (every vector in V can be expressed as a linear combination)
2. Is **linearly independent**

### Key Properties

1. **Uniqueness of Representation**: Every vector v ∈ V can be written **uniquely** as a linear combination of basis vectors.

2. **Minimal Spanning Set**: A basis is a minimal spanning set (removing any vector destroys the spanning property).

3. **Maximal Independent Set**: A basis is a maximal linearly independent set (adding any vector creates dependence).

### Standard Bases

**R²:**
```
{(1, 0), (0, 1)}
```

**R³:**
```
{(1, 0, 0), (0, 1, 0), (0, 0, 1)}
```

**Rⁿ:**
```
{e₁, e₂, ..., eₙ} where eᵢ has 1 in position i and 0 elsewhere
```

### Finding a Basis

#### Method 1: From Spanning Set
1. Write vectors as rows of a matrix
2. Row reduce to RREF
3. Non-zero rows form a basis

#### Method 2: From Column Space
1. Write vectors as columns of a matrix
2. Row reduce to RREF
3. Original columns corresponding to pivot columns form a basis

#### Method 3: Extension
Start with linearly independent set and add vectors until you span the space.

### Examples

**Example 1: Basis for R³**
```
v₁ = (1, 0, 0)
v₂ = (1, 1, 0)
v₃ = (1, 1, 1)

This is a valid basis for R³ (can be verified by checking independence and span).
```

**Example 2: Basis for Polynomial Space P₂**
```
{1, x, x²} is the standard basis for polynomials of degree ≤ 2
```

**Example 3: Non-Standard Basis for R²**
```
{(1, 1), (1, -1)} forms a basis for R²
```

### Coordinate Vector
If B = {b₁, b₂, ..., bₙ} is a basis for V and v = c₁b₁ + c₂b₂ + ... + cₙbₙ, then:
```
[v]ᵦ = (c₁, c₂, ..., cₙ)
```
is the **coordinate vector** of v with respect to basis B.

### Change of Basis
Given two bases B and B', there exists a change of basis matrix P such that:
```
[v]ᵦ = P[v]ᵦ'
```

---

## Dimension

### Definition
The **dimension** of a vector space V (denoted dim(V)) is the number of vectors in any basis for V.

### Key Properties

1. **Well-Defined**: All bases of a vector space have the same number of vectors.

2. **Invariant**: Dimension is an intrinsic property of the vector space, independent of the choice of basis.

3. **Finite vs Infinite**: 
   - If V has a finite basis, V is **finite-dimensional**
   - Otherwise, V is **infinite-dimensional**

### Important Theorems

1. **Basis Theorem**: Any two bases for a finite-dimensional vector space have the same number of elements.

2. **Dimension Theorem**: If dim(V) = n, then:
   - Any set of n linearly independent vectors in V is a basis
   - Any set of n vectors that spans V is a basis
   - Any linearly independent set can be extended to a basis
   - Any spanning set can be reduced to a basis

3. **Comparison Theorem**: 
   - If dim(V) = n, then any set of more than n vectors is linearly dependent
   - Any set of fewer than n vectors cannot span V

### Examples of Dimensions

| Vector Space | Dimension |
|--------------|-----------|
| {0} (zero space) | 0 |
| R | 1 |
| R² | 2 |
| R³ | 3 |
| Rⁿ | n |
| Pₙ (polynomials degree ≤ n) | n + 1 |
| Mₘₓₙ (m×n matrices) | m × n |
| C[a,b] (continuous functions) | ∞ |

### Dimension Formulas

1. **Rank-Nullity Theorem**:
   ```
   dim(V) = rank(A) + nullity(A)
   ```
   where rank(A) = dim(Col(A)) and nullity(A) = dim(Null(A))

2. **Sum of Subspaces**:
   ```
   dim(U + W) = dim(U) + dim(W) - dim(U ∩ W)
   ```

3. **Product Spaces**:
   ```
   dim(V × W) = dim(V) + dim(W)
   ```

### Applications

1. **Solution Spaces**: The dimension of the solution space of Ax = 0 equals the number of free variables.

2. **Degrees of Freedom**: In physics and engineering, dimension represents degrees of freedom.

3. **Data Science**: Dimensionality reduction techniques (PCA) work in lower-dimensional subspaces.

---

## Standard Basis

### Definition
The **standard basis** for Rⁿ is the set:
```
{e₁, e₂, ..., eₙ}
```
where eᵢ is the vector with 1 in the iᵗʰ position and 0 elsewhere.

### Standard Basis Vectors

**R²:**
```
e₁ = (1, 0)
e₂ = (0, 1)
```

**R³:**
```
e₁ = (1, 0, 0)
e₂ = (0, 1, 0)
e₃ = (0, 0, 1)
```

**Rⁿ:**
```
e₁ = (1, 0, 0, ..., 0)
e₂ = (0, 1, 0, ..., 0)
⋮
eₙ = (0, 0, 0, ..., 1)
```

### Properties

1. **Orthonormality**: Standard basis vectors are:
   - **Orthogonal**: eᵢ · eⱼ = 0 for i ≠ j
   - **Normalized**: ||eᵢ|| = 1 for all i

2. **Simple Coordinates**: In the standard basis, the coordinate vector equals the vector itself:
   ```
   v = (v₁, v₂, ..., vₙ) ⟹ [v]ₛₜd = (v₁, v₂, ..., vₙ)
   ```

3. **Identity Matrix Columns**: The standard basis vectors are the columns of the identity matrix Iₙ.

4. **Canonical Choice**: The standard basis is the "natural" or default basis for Rⁿ.

### Standard Bases for Other Spaces

#### Polynomial Spaces
**P₂ (polynomials of degree ≤ 2):**
```
{1, x, x²}
```

**Pₙ (polynomials of degree ≤ n):**
```
{1, x, x², ..., xⁿ}
```

#### Matrix Spaces
**M₂ₓ₂ (2×2 matrices):**
```
E₁₁ = [1 0]    E₁₂ = [0 1]    E₂₁ = [0 0]    E₂₂ = [0 0]
      [0 0]          [0 0]          [1 0]          [0 1]
```

**Mₘₓₙ (m×n matrices):**
The standard basis consists of matrices Eᵢⱼ with 1 in position (i,j) and 0 elsewhere.

### Why Standard Basis is Special

1. **Computational Simplicity**: Matrix operations are simplest in the standard basis.

2. **Geometric Interpretation**: Aligns with coordinate axes.

3. **Universal Reference**: Provides a common framework for comparison.

4. **Identity Transformation**: The identity matrix represents the identity transformation in the standard basis.

### Converting Between Bases

To convert from standard basis to another basis B = {b₁, b₂, ..., bₙ}:

1. Form the **change of basis matrix** P with basis vectors as columns:
   ```
   P = [b₁ | b₂ | ... | bₙ]
   ```

2. To find coordinates in basis B:
   ```
   [v]ᵦ = P⁻¹v
   ```

3. To convert from B back to standard basis:
   ```
   v = P[v]ᵦ
   ```

### Example: Computing in Different Bases

**Problem**: Express v = (5, 3) in the basis B = {(1, 1), (1, -1)}

**Solution**:
1. Find coefficients: (5, 3) = c₁(1, 1) + c₂(1, -1)
2. Solve system: 5 = c₁ + c₂, 3 = c₁ - c₂
3. Result: c₁ = 4, c₂ = 1
4. Therefore: [v]ᵦ = (4, 1)

### Advantages of Non-Standard Bases

While the standard basis is convenient, other bases can be advantageous:

1. **Eigenbases**: Diagonalize matrices
2. **Fourier Basis**: Signal processing
3. **Wavelet Basis**: Image compression
4. **Principal Components**: Data analysis (PCA)

---

## Summary Table

| Concept | Definition | Key Property |
|---------|------------|--------------|
| **Span** | All linear combinations of a set | Forms a subspace |
| **Linear Independence** | Only trivial solution to c₁v₁ + ... + cₙvₙ = 0 | No redundancy |
| **Basis** | Linearly independent spanning set | Unique representation |
| **Dimension** | Number of vectors in a basis | Intrinsic to the space |
| **Standard Basis** | {e₁, ..., eₙ} with eᵢ having 1 at position i | Orthonormal, canonical |

---

## Practice Problems

### Problem 1: Span
Determine if v = (2, 5, 3) is in Span{(1, 2, 1), (0, 1, 1)}.

### Problem 2: Linear Independence
Determine if the vectors (1, 2, 3), (2, 3, 4), (3, 4, 5) are linearly independent.

### Problem 3: Basis
Find a basis for the subspace of R⁴ consisting of vectors of the form (a, b, a+b, a-b).

### Problem 4: Dimension
What is the dimension of the space of 3×3 symmetric matrices?

### Problem 5: Change of Basis
Given basis B = {(1, 2), (3, 4)} for R², find the coordinate vector [v]ᵦ where v = (5, 6) in standard coordinates.

---

## Important Notes for GATE Exam

1. **Quick Tests**:
   - More vectors than dimension → dependent
   - Fewer vectors than dimension → cannot span
   - Zero vector present → dependent

2. **Matrix Methods**: Use row reduction for systematic checking of independence and span.

3. **Dimension Counting**: Know standard dimensions (Rⁿ, Pₙ, Mₘₓₙ).

4. **Basis Construction**: Can extend independent sets or reduce spanning sets.

5. **Coordinate Calculations**: Practice converting between bases quickly.

---

*Last Updated: November 8, 2025*
