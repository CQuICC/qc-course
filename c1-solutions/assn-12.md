## Assignment 11

**Q1**: What is the basis of RSA algorithm?

**Options**:
* Prime number factorization
* Elliptic curve schemes
* Lattice-based schemes
* Dijkstra's algorithm

**Solution**: RSA's security **relies** on the computational hardness of factoring the product of two large prime numbers (known as integer factorization problem subset of hidden subgroup problem).

**Answer**: Prime number factorization

---

**Q2**: Which encryption method can be used for private key cryptography?

**Options**:
* Bitwise XOR
* Bitwise AND
* Bitwise OR
* Bitwise NAND

**Solution**: When you XOR a value with a key twice, you get back the original value: $(A ⊕ K) ⊕ K = A$. Other bitwise operations are not reversible. This is one of the reasons why it is often said XOR has memory.

**Answer**: Bitwise XOR

---

**Q3**: Which of the following is not a quantum cryptography protocol?

**Options**:
* Quantum key distribution
* Quantum secret sharing
* Quantum teleportation
* Quantum secure direct communication

**Solution**: While quantum teleportation is a quantum information protocol, it's not specifically a cryptography protocol. It may be *used* to create some cryptographic protocols, but it's not a cryptographic protocol itself.

**Answer**: Quantum teleportation

---

**Q4**: What components are needed in BB84 protocol?

**Options**:
* A quantum channel
* A classical channel
* A single photon source
* A single photon detector

**Solution**: BB84 protocol requires all these components:
1. Quantum channel: For transmitting quantum states
2. Classical channel: For post-processing and verification
3. Single photon source: To generate individual photons
4. Single photon detector: To measure received photons
Each component is essential for the protocol's security and functionality.

**Answer**: All correct

---

**Q5**: Which statement is *not true* for quantum key distribution?

**Options**:
1. Used for private key cryptography
2. Can be implemented with product states
3. Ekert-91 is a QKD protocol based on entangled states
4. BB84 is not proven unconditionally secure against arbitrary attack

**Solution**: BB84 has been mathematically proven to be unconditionally secure against arbitrary attacks when implemented perfectly. It is worth noting that in recent years there have been contentions to this claim.

**Answer**: BB84 is not proven unconditionally secure against arbitrary attack is false

---

**Q6**: What is true for states transmitted in BB84 protocol?

**Options**:
1. Four states needed
2. All states are orthogonal
3. States belong to two mutually unbiased bases
4. Key sifting is independent of the basis for preparing and measuring states

**Solution**: BB84 requires:
1. Four distinct states (|0⟩, |1⟩, |+⟩, |-⟩)
2. These states come from two mutually unbiased bases (computational and Hadamard)
The states within each basis are orthogonal, but states from different bases are not. Key sifting depends on basis matching.

**Answer**:
1. Four states needed
3. States belong to two mutually unbiased bases

---

**Q7**: What is true about the quantum circuit shown in the question?

**Options**:
1. Used to measure state in arbitrary basis
2. Default qiskit measurement operator measures in X basis
3. If measurement result is |+⟩, is measured in Z basis
4. Equivalent to quantum circuit for measurement setup of Bob in BB84 protocol

**Solution**: The circuit shown matches Bob's measurement setup in BB84 protocol, where he needs to measure incoming qubits in either the computational (Z) or Hadamard (X) basis. The Hadamard gate before measurement allows switching between these bases.

**Answer**: Equivalent to quantum circuit for measurement setup of Bob in BB84 protocol

---

**Q8**: In BB84, to establish a key of length n, what should be the approximate number of raw bits needed?

**Options**:
1. $n$
2. $2n$
3. $n/2$
4. $4n$

**Solution**: In BB84:
1. ~50% of bits are lost due to basis mismatch
2. ~25% (of total sent) are used for error checking
3. Additional overhead for privacy amplification (optional, not mentioned in the original protocol)
Therefore, to get n final key bits, $>4n$ raw bits need to be transmitted.

**Answer**: $4n$

---

**Q9**: Which statements are true for HBB quantum secret sharing (QSS) scheme?

**Options**:
1. It is an entanglement-based QSS scheme
2. Identical keys are generated for all three parties
3. There exists no classical analog of quantum secret sharing
4. The X and Y basis used for measurement are not mutually unbiased

**Solution**: The HBB scheme uses entangled GHZ states to share secrets among parties, making it an entanglement-based protocol. The other statements are false: classical secret sharing exists, bases are mutually unbiased, and keys aren't necessarily identical.

**Answer**: It is an entanglement-based QSS scheme

---

**Q10**: For a GHZ state $\frac{1}{\sqrt{2}}(|000⟩ + |111⟩)_{ABC}$ shared among three parties, if A and B measure in X basis and get same results, what will be C's state?

**Options**:
1. $\frac{1}{\sqrt{2}}(|0⟩ - |1⟩)$
2. $\frac{1}{\sqrt{2}}(|0⟩ + |1⟩)$
3. Any one of (1) or (2)
4. None of the above

**Solution**: When A and B measure in X basis and get same results, due to GHZ state properties and entanglement correlations, C's particle will collapse to the state $\frac{1}{\sqrt{2}}(|0⟩ + |1⟩)$. This follows from the measurement postulates and the original GHZ state structure.

**Answer**: $\frac{1}{\sqrt{2}}(|0⟩ + |1⟩)$