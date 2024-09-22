## Assignment 1

**Q1:** Find the values of $a$ and $b$ so that the inner product of the vectors $|\psi\rangle = \frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle$ and $|\phi\rangle = a|0\rangle + b|1\rangle$ is $\frac{1+\sqrt2}{\sqrt6}$.

**Options**:
- $a = 1$ and $b = 1$
- $a = \frac{1}{\sqrt2}$ and $b = \frac{1}{\sqrt2}$
- $a = \frac{1}{\sqrt2}$ and $b = \frac{1}{2}$
- None of the above

**Solution:**
The inner product of two vectors $|\psi\rangle$ and $|\phi\rangle$ is given by $\langle \psi | \phi \rangle = \frac{2}{3} a + \frac{1}{3} b$. We are given that this is equal to $\frac{1+\sqrt2}{\sqrt6}$.

$$
\frac{2}{3} a + \frac{1}{3} b = \frac{1+\sqrt2}{\sqrt6}
$$

Additionally we know that $a^2 + b^2 = 1$ since $|\phi\rangle$ is a normalized vector. We can solve these two equations to find the values of $a$ and $b$ as

**Answer**: $a = \frac{1}{\sqrt2}$ and $b = \frac{1}{\sqrt2}$

---

**Q2**: Which of the following pairs of vectors are mutually orthogonal?

**Options**:
- $ \left( \sqrt{\frac{6}{19}} |0\rangle + \sqrt{\frac{13}{19}} |1\rangle, \sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle \right) $
- $ \left( \sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle, -\sqrt{\frac{13}{19}} |0\rangle - \sqrt{\frac{6}{19}} |1\rangle \right) $
- $ \left( \sqrt{\frac{6}{19}} |0\rangle + \sqrt{\frac{13}{19}} |1\rangle, -\sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle \right) $
- $ \left( \sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle, -\sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle \right) $

**Solution:**
Calculating inner products of each pair, the pair that satisfies $\langle \psi | \phi \rangle = 0$ are:

**Answer:**
$ \left( \sqrt{\frac{6}{19}} |0\rangle - \sqrt{\frac{13}{19}} |1\rangle, -\sqrt{\frac{13}{19}} |0\rangle - \sqrt{\frac{6}{19}} |1\rangle \right) $

---

**Q3:** What is $H^{13}$, where $H$ is the Hadamard matrix $H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$?

**Options**:
- $\begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$
- $\begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & -\frac{1}{2} \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$

**Solution:**
The Hadamard matrix has the property that $H^2 = I$, meaning it squares to the identity matrix. Since $H^{13} = H^{12} \cdot H = I^6 \cdot H = H$, the result is just $H$ itself.
Thus, the answer is $\frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$, which matches option (a).

**Answer:** $\begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix}$

---

**Q4:** A vector $|u\rangle = \begin{pmatrix} \frac{3}{5} \\ \frac{4}{5} \end{pmatrix}$ is acted on by the Hadamard matrix. What is the value of $| \langle 0 | H | u \rangle |^2$?

**Options**:
- 0.98
- 0.02
- 0.36
- 0.8

**Solution:**
Apply the Hadamard matrix to the vector $|u\rangle$, then compute the overlap with $|0\rangle$. The Hadamard matrix is $H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$.

Step 1: Apply $H$ to $|u\rangle$:

$$
H|u\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} \frac{3}{5} \\ \frac{4}{5} \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} \frac{7}{5} \\ -\frac{1}{5} \end{pmatrix}
$$


Step 2: Compute $\langle 0 | H | u \rangle = \frac{7}{5\sqrt{2}}$.

Step 3: The probability is $| \langle 0 | H | u \rangle |^2 = \left( \frac{7}{5\sqrt{2}} \right)^2 = 0.98$.

**Answer:** 0.98

---

**Q5:** If $A$ and $B$ are Hermitian, which of the following is/are Hermitian?

**Options**:
- AB + BA
- $i(AB - BA)$
- AB - BA
- AB

**Solution:**
- The sum of two Hermitian operators $A$ and $B$ is Hermitian if $A = B^\dagger$. Here, $AB + BA$ is Hermitian.
- The commutator $i(AB - BA)$ is Hermitian because multiplying the anti-Hermitian part by $i$ gives a Hermitian operator.
- $AB - BA$ is anti-Hermitian, not Hermitian.
- $AB$ is not necessarily Hermitian.

**Answer:** AB + BA, $i(AB - BA)$

---

**Q6:** What are the possible values of the complex variable $x$, for which the vector $|\psi\rangle = \begin{pmatrix} \frac{1-i}{\sqrt{2}} \\ x \end{pmatrix}$ is normalized?

**Options**:
- $\frac{i+1}{4}$
- $-\frac{i}{\sqrt{2}}$
- $\frac{i-1}{\sqrt{2}}$
- 0

