**Q10**: In the quantum teleportation protocol, Alice and Bob share the entangled state $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$. Let $m$ be the measurement outcome of the state being teleported, and $n$ be Alice's measurement outcome. Which gates must Bob apply to recover the state $|\psi\rangle$?

**Options**:
- $\sigma_x^{1-n} \sigma_z^{1-m}$
- $\sigma_x^n \sigma_z^m$
- $\sigma_x^{1-n} \sigma_z^m$
- $\sigma_x^n \sigma_z^{1-m}$

**Solution**: We have state $|\psi\rangle = \alpha|0\rangle + \beta |1\rangle$, which is tensored with the given shared state $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$. Therefore we have

$$
\begin{align*}
|\psi\rangle \otimes |\Psi^-\rangle\\
= \alpha|0\rangle + \beta |1\rangle \otimes \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)\\
= \frac{1}{\sqrt{2}} [
  \alpha(|001\rangle - |010\rangle) + \beta(|101\rangle - |110\rangle)
]
\end{align*}
$$

We then apply a bell state measurement on this with a CNOT and Hadamard gate.

$$
\begin{align*}
H_0 \otimes CX_{01} \otimes |\psi\rangle \otimes |\Psi^-\rangle\\
= H_0 \otimes \frac{1}{\sqrt{2}} [
  \alpha(|001\rangle - |010\rangle) + \beta(|111\rangle - |100\rangle)
]\\
= \frac12 [
  \alpha(|001\rangle - |101\rangle - |010\rangle - |110\rangle)
  + \beta(|001\rangle - |111\rangle - |000\rangle + |100\rangle)
] \\
= \frac12 [
    |00\rangle(\alpha|1\rangle - \beta|0\rangle)
  + |10\rangle(\alpha|1\rangle + \beta|0\rangle)
  + |01\rangle(-\alpha|0\rangle + \beta|1\rangle)
  + |11\rangle(-\alpha|0\rangle - \beta|1\rangle)
]
\end{align*}
$$

We can see our measurement table is:

| Bits | Gates |
|------|-------|
| 00   | $ZX$  |
| 01   | $X$   |
| 10   | $Z$   |
| 11   | $I$   |

Therefore we need to apply: $\sigma_x^{1-n} \sigma_z^{1-m}$

**Answer**: $\sigma_x^{1-n} \sigma_z^{1-m}$

---

**Q11**: In the classical worst case, how many times would you need to select a card from a well-shuffled standard deck of cards (52 total) to find the Ace of Spades?

**Options**:
- $\sqrt{52}$ times
- $\log(52)$ times
- $52^2$ times
- $(52-1)$ times

**Solution**: You need to check 51 cards. Assuming no tricks or Joker the Ace of Spades will be the last card.

**Answer**: $(52-1)$ times

---

**Q12**: Using a quantum algorithm, approximately how many times would you need to select a card from a well-shuffled standard deck of cards (52 total) to find the Ace of Spades?

**Options**:
- 52 times
- $\log(52)$ times
- $\frac{52}{2}$ times
- $(52-1)$ times

**Solution**: Grover's search requires $\mathcal{O}(\sqrt{N})$ queries to find the target item in an unstructured search problem. Therefore assuming this problem can be mapped to a Grover search, the number of queries would be $\sqrt{52}$.

**Answer**: $\sqrt{52}$ times

---

**Q13**: Which quantum algorithm enables this speed-up in searching?

**Options**:
- Deutsch-Josza Algorithm
- Grover's Search
- Shor's Algorithm
- Bernstein-Vazirani Algorithm

**Solution**: Grover's search algorithm provides a quadratic speedup for unstructured search problems, reducing the search complexity from linear to square root.

**Answer**: Grover search

---

**Q14**: Find the output of the given quantum circuit:

```txt
       ┌───┐
|1>: ┤  H   ├──■──
       └───┘┌─┴─┐
|1>: ─────┤   X   ├
                     └───┘
```

**Options**:
- $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$
- $\frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)$
- $\frac{1}{\sqrt{2}}(|01\rangle - |10\rangle)$
- $\frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)$

**Solution**: Dry run the circuit to determine the output state based on the initial state and the quantum gates applied. Or you can use the Qiskit code to simulate the circuit.

