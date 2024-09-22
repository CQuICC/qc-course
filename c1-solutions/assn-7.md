## Assignment 7

**Q1**: Let $\{|0\rangle, |1\rangle, . . . , |N − 1\rangle\}$ denote an orthonormal basis for an N-dimensional complex linear vector space. Recall that the Quantum Fourier Transform (QFT) transforms the states in this basis to the set $\{|\tilde{0}\rangle, |\tilde{1}\rangle, . . . , |\tilde{N − 1}\rangle\}$ according to the formula:

$$
|\tilde{k}\rangle = \frac{1}{\sqrt{N}} \sum_{j=0}^{N-1} e^{2\pi i jk/N} |j\rangle, \forall k = 0, 1, . . . , N − 1
$$


Which of the following statements about the QFT are true?

**Options**:
- The QFT simply permutes the vectors of the orthonormal basis.
- The QFT transforms the original orthonormal basis into a different orthonormal basis.
- The QFT is a unitary transformation, which can represented as a $N × N$ unitary matrix.
- The QFT is a unitary transformation, which can represented as a $2^N × 2^N$ unitary matrix.

**Solution**: The QFT is a unitary transformation that maps the original orthonormal basis to a different orthonormal basis. It is represented as an $N × N$ unitary matrix.

See [here](../../mod8/qpe.ipynb) for the unitary representation of QFT

**Answer**:
- The QFT transforms the original orthonormal basis into a different orthonormal basis.
- The QFT is a unitary transformativon, which can be represented as an N × N unitary matrix.

---

**Q2**: Consider the states $\{|\tilde{0}\rangle, |\tilde{1}\rangle, . . . , |\tilde{N − 1}\rangle\}$ obtained via performing a QFT on the orthonormal basis $\{|0\rangle, |1\rangle, . . . , |N − 1\rangle\}$. Which of the following statements describe correctly the properties of the Fourier transformed states?

**Options**:
- All states $|\tilde{k}\rangle$  are uniform superpositions of the original basis states in the set $\{|0\rangle, |1\rangle, . . . , |N − 1\rangle\}$ for all values of $k \in \{0, 1, . . . , N − 1\}$
- Only the state $|\tilde{0}\rangle$ is a uniform superposition of the original basis states in the set $\{|0\rangle, |1\rangle, . . . , |N − 1\rangle\}$
- The states $|\tilde{k}\rangle$ satisfy $\langle\tilde{j}|\tilde{k}\rangle = \delta_{j,k}$ for all values of $j, k \in \{0, 1, . . . , N − 1\}$
- The states $|\tilde{k}\rangle$ satisfy $\langle\tilde{j}|\tilde{k}\rangle = \frac{1}{N}\delta_{j,k}$

**Solution**: The states $|\tilde{k}\rangle$ are uniform superpositions of the original basis states for all values of $k \in \{0, 1, . . . , N − 1\}$ as can be seen from the expression of the QFT. They satisfy $\langle\tilde{j}|\tilde{k}\rangle = \delta_{j,k}$, which means they are orthogonal to each other.

**Answer**:
- All states $|\tilde{k}\rangle$  are uniform superpositions of the original basis states in the set $\{|0\rangle, |1\rangle, . . . , |N − 1\rangle\}$ for all values of $k \in \{0, 1, . . . , N − 1\}$
- The states $|\tilde{k}\rangle$ satisfy $\langle\tilde{j}|\tilde{k}\rangle = \delta_{j,k}$ for all values of $j, k \in \{0, 1, . . . , N − 1\}$

---

**Q3**: Recall the quantum cricuit that implements the QFT on an n-qubit space.

**Options**:
- The QFT circuit needs $O(2^n)$
- The QFT circuit needs $O(n^2)$
- The QFT circuit can be decomposed as a tensor product of single-qubit unitary gates.
- The final n-qubit state after the QFT circuit can be written as a tensor product of n single-qubit states.

**Solution**: For each qubit we apply successively $n, n-1, \ldots, 1$ gates followed by swaps. This gives a total of $n + (n-1) + \ldots + 1 = O(n^2)$ gates. The final representation as a product of single-qubit states is as

$$
\frac{1}{\sqrt{2^n}}
  \left(|0\rangle + e^{\frac{2\pi i}{2}x} |1\rangle\right)   \otimes
  \left(|0\rangle + e^{\frac{2\pi i}{2^2}x} |1\rangle\right)   \otimes
  \ldots  \otimes
  \left(|0\rangle + e^{\frac{2\pi i}{2^{n-1}}x} |1\rangle\right)
  \otimes
  \left(|0\rangle + e^{\frac{2\pi i}{2^n}x} |1\rangle\right)
$$

**Answer**:
- The QFT circuit needs $O(n^2)$
- The final n-qubit state after the QFT circuit can be written as a tensor product of n single-qubit states.

---

**Q4**: Which of the following single-qubit gates belong to the set of phase gates that are used in the QFT circuit?

**Options**:
- The Hadamard gate: $H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$
- The S gate: $S = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}$
- The X gate: $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
- The T gate: $T = \begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/4} \end{pmatrix}$

