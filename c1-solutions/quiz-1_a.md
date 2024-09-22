**Q1**: Which of the following states are entangled?

**Options**:
- $\frac{1}{2}|01\rangle + \frac{\sqrt{3}}{2}|10\rangle$
- $\frac{1}{\sqrt{2}}(|11\rangle + |10\rangle)$
- $\frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$
- $\frac{1}{\sqrt{2}}(|00\rangle + |01\rangle + |10\rangle - |11\rangle)$

**Solution**: For small states such as these we can just factorise the state and check,
- $\frac{1}{\sqrt{2}}(|11\rangle + |10\rangle)$ &rarr; $|1\rangle \otimes \frac{1}{\sqrt{2}}(|1\rangle + |0\rangle)$
- $\frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$ &rarr; $\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) \otimes \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$

**Answer**:
- $\frac{1}{2}|01\rangle + \frac{\sqrt{3}}{2}|10\rangle$
- $\frac{1}{\sqrt{2}}(|00\rangle + |01\rangle + |10\rangle - |11\rangle)$

Alternatively, for larger or 'more complicated' states you may apply the [Peres-Horodecki criterion](https://en.wikipedia.org/wiki/Peres%E2%80%93Horodecki_criterion).

---

**Q2**: Choose the correct gate identities for the phase gate S.

**Options**:
- $SXS^\dagger = Y$
- $SYS^\dagger = -X$
- $SXS^\dagger = -Y$
- $SYS^\dagger = X$

**Solution**: Verify trivially by multiplying the matrices for $S, X, Y$.

**Answer**:
- $SXS^\dagger = Y$
- $SYS^\dagger = -X$

---

**Q3**: For the state $\frac12(|+-\rangle + |-+\rangle)$, which of the following statements are true?

**Options**:
- All four outcomes (0,0), (0,1), (1,0), (1,1) are equally likely
- If the first qubit is 0, the second qubit must be 0
- Only outcomes (0,1) and (1,0) are possible
- If the first qubit is 1, the second qubit must be 0

**Solution**: For simplicity converting the state to computational basis,

$$
\begin{align*}
\frac{1}{\sqrt{2}}(|+-\rangle + |-+\rangle) =
\frac{1}{\sqrt{2}}((|0\rangle + |1\rangle) \otimes (|0\rangle - |1\rangle) - (|0\rangle - |1\rangle) \otimes (|0\rangle + |1\rangle)) =
\frac{1}{\sqrt{2}}(|10\rangle - |01\rangle) =
\end{align*}
$$

**Answer**:
- Only outcomes (0,1) and (1,0) are possible
- If the first qubit is 1, the second qubit must be 0

---

**Q4**: Which tasks can a quantum computer solve exponentially faster than a classical computer?

**Options**:
- Determining if an oracle function is constant or balanced
- Finding $f(x)$ for a function $f(x) = a \cdot x$
- Prime factorization of a two-prime product
- Search over unstructured databases

**Solution**:
- Grover's algorithm doesn't solve the search problem exponentially faster, but quadratic faster.

**Answer**:
- Determining if an oracle function is constant or balanced
- Prime factorization of a two-prime product

---

**Q5**: Which statements about the Quantum Fourier Transform (QFT) are true?

**Options**:
- QFT is a unitary transformation represented as an $N \times N$ matrix
- QFT can be represented as a $2^N\times2^N$ unitary matrix
- QFT amplitudes change by a factor of $l/N$ when a state is shifted
- QFT amplitudes remain the same when a state is shifted

**Solution**: Can be answered trivially from either the unitary matrix representation or the properties of the QFT. Refer to past assignments.

**Answer**:
- QFT is a unitary transformation represented as an $N \times N$ matrix
- QFT amplitudes remain the same when a state is same

---

**Q6**: Which circuit leads to an entangled state?

(refer to the quiz for the circuit diagram)

**Solution**: You may dry run the states as demonstrated before in assignments or use qiskit to run the circuit.

**Answer**: (B), (C)

---

**Q7**: Which statements about the BB84 protocol are incorrect?

**Options**:
- Any pair of orthonormal bases can be used for the protocol.
- The two orthonormal bases used in the protocol should be mutually unbiased.
- If a state prepared in one basis is measured in a different basis, the resulting shared key has errors with 50% probability.
- If a state prepared in one basis is measured in a different basis, the resulting shared key always has errors

**Solution**: Part of the definition of the BB84 protocol is that the two bases used should be mutually unbiased.

**Answer**:
- Any pair of orthonormal bases can be used for the protocol.
- If a state prepared in one basis is measured in a different basis, the resulting shared key always has errors

---

**Q8**: Which qubit platforms work at room temperature?

**Options**:
- Ion-trap qubits
- Photonics-based qubits
- Superconducting qubits
- Nuclear Magnetic Resonance (NMR) qubits

**Solution**: Both ion trap and superconducting qubits require cryogenic temperatures and are usually done in dilution refrigerators.

**Answer**: Photonics-based qubits and Nuclear Magnetic Resonance (NMR) qubits

---

**Q9**: A Hermitian matrix is called a density matrix if its eigenvalues are non-negative and sum to one. Which of the following are density matrices?

**Options**:
- $\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
- $\begin{pmatrix} \frac34 & 0 \\ 0 & \frac14 \end{pmatrix}$
- $\begin{pmatrix} \frac12 & \frac12 \\ \frac12 & \frac12 \end{pmatrix}$
- $\begin{pmatrix} \frac12 & 0 \\ 0 & \frac12 \end{pmatrix}$

**Solution**: B, D are trivially density matrices. We can check C by calculating the eigenvalues.

**Answer**: All except the first matrix which is simply the $\sigma_x$ gate.
