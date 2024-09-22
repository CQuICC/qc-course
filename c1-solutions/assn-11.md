## Assignment 11

**Q1**: Suppose M out of N elements are marked in an array. How many Grover's iterations will be needed?

**Options**:
1. $O\left( \frac{N}{M} \right)$
2. $O\left( \sqrt{\frac{N}{M}} \right)$
3. $O\left( \frac{\sqrt{N}}{M} \right)$
4. $O\left( \sqrt{N} - M \right)$

**Solution**:

Recall that the order of the number of rotations needed to reach the state $|\beta\rangle$ in the state $|\psi\rangle = \sqrt{\frac{N - M}{N}}|\alpha\rangle + \sqrt{\frac{M}{N}}|\beta\rangle$ is inversely proportional to the angle $\theta$ (here, $\sin{\frac{\theta}{2}} = \sqrt{\frac{M}{N}}$). Since $\theta$ follows $\Omega\left( \sqrt{\frac{M}{N}} \right)$ (Refer to notes of module 10), the number of rotations needed will be $O\left( \sqrt{\frac{N}{M}} \right)$.

**Answer**:

$O\left( \sqrt{\frac{N}{M}} \right)$

---

**Q2**: Suppose M out of N elements are marked in an array, how much is the rotation in each of the Grover iterations?

**Note:** Options are not in $O(\cdot)$ notation. So do include constants.

**Options**:
1. $\sin^{-1} \left( \sqrt{\frac{M}{N}} \right)$
2. $2 \sin^{-1} \left( \sqrt{\frac{M}{N}} \right)$
3. $\sin^{-1} \left( \frac{M}{N} \right)$
4. $\sqrt{\frac{M}{N}}$

**Solution**:

