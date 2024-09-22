## Assignment 11

**Q1**: Let us consider a quantum anonymous transmission protocol with three players. After the application of phase flip by one of the players, say Alice, all the players apply a Hadamard transform on their respective state. The application of the Hadamard transform on the quantum state results in

**Options**:
1. $\frac1{\sqrt2}[(|0\rangle + |1\rangle)^{\otimes 3} + (|0\rangle - |1\rangle)^{\otimes 3}]$
2. $\frac1{\sqrt2}[|+\rangle^{\otimes 3} + (-1)^d|-\rangle^{\otimes 3}]$
3. $\frac1{\sqrt{2^{n+1}}}[|+\rangle^{\otimes 3} + (-1)^d|-\rangle^{\otimes 3}]$
4. $\frac1{\sqrt2}[(|0\rangle + |1\rangle)^{\otimes 3} + (-1)^d(|0\rangle - |1\rangle)^{\otimes 3}]$
**Solution**:
The state after the phase flip is given by $|\psi\rangle = \frac1{\sqrt2}[|0\rangle^{\otimes 3} + (-1)^d|1\rangle^{\otimes 3}]$. When all players then apply the Hadamard gate, the resultant state is simply given by: $H^{\otimes 3}|\psi\rangle = \frac1{\sqrt2}[|+\rangle^{\otimes 3} + (-1)^d|-\rangle^{\otimes 3}]$

**Answer**:
$\frac1{\sqrt2}[|+\rangle^{\otimes 3} + (-1)^d|-\rangle^{\otimes 3}]$

---

**Q2**: In an anonymous transmission involving $n$ players, the global transformation when the $i^{th}$ player applies the phase flip operation is

**Options**:
1. $U_i = I^{\otimes (n-i)} \bigotimes \sigma_x^{\otimes i}$
2. $U_i = \sigma_z^{\otimes n}$
3. $U_i = I^{\otimes (n-1)} \bigotimes \sigma_z$
4. $U_i = I^{\otimes (i-1)} \bigotimes \sigma_z \bigotimes I^{\otimes (n-i)}$

**Solution**:
The phase flip operation is done through the $\sigma_z$ operator by the $i^{th}$ player and the remaining players do not do any operation (i.e. Identity operations)

This means the global transformation will be of the form: $U_i = I^{\otimes (i-1)} \bigotimes \sigma_z \bigotimes I^{\otimes (n-i)}$

**Answer**:
$U_i = I^{\otimes (i-1)} \bigotimes \sigma_z \bigotimes I^{\otimes (n-i)}$

---

**Q3**: To obtain a traceless anonymous transmission when n players are involved, the resources needed are:
**Options**:
1. A pair of Hadamard gates
2. A reliable broadcast channel
3. A n-qubit GHZ state
4. An X-gate operated by one of the players
**Solution**:
The only resource needed for a traceless anonymous transmission for $n$ players is a n-qubit GHZ state.

**Answer**:
A n-qubit GHZ state

---

**Q4**: A transmission protocol remains secure if an adversary has the access to all the resources in the protocol. This property is referred to as

**Option**:
1. Traceless
2. Anonymity
3. Both traceless and anonymity
4. Neither traceless nor anonymity
**Solution**:
This is the definition of the traceless property of the protocol

**Answer**:
Traceless

---

**Q5**: In the Dining Cryptographers protocol if any one of the diners has paid the bill

**Options**:
1. There are odd number of 0’s.
2. There are even number of 1’s
3. There are even number of 0’s.
4. There are odd number of 1’s.

**Solution**:
After taking the XOR operation of all the values, If the resultant number is 1, then condition for one of the diner to have paid the bill is satisfied. This will be possible only when there is an odd number of 1's.

**Answer**:
There are odd number of 1’s.

---

**Q6**: In the Quantum anonymous transmission protocol, the transmitted information is of

**Options**:
1. Classical bits
2. Quantum bits in the Z-basis
3. Quantum bits in the X-basis
4. Quantum bits in the Z-basis which is transformed to the bits in the X-basis using a Hadamard operation.
**Solution**:
The transmitted information in the Quantum anonymous transmission protocol if of the form of classical bits.

**Answer**:
Classical bits

---

**Q7**: Let us consider a quantum teleportation protocol in which Alice is the sender and Bob is the receiver. After the application of CNOT gate and the Hadamard gate, the probability of Bob's state being $(\alpha|0\rangle + \beta|1\rangle)$ is

**Options**:
1. $1$
2. $0.5$
3. $0.25$
4. $0.333$

**Solution**:
After the application of the CNOT and Hadamard gate, on measurement the state collapses to one of four bell states out of which only one of them would correspond to $(\alpha|0\rangle + \beta|1\rangle)$ without any changes. Therefore, the probability is 0.25

**Answer**:
0.25

---

**Q8**: The quantum teleportation protocol achieves the following:

**Options**:
1. Alice has transferred a qubit state physically to Bob.
2. Alice transferred a physical qubit securely and anonymously.
3. The qubit transfer process is traceless.
4. Only quantum information is transferred from Alice to Bob and there is no transfer of physical qubit.

**Solution**:
In the quantum teleportation protocol, the only information transferred is the state of Alice's qubit and not the physical qubit itself and that is the main objective of the protocol.

**Answer**:
Only quantum information is transferred from Alice to Bob and there is no transfer of physical qubit.

---

**Q9**: Choose the correct response:

**Options**:
1. Quantum teleportation aims to transfer two bits of classical information.
2. Super dense coding transfers two classical bits of information using one qubit state.
3. Quantum teleportation and Super dense coding are complementary in their aim.
4. Quantum teleportation and Quantum anonymous transmission are complementary in their aim.

**Solution**:
1. Quantum teleportation does not aim to transfer two bits of classical information (that is superdense coding).
2. Super dense coding does transfer two classical bits of information using one qubit state.
3. By looking at the objectives of both Quantum teleportation and Super dense coding, it is apparent that one is the compliment of the other.
4. Quantum teleportation and Quantum anonymous transmission are not complementary in their aim.

**Answer**:
Super dense coding transfers two classical bits of information using one qubit state.

Quantum teleportation and Super dense coding are complementary in their aim.

---
**Q10**: In super dense coding one qubit is being used to transfer two classical bits of information. This is due to

**Options**:
1. Shared entanglement between the sender Alice and the receiver Bob.
2. The role of quantum gates.
3. The conditional security of the protocol.
4. None of the above.
**Solution**:
This is possible because Alice and Bob share an entangled qubit, through which two classical bits of information can be transferred.

**Answer**:
Shared entanglement between the sender Alice and the receiver Bob.