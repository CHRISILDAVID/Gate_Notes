# Practice Problems: Span and Linear Combinations

## Basic Problems

### Problem 1: Simple Linear Combination
Given vectors $v_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 1 \\ 3 \end{bmatrix}$

Find the linear combination: $3v_1 - 2v_2$

<details>
<summary>Solution</summary>

$$3v_1 - 2v_2 = 3\begin{bmatrix} 2 \\ -1 \end{bmatrix} - 2\begin{bmatrix} 1 \\ 3 \end{bmatrix}$$

$$= \begin{bmatrix} 6 \\ -3 \end{bmatrix} - \begin{bmatrix} 2 \\ 6 \end{bmatrix} = \begin{bmatrix} 4 \\ -9 \end{bmatrix}$$

</details>

---

### Problem 2: Testing Membership
Determine if $b = \begin{bmatrix} 5 \\ 7 \end{bmatrix}$ is in span$\left\{\begin{bmatrix} 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 3 \\ 4 \end{bmatrix}\right\}$

<details>
<summary>Solution</summary>

We need to find $c_1, c_2$ such that:
$$c_1\begin{bmatrix} 1 \\ 2 \end{bmatrix} + c_2\begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} 5 \\ 7 \end{bmatrix}$$

This gives:
- $c_1 + 3c_2 = 5$ ... (1)
- $2c_1 + 4c_2 = 7$ ... (2)

From (1): $c_1 = 5 - 3c_2$

Substitute into (2): $2(5 - 3c_2) + 4c_2 = 7$

$10 - 6c_2 + 4c_2 = 7$

$10 - 2c_2 = 7$

$c_2 = \frac{3}{2}$

Therefore: $c_1 = 5 - 3(\frac{3}{2}) = 5 - \frac{9}{2} = \frac{1}{2}$

**Check**: $\frac{1}{2}\begin{bmatrix} 1 \\ 2 \end{bmatrix} + \frac{3}{2}\begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} 0.5 + 4.5 \\ 1 + 6 \end{bmatrix} = \begin{bmatrix} 5 \\ 7 \end{bmatrix}$ ✓

**Yes**, $b$ is in the span.

</details>

---

### Problem 3: Geometric Interpretation
What is the geometric representation of span$\left\{\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}\right\}$ in $\mathbb{R}^3$?

<details>
<summary>Solution</summary>

span$\left\{\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}\right\} = \left\{c\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} : c \in \mathbb{R}\right\}$

This represents **a line through the origin** in the direction of the vector $\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$.

Parametric form: $(x, y, z) = (t, 2t, 3t)$ for $t \in \mathbb{R}$

</details>

---

## Intermediate Problems

### Problem 4: Span of Multiple Vectors
Find the span of $S = \left\{\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix}\right\}$

<details>
<summary>Solution</summary>

First, check if the third vector is in the span of the first two:
$$c_1\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} + c_2\begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix}$$

This gives:
- $c_1 = 1$
- $c_2 = 1$
- $c_1 + c_2 = 2$ (Check: $1 + 1 = 2$ ✓)

So $\begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}$

The third vector is linearly dependent on the first two.

Therefore: span($S$) = span$\left\{\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}\right\}$

This is **a plane through the origin** in $\mathbb{R}^3$.

</details>

---

### Problem 5: Does it Span $\mathbb{R}^3$?
Does $S = \left\{\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}\right\}$ span $\mathbb{R}^3$?

<details>
<summary>Solution</summary>

We need to check if any vector $\begin{bmatrix} a \\ b \\ c \end{bmatrix}$ can be written as a linear combination:

$$c_1\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + c_2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + c_3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} a \\ b \\ c \end{bmatrix}$$

$$\begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} = \begin{bmatrix} a \\ b \\ c \end{bmatrix}$$

This always has a solution: $c_1 = a, c_2 = b, c_3 = c$

**Yes**, $S$ spans $\mathbb{R}^3$. This is the **standard basis** of $\mathbb{R}^3$.

</details>

---

### Problem 6: Redundant Vectors
Given $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $v_2 = \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$

Find a minimal spanning set for span$\{v_1, v_2, v_3\}$

<details>
<summary>Solution</summary>

Notice that $v_2 = 2v_1$, so $v_2$ is linearly dependent on $v_1$.

