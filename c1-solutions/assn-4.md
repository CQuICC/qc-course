## Assignment 4

**Q1**: Identify the two-qubit state, when the individual qubits are in the following states:
Qubit 1: $\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle$
Qubit 2: $\frac{1}{{2}}|0\rangle + \frac{\sqrt{3}}{2}|1\rangle$

**Options**:
- $\frac{1}{2}|00\rangle + \frac{1}{2}|01\rangle + \frac{1}{4}|10\rangle + \frac{3}{4}|11\rangle$
- $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle + \frac{1}{2}|10\rangle + \frac{\sqrt3}{2}|11\rangle$
- $\frac{1}{2\sqrt2}|00\rangle + \frac{\sqrt3}{2\sqrt2}|01\rangle + \frac{1}{2\sqrt2}|10\rangle + \frac{\sqrt3}{2\sqrt2}|11\rangle$
- $\frac{1}{2\sqrt2}|00\rangle + \frac{1}{2\sqrt2}|01\rangle + \frac{\sqrt3}{2\sqrt2}|10\rangle + \frac{\sqrt3}{2\sqrt2}|11\rangle$

**Solution**: To find the two-qubit state, we take the tensor product of the individual qubit states:

$$
\begin{aligned}
|\psi\rangle &= (\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle) \otimes (\frac{1}{2}|0\rangle + \frac{\sqrt{3}}{2}|1\rangle)\\
&= \frac{1}{\sqrt{2}}(\frac{1}{2}|00\rangle + \frac{\sqrt{3}}{2}|01\rangle + \frac{1}{2}|10\rangle + \frac{\sqrt{3}}{2}|11\rangle)
\end{aligned}
$$

**Answer**: $\frac{1}{2\sqrt2}|00\rangle + \frac{\sqrt3}{2\sqrt2}|01\rangle + \frac{1}{2\sqrt2}|10\rangle + \frac{\sqrt3}{2\sqrt2}|11\rangle$

---

**Q2**: If both the qubits of the Bell state $(|00\rangle - |11\rangle)/\sqrt{2}$ were to be measured in the $\{|+\rangle, |-\rangle\}$ basis, which of the following statements correctly describes the measurement output?

**Options**:
* All four outcomes $(+,+), (+,-), (-,+), (-,-)$ are equally likely.
* If the measurement outcome at the first qubit is $+$, the measurement outcome at the second qubit has to be $+$
* If the measurement outcome at the first qubit is $+$, the measurement outcome at the second qubit has to be $-$
* The only possible outcomes are $(+,-)$ and $(-,+)$.

**Solution**: The Bell state $(|00\rangle - |11\rangle)/\sqrt{2}$ can be rewritten in the $\{|+\rangle, |-\rangle\}$ basis:

