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
