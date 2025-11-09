# Matrices in Linear Algebra

## Table of Contents
1. [Basic Definitions](#basic-definitions)
2. [Matrix Operations](#matrix-operations)
3. [Special Types of Matrices](#special-types-of-matrices)
4. [Matrix Properties](#matrix-properties)
5. [Determinants](#determinants)
6. [Matrix Inverse](#matrix-inverse)
7. [Rank of a Matrix](#rank-of-a-matrix)
8. [Eigenvalues and Eigenvectors](#eigenvalues-and-eigenvectors)
9. [Matrix Decompositions](#matrix-decompositions)
10. [Applications in GATE DA](#applications-in-gate-da)

---

## Basic Definitions

### What is a Matrix?

A **matrix** is a rectangular array of numbers, symbols, or expressions arranged in rows and columns.

**General form of an m×n matrix A:**
$$A = \begin{bmatrix} 
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}$$

- **Dimensions**: m × n (m rows, n columns)
- **Elements**: $a_{ij}$ represents the element in the i-th row and j-th column
- **Notation**: $A = [a_{ij}]_{m \times n}$ or $A_{m \times n}$

### Matrix Terminology

| Term | Definition | Example |
|------|------------|---------|
| **Element/Entry** | Individual value in the matrix | $a_{23} = 5$ |
| **Row** | Horizontal line of elements | Row 2: $[a_{21}, a_{22}, \ldots, a_{2n}]$ |
| **Column** | Vertical line of elements | Column 3: $[a_{13}, a_{23}, \ldots, a_{m3}]^T$ |
| **Main Diagonal** | Elements $a_{ii}$ where i = j | $a_{11}, a_{22}, a_{33}, \ldots$ |
| **Order/Size** | Dimensions m × n | 3 × 4 matrix has 3 rows, 4 columns |

### Types by Dimensions

1. **Square Matrix**: m = n (same number of rows and columns)
2. **Row Matrix**: m = 1 (single row)
3. **Column Matrix**: n = 1 (single column)
4. **Rectangular Matrix**: m ≠ n

---

## Matrix Operations

### 1. Matrix Addition and Subtraction

**Definition**: Two matrices A and B can be added/subtracted if and only if they have the same dimensions.

**Formula**: $(A \pm B)_{ij} = a_{ij} \pm b_{ij}$

**Example**:
$$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} + \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 6 & 8 \\ 10 & 12 \end{bmatrix}$$

**Properties**:
- **Commutative**: A + B = B + A
- **Associative**: (A + B) + C = A + (B + C)
- **Identity**: A + 0 = A (where 0 is the zero matrix)
- **Inverse**: A + (-A) = 0

### 2. Scalar Multiplication

**Definition**: Multiply every element of a matrix by a scalar.

**Formula**: $(kA)_{ij} = k \cdot a_{ij}$

**Example**:
$$3 \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 3 & 6 \\ 9 & 12 \end{bmatrix}$$

**Properties**:
- **Distributive**: k(A + B) = kA + kB
- **Distributive**: (k + l)A = kA + lA
- **Associative**: k(lA) = (kl)A
- **Identity**: 1A = A

### 3. Matrix Multiplication

**Definition**: For matrices A_{m×n} and B_{n×p}, the product AB is an m×p matrix.

**Formula**: $(AB)_{ij} = \sum_{k=1}^{n} a_{ik}b_{kj}$

**Requirement**: Number of columns in A = Number of rows in B

**Example**:
$$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 19 & 22 \\ 43 & 50 \end{bmatrix}$$

**Properties**:
- **Associative**: (AB)C = A(BC)
- **Distributive**: A(B + C) = AB + AC
- **NOT Commutative**: AB ≠ BA (in general)
- **Identity**: AI = IA = A (where I is the identity matrix)

### 4. Matrix Transpose

**Definition**: The transpose of A, denoted A^T, is obtained by interchanging rows and columns.

**Formula**: $(A^T)_{ij} = a_{ji}$

**Example**:
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{bmatrix} \Rightarrow A^T = \begin{bmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{bmatrix}$$

**Properties**:
- $(A^T)^T = A$
- $(A + B)^T = A^T + B^T$
- $(kA)^T = kA^T$
- $(AB)^T = B^T A^T$

---

## Special Types of Matrices

### 1. Zero Matrix (Null Matrix)

**Definition**: All elements are zero.
$$0 = \begin{bmatrix} 0 & 0 & \cdots & 0 \\ 0 & 0 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 0 \end{bmatrix}$$

**Properties**:
- A + 0 = A
- A · 0 = 0
- 0 · A = 0

### 2. Identity Matrix

**Definition**: Square matrix with 1s on the main diagonal and 0s elsewhere.
$$I_n = \begin{bmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{bmatrix}$$

**Properties**:
- AI = IA = A
- $I^n = I$ for any positive integer n
- $\det(I) = 1$

### 3. Diagonal Matrix

**Definition**: Square matrix with non-zero elements only on the main diagonal.
$$D = \begin{bmatrix} d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n \end{bmatrix}$$

**Properties**:
- Easy multiplication: If A and B are diagonal, then AB is diagonal
- $\det(D) = d_1 \cdot d_2 \cdot \ldots \cdot d_n$

### 4. Symmetric Matrix

**Definition**: A square matrix equal to its transpose: $A = A^T$

**Condition**: $a_{ij} = a_{ji}$ for all i, j

**Example**:
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 5 \\ 3 & 5 & 6 \end{bmatrix}$$

**Properties**:
- All eigenvalues are real
- Eigenvectors corresponding to distinct eigenvalues are orthogonal
- Always diagonalizable

### 5. Skew-Symmetric Matrix

**Definition**: A square matrix where $A = -A^T$

**Condition**: $a_{ij} = -a_{ji}$ for all i, j

**Properties**:
- Main diagonal elements are zero
- All eigenvalues are purely imaginary
- Determinant is zero if matrix is odd-sized

### 6. Orthogonal Matrix

**Definition**: A square matrix Q where $Q^T Q = QQ^T = I$

**Properties**:
- $Q^{-1} = Q^T$
- $\det(Q) = \pm 1$
- Preserves lengths and angles
- Columns (and rows) form an orthonormal set

### 7. Upper/Lower Triangular Matrices

**Upper Triangular**: All elements below the main diagonal are zero
$$U = \begin{bmatrix} u_{11} & u_{12} & u_{13} \\ 0 & u_{22} & u_{23} \\ 0 & 0 & u_{33} \end{bmatrix}$$

**Lower Triangular**: All elements above the main diagonal are zero
$$L = \begin{bmatrix} l_{11} & 0 & 0 \\ l_{21} & l_{22} & 0 \\ l_{31} & l_{32} & l_{33} \end{bmatrix}$$

**Properties**:
- Determinant = product of diagonal elements
- Easy to solve linear systems
- Product of two upper (lower) triangular matrices is upper (lower) triangular

---

## Matrix Properties

### 1. Commutativity in Matrix Multiplication

**General Rule**: Matrix multiplication is NOT commutative (AB ≠ BA)

**Exceptions where AB = BA**:
- A or B is the identity matrix
- A or B is the zero matrix
- A and B are both diagonal matrices
- A and B commute (special cases)

### 2. Matrix Powers

**Definition**: $A^n = A \cdot A \cdot \ldots \cdot A$ (n times)

**Properties**:
- $A^m \cdot A^n = A^{m+n}$
- $(A^m)^n = A^{mn}$
- $A^0 = I$ (if A is invertible)

### 3. Trace of a Matrix

**Definition**: Sum of diagonal elements of a square matrix
$$\text{tr}(A) = \sum_{i=1}^{n} a_{ii}$$

**Properties**:
- $\text{tr}(A + B) = \text{tr}(A) + \text{tr}(B)$
- $\text{tr}(kA) = k \cdot \text{tr}(A)$
- $\text{tr}(AB) = \text{tr}(BA)$
- $\text{tr}(A) = \sum_{i=1}^{n} \lambda_i$ (sum of eigenvalues)

---

## Determinants

### Definition

The **determinant** is a scalar value associated with a square matrix that provides important information about the matrix.

### Calculation Methods

#### 1. 2×2 Matrix
$$\det\begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc$$

#### 2. 3×3 Matrix (Rule of Sarrus)
$$\det\begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix} = aei + bfg + cdh - ceg - afh - bdi$$

#### 3. Cofactor Expansion (Laplace Expansion)
For an n×n matrix A:
$$\det(A) = \sum_{j=1}^{n} a_{ij}C_{ij}$$

where $C_{ij} = (-1)^{i+j}M_{ij}$ and $M_{ij}$ is the minor.

### Properties of Determinants

1. **Multiplicative**: $\det(AB) = \det(A) \cdot \det(B)$
2. **Transpose**: $\det(A^T) = \det(A)$
3. **Scalar Multiple**: $\det(kA) = k^n \det(A)$ for n×n matrix
4. **Row Operations**:
   - Swapping rows: determinant changes sign
   - Multiplying row by k: determinant multiplied by k
   - Adding multiple of one row to another: determinant unchanged

### Special Values

| Condition | Determinant | Meaning |
|-----------|-------------|---------|
| $\det(A) = 0$ | Zero | Matrix is singular (not invertible) |
| $\det(A) \neq 0$ | Non-zero | Matrix is non-singular (invertible) |
| $\det(A) = 1$ | One | Volume-preserving transformation |
| $\det(A) = -1$ | Negative one | Volume-preserving with orientation reversal |

---

## Matrix Inverse

### Definition

The **inverse** of a square matrix A, denoted $A^{-1}$, is a matrix such that:
$$A \cdot A^{-1} = A^{-1} \cdot A = I$$

### Existence Conditions

A matrix A has an inverse if and only if:
- A is square
- $\det(A) \neq 0$ (A is non-singular)

### Methods to Find Inverse

#### 1. 2×2 Matrix Formula
$$A^{-1} = \frac{1}{\det(A)} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$$
for $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$

#### 2. Adjugate Method
$$A^{-1} = \frac{1}{\det(A)} \text{adj}(A)$$
where $\text{adj}(A)$ is the adjugate (transpose of cofactor matrix)

#### 3. Gauss-Jordan Elimination
Augment A with I and row reduce [A|I] to [I|A^{-1}]

#### 4. Elementary Row Operations
Use elementary matrices to transform A to I

### Properties of Inverse

1. $(A^{-1})^{-1} = A$
2. $(AB)^{-1} = B^{-1}A^{-1}$
3. $(A^T)^{-1} = (A^{-1})^T$
4. $\det(A^{-1}) = \frac{1}{\det(A)}$
5. $(kA)^{-1} = \frac{1}{k}A^{-1}$ for $k \neq 0$

### Applications

- Solving linear systems: $Ax = b \Rightarrow x = A^{-1}b$
- Finding matrix equations: $AXB = C \Rightarrow X = A^{-1}CB^{-1}$
- Cryptography and coding theory

---

## Rank of a Matrix

### Definition

The **rank** of a matrix A, denoted rank(A), is:
- The dimension of the column space (column rank)
- The dimension of the row space (row rank)
- The number of linearly independent rows/columns
- The number of pivot positions in RREF

### Methods to Find Rank

#### 1. Row Reduction Method
1. Reduce matrix to Row Echelon Form (REF) or Reduced Row Echelon Form (RREF)
2. Count the number of non-zero rows

#### 2. Determinant Method
- For square matrices: rank = n if det ≠ 0, rank < n if det = 0
- Check determinants of all k×k submatrices

### Properties of Rank

1. **Range**: $0 \leq \text{rank}(A) \leq \min(m,n)$ for m×n matrix
2. **Additivity**: $\text{rank}(A + B) \leq \text{rank}(A) + \text{rank}(B)$
3. **Products**: $\text{rank}(AB) \leq \min(\text{rank}(A), \text{rank}(B))$
4. **Transpose**: $\text{rank}(A^T) = \text{rank}(A)$
5. **Full Rank**: rank(A) = min(m,n) means A has full rank

### Rank-Nullity Theorem

For an m×n matrix A:
$$\text{rank}(A) + \text{nullity}(A) = n$$

where nullity(A) = dimension of null space = number of free variables

### Applications

- **Linear Systems**: Number of solutions depends on rank
- **Linear Independence**: Columns are independent ↔ full column rank
- **Invertibility**: Square matrix is invertible ↔ full rank
- **Least Squares**: Normal equations solvability

---

## Eigenvalues and Eigenvectors

### Definitions

For a square matrix A:
- **Eigenvalue** λ: A scalar such that $Av = \lambda v$ for some non-zero vector v
- **Eigenvector** v: A non-zero vector satisfying $Av = \lambda v$
- **Eigenspace**: The set of all eigenvectors corresponding to an eigenvalue

### Finding Eigenvalues

#### Characteristic Equation
$$\det(A - \lambda I) = 0$$

#### Characteristic Polynomial
$$p(\lambda) = \det(A - \lambda I)$$

The roots of this polynomial are the eigenvalues.

### Example Calculation

For $A = \begin{bmatrix} 3 & 1 \\ 0 & 2 \end{bmatrix}$:

1. **Characteristic equation**:
   $$\det\begin{bmatrix} 3-\lambda & 1 \\ 0 & 2-\lambda \end{bmatrix} = (3-\lambda)(2-\lambda) = 0$$

2. **Eigenvalues**: λ₁ = 3, λ₂ = 2

3. **Eigenvectors**:
   - For λ₁ = 3: $(A - 3I)v = 0$ gives $v₁ = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$
   - For λ₂ = 2: $(A - 2I)v = 0$ gives $v₂ = \begin{bmatrix} 1 \\ -1 \end{bmatrix}$

### Properties

1. **Trace**: $\text{tr}(A) = \sum \lambda_i$ (sum of eigenvalues)
2. **Determinant**: $\det(A) = \prod \lambda_i$ (product of eigenvalues)
3. **Powers**: If λ is eigenvalue of A, then λⁿ is eigenvalue of Aⁿ
4. **Inverse**: If λ is eigenvalue of A, then 1/λ is eigenvalue of A⁻¹

### Diagonalization

A matrix A is **diagonalizable** if there exists an invertible matrix P such that:
$$P^{-1}AP = D$$
where D is diagonal.

**Conditions for Diagonalization**:
- A has n linearly independent eigenvectors
- Geometric multiplicity = Algebraic multiplicity for each eigenvalue

**Process**:
1. Find eigenvalues and eigenvectors
2. Form P using eigenvectors as columns
3. D has eigenvalues on the diagonal

### Applications

- **Principal Component Analysis (PCA)**
- **Google PageRank Algorithm**
- **Stability Analysis in Systems**
- **Quantum Mechanics**
- **Vibration Analysis**

---

## Matrix Decompositions

### 1. LU Decomposition

**Purpose**: Factor A into lower and upper triangular matrices
$$A = LU$$

**Applications**:
- Solving linear systems efficiently
- Computing determinants
- Matrix inversion

**Example**:
$$\begin{bmatrix} 2 & 1 \\ 4 & 3 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 2 & 1 \end{bmatrix} \begin{bmatrix} 2 & 1 \\ 0 & 1 \end{bmatrix}$$

### 2. QR Decomposition

**Purpose**: Factor A into orthogonal and upper triangular matrices
$$A = QR$$

where Q is orthogonal and R is upper triangular.

**Applications**:
- Least squares solutions
- Eigenvalue algorithms
- Gram-Schmidt process

### 3. Singular Value Decomposition (SVD)

**Purpose**: Factor any m×n matrix as
$$A = U\Sigma V^T$$

where:
- U: m×m orthogonal matrix
- Σ: m×n diagonal matrix with singular values
- V: n×n orthogonal matrix

**Applications**:
- **Data compression**
- **Principal Component Analysis**
- **Recommender systems**
- **Image processing**

### 4. Cholesky Decomposition

**Purpose**: For positive definite symmetric matrix A
$$A = LL^T$$

where L is lower triangular.

**Applications**:
- Solving systems with symmetric positive definite matrices
- Monte Carlo simulations
- Optimization algorithms

---

## Applications in GATE DA

### 1. Machine Learning

#### Principal Component Analysis (PCA)
- **Covariance Matrix**: C = (1/n)X^TX
- **Eigendecomposition**: Find eigenvectors of C
- **Dimensionality Reduction**: Project data onto principal components

#### Linear Regression
- **Normal Equations**: $\theta = (X^TX)^{-1}X^Ty$
- **Gradient Descent**: Update rules using matrix operations
- **Regularization**: Ridge regression adds λI to X^TX

### 2. Data Analysis

#### Correlation and Covariance
- **Correlation Matrix**: Pairwise correlations between variables
- **Covariance Matrix**: Measures joint variability

#### Least Squares
- **Problem**: Minimize ||Ax - b||²
- **Solution**: x = (A^TA)⁻¹A^Tb (when A^TA is invertible)
- **Pseudoinverse**: A† = (A^TA)⁻¹A^T

### 3. Graph Theory and Networks

#### Adjacency Matrix
- **Representation**: A[i,j] = 1 if edge exists, 0 otherwise
- **Powers**: A^n gives number of paths of length n
- **Eigenvalues**: Related to connectivity and spectral properties

#### Laplacian Matrix
- **Definition**: L = D - A (D is degree matrix)
- **Properties**: Positive semidefinite, smallest eigenvalue is 0
- **Applications**: Graph clustering, random walks

### 4. Optimization

#### Linear Programming
- **Standard Form**: min c^Tx subject to Ax = b, x ≥ 0
- **Simplex Method**: Uses matrix operations
- **Duality**: Involves transpose matrices

#### Quadratic Programming
- **Form**: min (1/2)x^TQx + c^Tx subject to constraints
- **Positive Definiteness**: Q must be positive definite

### 5. Statistics and Probability

#### Multivariate Normal Distribution
- **PDF**: Involves inverse and determinant of covariance matrix
- **Properties**: Determined by mean vector and covariance matrix

#### Factor Analysis
- **Model**: X = Λf + ε
- **Estimation**: Uses eigendecomposition and matrix algebra

---

## Important Theorems for GATE

### 1. Matrix Rank Theorems

1. **Rank-Nullity Theorem**: rank(A) + nullity(A) = n
2. **Row Rank = Column Rank**
3. **Rank of Product**: rank(AB) ≤ min(rank(A), rank(B))

### 2. Determinant Theorems

1. **Multiplicative Property**: det(AB) = det(A)det(B)
2. **Invertibility**: A is invertible ↔ det(A) ≠ 0
3. **Cramer's Rule**: x_i = det(A_i)/det(A)

### 3. Eigenvalue Theorems

1. **Characteristic Polynomial**: deg(p(λ)) = n for n×n matrix
2. **Cayley-Hamilton Theorem**: A satisfies its characteristic equation
3. **Spectral Theorem**: Real symmetric matrices are diagonalizable

### 4. Matrix Decomposition Theorems

1. **LU Decomposition**: Exists if all leading principal minors ≠ 0
2. **QR Decomposition**: Exists for any matrix
3. **SVD**: Exists for any matrix

---

## Problem-Solving Strategies for GATE

### 1. Matrix Operations
- **Check dimensions** before operations
- **Use properties** to simplify calculations
- **Block matrices** for large problems

### 2. Determinants
- **Row operations** to simplify
- **Cofactor expansion** along row/column with most zeros
- **Special patterns** (triangular, diagonal)

### 3. Eigenvalues
- **Characteristic equation** method
- **Special matrices** (symmetric, triangular)
- **Trace and determinant** relationships

### 4. Linear Systems
- **Gaussian elimination** for general systems
- **Matrix inverse** when needed multiple times
- **Rank analysis** for solution existence

### 5. Optimization Problems
- **Matrix calculus** for derivatives
- **Positive definiteness** for minima
- **Constraint matrices** in optimization

---

## Common GATE Problem Types

### 1. Basic Matrix Operations
- Addition, multiplication, transpose
- Powers of matrices
- Trace and determinant calculations

### 2. Matrix Properties
- Determine if matrix is symmetric, orthogonal, etc.
- Find rank, eigenvalues, eigenvectors
- Check invertibility

### 3. Linear Systems
- Solve Ax = b using various methods
- Determine number of solutions
- Least squares problems

### 4. Applications
- PCA implementation
- Graph adjacency matrices
- Optimization problems with matrix constraints

### 5. Theoretical Questions
- Prove matrix properties
- Relationship between rank, determinant, eigenvalues
- Matrix decomposition existence and uniqueness

---

## Quick Reference Formulas

### Basic Operations
- Matrix multiplication: $(AB)_{ij} = \sum_k a_{ik}b_{kj}$
- Transpose: $(A^T)_{ij} = a_{ji}$
- Trace: $\text{tr}(A) = \sum_i a_{ii}$

### Determinants
- 2×2: $ad - bc$
- 3×3: $aei + bfg + cdh - ceg - afh - bdi$
- Properties: $\det(AB) = \det(A)\det(B)$, $\det(A^T) = \det(A)$

### Inverse
- 2×2: $\frac{1}{\det(A)}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$
- General: $A^{-1} = \frac{1}{\det(A)}\text{adj}(A)$

### Eigenvalues
- Characteristic equation: $\det(A - \lambda I) = 0$
- Properties: $\sum \lambda_i = \text{tr}(A)$, $\prod \lambda_i = \det(A)$

---

## Tips for GATE Preparation

1. **Practice Mental Calculations**: Simple 2×2 and 3×3 determinants
2. **Memorize Properties**: Especially for determinants and eigenvalues
3. **Use Shortcuts**: Row operations, special matrix types
4. **Understand Applications**: How matrices appear in ML and data analysis
5. **Pattern Recognition**: Look for structure in problems
6. **Time Management**: Know when to use different methods

---

*Last Updated: November 9, 2025*