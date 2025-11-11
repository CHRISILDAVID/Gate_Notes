# Practice Problems: Linear Independence

## Basic Problems

### Problem 1: Simple Two Vectors
Determine if $v_1 = \begin{bmatrix} 2 \\ 3 \end{bmatrix}$ and $v_2 = \begin{bmatrix} 4 \\ 6 \end{bmatrix}$ are linearly independent.

<details>
<summary>Solution</summary>

Notice that $v_2 = 2v_1$:
$$\begin{bmatrix} 4 \\ 6 \end{bmatrix} = 2\begin{bmatrix} 2 \\ 3 \end{bmatrix}$$

Therefore: $2v_1 - v_2 = 0$ (non-trivial solution with $c_1 = 2, c_2 = -1$)

**Answer**: Linearly **dependent**

**Alternative**: Check if one is a scalar multiple of the other:
$$\frac{4}{2} = 2, \quad \frac{6}{3} = 2$$

Both ratios are equal, so they're parallel → dependent.

</details>

---

### Problem 2: Three Vectors in $\mathbb{R}^2$
Are $v_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$, $v_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$ linearly independent?

<details>
<summary>Solution</summary>

**Quick Recognition**: We have 3 vectors in $\mathbb{R}^2$ (2-dimensional space).

By the size constraint property: **More vectors than dimensions** → automatically linearly **dependent**.

**Finding the dependency**: 
$$v_3 = v_1 + v_2$$
$$\begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \end{bmatrix}$$

So: $v_1 + v_2 - v_3 = 0$ (non-trivial solution)

**Answer**: Linearly **dependent**

</details>

---

### Problem 3: Standard Basis Vectors
Show that $e_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}$, $e_2 = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}$, $e_3 = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$ are linearly independent.

<details>
<summary>Solution</summary>

**Method 1: Direct Test**
$$c_1\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + c_2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + c_3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

$$\begin{bmatrix} c_1 \\ c_2 \\ c_3 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

This gives: $c_1 = 0, c_2 = 0, c_3 = 0$ (only trivial solution)

**Method 2: Determinant**
$$\det\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} = 1 \neq 0$$

**Answer**: Linearly **independent** ✓

These form the standard basis of $\mathbb{R}^3$.

</details>

---

### Problem 4: Containing Zero Vector
Are $v_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$, $v_2 = \begin{bmatrix} 3 \\ 4 \end{bmatrix}$, $v_3 = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$ linearly independent?

<details>
<summary>Solution</summary>

**Quick Recognition**: The set contains the **zero vector**.

Any set containing the zero vector is automatically linearly **dependent**.

**Proof**: $0 \cdot v_1 + 0 \cdot v_2 + 1 \cdot v_3 = 0$

This is a non-trivial solution (not all coefficients are zero).

**Answer**: Linearly **dependent**

</details>

---

## Intermediate Problems

### Problem 5: Using Determinant
Determine if $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $v_2 = \begin{bmatrix} 4 \\ 5 \\ 6 \end{bmatrix}$, $v_3 = \begin{bmatrix} 7 \\ 8 \\ 9 \end{bmatrix}$ are linearly independent.

<details>
<summary>Solution</summary>

Form matrix with vectors as columns:
$$A = \begin{bmatrix} 1 & 4 & 7 \\ 2 & 5 & 8 \\ 3 & 6 & 9 \end{bmatrix}$$

Calculate determinant:
$$\det(A) = 1\begin{vmatrix} 5 & 8 \\ 6 & 9 \end{vmatrix} - 4\begin{vmatrix} 2 & 8 \\ 3 & 9 \end{vmatrix} + 7\begin{vmatrix} 2 & 5 \\ 3 & 6 \end{vmatrix}$$

$$= 1(45 - 48) - 4(18 - 24) + 7(12 - 15)$$

$$= 1(-3) - 4(-6) + 7(-3)$$

$$= -3 + 24 - 21 = 0$$

Since $\det(A) = 0$, the vectors are linearly **dependent**.

**Finding the dependency**: Notice that $v_3 - v_2 = v_2 - v_1$
$$\begin{bmatrix} 3 \\ 3 \\ 3 \end{bmatrix} = \begin{bmatrix} 3 \\ 3 \\ 3 \end{bmatrix}$$

So: $v_1 - 2v_2 + v_3 = 0$

</details>

---

### Problem 6: Using Row Reduction
Test linear independence of $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}$, $v_2 = \begin{bmatrix} 0 \\ 1 \\ 2 \\ 3 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 3 \\ 5 \\ 7 \end{bmatrix}$

