## Assignment 8

**Q1**: Recall that in the Quantum Fourier Transformation, we need the following unitary matrix

$R_k = \begin{pmatrix} 1 & 0 \\ 0 & e^{i2\pi/2^k} \end{pmatrix}$

Which of the following gates in qiskit do we use to implement this matrix?

**Options**:
- The S gate
- The T gate
- The P gate
- Combination of all the above gates

**Solution**: The matrix $R_k$ represents a phase rotation by an angle $2\pi/2^k$. In qiskit, the P gate (phase gate) is used to apply an arbitrary phase rotation. The P gate with parameter $\lambda$ applies the unitary $\begin{pmatrix} 1 & 0 \\ 0 & e^{i\lambda} \end{pmatrix}$. Setting $\lambda = 2\pi/2^k$ gives us the required $R_k$ matrix. So while in specific cases we do use the S and T gates, the general gate to implement $R_k$ is the P gate.

**Answer**: The P gate

---

**Q2**: Which of the following commands can implement a controlled-S gate in QISKIT?

**Options**:
- `qc=QuantumCircuit(2)
qc.cs(0,1)`
- `qc=QuantumCircuit(2)
qc.cp(1.0, 0,1)`
- `qc=QuantumCircuit(2)
qc.cp(pi/2, 0,1)`
- `qc=QuantumCircuit(2)
qc.cp(pi/2, 1,0)`

**Solution**: The S gate is equivalent to a phase rotation of $\pi/2$. In qiskit, a controlled phase rotation is implemented using the `cp` gate. The `cp` gate takes three arguments: the rotation angle, the control qubit, and the target qubit. Therefore, to implement a controlled-S gate, we need to use `cp` with an angle of $\pi/2$.

**Answer**: `qc=QuantumCircuit(2)
qc.cp(pi/2, 0,1)` or `qc=QuantumCircuit(2)
qc.cp(pi/2, 1,0)`

---

**Q3**: Which simulator gives us the matrix form of a circuit, provided the circuit does not contain any measurements or re-initialization?

**Options**:
- qasm-simulator
- statevector-simulator
- simulator-stabilizer
- unitary-simulator

**Solution**: The unitary-simulator in qiskit is specifically designed to return the unitary matrix representation of a quantum circuit. It works only for circuits without measurements or re-initialization operations, as these non-unitary operations cannot be represented by a unitary matrix.

**Answer**: unitary-simulator

---

**Q4**: Which are the correct commands to execute a circuit in qiskit?

**Options**:
- `job= execute(circuit,backend,shots=1024)`
- `job= execute(shots=1024,backend,circuit)`
- `job= execute('circuit.backend=backend',circuit.shots=1024)`
- `job=execute(backend.circuit, shots.circuit=1024)`

**Solution**: In qiskit, the `execute` function takes the circuit as its first argument, followed by the backend, and then any additional parameters like the number of shots. The correct syntax is `execute(circuit, backend, shots=number_of_shots)`.

**Answer**: `job= execute(circuit,backend,shots=1024)`

**Note:** The execute command has now been deprecated in qiskit. The correct command to execute a circuit is `job = backend.run(circuit, shots=1024)`. The `backend` object is obtained using `backend = Aer.get_backend('qasm_simulator')` for the qasm simulator, or `backend = Aer.get_backend('statevector_simulator')` for the statevector simulator.

---

**Q5**: Use the following oracles on a Deutsch-Jozsa algorithm and identify which of the follow- ing are balanced functions. Note: the last qubit in the oracle definition is the ancillary qubit.

**Options**:
- ```py
  def NewOracle():
      oracle=QuantumCircuit(4)
      oracle.ccx(1,2,3)
      oracle.cx(0,3)
      return oracle
  ```
- ```python
  def NewOracle():
      oracle=QuantumCircuit(3)
      oracle.cx(1,2)
      oracle.cx(0,2)
      return oracle
  ```
- ```python
  def NewOracle():
      oracle=QuantumCircuit(4)
      oracle.x(3)
      return oracle
  ```
- ```python
  def NewOracle():
      oracle=QuantumCircuit(4)
      oracle.cx(0,1)
      oracle.cx(1,2)
      oracle.x(3)
      return oracle
  ```

**Solution**: One can check trivially by running the circuits in a dry run or on simulator.

**Answer**:
```python
def NewOracle():
    oracle=QuantumCircuit(4)
    oracle.ccx(1,2,3)
    oracle.cx(0,3)
    return oracle
```
and
```python
def NewOracle():
    oracle=QuantumCircuit(3)
    oracle.cx(1,2)
    oracle.cx(0,2)
    return oracle
```

---

**Q6**:
2 points
Which of the following is correctly implementing the Bell basis measurement in `circuit = QuantumCircuit(2, 2)`?

**Options**:
- ```python
  circuit.cx(0, 1)
  circuit.measure([0,1], [0,1])
  ```
- ```python
  circuit.h(0)
  circuit.cx(0, 1)
  circuit.measure([0,1], [0,1])
  ```