For a state defined as $|\psi\rangle = \sqrt{\frac{N - M}{N}}|\alpha\rangle + \sqrt{\frac{M}{N}}|\beta\rangle$ (where $|\beta\rangle$ is the state we want to get closer to using the Grover's search), The half angle is defined as $\sin^{-1} \left( \sqrt{\frac{M}{N}} \right)$. Therefore, the rotation caused by the Grover's search will be twice of the half angle, i.e., $2 \sin^{-1} \left( \sqrt{\frac{M}{N}} \right)$

**Answer**:

$2 \sin^{-1} \left( \sqrt{\frac{M}{N}} \right)$

---

**Q3**: Given a state $|\psi\rangle = \alpha|G\rangle|1\rangle + \beta|B\rangle|0\rangle$, one needs to amplify the amplitudes corresponding to $\lvert G \rangle$. How many iterations will be needed?

**Options**:
1. $O\left( \frac{1}{|\alpha^2|} \right)$
2. $O\left( \alpha \right)$
3. $O\left( \frac{1}{|\alpha|} \right)$
4. $O\left( \alpha^2 \right)$

**Solution**:

Following the solution for Q1, the state $|G\rangle$ is similar to the state $|\beta\rangle$, this means $\alpha$ can be looked at as $\sqrt{\frac{M}{N}}$. The solution can then be written as $O\left( \frac{1}{|\alpha|} \right)$. (Refer to solution 1)

**Answer**:

$O\left( \frac{1}{|\alpha|} \right)$

---

**Q4**: Which of the following is one of the eigen values of Grover’s reflection operator? ($\theta_0$ denoted is the initial angle between the initial state and the state of marked elements)

**Option**:
1. $e^{2i\theta_0}$
2. $e^{-i\theta_0}$
3. $e^{4i\theta_0}$
4. $e^{-4i\theta_0}$

**Solution**:

The Grover reflection operator in the basis of $|G\rangle|1\rangle$ and $|B\rangle|0\rangle$ is given by the following matrix (refer to notes from Module 11):
$$
\begin{pmatrix}
\cos(2\theta_0) & -\sin(2\theta_0) \\
\sin(2\theta_0) & \cos(2\theta_0)
\end{pmatrix}
$$
This has the eigenvalues of $e^{2i\theta_0}$ and $e^{-2i\theta_0}$.

**Answer**:

$e^{2i\theta_0}$

---

**Q5**: For a state $|\psi\rangle = \alpha|G\rangle|1\rangle + \beta|B\rangle|0\rangle$, what is the rotation angle in each of the Grover’s iteration?

**Options**:
1. $2\sin^{-1}|\alpha|$
2. $\sin^{-1}|\alpha|$
3. $\sin^{-1}\frac{1}{|\alpha|}$
4. $\sin^{-1}\frac{1}{|\alpha|^2}$

**Solution**:

Following the same process as Q2, For a state defined as $|\psi\rangle = \alpha|G\rangle|1\rangle + \beta|B\rangle|0\rangle$, The half angle is defined as $\sin^{-1}|\alpha|$. Therefore, the rotation caused by the Grover's search will be twice of the half angle, i.e., $2\sin^{-1}|\alpha|$

**Answer**:

$2\sin^{-1}|\alpha|$

---

**Q6**: Suppose $A = \lambda I$ (scalar multiple of identity), what is (k), the condition number of A?

**Options**:
1. 0
2. $\infty$
3. 1
4. 0.5

**Solution**:

the condition number $k$ of a matrix $A$ is defined as the ratio of the largest eigenvalue to the smallest nonzero eigenvalue of $A$. For the case $A = \lambda I$, all the eigenvalues are equal to $\lambda$. Therefore, $k = \frac{\lambda}{\lambda} = 1$

**Answer**:

1

---

**Q7**: Suppose a matrix A is not Hermitian. How to modify the system of equations $A|x\rangle = |b\rangle$ for solving HHL?

**Options**:

1. $$A' = \begin{pmatrix} 0 & A^{T} \\ A & 0  \end{pmatrix};  \quad b' = \begin{pmatrix} b \\ 0 \end{pmatrix},  \text{ solve, } A'|x\rangle = |b'\rangle$$
2. $$A' = \frac{1}{2}\left(A + A^T\right), \text{ solve, } A'|x\rangle = |b\rangle$$
3. $$A' = AA^T, \text{ solve, } A'|x\rangle = |b\rangle$
4. $$A' = \left( AA^T \right)^{\frac{1}{2}}, \text{ solve, } A'|x\rangle = |b\rangle$$

**Solution**:

To make this work we need to convert the matrix $A$ to a hermitian one without changing the solution in the process. The following option is the only valid option that satisfies this condition. The other options do convert $A$ to a hermitian matrix but do not preserve the original systems solution.

$$
A' = \begin{pmatrix} 0 & A^{T} \\ A & 0  \end{pmatrix};  \quad b' = \begin{pmatrix} b \\ 0 \end{pmatrix},  \text{ solve, } A'|x\rangle = |b'\rangle
$$


**Answer**:

$$
A' = \begin{pmatrix} 0 & A^{T} \\ A & 0  \end{pmatrix};  \quad b' = \begin{pmatrix} b \\ 0 \end{pmatrix},  \text{ solve, } A'|x\rangle = |b'\rangle
$$

---

**Q8**: Suppose probability amplification is not performed. What is the success probability of a single run of HHL in terms of condition number k?

**Options**:
1. $\frac{1}{k^2}$
2. $\frac{1}{k}$
3. $\frac{1}{\sqrt{k}}$
4. $O\left(1\right)$ constant

**Solution**:

For the case where probability amplification is not performed, the success probability of a single run of HHL in terms of condition number k is given by $P_{\text{success}} \propto \frac{1}{k^2}$

**Answer**:

$\frac{1}{k^2}$

---
**Q9**: Suppose probability amplification is performed. What is the success probability of a single run of HHL in terms of condition number k?

**Options**:
1. $\frac{1}{k^2}$
2. $\frac{1}{k}$
3. $\frac{1}{\sqrt{k}}$
4 $O\left(1\right)$ constant

**Solution**:

For the case where probability amplification is performed, the success probability of a single run of HHL in terms of condition number k is given by $P_{\text{success}} \propto \sqrt{\frac{1}{k^2}} \propto \frac{1}{k} $

**Answer**:

$\frac{1}{k}$

---
**Q10**: How many Grover’s iterations are needed for amplitude amplification of HHL?

**Options**:
1. $O\left(k\right)$
2. $O\left(k^2\right)$
3. $O\left(1\right)$
4 $O\left(2^k\right)$

**Solution**:

1. Initial Success Probability: Without amplitude amplification, the initial success probability of the HHL algorithm is:
$$P_{\text{success}} \propto \frac{1}{k^2}$$
where $k$ is the condition number of the matrix $A$.

2. Number of Grover Iterations: The number of Grover iterations $N_G$ needed to amplify the success probability to a value near 1 is given by:
$$N_G = \mathcal{O}\left(\frac{1}{\sqrt{P_{\text{success}}}}\right)$$

3. Substitute $P_{\text{success}}$:
$$N_G = \mathcal{O}\left(\frac{1}{\sqrt{\frac{1}{k^2}}}\right)$$

4. Simplify:
$$N_G = \mathcal{O}(k)$$

Thus, the number of Grover iterations required for amplitude amplification in the HHL algorithm is of the order $\mathcal{O}(k)$.

**Answer**:

$O\left(k\right)$

---