<details>
<summary>Solution</summary>

Form matrix and row reduce:
$$A = \begin{bmatrix} 1 & 0 & 1 \\ 2 & 1 & 3 \\ 3 & 2 & 5 \\ 4 & 3 & 7 \end{bmatrix}$$

$R_2 = R_2 - 2R_1$, $R_3 = R_3 - 3R_1$, $R_4 = R_4 - 4R_1$:
$$\begin{bmatrix} 1 & 0 & 1 \\ 0 & 1 & 1 \\ 0 & 2 & 2 \\ 0 & 3 & 3 \end{bmatrix}$$

$R_3 = R_3 - 2R_2$, $R_4 = R_4 - 3R_2$:
$$\begin{bmatrix} 1 & 0 & 1 \\ 0 & 1 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}$$

**Rank = 2** (only 2 pivot columns)

Since rank $(A) = 2 < 3$ (number of vectors), the vectors are linearly **dependent**.

**Dependency**: The third column is not a pivot column. From the reduced form:
$$v_3 = v_1 + v_2$$

Verify: $\begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 1 \\ 3 \\ 5 \\ 7 \end{bmatrix}$ ✓

</details>

---

### Problem 7: Parametric Dependency
For what value(s) of $k$ are the vectors $v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $v_2 = \begin{bmatrix} 1 \\ k \\ 4 \end{bmatrix}$, $v_3 = \begin{bmatrix} 1 \\ 2 \\ k \end{bmatrix}$ linearly dependent?

<details>
<summary>Solution</summary>

Vectors are linearly dependent when $\det(A) = 0$:

$$A = \begin{bmatrix} 1 & 1 & 1 \\ 2 & k & 2 \\ 3 & 4 & k \end{bmatrix}$$

$$\det(A) = 1\begin{vmatrix} k & 2 \\ 4 & k \end{vmatrix} - 1\begin{vmatrix} 2 & 2 \\ 3 & k \end{vmatrix} + 1\begin{vmatrix} 2 & k \\ 3 & 4 \end{vmatrix}$$

$$= 1(k^2 - 8) - 1(2k - 6) + 1(8 - 3k)$$

$$= k^2 - 8 - 2k + 6 + 8 - 3k$$

$$= k^2 - 5k + 6$$

$$= (k - 2)(k - 3)$$

Set $\det(A) = 0$:
$$(k - 2)(k - 3) = 0$$

**Answer**: $k = 2$ or $k = 3$

The vectors are linearly dependent when $k \in \{2, 3\}$.

</details>

---

### Problem 8: Polynomial Independence
Are $p_1(x) = 1$, $p_2(x) = x$, $p_3(x) = x^2$ linearly independent in $P_2$?

<details>
<summary>Solution</summary>

Set up: $c_1 \cdot 1 + c_2 \cdot x + c_3 \cdot x^2 = 0$ (zero polynomial)

For a polynomial to be identically zero, all coefficients must be zero:
$$c_1 + c_2x + c_3x^2 = 0 \text{ for all } x$$

Comparing coefficients:
- Constant term: $c_1 = 0$
- Coefficient of $x$: $c_2 = 0$
- Coefficient of $x^2$: $c_3 = 0$

Only trivial solution exists.

**Answer**: Linearly **independent** ✓

This is the standard basis for $P_2$.

</details>

---

## Advanced Problems

### Problem 9: GATE-Style Problem
Let $A$ be a $3 \times 3$ matrix with $\det(A) = 5$. Are the columns of $A$ linearly independent?

<details>
<summary>Solution</summary>

**Key Theorem**: For a square matrix, columns are linearly independent if and only if $\det(A) \neq 0$.

Given: $\det(A) = 5 \neq 0$

**Answer**: Yes, the columns are linearly **independent**.

**Additional**: This also means:
- The matrix $A$ is invertible
- The rows are also linearly independent
- rank$(A) = 3$
- The null space contains only the zero vector

</details>

---

### Problem 10: Subset Independence
If $\{v_1, v_2, v_3, v_4\}$ is linearly independent, is $\{v_1, v_2\}$ linearly independent?

<details>
<summary>Solution</summary>

**Theorem**: If a set is linearly independent, then every subset is also linearly independent.

**Proof by contradiction**:
Suppose $\{v_1, v_2\}$ is linearly dependent.
Then: $c_1v_1 + c_2v_2 = 0$ with not all $c_i = 0$.

But then: $c_1v_1 + c_2v_2 + 0 \cdot v_3 + 0 \cdot v_4 = 0$

