## Assignment 6

**Q1**: Which of the following statements is an accurate description of the effect of noise on quantum states?

**Options:**  

- [ ] Noise causes a pure quantum state to transform into an incoherent mixture of multiple states.  
- [ ] Noise is caused when a quantum system evolves with time via a unitary transformation.  
- [ ] Noise is caused when a quantum system is coupled to a bath or environment and the joint system evolves via a unitary transformation.  
- [ ] Noise is a reversible process.  

**Solution:**  

Noise in quantum systems typically arises due to interactions with an external environment (a bath), leading to decoherence. This process transforms a pure state into a mixed state by introducing incoherence between the components of the superposition. The evolution of a closed quantum system is governed by unitary transformations, which are reversible and do not introduce noise. However, when a system is coupled to an environment, the overall evolution remains unitary, but the reduced dynamics of the system alone appear non-unitary and noisy. Additionally, noise is inherently irreversible due to the loss of quantum information into the environment.

The first and third statements accurately describe the effect of noise on quantum states. The second and fourth statements are incorrect because unitary evolution alone does not cause noise, and noise is not a reversible process.

**Final Answer:**  

Noise causes a pure quantum state to transform into an incoherent mixture of multiple states.  
Noise is caused when a quantum system is coupled to a bath or environment and the joint system evolves via a unitary transformation. 

---

**Q2**: Which of the following statements correctly describes the action of the single-qubit bit-flip noise (with noise parameter p) on the qubit state α|0⟩ + β|1⟩?

**Options:**  
- [ ] The state α|0⟩ + β|1⟩ always gets transformed to α|1⟩ + β|0⟩.  
- [ ] The state is always left unchanged.  
- [ ] The state α|0⟩ + β|1⟩ gets transformed to α|1⟩ + β|0⟩ with probability p.  
- [ ] The state α|0⟩ + β|1⟩ remains α|0⟩ + β|1⟩ with probability 1 - p.  

**Solution:**  

Bit-flip noise is a quantum channel that flips a qubit (applies the Pauli-X operator) with probability \( p \) and leaves it unchanged with probability \( 1 - p \). This means that the state α|0⟩ + β|1⟩ is transformed to α|1⟩ + β|0⟩ with probability \( p \) and remains α|0⟩ + β|1⟩ with probability \( 1 - p \).

The first and second options are incorrect because the bit-flip noise does not always flip the state or leave it unchanged deterministically. Instead, it introduces a probabilistic transformation. The third and fourth options correctly describe this probabilistic nature.

**Final Answer:**  

The state α|0⟩ + β|1⟩ gets transformed to α|1⟩ + β|0⟩ with probability p.  
The state α|0⟩ + β|1⟩ remains α|0⟩ + β|1⟩ with probability 1 - p.  

---

**Q3**: Which of the following statements correctly explains the basic principle behind a quantum error correcting (QEC) code?

**Options:**  
- [ ] The QEC code entangles the single-qubit state of the input qubit with a single-qubit state of the output.  
- [ ] In a QEC code, the single-qubit state is teleported from the input to the output.  
- [ ] The QEC code makes multiple copies of the single-qubit state and these copies are transmitted to the output.  
- [ ] In a QEC code, the single-qubit state is entangled with other ancillary states and this entangled state is transmitted to the output.  

**Solution:**  

Quantum error correction works by encoding a single logical qubit into a larger entangled state involving multiple physical qubits. This is done using ancillary qubits to spread quantum information across a larger system, allowing errors to be detected and corrected without violating the no-cloning theorem. 

The first option is incorrect because QEC does not simply entangle an input qubit with an output qubit. The second option is incorrect because quantum teleportation is a different process that does not inherently involve error correction. The third option is incorrect because making multiple copies of an unknown quantum state is prohibited by the no-cloning theorem. The fourth option is correct because QEC encodes the logical qubit into an entangled state with ancillary qubits to enable error detection and correction.

**Final Answer:**  

In a QEC code, the single-qubit state is entangled with other ancillary states and this entangled state is transmitted to the output.  

---

**Q4**: What is the output of the following circuit? (refer to Q4 in assignment for circuit diagram)

**Options:**  

- [ ] \( |+\rangle |1\rangle |1\rangle \)  
- [ ] \( \frac{1}{\sqrt{2}} (|000\rangle + |111\rangle) \)  
- [ ] \( |+\rangle |+\rangle |+\rangle \)  
- [ ] \( \frac{1}{2} (|000\rangle + |111\rangle) \)  