**Answer**: $\frac{1}{\sqrt{2}}(|01\rangle - |10\rangle)$

---

**Q15**: (refer to quiz for circuit)

<!-- # |++1-> -->
<!-- # -1/rt(2) [ |-01-> + |+11-> ] -->
<!-- # 1/2 [ |001-> - |011-> - |101-> + |111-> ] -->

**Options**:
- $|++1-\rangle$
- $-\frac{1}{\sqrt{2}}(|-01-\rangle + |+11-\rangle)$
- $\frac12 (|001-\rangle - |011-\rangle - |101-\rangle + |111-\rangle)$
- None of the above

**Solution**: The fastest way is the run the circuit via `StatevectorSimulator` in Qiskit and calculate the `state_fidelity` with the expected state. One example is:

```py
qc = # create the circuit

statevector = backend.run(qc).result().get_statevector()
statevector.draw('latex')

# |++1->
_pp1m = minus.tensor(ket_1).tensor(plus).tensor(plus)

print(state_fidelity(statevector, _pp1m)) # 0.25, we expect 1
```

**Answer**:
- $-\frac{1}{\sqrt{2}}(|-01-\rangle + |+11-\rangle)$

---

**Q16**: Which of the following codes implements the logical OR gate on the first two qubits and gives the result on the third qubit?

**Options**:
- ```py
  ORgate = QuantumCircuit(3,1)
  ORgate.ccx(0,1,2)
  ORgate.measure(2,0)
  ```
- ```py
  ORgate = QuantumCircuit(3,1)
  ORgate.cx(0,2)
  ORgate.ccx(0,1,2)
  ORgate.measure(2,0)
  ```
- ```py
  ORgate = QuantumCircuit(3,1)
  ORgate.cx(1,2)
  ORgate.ccx(0,1,2)
  ORgate.measure(2,0)
  ```
- ```py
  ORgate = QuantumCircuit(3,1)
  ORgate.cx(1,2)
  ORgate.cx(0,2)
  ORgate.ccx(0,1,2)
  ORgate.measure(2,0)
  ```

**Answer**:
```py
ORgate = QuantumCircuit(3,1)
ORgate.cx(1,2)
ORgate.cx(0,2)
ORgate.ccx(0,1,2)
ORgate.measure(2,0)
```

---

**Q17**: In a 7-qubit circuit, what is the probability for all of the first 6 wires to output 0 when measured?

(Refer to the quiz for the circuit)

**Options**:
- 1/64
- 1/2
- 0
- 1

**Solution**: When applied to $|+\rangle$, since its values are all ones, the $X$ gate switching the columns around will still result in all ones. Therefore for the plus state, $X$ acts as the identity.

**Answer**: 1

---

**Q18**: In another 7-qubit circuit, what is the probability for all of the first 6 wires to output 0 when measured?

(Refer to the quiz for the circuit)

**Options**:
- 1/64
- 1/2
- 0
- 1

**Solution**: Run it on qiskit for fastest solution. When dry running be careful of the phase kickback given to the respective qubits. Resultant state will be $|1100001\rangle$.

**Answer**: 0

---

**Q19**: Consider a Grover search for N = 2, that is, a search over the two-bit space {00, 01, 10, 11}. Which of the following can be used as an oracle that can mark the element 11?.

**Options**:
- $\begin{pmatrix} 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}$
- $\begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & -1 & 0 & 0 \\ 0 & 0 & -1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}$

**Solution**: You can multiply out with all possible two qubit states and verify trivially that the oracle (B) will add a phase of -1 to the state $(0 0 0 1)$.

**Answer**:
- $\begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$

---

**Q20**: Identify the circuit diagram corresponding to the oracle for marking 11:

(Refer to the quiz for the options)

**Solution**: It's clear the circuit will have to be CZ gates between the qubits 0 and 1. You may verify all cases by making a truth table for the oracle.

**Answer**: (B)

---

**Q21**: For $U|0\rangle = \alpha|0\rangle + \beta|1\rangle$, what quantum operation should be applied to recover $U|0\rangle$ at the last qubit when the measurement results of the first 3 qubits is 000?

(refers to the quiz for the circuit)

**Options**:
- I gate
- H gate
- X gate
- Z gate