This would be a non-trivial solution for $\{v_1, v_2, v_3, v_4\}$, contradicting that it's linearly independent.

**Answer**: Yes, $\{v_1, v_2\}$ must be linearly **independent**.

</details>

---

### Problem 11: Extension Problem
$\{v_1, v_2\}$ is linearly independent in $\mathbb{R}^3$. If $v_3$ is not in span$\{v_1, v_2\}$, is $\{v_1, v_2, v_3\}$ linearly independent?

<details>
<summary>Solution</summary>

**Yes**, $\{v_1, v_2, v_3\}$ is linearly independent.

**Proof**:
Suppose $c_1v_1 + c_2v_2 + c_3v_3 = 0$.

**Case 1**: If $c_3 \neq 0$, then:
$$v_3 = -\frac{c_1}{c_3}v_1 - \frac{c_2}{c_3}v_2$$

This means $v_3 \in \text{span}\{v_1, v_2\}$, which contradicts the given condition.

**Case 2**: If $c_3 = 0$, then:
$$c_1v_1 + c_2v_2 = 0$$

Since $\{v_1, v_2\}$ is linearly independent, we must have $c_1 = c_2 = 0$.

Therefore, the only solution is $c_1 = c_2 = c_3 = 0$ (trivial solution).

**Answer**: Linearly **independent** ✓

This is the **Extension Theorem**.

</details>

---

### Problem 12: Function Independence
Are $f_1(x) = \sin x$, $f_2(x) = \cos x$ linearly independent?

<details>
<summary>Solution</summary>

**Method 1: Direct Test**
Suppose $c_1\sin x + c_2\cos x = 0$ for all $x$.

Evaluate at $x = 0$: $c_1 \cdot 0 + c_2 \cdot 1 = 0$ → $c_2 = 0$

Evaluate at $x = \frac{\pi}{2}$: $c_1 \cdot 1 + c_2 \cdot 0 = 0$ → $c_1 = 0$

Only trivial solution exists.

**Method 2: Wronskian**
$$W(\sin x, \cos x) = \begin{vmatrix} \sin x & \cos x \\ \cos x & -\sin x \end{vmatrix}$$

$$= \sin x \cdot (-\sin x) - \cos x \cdot \cos x$$

$$= -\sin^2 x - \cos^2 x = -1 \neq 0$$

Since Wronskian is non-zero, the functions are linearly independent.

**Answer**: Linearly **independent** ✓

</details>

---

### Problem 13: Matrix Space
In $M_{2 \times 2}$ (space of $2 \times 2$ matrices), are the following linearly independent?

$$A_1 = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}, \quad A_2 = \begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix}, \quad A_3 = \begin{bmatrix} 0 & 0 \\ 1 & 0 \end{bmatrix}, \quad A_4 = \begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix}$$

<details>
<summary>Solution</summary>

Set up: $c_1A_1 + c_2A_2 + c_3A_3 + c_4A_4 = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}$

$$c_1\begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix} + c_2\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix} + c_3\begin{bmatrix} 0 & 0 \\ 1 & 0 \end{bmatrix} + c_4\begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}$$

$$\begin{bmatrix} c_1 & c_2 \\ c_3 & c_4 \end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}$$

This gives: $c_1 = c_2 = c_3 = c_4 = 0$ (only trivial solution)

**Answer**: Linearly **independent** ✓

These form the **standard basis** for $M_{2 \times 2}$, which has dimension 4.

</details>

---

### Problem 14: Complex Numbers
Are $v_1 = \begin{bmatrix} 1 + i \\ 2 \end{bmatrix}$, $v_2 = \begin{bmatrix} 1 - i \\ 0 \end{bmatrix}$ linearly independent over $\mathbb{C}$?

<details>
<summary>Solution</summary>

Set up: $c_1\begin{bmatrix} 1 + i \\ 2 \end{bmatrix} + c_2\begin{bmatrix} 1 - i \\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$

This gives:
- $c_1(1 + i) + c_2(1 - i) = 0$ ... (1)
- $2c_1 = 0$ ... (2)

From (2): $c_1 = 0$

Substitute into (1): $c_2(1 - i) = 0$

Since $1 - i \neq 0$, we have $c_2 = 0$.

Only trivial solution exists.

**Answer**: Linearly **independent** ✓

**Determinant Check**:
$$\det\begin{bmatrix} 1+i & 1-i \\ 2 & 0 \end{bmatrix} = 0 - 2(1-i) = -2(1-i) = -2 + 2i \neq 0$$

</details>

---