**Solution:**

The circuit consists of:  
1. The first qubit initialized in the \( |+\rangle \) state, which is \( \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \).  
2. Two controlled-NOT (CNOT) gates, where the first qubit (in state \( |+\rangle \)) is the control and the second and third qubits (both initialized to \( |0\rangle \)) are the targets.

Thus, after applying the CNOTs, the state transforms into  
\[
\frac{1}{\sqrt{2}} (|000\rangle + |111\rangle)
\]  
which is a maximally entangled GHZ state.

The third and fourth options are incorrect because they do not represent the correct quantum entanglement pattern. The first option is incorrect because the first qubit remains in superposition, not collapsed to \( |+\rangle |1\rangle |1\rangle \).

**Final Answer:**  

\( \frac{1}{\sqrt{2}} (|000\rangle + |111\rangle) \)  

---

Q5) Which of the following states remains unaffected by bit-flip noise?

**Options:**  
- [ ] \( |0\rangle \)  
- [ ] \( |+\rangle \)  
- [ ] \( |-\rangle \)  
- [ ] None of the above  

**Solution:**  

Bit-flip noise applies a Pauli-X operation (\( X \), which swaps \( |0\rangle \) and \( |1\rangle \)) with some probability \( p \), leaving the state unchanged with probability \( 1 - p \). 

- \( |0\rangle \) is flipped to \( |1\rangle \), so it is affected.  
- \( |+\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \) transforms into \( |+\rangle \), meaning it is unaffected.  
- \( |-\rangle = \frac{1}{\sqrt{2}} (|0\rangle - |1\rangle) \) transforms into \( - |-\rangle \), ignoring global phase, it is \( |-\rangle \), meaning it is unaffected as well.  

**Final Answer:**  

\( |+\rangle \)

\( |-\rangle \)

---

Q6) Consider the 3-qubit encoded state \( \frac{1}{\sqrt{2}} (|000\rangle + |111\rangle). \) Which of the following sets of errors map this state to distinct, distinguishable states?

**Options:**  
- [ ] \( XII, IXX \)  
- [ ] \( XII, XXI, XIX \)  
- [ ] \( IXI, XIX \)  
- [ ] \( XII, IXI, IIX \)  

**Solution:**  
The given state is the 3-qubit GHZ state, which is commonly used in quantum error correction. When single-qubit \( X \) errors (bit-flip errors) are applied, they map the state to orthogonal states that are distinguishable. 

- The bit-flip errors on different qubits should be orthogonal and distinguishable.  
- The key idea is that different errors should map the GHZ state to states that have different error syndromes, making them distinguishable using stabilizer measurements.

Analyzing the given options:
1. \( XII \) and \( IXX \) applied give non-distinct states.
2. \( XII, XXI, XIX \) applied on the GHZ leads to distinct states.
3. \( IXI, XIX \) also results in non-distinct states.
4. \( XII, IXI, IIX \) applied on the GHZ leads to distinct states.

Since we are looking for sets of errors that lead to distinct, distinguishable states, we have two options that are correct

**Final Answer:**  

\( XII, XXI, XIX \)  

\( XII, IXI, IIX \) 

---

Q7) Identify the valid density matrices among the matrices listed below.