**Solution:**
For $|\psi\rangle$ to be normalized, $\langle \psi | \psi \rangle = 1$, meaning the sum of the squares of the magnitudes of the components must be 1.

$$
\left| \frac{1-i}{\sqrt{2}} \right|^2 + |x|^2 = 1
$$

We can see $\frac{1-i}{\sqrt2} = e^{-i\pi/4}$, so the first term is 1. The second term is $|x|^2$. Thus, $x = 0$ is the correct value.

**Answer:** 0

---

**Q7:** Which of these are unitary matrices?

**Options**:
- $\begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/4} \end{pmatrix}$
- $\begin{pmatrix} \frac{1}{\sqrt{2}} & -\frac{i}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & \frac{i}{\sqrt{2}} \end{pmatrix}$
- $\begin{pmatrix} \frac{1}{\sqrt{2}} & 0 \\ \frac{1}{\sqrt{2}} & e^{i\pi/4} \end{pmatrix}$
- $\begin{pmatrix} e^{-\pi i / 3} & 0 \\ 0 & e^{\pi i / 3} \end{pmatrix}$

**Solution:**
A matrix $U$ is unitary if $U^\dagger U = I$.
- Option (- is unitary because its diagonal elements are complex exponentials.
- Option (- is unitary because it represents a valid rotation (check orthogonality and normalization).
- Option (- is not unitary
- Option (- is unitary because its diagonal elements are also complex exponentials.

**Answer:** a), b), d)

------


**Q8**: Which of the following correspond to outer product representations of the matrix $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} $?

**Options**:
- $|0\rangle \langle 0| + |1\rangle \langle 1|$
- $|0\rangle \langle 1| + |1\rangle \langle 0|$
- $|+\rangle \langle +| - |-\rangle \langle -|$
- $|+\rangle \langle +| + |-\rangle \langle -|$

**Solution:**
$|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$, $|+\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}$, and $|-\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}$.

Therefore $|0\rangle \langle 1| = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}$ and $|1\rangle \langle 0| = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.

**Answer:** One can trivially check this way that the correct options are $|0\rangle \langle 1| + |1\rangle \langle 0|$ and $|+\rangle \langle +| - |-\rangle \langle -|$.

---


**Q9**: Which of the following matrices are Hermitian?

**Options**:
- $\begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$
- $\begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}$
- $\begin{pmatrix} 1 & i \\ -i & -1 \end{pmatrix}$

**Solution:**
A Hermitian matrix satisfies $A = A^\dagger$.

**Answer:**
$$
\begin{pmatrix} 0 & i \\ -i & 0 \end{pmatrix} \quad \text{and} \quad \begin{pmatrix} 1 & i \\ -i & -1 \end{pmatrix}
$$

---

**Q10:** Which of the following are eigenvectors of the matrix $H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$?

**Options**:
- $\frac{1}{\sqrt{2} + \sqrt{2}} (|0\rangle + |+\rangle)$
- $\frac{\sqrt{2} + \sqrt{2}}{2} |0\rangle + \frac{\sqrt{2} - \sqrt{2}}{2} |1\rangle$
- $\frac{\sqrt{2} + \sqrt{2}}{2} |0\rangle - \frac{\sqrt{2} - \sqrt{2}}{2} |1\rangle$
- $\frac{1}{\sqrt{2} + \sqrt{2}} (|1\rangle - |-\rangle)$

**Solution**:
We need to determine which vectors are eigenvectors of the given matrix $H$. The matrix has eigenvalues $\pm 1$, and corresponding eigenvectors are typically combinations of $|0\rangle$ and $|1\rangle$.

- $\frac{1}{\sqrt{2} + \sqrt{2}} (|0\rangle + |+\rangle)$: This simplifies to an eigenvector corresponding to eigenvalue 1.
- $\frac{\sqrt{2} + \sqrt{2}}{2} |0\rangle + \frac{\sqrt{2} - \sqrt{2}}{2} |1\rangle$: This simplifies to the correct eigenvector form for the matrix $H$.
- $\frac{\sqrt{2} + \sqrt{2}}{2} |0\rangle - \frac{\sqrt{2} - \sqrt{2}}{2} |1\rangle$: This is also an eigenvector.
- $\frac{1}{\sqrt{2} + \sqrt{2}} (|1\rangle - |-\rangle)$: This corresponds to the eigenvalue $-1$.

Thus, the correct answers are:
- $\frac{1}{\sqrt{2} + \sqrt{2}} (|0\rangle + |+\rangle)$
- $\frac{\sqrt{2} + \sqrt{2}}{2} |0\rangle + \frac{\sqrt{2} - \sqrt{2}}{2} |1\rangle$
- $\frac{1}{\sqrt{2} + \sqrt{2}} (|1\rangle - |-\rangle)$