## GATE Previous Year Style Problems

### Problem 15: MCQ
Which of the following sets is linearly independent?

(A) $\left\{\begin{bmatrix} 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 2 \\ 0 \end{bmatrix}\right\}$

(B) $\left\{\begin{bmatrix} 1 \\ 1 \end{bmatrix}, \begin{bmatrix} -1 \\ -1 \end{bmatrix}\right\}$

(C) $\left\{\begin{bmatrix} 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 2 \\ 1 \end{bmatrix}\right\}$

(D) $\left\{\begin{bmatrix} 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 2 \\ 4 \end{bmatrix}, \begin{bmatrix} 3 \\ 6 \end{bmatrix}\right\}$

<details>
<summary>Solution</summary>

**(A)**: $\begin{bmatrix} 2 \\ 0 \end{bmatrix} = 2\begin{bmatrix} 1 \\ 0 \end{bmatrix}$ → **Dependent**

**(B)**: $\begin{bmatrix} -1 \\ -1 \end{bmatrix} = -1\begin{bmatrix} 1 \\ 1 \end{bmatrix}$ → **Dependent**

**(C)**: Check determinant:
$$\det\begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix} = 1 - 4 = -3 \neq 0$$ → **Independent** ✓

**(D)**: 3 vectors in $\mathbb{R}^2$ → **Dependent** (more vectors than dimension)

**Answer: (C)**

</details>

---

### Problem 16: MCQ
If $v_1, v_2, v_3$ are linearly independent vectors in $\mathbb{R}^3$, which of the following is FALSE?

(A) $\{v_1, v_2\}$ is linearly independent
(B) $\{v_1, v_2, v_3\}$ spans $\mathbb{R}^3$
(C) $\{v_1, v_2, v_3, v_1 + v_2\}$ is linearly independent
(D) $v_1 \neq 0$

<details>
<summary>Solution</summary>

**(A)**: TRUE - Subset of independent set is independent

**(B)**: TRUE - 3 independent vectors in $\mathbb{R}^3$ form a basis, so they span $\mathbb{R}^3$

**(C)**: **FALSE** - Since $v_1 + v_2$ can be written as $1 \cdot v_1 + 1 \cdot v_2 + 0 \cdot v_3 + (-1)(v_1 + v_2) = 0$, this is a non-trivial linear combination. The set is dependent.

**(D)**: TRUE - If $v_1 = 0$, the set would be dependent

**Answer: (C)**

</details>

---

### Problem 17: MCQ
The maximum number of linearly independent vectors in $\mathbb{R}^4$ is:

(A) 3
(B) 4
(C) 5
(D) Infinite

<details>
<summary>Solution</summary>

The dimension of $\mathbb{R}^4$ is 4.

The maximum number of linearly independent vectors in an $n$-dimensional space is $n$.

Any set of more than 4 vectors in $\mathbb{R}^4$ must be linearly dependent.

**Answer: (B) 4**

</details>

---

### Problem 18: Numerical
Find the value of $k$ for which vectors $\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$, $\begin{bmatrix} 2 \\ 3 \\ 4 \end{bmatrix}$, $\begin{bmatrix} 3 \\ 4 \\ k \end{bmatrix}$ are linearly dependent.

<details>
<summary>Solution</summary>

Form matrix and compute determinant:
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 3 & 4 \\ 3 & 4 & k \end{bmatrix}$$

$$\det(A) = 1\begin{vmatrix} 3 & 4 \\ 4 & k \end{vmatrix} - 2\begin{vmatrix} 2 & 4 \\ 3 & k \end{vmatrix} + 3\begin{vmatrix} 2 & 3 \\ 3 & 4 \end{vmatrix}$$

$$= 1(3k - 16) - 2(2k - 12) + 3(8 - 9)$$

$$= 3k - 16 - 4k + 24 - 3$$

$$= -k + 5$$

For linear dependence: $\det(A) = 0$

$$-k + 5 = 0$$

$$k = 5$$

**Answer**: $k = 5$

**Verification**: When $k = 5$, notice that $\begin{bmatrix} 3 \\ 4 \\ 5 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} + \begin{bmatrix} 2 \\ 3 \\ 4 \end{bmatrix}$ - Not quite!

Let's verify: $1 + 2 = 3$ ✓, $2 + 3 = 5$ ✗

Actually the dependency is different. Let's find it from the matrix.

</details>

---

### Problem 19: True/False
If vectors $v_1, v_2, \ldots, v_n$ are linearly dependent, then one of them can be written as a linear combination of the others.

<details>
<summary>Solution</summary>