We can remove $v_2$ without changing the span.

Now check if $v_3$ is in span$\{v_1\}$:
$$c_1\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$$

This would require: $c_1 = 1$, $2c_1 = 1$, $3c_1 = 1$

These are inconsistent, so $v_3$ is NOT in span$\{v_1\}$.

**Minimal spanning set**: $\{v_1, v_3\}$ or $\{v_2, v_3\}$

The span is a **plane** in $\mathbb{R}^3$.

</details>

---

## Advanced Problems

### Problem 7: GATE-Style Problem
Let $V = \{(x, y, z) \in \mathbb{R}^3 : x + y + z = 0\}$. Find a basis for $V$ and determine if $\begin{bmatrix} 2 \\ -1 \\ -1 \end{bmatrix}$ is in $V$.

<details>
<summary>Solution</summary>

$V$ is the set of all vectors whose components sum to zero.

From $x + y + z = 0$, we get $z = -x - y$

So any vector in $V$ can be written as:
$$\begin{bmatrix} x \\ y \\ -x-y \end{bmatrix} = x\begin{bmatrix} 1 \\ 0 \\ -1 \end{bmatrix} + y\begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix}$$

**Basis for V**: $\left\{\begin{bmatrix} 1 \\ 0 \\ -1 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix}\right\}$

**Testing membership**: $2 + (-1) + (-1) = 0$ ✓

**Yes**, $\begin{bmatrix} 2 \\ -1 \\ -1 \end{bmatrix}$ is in $V$.

We can verify: $2\begin{bmatrix} 1 \\ 0 \\ -1 \end{bmatrix} + (-1)\begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix} = \begin{bmatrix} 2 \\ -1 \\ -1 \end{bmatrix}$

</details>

---

### Problem 8: Matrix Columns Span
For what value(s) of $k$ do the columns of $A = \begin{bmatrix} 1 & 2 & k \\ 2 & 5 & 8 \\ 1 & 3 & 7 \end{bmatrix}$ span $\mathbb{R}^3$?

<details>
<summary>Solution</summary>

The columns span $\mathbb{R}^3$ if and only if the matrix has full rank (rank = 3), which means $\det(A) \neq 0$.

$$\det(A) = 1\begin{vmatrix} 5 & 8 \\ 3 & 7 \end{vmatrix} - 2\begin{vmatrix} 2 & 8 \\ 1 & 7 \end{vmatrix} + k\begin{vmatrix} 2 & 5 \\ 1 & 3 \end{vmatrix}$$

$$= 1(35 - 24) - 2(14 - 8) + k(6 - 5)$$

$$= 11 - 12 + k = k - 1$$

For the columns to span $\mathbb{R}^3$: $k - 1 \neq 0$

**Answer**: $k \neq 1$

</details>

---

### Problem 9: Polynomial Span
Let $P_2$ be the vector space of polynomials of degree at most 2. Does $S = \{1 + x, x + x^2, 1 + x^2\}$ span $P_2$?

<details>
<summary>Solution</summary>

A general polynomial in $P_2$ is: $a + bx + cx^2$

We need to check if:
$$c_1(1 + x) + c_2(x + x^2) + c_3(1 + x^2) = a + bx + cx^2$$

Expanding:
$$c_1 + c_1x + c_2x + c_2x^2 + c_3 + c_3x^2 = a + bx + cx^2$$

$$(c_1 + c_3) + (c_1 + c_2)x + (c_2 + c_3)x^2 = a + bx + cx^2$$

This gives the system:
- $c_1 + c_3 = a$
- $c_1 + c_2 = b$
- $c_2 + c_3 = c$

Matrix form: $\begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{bmatrix}\begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} = \begin{bmatrix} a \\ b \\ c \end{bmatrix}$

$$\det\begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{bmatrix} = 1(1 - 0) - 0 + 1(1 - 0) = 2 \neq 0$$

The system has a unique solution for any $(a, b, c)$.

**Yes**, $S$ spans $P_2$.

</details>

---

### Problem 10: Row Space
Find a basis for the row space of $A = \begin{bmatrix} 1 & 2 & 3 & 4 \\ 2 & 4 & 6 & 8 \\ 1 & 3 & 5 & 7 \end{bmatrix}$