$(|0\rangle = \frac{1}{\sqrt{2}}(|+\rangle + |-\rangle)$ and $(|1\rangle = \frac{1}{\sqrt{2}}(|+\rangle - |-\rangle)$. This shows that only the outcomes $(+,-)$ and $(-,+)$ have non-zero amplitudes.

**Answer**: The only possible outcomes are $(+,-)$ and $(-,+)$, and therefore also if the measurement outcome at the first qubit is $+$, the measurement outcome at the second qubit has to be $-$ (in any order).

---

**Q3**: Suppose the three qubits held by Alice, Bob, and Charlie are in a quantum state $\frac{1}{\sqrt{3}}[|001\rangle + |010\rangle + |100\rangle]$. If Alice measures her qubit to be in the state $|1\rangle$, what is the probability that Bob and Charlie will find their qubits to be in the state $|0\rangle$?

**Options**:
- $1$
- $2/3$
- $1/\sqrt3$
- $1/3$

**Solution**: After Alice measures her qubit to be $|1\rangle$, the state collapses to $|100\rangle$. The probability of Bob and Charlie finding their qubits in state $|0\rangle$ is:

$P(|00\rangle_{BC} | |1\rangle_A) = 1$

**Answer**: $1$

---

**Q4**: Based on diagram (skipped here)

**Method**: You may solve this question by either doing a full matrix multiplication after kronecker product or circuit simulation, both are equivalent.

---

**Q5**: Find the equivalent circuit that implements the operator:

$O = \begin{pmatrix}
0 & 1 & 0 & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}$

**Options**:
- $CNOT(0, 1)$
- $X(1) \rightarrow CNOT(1, 0) \rightarrow X(1)$
- $CNOT(1, 0)$
- $X(0) \rightarrow CNOT(0, 1) \rightarrow X(0)$

**Solution**: One can trivially check via matrix multiplication. Or follow such that since $X$ is set, we get $|11\rangle$ after CNOT, and then $|01\rangle$ which is the desired output of the operator.

**Answer**: $X(0) \rightarrow CNOT(0, 1) \rightarrow X(0)$

---

**Q6**: Consider a teleportation protocol, where Alice and Bob share the Bell state $(|00\rangle + |11\rangle)/\sqrt{2}$. At the end of the protocol, Bob applies the gate sequence (X, I) in order to obtain the teleported state. What is the two-bit message string that Bob received from Alice?

**Options**:
- 01
- 11
- 00
- 10

**Solution**: Run the teleportation protocol with the given gate sequence. You may modify the notebook and add this gate sequence.

**Answer**: 01

---

**Q7**: The first qubit of the state $|\Phi\rangle = (\frac{1+i\sqrt{3}}{4}|00\rangle + \frac{1-i\sqrt{3}}{4}|01\rangle + \frac{1-i\sqrt{3}}{4}|10\rangle + \frac{1+i\sqrt{3}}{4}|11\rangle)$ was measured in the $\{|+\rangle, |-\rangle\}$ basis with the result $|-\rangle$. What is the probability of obtaining $|0\rangle$ as the result of a second qubit measurement in the basis $\{|0\rangle, |1\rangle\}$?

**Solution**: You may measure in the $\{|0\rangle, |1\rangle\}$ basis and calculate the probability of obtaining $|0\rangle$.

**Answer**: $\frac{1}{2}$

---

**Q8**: Which of the following gate sequences represents a decomposition of the controlled-Y (CY) gate?

**Options**:
- $CNOT(0, 1) \rightarrow H \rightarrow CNOT(0, 1) \rightarrow H$
- $S(0)^\dagger \rightarrow CNOT(0, 1) \rightarrow S(0)$
- $CNOT(0, 1) \rightarrow H \rightarrow CNOT(0, 1)$
- $S(1)^\dagger \rightarrow CNOT(0, 1) \rightarrow S(1)$

**Solution**: CY gate is written as $I \otimes |0\rangle\langle0| + Y \otimes |1\rangle\langle1|$. We can decompose this into a sequence of gates as

**Answer**: $S(1)^{\dagger} \rightarrow CNOT(0, 1) \rightarrow S(1)$

---

**Q9**: Which of the following statements correctly describes the action of the CNOT gate in the $\{|+\rangle, |-\rangle\}$ basis?

**Options**:
* If the control qubit is in the $|+\rangle$ state, the target qubit undergoes a phase flip.
* If the target qubit is in the $|+\rangle$ state, the control qubit undergoes a phase flip.
* If the control qubit is in the $|-\rangle$ state, the target qubit undergoes a phase flip.
* If the target qubit is in the $|-\rangle$ state, the control qubit undergoes a phase flip.

**Solution**: This question is an implementation of phase-kickback.

$ CNOT \left(\frac{|01\rangle - |11\rangle}{\sqrt{2}}\right) = \frac{|11\rangle - |01\rangle}{\sqrt{2}} = - \left( \frac{|01\rangle - |11\rangle}{\sqrt{2}}\right) = -\frac{|0\rangle - |1\rangle}{2} \otimes |1\rangle$

We can see how we were able to pull out a global phase of -1 on the control qubit. This is the essence of phase-kickback. Similarly

**Answer**: If the target qubit is in the $|-\rangle$ state, the control qubit undergoes a phase flip.

---

**Q10**: (Refer to the diagram in the assignment)

**Options**:
* The given circuit is that of a teleportation and the initial state of q1 will be transferred up to a unitary to q2
* The given circuit is that of a teleportation and the initial state of q1 will be transferred up to a unitary to q3
* At no point in the circuit is an entanglement
* The circuit creates an entanglement between q2 and q3 initially.

**Answer**:
- The given circuit is that of a teleportation and the initial state of q1 will be transferred up to a unitary to q3
- The circuit creates an entanglement between q2 and q3 initially.