**TRUE**

**Proof**:
If vectors are linearly dependent, then:
$$c_1v_1 + c_2v_2 + \cdots + c_nv_n = 0$$

with at least one $c_i \neq 0$.

Without loss of generality, assume $c_1 \neq 0$.

Then we can solve for $v_1$:
$$v_1 = -\frac{c_2}{c_1}v_2 - \frac{c_3}{c_1}v_3 - \cdots - \frac{c_n}{c_1}v_n$$

Thus $v_1$ is a linear combination of the other vectors.

**Answer: TRUE**

</details>

---

### Problem 20: Application Problem
In a machine learning dataset, we have three features:
- $f_1$: Temperature in Celsius
- $f_2$: Temperature in Fahrenheit
- $f_3$: Humidity

Are these features linearly independent? Why or why not?

<details>
<summary>Solution</summary>

**NO**, these features are linearly **dependent**.

**Reason**: Temperature in Fahrenheit and Celsius are related by:
$$f_2 = \frac{9}{5}f_1 + 32$$

This can be rewritten as:
$$f_2 - \frac{9}{5}f_1 = 32$$

Or in terms of centered variables (subtracting means):
$$f_2 - \frac{9}{5}f_1 = \text{constant}$$

This shows a linear dependency between $f_1$ and $f_2$.

**Implication**: In machine learning, having linearly dependent features leads to:
- **Multicollinearity** in linear regression
- **Singular or near-singular covariance matrices**
- **Redundant information** that doesn't improve model performance
- **Numerical instability** in optimization

**Solution**: Remove one of the temperature features before training the model.

</details>

---

## Challenge Problems

### Problem 21: Proof Problem
Prove that if $\{v_1, v_2, \ldots, v_n\}$ is linearly independent and $w \notin \text{span}\{v_1, v_2, \ldots, v_n\}$, then $\{v_1, v_2, \ldots, v_n, w\}$ is linearly independent.

### Problem 22: Eigenvalue Connection
If all eigenvalues of a matrix $A$ are non-zero, prove that the columns of $A$ are linearly independent.

### Problem 23: Orthogonal Vectors
Prove that any set of non-zero orthogonal vectors is linearly independent.

### Problem 24: Dimension Theory
If $V$ is a vector space with $\dim(V) = n$ and $S = \{v_1, v_2, \ldots, v_n\}$ spans $V$, prove that $S$ is linearly independent.

### Problem 25: Polynomial Roots
Show that if $r_1, r_2, \ldots, r_n$ are distinct real numbers, then the exponential functions $\{e^{r_1x}, e^{r_2x}, \ldots, e^{r_nx}\}$ are linearly independent.

---

## Quick Practice Exercises

Test these mentally for speed:

1. $\left\{\begin{bmatrix} 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \end{bmatrix}\right\}$ → **Dependent** (zero vector)

2. $\left\{\begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \\ 5 \end{bmatrix}\right\}$ → **Independent** (single non-zero vector)

3. Four vectors in $\mathbb{R}^3$ → **Dependent** (more than dimension)

4. $\left\{\begin{bmatrix} 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \end{bmatrix}\right\}$ → **Independent** (standard basis)

5. $\{1, x, x^2\}$ in $P_3$ → **Independent** (different degrees)

---

## Tips for GATE Exam

### Quick Recognition Patterns
1. **Zero vector present** → Dependent (immediate)
2. **More vectors than dimensions** → Dependent (immediate)
3. **One vector is scalar multiple** → Dependent (check ratios)
4. **Obvious pattern** (like $v_3 = v_1 + v_2$) → Dependent

### Calculation Priorities
1. **For 2×2**: Use determinant (5 seconds)
2. **For 3×3**: Use determinant if simple, else row reduce
3. **For larger**: Always row reduce

### Time Management
- Don't compute if you can recognize
- Use properties before calculations
- Partial row reduction is often enough
- Look for zeros to simplify determinant

### Common Tricks in MCQs
- Options with zero vector → usually wrong
- More vectors than dimension → dependent
- Orthogonal non-zero vectors → independent
- Standard basis vectors → independent

---

## Summary Checklist

✅ Can you define linear independence?
✅ Can you test 2-3 vectors quickly?
✅ Do you know when to use determinants?
✅ Can you row reduce efficiently?
✅ Can you recognize immediate dependencies?
✅ Do you understand geometric meaning?
✅ Can you find actual dependency relations?
✅ Can you handle parametric problems?
✅ Do you know the relationship with span and basis?
✅ Can you solve MCQs within 1-2 minutes?