- ```python
  circuit.cx(0, 1)
  circuit.h(0)
  circuit.measure([0,1], [0,1])
  ```
- ```python
  circuit.cx(1, 0)
  circuit.h(0)
  circuit.measure([0,1], [0,1])
  ```

**Solution**: The Bell basis measurement is performed by first applying a CNOT gate with the first qubit as control and the second as target, followed by a Hadamard gate on the first qubit. This transforms the Bell states to the computational basis states following which we can make the standard $Z$ basis measurements.

**Answer**:
```python
circuit.cx(0, 1)
circuit.h(0)
circuit.measure([0,1], [0,1])
```

---

**Q7**: Which option correctly represents the recovery circuit to be appended to the right of the given teleportation circuit?

(see assignment for the circuit)

**Options**:
- `Tcircuit.z(q2).cif(c0, 0)
Tcircuit.x(q2).cif(c1, 1)`
- `Tcircuit.z(q2).cif(c0, 1)
Tcircuit.x(q2).cif(c1, 1)`
- `Tcircuit.x(q2).cif(c0, 1)
Tcircuit.z(q2).cif(c1, 1)`
- `Tcircuit.x(q2).cif(c0, 0)
Tcircuit.z(q2).cif(c1, 1)`

**Solution**: In quantum teleportation, the recovery circuit applies X and Z gates conditionally based on the measurement outcomes. The X gate is applied if the second qubit measurement is 1, and the Z gate is applied if the first qubit measurement is 1. In qiskit, `cif(c, 1)` applies the gate if the classical bit c is 1.

**Answer**:
```python
Tcircuit.z(q2).cif(c0, 1)
Tcircuit.x(q2).cif(c1, 1)
```

**Note:** The `cif` method has been deprecated in qiskit. The correct way to conditionally apply gates based on classical bits is to use the `c_if` method.

---

**Q8**: Which of the following is the correct definition of a function to implement $R_k$ (defined in Question 1 above)?

(see assignment for circuit)

**Options**:
- ```python
  U=UnitaryGate(data=[[1,0],[0,e**(i*2*pi/2**k)]])
  CUD= U.control(num_ctrl_qubits=1)
  return CUD
  ```
- ```python
  U=UnitaryGate(data=[[1,0],[0,e**(-i*2*pi/2**k)]])
  CUD= U.control(num_ctrl_qubits=1)
  return CUD
  ```
- ```python
  U=UnitaryGate(data=[[1,0],[0,e**(-i*2*pi/2**(k-1))]])
  CUD= U.control(num_ctrl_qubits=1)
  return CUD
  ```
- ```python
  U=UnitaryGate(data=[[1,0],[0,e**(i*2*pi/2**(k+1))]])
  CUD= U.control(num_ctrl_qubits=1)
  return CUD
  ```

**Solution**: From definition.

**Answer**:
```python
U=UnitaryGate(data=[[1,0],[0,e**(i*2*pi/2**k)]])
CUD= U.control(num_ctrl_qubits=1)
return CUD
```

---

**Q9**: Consider the problem finding the order of $x$ modulo $N$, where $x$ has an $n$-bit binary representation and $N$ has an $L$-bit binary representation. To find the order $r$ to $L$ bits of accuracy, how many data qubits and ancilla qubits does the quantum order-finding algorithm require?

**Options**:
- $n$ data qubits and $L$ ancilla qubits.
- $O(2^L)$ data qubits and $L$ ancilla qubits.
- $O(L)$ data qubits and $L$ ancilla qubits.
- $O(L)$ data qubits and $2L$ ancilla qubit

**Solution**: The quantum order-finding algorithm requires $O(L)$ data qubits and $L$ ancilla qubits. The number of data qubits is determined by the number of bits required to store the value of $N$, which is $L$ bits. The number of ancilla qubits is also $L$.

Refer to [Quantum Phase Est Notebook](../../mod8/qpe.ipynb) for more details.

**Answer**: $O(L)$ data qubits and $L$ ancilla qubits

---

**Q10**: For the unitary $U_{x,N}$ that acts on computational basis states $|y\rangle$ as $U_{x,N}|y\rangle = |xy \mod N\rangle$, where $r$ denotes the order of $x$ modulo $N$, which of the following are eigenstates of $U_{x,N}$?

**Options**:
- $\frac{1}{\sqrt{r}}\sum_{k=0}^{r-1}|x^k \mod N\rangle$
- $\frac{1}{\sqrt{r}}\sum_{k=0}^{r-1}e^{-2\pi ik/r}|x^k \mod N\rangle$
- $\frac{1}{\sqrt{r}}\sum_{k=0}^{r-1}e^{-i\pi k/r}|x^k \mod N\rangle$
- $\frac{1}{\sqrt{r}}\sum_{k=0}^{r-1}e^{-2\pi isk/r}|x^k \mod N\rangle$, for $0 \leq s \leq r - 1$

**Solution**: Use the defination of an eigenstate $U_{x,N}|v\rangle = \lambda|v\rangle$. and check which of the options satisfy this.

**Answer**: a), b) and d)