**Options:**  
- [ ] \( \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \)  
- [ ] \( \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  
- [ ] \( \begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  
- [ ] \( \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \)

**Solution:**  

A density matrix \( \rho \) must satisfy:
1. **Hermitian**: \( \rho = \rho^\dagger \).
2. **Positive semi-definite**: All eigenvalues must be \( \geq 0 \).
3. **Trace 1**: \( \text{Tr}(\rho) = 1 \).

Checking Each Matrix:

1. \( \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \)  
   - Trace = \( 1+1 = 2 \neq 1 \), so **not a valid density matrix**.  

2. \( \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  
   - Trace = \( \frac{1}{2} + \frac{1}{2} = 1 \).  
   - Eigenvalues are \( \{1, 0\} \) (both \( \geq 0 \)), so **valid density matrix**.  

3. \( \begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  
   - Trace = 1.  
   - Eigenvalues = \( \{1, 0\} \) (both \( \geq 0 \)), so **valid density matrix**.  

4. \( \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \)  
   - Trace = 1.  
   - Eigenvalues = \( \{0.5, 0.5\} \) (both \( \geq 0 \)), so **valid density matrix**.  

**Final Answer:**

\( \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  

\( \begin{pmatrix} \frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} \end{pmatrix} \)  

\( \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \)  

---

Q8) Consider a 3-qubit state in the \( |+\rangle, |-\rangle \) basis, of the form  
\[
\frac{1}{\sqrt{2}} (|+ + +\rangle + |- - -\rangle)
\]
Which of the following sets of errors can be detected on this state?

**Options:**  
- [ ] \( XII, IXI, IIX \)  
- [ ] \( IZI, ZIZ \)  
- [ ] \( ZII, IZI, IIZ \)  
- [ ] \( ZII, IZZ, ZZZ \)  

**Solution:**  

- \( XII, IXI, IIX \): These are \( X \)-type errors that flip signs in the \( |-\rangle \) basis and cannot be detected in this case, as all lead to the same state. 
- \( IZI, ZIZ \): These are \( Z \)-type errors, In this particular set of gates, they also lead to non-distinct states and cant be distinguished.
- \( ZII, IZI, IIZ \): These set of gates on the other hand produce distinct states that can be distinguished.
- \( ZII, IZZ, ZZZ \): These lead to non-distinct states and cant be distinguished.  

**Final Answer:**  
✔ \( ZII, IZI, IIZ \)  

---

Q9) Consider the *phase-flip* noise process, wherein the state of the qubit gets transformed by the \( Z \) operator with probability \( p \) and remains unaffected with probability \( 1 - p \). If the qubit is initially in the \( |-\rangle \) state, which of the following correctly describes the final noisy state?

**Options:**  
- [ ] \( \sqrt{p} |+\rangle + \sqrt{1 - p} |-\rangle \)  
- [ ] \( p |+\rangle \langle +| + (1 - p) |-\rangle \langle -| \)  
- [ ] Density matrix in computational basis  
  \[
  \begin{pmatrix} 
  \frac{1}{2} (1 - 2p) & \frac{1}{2} \\ 
  \frac{1}{2} & \frac{1}{2} 
  \end{pmatrix}
  \]
- [ ] Density matrix in computational basis  
  \[
  \begin{pmatrix} 
  \frac{1}{2} & \frac{1}{2} (2p - 1) \\ 
  \frac{1}{2} (2p - 1) & \frac{1}{2} 
  \end{pmatrix}
  \]

**Solution:**  

- The phase-flip noise applies a \( Z \) operator with probability \( p \), which maps \( |-\rangle \) to \( |+\rangle \) with probability \( p \), while with probability \( 1 - p \), it remains \( |-\rangle \).  
- The density matrix in the \( |+\rangle, |-\rangle \) basis is given by:
  \[
  \rho = (1 - p) |-\rangle \langle -| + p |+\rangle \langle +|
  \]
- Converting to the computational basis, the correct density matrix corresponds to:  
  \[
  \begin{pmatrix} 
  \frac{1}{2} & \frac{1}{2} (2p - 1) \\ 
  \frac{1}{2} (2p - 1) & \frac{1}{2} 
  \end{pmatrix}
  \]

**Final Answer:**  

Density matrix in computational basis  
  \[
  \begin{pmatrix} 
  \frac{1}{2} & \frac{1}{2} (2p - 1) \\ 
  \frac{1}{2} (2p - 1) & \frac{1}{2} 
  \end{pmatrix}
  \]

---

Q10) Suppose the syndrome bits at the end of the 3-qubit QEC code are observed to be \( s_1 = 1 \) and \( s_2 = 0 \). What is the correct error diagnosis?

**Options:**  
- [ ] None of the three qubits were affected by a bit-flip error.  
- [ ] Only the first qubit was affected by a bit-flip error.  
- [ ] Only the second qubit was affected by a bit-flip error.  
- [ ] Only the third qubit was affected by a bit-flip error.  

**Solution:**    

- The 3-qubit bit-flip code detects errors using two parity checks:  
  \[
  s_1 = q_1 \oplus q_2, \quad s_2 = q_2 \oplus q_3
  \]
  where \( \oplus \) denotes XOR.  
- Given \( s_1 = 1 \) and \( s_2 = 0 \), we analyze:  
  - \( s_1 = 1 \) means \( q_1 \) and \( q_2 \) differ.  
  - \( s_2 = 0 \) means \( q_2 \) and \( q_3 \) are the same.  
  - This implies that only \( q_1 \) is flipped.  

**Final Answer:**   

Only the first qubit was affected by a bit-flip error.

---
