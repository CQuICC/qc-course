## Assignment 5

**Q1**: Out of the different qubit platforms given below, for which ones is scalability tough?

**Options**:
* Ion trap qubits
* NMR qubits
* NV Center qubits
* Photonic qubits

**Solution**: Scalability is a crucial factor in developing practical quantum computers. Among the given options:

1. Ion trap qubits: Generally considered scalable, though with some engineering challenges.
2. NMR qubits: Difficult to scale due to the exponential decrease in signal-to-noise ratio as the number of qubits increases.
3. NV Center qubits: Challenging to scale due to difficulties in precisely placing and controlling multiple NV centers.
4. Photonic qubits: Relatively scalable, especially with integrated photonic circuits.

**Answer**: NMR qubits, NV Center qubits

---

**Q2**: Identify the quantum circuit of the two-qubit Bell state $|\psi^+\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$.

**Solution**: The Bell state $|\psi\rangle = \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$ is one of the maximally entangled two-qubit states. To create this state:

1. Start with $|00\rangle$
2. Apply X gate to the second qubit: $|01\rangle$
3. Apply Hadamard (H) gate to the first qubit: $\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)|1\rangle$
4. Apply CNOT with first qubit as control: $\frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$

**Answer**: c)
---

**Q3**: Identify the quantum state corresponding to the given circuit:
```py
Circuit = QuantumCircuit(q, c)
Circuit.x(q[1])
Circuit.h(q[0])
Circuit.z(q[0])
Circuit.z(q[1])
Circuit.cx(q[0], q[1])
Circuit.measure(q, c)
```

**Solution**: Let's analyze the circuit step by step:

1. Start with $|00\rangle$
2. Apply X gate to the second qubit: $|01\rangle$
3. Apply Hadamard (H) gate to the first qubit: $|+\rangle|1\rangle$
4. Apply Z gate to the first qubit: $|-\rangle|1\rangle$
5. Apply Z gate to the second qubit: $|-\rangle|-1\rangle$
6. Apply CNOT and create a maximally mixed state


**Answer**: $\frac{1}{\sqrt2}\begin{pmatrix} 0 \\ -1 \\ 1 \\ 0 \end{pmatrix}$

---

**Q4**: Identify the quantum state corresponding to the circuit:

$H(0) \rightarrow CNOT(0, 1) \rightarrow CNOT(0,  2)$

**Solution**: This circuit creates the well known GHZ state, which is a maximally entangled three-qubit state. The steps are:

1. Apply Hadamard gate to the first qubit: $\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)|0\rangle|0\rangle$
2. Apply CNOT with first qubit as control and second qubit as target: $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)|0\rangle$
3. Apply CNOT with first qubit as control and third qubit as target: $\frac{1}{\sqrt{2}}(|000\rangle + |111\rangle)$

**Answer**: $\frac{1}{\sqrt{2}}(|000\rangle + |111\rangle)$

---

**Q5**: Consider a new two-qubit gate K which is equivalent to $H \otimes I$. What is the result of K gate acting on the quantum state $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$?

**Solution**: The gate K applies a Hadamard transform to the first qubit and leaves the second qubit unchanged.

$$
\begin{align*}
K\left(\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)\right) &= \left(H \otimes I\right)\left(\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)\right) \\
&= \frac{1}{\sqrt{2}}\left(H|0\rangle|0\rangle + H|1\rangle|1\rangle\right) \\
&= \frac{1}{\sqrt{2}}\left(\frac{|0\rangle + |1\rangle}{\sqrt{2}}|0\rangle + \frac{|0\rangle - |1\rangle}{\sqrt{2}}|1\rangle\right) \\
&= \frac{1}{2}(|00\rangle + |10\rangle + |01\rangle - |11\rangle)
\end{align*}
$$

**Answer**: $\frac{1}{2}(|00\rangle + |10\rangle + |01\rangle - |11\rangle)$

---

**Q6**: Choose the correct option for a two-qubit circuit:
Note that C is a CNOT gate with the first qubit as the control qubit and the second qubit is the target qubit.

**Options**:
* $CX_1C = X_1X_2$
* $CZ_1C = Z_1$
* $CY_2C = Y_2Z_1$
* $CY_1C = X_2Y_1$

**Solution**: All options are correct. You may verify by dry running the circuit with the given gates or executing them on the simulator.

**Answer**: All options are correct

---

**Q7**: What is the output of the following circuit?

$X(1) \rightarrow \text{Controlled }H(0, 1)$

**Options**:
* $|0\rangle|+\rangle$
* $|-\rangle|0\rangle$
* $|+\rangle|0\rangle$
* $|0\rangle|1\rangle$

**Solution**: You may analyze the circuit step by step as shown in the questions before or, execute the circuit on a quantum simulator to get the output via

```py
qc = QuantumCircuit(2)
qc.x(1)
qc.ch(0, 1)
```

**Answer**: $|0\rangle|1\rangle$

---

**Q8**: What are the resources needed to teleport a quantum state?

**Options**:
* Entanglement
* Entropy
* Two classical bits
* Global phase

**Solution**: Quantum teleportation requires:
1. Entanglement: A shared entangled pair between sender and receiver.
2. Two classical bits: To communicate the result of the sender's measurement.

Entropy and global phase are not necessary resources for teleportation.

**Answer**: Entanglement, Two classical bits

---

**Q9**: Let $M = N_1N_2$ and executes the following action on a quantum state $M|0\rangle = -i|1\rangle$ and $M|1\rangle = -i|0\rangle$. What are $N_1$ and $N_2$?

**Options**:
- $N_1 = Y$, $N_2 = Z$
- $N_1 = X$, $N_2 = Y$
- $N_1 = Y$, $N_2 = X$
- $N_1 = Z$, $N_2 = Y$

**Solution**: The gate $M$ will be applied as $M|0\rangle = N_1N_2|0\rangle = -i|1\rangle$ and $M|1\rangle = N_1N_2|1\rangle = -i|0\rangle$. We have to be careful with the order of the gates. The gates are applied as $N_2$ **then** $N_1$ not the other way around.

**Answer**: $N_1 = Z$, $N_2 = Y$

---

**Q10**: Of the four gates given below, identify the gates which are present in both the classical and quantum domain:

**Options**:
* Swap gate
* X gate
* Y gate
* CCNOT gate

**Solution**:
1. Swap gate: "Exchange gate"
2. X gate: NOT gate
3. Y gate: Pauli Y gate
4. CCNOT gate: Toffoli gate, 3 XOR gate

**Answer**: Swap gate, X gate, CCNOT gate