**Answer**: I gate

---

**Q22**: For the quantum circuit with code fragment:
```py
qc = QuantumCircuit(1)
qc.x(0)
qc.ry(5*pi/8, 0)
```
What is the probability that a measurement of the final state would result in |1⟩?

**Options**:
- 0.25
- 0.31
- 0.47
- 0.69

**Solution**: With the state $(0 1)$ i.e $|1\rangle$ when multiplied by the $R_y$ gate:

$$
\begin{pmatrix}
\cos(5\pi/16) & -\sin(5\pi/16) \\
\sin(5\pi/16) & \cos(5\pi/16)
\end{pmatrix} \cdot
\begin{pmatrix}
0 \\
1
\end{pmatrix} = \begin{pmatrix}
-\sin(5\pi/16) \\
\cos(5\pi/16)
\end{pmatrix}
$$

**Answer**: $\cos(5\pi/16)^2 \approx 0.308 \approx 0.31$

---

**Q23**: What is the circuit depth of the following circuit after transpilation and maximum possible optimization on the 'QASM' simulator?
```py
qc = QuantumCircuit(3)
qc.ccx(0,1,2)
```

**Options**:
- 1
- 5
- 10
- 11

**Solution**: Run
```py
qc = QuantumCircuit(3)
qc.ccx(0,1,2)
qc = qc.decompose()

print(qc.draw())
```

**Answer**: 11

---

**Q24**: A truck travels to set of n cities and returns to the starting point. From the knowledge of the list of cities and the distance between them, if we were to find the shortest possible route and return to the starting point, what class does this problem belong to?

**Options**:
- $\mathbb{O}(n)$
- $\mathbb{O}(n^n)$
- $\mathbb{O}(\log(n))$
- $\mathbb{O}(e^n)$

**Solution**: This describes the Traveling Salesman Problem, which is known to be an NP-hard problem. In general it is of the order of $O(n!)$, making the "most appropriate" answer $O(n^n)$ (via Stirling's approximation). There however do exist algorithms that can solve it in $O(n^2 2^n)$ via dynamic programming.

**Answer**: $\mathbb{O}(n^n)$

---

**Q25**: Identify the correct complexity inequalities from the set given below. Here,
$\mathbb{O}(f(n)) > \mathbb{O}(g(n))$ means the complexity of $f(n)$ is greater than that of $g(n)$.

**Options**:
- $\mathbb{O}(n^b) > \mathbb{O}(n^n) > \mathbb{O}(1), for b < n$
- $\mathbb{O}(1) > \mathbb{O}(\log(n)) > \mathbb{O}(n\log(n)), for b < n$
- $\mathbb{O}(n!) > \mathbb{O}(e^n) > \mathbb{O}(n^b), for b < n$
- $\mathbb{O}(b^n) > \mathbb{O}(n!) > \mathbb{O}(n\log(n)), for b > 1$

**Solution**: The strictly correct way of comparing any two $O(f(x)), O(g(x))$ is to take the $\frac{f(x)}{g(x)}$ and see if it converges to a constant, infinity, or zero. However for a fast answer we can just substitute $10^100$ (a googol) for $n$ and see which one grows the fastest. An example of the strict way is:

$$
\begin{align*}
\lim_{n \to \infty} \frac{n!}{e^n} =
\lim_{n \to \infty} \frac{\sqrt{2\pi n}(\frac{n}{e})^n}{e^n} =
\lim_{n \to \infty} \frac{n^n}{e^{2n}} =
\lim_{n \to \infty} \left(\frac{n}{e^{2}}\right)^n = \infty
\end{align*}
$$

**Answer**: Clearly $\mathbb{O}(n!) > \mathbb{O}(e^n) > \mathbb{O}(n^b), \forall b < n$

---

**Q26**: What is the output state and depth of the given circuit?

**Options**:
- |0001⟩ and depth=10
- |0100⟩ and depth = 4
- |0100⟩ and depth = 12
- |0001⟩ and depth = 11

**Solution**: Each SWAP gate decomposes into 3 CNOT gates. And since here none of the CNOTs will combine into a single layer or cancel out we get a depth of $4\times3=12$.

**Answer**: |0100⟩ and depth = 12