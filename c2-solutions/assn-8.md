## Assignment 8

**Q1**: Let us suppose we want to transpile a circuit into a particular set of basis gates. Which of the following options, when set as basis gate sets, will lead to an error for the publicly available Eagle and Heron processors? (See https://quantum.ibm.com/services/resources?tab=systems)

**Options**:

1. ['x', 'sx', 'rz', 'ecr', 'id']

2. ['x', 'sx', 'rz', 'ecr', 'id', 'swap']  

3. ['x', 'sx', 'rz', 'id', 'swap']  

4. ['x', 'sx', 'rz', 'ecr', 'swap']

**Solution**:

The Eagle and Heron processors support the basis gates: ['x', 'sx', 'rz', 'ecr']. The `swap` gate is not a native gate and must be decomposed into native two-qubit gates like `ecr`. If the set of basis gates includes `swap` but omits `ecr`, the transpiler will not know how to implement `swap` using native operations, leading to an error.

- Option 1 is valid as all gates are either native or ignorable (like `id`).
- Option 2 includes `swap`, but since `ecr` is present, `swap` can be decomposed.
- Option 3 includes `swap` without any native two-qubit gate like `ecr`, which will lead to a transpilation error.
- Option 4 includes `swap` and `ecr`, so it is valid.

**Final Answer**: 

['x', 'sx', 'rz', 'id', 'swap']

---

**Q2**: Let us suppose that the same circuit is transpiled multiple times with optimization_level = 3. Is it possible to have different transpiled circuits, i.e. circuits with different mapping? (Hint: Try it out yourself)

**Options**:

1. Yes  

2. No

**Solution**:  
Yes, it is possible. Transpilation with optimization_level = 3 uses various heuristics and optimization passes that are not fully deterministic. These can include different initial qubit layouts and routing strategies depending on stochastic choices or changes in internal compiler state (like random seeds). Therefore, running the transpiler multiple times on the same input circuit may result in different output circuits with different qubit mappings or gate sequences.

**Final Answer**: 

Yes

---

**Q3**: Which of the following is/are good candidate(s) for circuit cutting? (Recall that the postprocessing time and the number of subcircuits scale exponentially with the number of cuts)

**Options**:

1. A QML circuit with CNOT gates between every pair of qubits  

2. An n-qubit GHZ circuit  

3. An n-qubit RealAmplitudes circuit (See https://docs.quantum.ibm.com/api/qiskit/qiskit.circuit.library.RealAmplitudes)  

4. None of the above

**Solution**:  

Circuit cutting is efficient only when the number of cuts is small, which typically means the circuit has a modular structure or limited entanglement between parts.

- **Option 1**: A QML circuit with CNOTs between every pair of qubits that creates a fully entangled network along with many repetitions of these layers, requiring many cuts. This leads to a large number of subcircuits and heavy postprocessing — **not a good candidate**.

- **Option 2**: A GHZ circuit is highly entangled, but the entanglement layer is just used once. It can be cut with fewer cuts, though it still introduces some complexity — **feasible**.

- **Option 3**: RealAmplitudes circuits are often shallow and have a layered structure, making them more amenable to being split into subcircuits with fewer cuts — **a good candidate**.

- Therefore, **Option 3** is clearly a good candidate, and **Option 2** is also acceptable.

**Final Answer**: 

2. An n-qubit GHZ circuit  

3. An n-qubit RealAmplitudes circuit

---

**Q4**: Which of the following quantum protocols will require dynamic circuits for implementation?

**Options**:

1. Quantum teleportation  

2. Quantum error correction  

3. Quantum machine learning  

4. Grover’s algorithm

**Solution**:  

Dynamic circuits are those that include mid-circuit measurements and classically-controlled operations based on measurement results. These are essential in protocols where actions depend on intermediate outcomes.

- **Quantum teleportation**: Requires mid-circuit measurement and conditional operations based on classical bits — **requires dynamic circuits**.

- **Quantum error correction**: Involves syndrome measurements followed by classically-controlled corrections — **requires dynamic circuits**.

- **Quantum machine learning**: Not inherently dependent on dynamic circuits, though some advanced protocols might use them. Generally, **not required**.

- **Grover’s algorithm**: A fixed sequence of unitary operations and oracles; no measurements or classical control during the main execution — **does not require dynamic circuits**.

**Final Answer**:  

1. Quantum teleportation  

2. Quantum error correction

---

**Q5**:  Consider the following circuit:

```python
qc = QuantumCircuit(4)
qc.h(0)
qc.cx(0,1)
qc.cx(0,2)
qc.cx(0,3)
```

And some toy backend with coupling map = [[0,1],[1,2],[2,3]]. Which of the following initial layouts leads to the least number of SWAP gates? 
(Note: A layout [i,j,k,l] means circuit qubit 0 is placed on physical qubit 'i', circuit qubit 1 on 'j', and so on.)

**Options**:
1. [1, 0, 2, 3]  
2. [2, 1, 3, 0]  
3. [0, 1, 2, 3]  
4. [1, 2, 0, 3]  

**Solution**:  
We are given a quantum circuit where qubit 0 is the control for three CNOTs targeting qubits 1, 2, and 3. 

To minimize SWAPs, we want the control qubit (0) to be adjacent to all targets in the coupling map: [[0,1], [1,2], [2,3]], which forms a linear topology. Let’s evaluate each layout to see how the logical-to-physical mapping aligns:

1. **[1, 0, 2, 3]**
   - Logical 0 → Physical 1  
   - Logical 1 → Physical 0  
   - Logical 2 → Physical 2  
   - Logical 3 → Physical 3  
   Connections:  
   - 0→1: 1→0 — adjacent  
   - 0→2: 1→2 — adjacent  
   - 0→3: 1→3 — **not adjacent**, **needs one SWAP**

2. **[2, 1, 3, 0]**
   - Logical 0 → Physical 2  
   - Logical 1 → Physical 1  
   - Logical 2 → Physical 3  
   - Logical 3 → Physical 0  
   Connections:  
   - 0→1: 2→1 — adjacent  
   - 0→2: 2→3 — adjacent  
   - 0→3: 2→0 — **not adjacent**, **needs one SWAP**

3. **[0, 1, 2, 3]**
   - Logical 0 → Physical 0  
   - Logical 1 → Physical 1  
   - Logical 2 → Physical 2  
   - Logical 3 → Physical 3  
   Connections:  
   - 0→1: 0→1 — adjacent  
   - 0→2: 0→2 — **not directly connected**, needs 0→1→2 — **needs SWAP**  
   - 0→3: 0→3 — **needs multiple SWAPs**

4. **[1, 2, 0, 3]**
   - Logical 0 → Physical 1  
   - Logical 1 → Physical 2  
   - Logical 2 → Physical 0  
   - Logical 3 → Physical 3  
   Connections:  
   - 0→1: 1→2 — adjacent  
   - 0→2: 1→0 — adjacent  
   - 0→3: 1→3 — **not adjacent**, **needs one SWAP**

We can see that 3 of these layouts only require one swap and are the best options.

**Final Answer**: 

1. [1, 0, 2, 3]

2. [2, 1, 3, 0]

4. [1, 2, 0, 3]

---

**Q6**: Consider the following code:

```python
creg = ClassicalRegister(2)
qc = QuantumCircuit(1)
qc.add_register(creg)

qc.h(0)
qc.measure(0, creg[0])

with qc.if_test((creg[0], 1)):
    qc.x(0)

qc.measure(0, creg[1])
```

If this circuit is executed on a noiseless simulator with shots=1000, what is the probability of obtaining outcome '0' on 'creg[1]'?  
(Hint: Recall that Qiskit uses little-endian convention.)

**Options**:
1. 1  
2. 0  
3. 0.5  
4. 0.25  

**Solution**:  
Let’s analyze the circuit step by step:

1. `qc.h(0)` — Apply Hadamard to qubit 0 → puts qubit in superposition: $|\psi\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$

2. `qc.measure(0, creg[0])` — Measure qubit 0 into classical register creg[0]:  
   With 50% chance, creg[0] will be 0; with 50% chance, creg[0] will be 1.

3. Conditional: `with qc.if_test((creg[0], 1)):`  
   If creg[0] == 1, apply X gate to qubit 0 (flip the qubit).

   Let's follow both branches:

   - If creg[0] == 0 (happens 50% of the time):  No X gate, qubit remains in state |0⟩.

   - If creg[0] == 1 (happens 50% of the time): Apply X, qubit was |1⟩ (from measurement), now becomes |0⟩.

   So in **both** cases, by the time we reach the second measurement, **qubit 0 is in state |0⟩**.

4. `qc.measure(0, creg[1])` — Measure qubit 0 again into creg[1]. Since the qubit is always in |0⟩ at this point, creg[1] will always be 0.

**Final Answer**: 

1

---

**Q8**: Which of the following are used to find an optimal layout of qubits in the device to run an input circuit? (select all that apply)

**Options**:

1. qubit connectivity in the HW  

2. application domain of the problem statement  

3. noise with respect to single-qubit operations  

4. noise with respect to two-qubit operations  

**Solution**:  
To optimize the layout of qubits on quantum hardware for running an input circuit, several hardware-specific and error-related factors are considered:

- Qubit connectivity in the HW (Option 1): Ensures efficient mapping by minimizing the number of SWAP operations required for two-qubit gates, which can be expensive in terms of time and error.

- Application domain of the problem statement (Option 2) is not typically used in layout optimization since it pertains more to algorithm design than hardware execution.

- Noise with respect to single-qubit operations (Option 3) and two-qubit operations (Option 4): Different qubits and gates on real devices exhibit varying error rates. Choosing qubits with lower error rates for operations improves fidelity.

**Final Answer**: 

1. qubit connectivity in the HW  

3. noise with respect to single-qubit operations  

4. noise with respect to two-qubit operations  

---

**Q9**: Transpilation increases the noise level of the output whenever it increases the depth.

**Options**:

1. True  

2. False  

**Solution**:  

Transpilation does not necessarily increase the noise level just because it increases the depth. While increasing circuit depth can potentially lead to higher noise (since more gates are involved, and qubits need to maintain coherence longer), this is not always the case. The noise depends on *which* gates are added and their corresponding error rates (as noted in Q8: different gates and qubits have different noise characteristics). 

Furthermore, transpilers are designed to optimize based on real hardware constraints, such as qubit connectivity and gate error rates, and may add gates in a way that mitigates noise even if depth increases. Hence, the statement is not necessarily true.

**Final Answer**: 

False

---

**Q10**: Suppose you want to calculate the ground state energy of the silver chloride molecule. Circuit knitting can be used to efficiently solve this problem to cut it down to smaller circuits and then use a classical simulator to calculate expectation with respect to each of the smaller circuits.

**Options**:

1. True  

2. False  

**Solution**:  

Circuit knitting techniques do allow breaking down a quantum circuit into smaller components. However, for complex molecular systems like silver chloride, the process is not guaranteed to be efficient or accurate solely with classical simulation of the smaller circuits. Quantum hardware is usually still required for executing the subcircuits, and circuit knitting may not always yield meaningful results for such large systems.

**Final Answer**: 

False

---