**Solution**: The QFT circuit uses Hadamard gates for creating superpositions and phase gates (S and T) for implementing relative phases. The X gate (NOT gate) is not typically used in the QFT circuit.

**Answer**:
- The Hadamard gate
- The S gate
- The T gate

---

**Q5**: Consider the following 4 × 4 matrix.

$$
U = \frac{1}{2}\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & i & -1 & * \\
1 & -1 & 1 & -1 \\
1 & * & -1 & i
\end{pmatrix}
$$​

**Solution**: The two-qubit QFT matrix is:

$$U = \frac{1}{2}\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & i & -1 & -i \\
1 & -1 & 1 & -1 \\
1 & -i & -1 & i
\end{pmatrix}$$

Comparing this with the given matrix, we can identify the missing entries. You can derive this trivially from the $N$ qubit unitary matrix for QFT as mentioned in the [QPE notebook](../../mod8/qpe.ipynb).

**Answer**: The * entries should be -i and i respectively.

---

**Q6**: Identify the gates U, V in the given 3-qubit QFT circuit.

(refer to assignment for image)

**Options**:
- U = H, V = S
- U = S, V = T
- U = T, V = S
- U = S, V = H

**Solution**: In the QFT circuit, controlled phase gates of increasing precision are used. The S gate provides a π/2 phase shift, while the T gate provides a π/4 phase shift. These correspond to the required controlled phase gates in the 3-qubit QFT circuit.

**Answer**: U = S, V = T

---

**Q7**: Let $|u\rangle$ denote the eigenstate of a unitary matrix U corresponding to eigenvalue $λ_u$. Which of the following statements are correct?

**Options**:
- λ is purely imaginary.
- $λ = e^{2πiφ_u}$, where $0 ≤ φ < 1$ is a phase angle.
- $U^t|u\rangle = \lambda^t|u\rangle$, for any t.
- $U^t|u\rangle = \lambda^t|u\rangle$, only for even values of t.

**Solution**: For a unitary matrix, eigenvalues have magnitude 1, so they can be expressed as $e^{2πiφ_u}$. The eigenvalue equation $U|u\rangle = \lambda|u\rangle$ can be applied repeatedly, leading to $U^t|u\rangle = \lambda^t|u\rangle$ for any integer t.

**Answer**:
- $λ = e^{2πiφ_u}$, where $0 ≤ φ < 1$ is a phase angle.
- $U^t|u\rangle = \lambda^t|u\rangle$, for any t.

---

**Q8**: Given a unitary matrix W = UV, which statements about its inverse are correct?

**Options**:
- $W^{-1} = V^{-1}U^{-1}$
- $W^{-1} = VU$
- $W^{-1} = W^\dagger = V^\dagger U^\dagger$
- If U and V are also Hermitian matrices, then $W^{-1} = VU$

**Solution**: For unitary matrices, $W^{-1} = W^\dagger$. Given W = UV, $W^{-1} = (UV)^{-1} = V^{-1}U^{-1}$. Also, for unitary matrices, $V^{-1} = V^\dagger$ and $U^{-1} = U^\dagger$, so $W^{-1} = V^\dagger U^\dagger$.

Furthermore, if U and V are Hermitian matrices, then $U = U^\dagger$ and $V = V^\dagger$, so $W^{-1} = VU$.

**Answer**:
- $W^{-1} = V^{-1}U^{-1}$
- $W^{-1} = W^\dagger = V^\dagger U^\dagger$
- If U and V are also Hermitian matrices, then $W^{-1} = VU$

---

**Q9**: What is the correct binary representation of 0.75?

**Options**:
- 0.100
- 0.101
- 0.011
- 0.110

**Solution**: To convert 0.75 to binary:
$$
\begin{align*}
0.75 &= 0 + 0.5 + 0.25 +0 \\
     &= 0*2^0 + 1*2^{-1} + 1*2^{-2} + 0*2^{-3} \\
     &= 0.110
\end{align*}
$$

**Answer**: 0.110

---

**Q10**: The inverse QFT is the operation that maps the set of vectors $\{∣\tilde{k}\rangle\}$ given in Q1, back to the original orthonormal basis states $∣j\rangle$. Which of the following statement about the inverse QFT is true?

**Options**:
- The quantum circuit corresponding to the inverse QFT is the same as the quantum circuit corresponding to the QFT.
- The circuit complexity of the inverse QFT circuit is the same as the circuit complexity of the QFT circuit.
- The circuit for the inverse QFT is obtained by simply reversing the sequence of gates in the QFT circuit.
- The circuit for inverse QFT is obtained by first flipping the sign of the phases of the phase gates in the QFT circuit and then reversing the sequence of gates in the QFT circuit.

**Solution**: The inverse QFT is the inverse of QFT. This means reversing the order of gates and conjugating each gate (which for phase gates means negating the phase). The complexity remains the same as we're using the same number of gates, just in reverse order with conjugated phases.

**Answer**:
- The circuit complexity of the inverse QFT circuit is the same as the circuit complexity of the QFT circuit.
- The circuit for inverse QFT is obtained by first flipping the sign of the phases of the phase gates in the QFT circuit and then reversing the sequence of gates in the QFT circuit.