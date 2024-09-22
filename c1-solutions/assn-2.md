## Assignment 2

**Q1**: Which vectors correspond to valid states of a four-dimensional quantum system?

**Options**:
- $\frac{1}{\sqrt{2}}(1, 0, 0, 1)$
- $\frac{1}{2}(1, i, -i, 1)$
- $\frac{1}{2}(0, \sqrt{3}, 1, 0)$
- $\frac{1}{\sqrt{2}}(1, i, -i, 1)$

**Solution**: Valid quantum states must be normalized (i.e., have a total probability of 1). For a vector $(a, b, c, d)$, this means $|a|^2 + |b|^2 + |c|^2 + |d|^2 = 1$.

**Answer**: Therefore options a), b), c) are correct

---

**Q2**: Suppose a quantum state is transformed via a phase operator $P = (|0\rangle\langle0| + e^{i\phi}|1\rangle\langle1|)$. What angle $\phi$ results in zero probability of obtaining $|+\rangle$ after the gate's action?

**Options**:
- $\phi = 0$
- $\phi = \pi/2$
- $\phi = \pi/4$
- $\phi = \pi$

**Solution**: The $|+\rangle$ state is $\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$. After applying P, to some state $\alpha|0\rangle + \beta|1\rangle$, we get:

$P(\alpha|0\rangle + \beta|1\rangle) = \alpha|0\rangle + e^{i\phi}\beta|1\rangle$

The only way to get a zero probability in $|+\rangle$ is if we make sure our state is $|-\rangle$. This means $\alpha = \beta$ and $e^{i\phi} = -1$

**Answer**: Thus, the correct answer is d) $\phi = \pi$.

---

**Q3**: Given a qubit in state $|q\rangle = \alpha|0\rangle + \beta|1\rangle$, what are the probabilities of obtaining $|+\rangle$ and $|-\rangle$ when measured in the $\{|+\rangle, |-\rangle\}$ basis?

**Options**:
- $P(|+\rangle) = |\alpha + \beta|$, $P(|-\rangle) = |\alpha - \beta|$
- $P(|+\rangle) = \frac{|\alpha + \beta|^2}{2}$, $P(|-\rangle) = \frac{|\alpha - \beta|^2}{2}$
- $P(|+\rangle) = \frac{|\alpha + \beta|^2}{2}$, $P(|-\rangle) = |\alpha - \beta|^2$
- $P(|+\rangle) = |\alpha + \beta|^2$, $P(|-\rangle) = \frac{|\alpha - \beta|^2}{2}$

**Solution**: The probability of measuring $|+\rangle$ is $|\langle+|q\rangle|^2 = |\frac{1}{\sqrt{2}}(\alpha + \beta)|^2 = \frac{|\alpha + \beta|^2}{2}$. Similarly, for $|-\rangle$, we get $\frac{|\alpha - \beta|^2}{2}$. Thus, the correct answer is b).

---

**Q4**: Which relation is correct for the spin operators $S_x$, $S_y$, and $S_z$?

**Options**:
- $S_xS_y - S_yS_x = 0$
- $S_xS_y - S_yS_x = -2iS_z$
- $S_xS_y - S_yS_x = 2iS_z$
- $S_xS_y + S_yS_x = 0$

**Solution**: The correct commutation relation for spin operators is $S_xS_y + S_yS_x = 0$ and $S_xS_y - S_yS_x = 2iS_z$, as can be trivially verified by multiplying the matrices.

---

**Q5**: For the state $|\phi\rangle = (\frac{1-\sqrt2i}{4})|0\rangle - (\frac{3-2i}{4})|1\rangle$, what is the probability of obtaining $|+\rangle$ when measured in the $\{|+\rangle, |-\rangle\}$ basis?

**Options**:
- $\frac{11}{32}$
- $\frac{7}{16}$
- $\frac{5-2\sqrt{2}}{32}$
- $\frac{5-2\sqrt{2}}{16}$