<details>
<summary>Solution</summary>

The row space is the span of the row vectors. Reduce to row echelon form:

$R_2 = R_2 - 2R_1$:
$$\begin{bmatrix} 1 & 2 & 3 & 4 \\ 0 & 0 & 0 & 0 \\ 1 & 3 & 5 & 7 \end{bmatrix}$$

$R_3 = R_3 - R_1$:
$$\begin{bmatrix} 1 & 2 & 3 & 4 \\ 0 & 0 & 0 & 0 \\ 0 & 1 & 2 & 3 \end{bmatrix}$$

Swap $R_2$ and $R_3$:
$$\begin{bmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 2 & 3 \\ 0 & 0 & 0 & 0 \end{bmatrix}$$

The non-zero rows form a basis for the row space.

**Basis**: $\left\{\begin{bmatrix} 1 & 2 & 3 & 4 \end{bmatrix}, \begin{bmatrix} 0 & 1 & 2 & 3 \end{bmatrix}\right\}$

Dimension = 2

</details>

---

## GATE Previous Year Questions Style

### Problem 11
If vectors $v_1, v_2, v_3$ span $\mathbb{R}^3$ and $w = 2v_1 - v_2 + 3v_3$, then which of the following is true?

(A) $\{v_1, v_2, v_3, w\}$ span $\mathbb{R}^4$  
(B) $\{v_1, v_2, v_3, w\}$ are linearly independent  
(C) $w$ is in span$\{v_1, v_2, v_3\}$  
(D) None of the above

<details>
<summary>Solution</summary>

**Answer: (C)**

Since $w = 2v_1 - v_2 + 3v_3$, by definition, $w$ is a linear combination of $v_1, v_2, v_3$.

Therefore, $w$ is in span$\{v_1, v_2, v_3\}$.

(A) is false: All four vectors are in $\mathbb{R}^3$, so they cannot span $\mathbb{R}^4$.

(B) is false: Since $w$ is a linear combination of the others, the set is linearly dependent.

</details>

---

### Problem 12
The dimension of span$\left\{\begin{bmatrix} 1 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ 0 \\ 0 \\ 1 \end{bmatrix}\right\}$ is:

(A) 1  
(B) 2  
(C) 3  
(D) 4

<details>
<summary>Solution</summary>

Form matrix with vectors as columns and find rank:
$$A = \begin{bmatrix} 1 & 0 & 0 & 1 \\ 1 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 1 \end{bmatrix}$$

Row reduce:
$R_2 = R_2 - R_1$:
$$\begin{bmatrix} 1 & 0 & 0 & 1 \\ 0 & 1 & 0 & -1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 1 \end{bmatrix}$$

$R_3 = R_3 - R_2$:
$$\begin{bmatrix} 1 & 0 & 0 & 1 \\ 0 & 1 & 0 & -1 \\ 0 & 0 & 1 & 1 \\ 0 & 0 & 1 & 1 \end{bmatrix}$$

$R_4 = R_4 - R_3$:
$$\begin{bmatrix} 1 & 0 & 0 & 1 \\ 0 & 1 & 0 & -1 \\ 0 & 0 & 1 & 1 \\ 0 & 0 & 0 & 0 \end{bmatrix}$$

Rank = 3

**Answer: (C) 3**

</details>

---

## Challenge Problems

### Problem 13
Prove that if $U$ and $W$ are subspaces of vector space $V$, then span$(U \cup W) = U + W$ where $U + W = \{u + w : u \in U, w \in W\}$.

### Problem 14
Let $V$ be the vector space of all $2 \times 2$ matrices. Find the dimension of the span of:
$$S = \left\{\begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix}, \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}\right\}$$

### Problem 15
Show that the set of all polynomial functions $\{1, x, x^2, x^3, \ldots\}$ spans the vector space of all polynomial functions, but is not a basis (it's not finite).

---

## Tips for GATE Exam

1. **Quick rank calculation**: Use determinants for small matrices, row reduction for larger ones
2. **Geometric intuition**: Visualize lines, planes, and spaces
3. **Check linear independence**: If vectors are dependent, one can be removed from the spanning set
4. **Matrix representation**: Convert span problems to matrix problems
5. **Dimension counting**: dim(span) = number of linearly independent vectors = rank of matrix