**Solution**: From a previous question, we know that the probability of measuring $|+\rangle$ is $|\langle+|\phi\rangle|^2 = |\frac{1}{\sqrt{2}}(\alpha + \beta)|^2$.

**Answer**: Substituting the values, we get $\frac{5-2\sqrt{2}}{16}$.

---

**Q6**: Which matrix represents the $S_z$ operator in the $\{|+\rangle, |-\rangle\}$ basis?

**Options**:
- $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$
- $\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$
- $\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$

**Solution**: In the $\{|0\rangle, |1\rangle\}$ basis, $S_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$. To change basis, we use the transformation $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$ and $|-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$. Applying this transformation, we get $S_z = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ in the $\{|+\rangle, |-\rangle\}$ basis

**Answer**: Thus, the correct answer is d).

---

**Q7**: If $|\psi\rangle = \begin{pmatrix} x \\ 4x \end{pmatrix}$, what is the probability of measuring $|0\rangle$?

**Options**:
- 0.059
- 0.970
- 0.941
- 0.242

**Solution**: The probability of measuring $|0\rangle$ is $|\langle0|\psi\rangle|^2 = |x|^2$. To find $x$, we normalize $|\psi\rangle$:

$|x|^2 + |4x|^2 = 1$\
$17|x|^2 = 1$\
$|x|^2 = \frac{1}{17} \approx 0.059$

**Answer**: Therefore probability of measuring $|0\rangle$ is 0.059.

---

**Q8**: Consider the states $|+i\rangle = \frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle)$ and $|-i\rangle = \frac{1}{\sqrt{2}}(|0\rangle - i|1\rangle)$. Which statements are true?

**Options**:
- The states are eigenstates of the $S_x$ operator.
- The states are eigenstates of the $S_y$ operator.
- When the $S_x$ operator is measured on $|+i\rangle$, both outcomes are equally likely.
- When the $S_y$ operator is measured on $|+i\rangle$, both outcomes are equally likely.

**Solution**: One can use the relations from before $S_x = \frac{1}{2}\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ and $S_y = \frac{1}{2}\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}$ to verify that $|\pm i\rangle$ is an eigenstate of $S_y$ and when measured via $S_x$, both outcomes are equally likely.

**Answer**: Thus, the correct answers are b) and c).

---

**Q9**: The normalized form of $|-\rangle + |+i\rangle$ is $\alpha|0\rangle + \beta|1\rangle$. What are $\alpha$ and $\beta$?

**Options**:
- $\alpha = \frac{2}{\sqrt{3}}$, $\beta = \frac{i-1}{\sqrt{6}}$
- $\alpha = \frac{1}{\sqrt{3}}$, $\beta = \frac{2}{\sqrt{3}}$
- $\alpha = \frac{2}{\sqrt{3}}$, $\beta = \frac{i+1}{\sqrt{6}}$
- $\alpha = \frac{1}{\sqrt{2}}$, $\beta = \frac{1}{\sqrt{2}}$

**Solution**: $|-\rangle + |+i\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle) + \frac{1}{\sqrt{2}}(|0\rangle + i|1\rangle) = \sqrt{2}|0\rangle + (i-1)\frac{1}{\sqrt{2}}|1\rangle$

Normalizing: $\sqrt{2 + |i-1|^2} = \sqrt{3}$

So, $\alpha = \frac{\sqrt 2}{\sqrt{3}}$, $\beta = \frac{i-1}{\sqrt{6}}$. The correct answer is a).

---

**Q10**: If U and V are unitary operators, which statements are true?

**Options**:
- UV is a unitary operator.
- The eigenvalues of U and V are all real.
- The eigenvalues of U and V are complex in general.
- U + V is a unitary operator.

**Solution**: For unitary operators:
1) The product of unitary operators is unitary: $(UV)^\dagger(UV) = V^\dagger U^\dagger UV = V^\dagger V = I$
2) Eigenvalues have magnitude 1 but can be complex: $e^{i\theta}$
3) The sum of unitary operators is not necessarily unitary

Thus, options a) and c) are correct.