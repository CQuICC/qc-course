## Assignment 3

**Q1**: Recall that the Bloch sphere representation of a quantum state is parameterized by two angles θ and ϕ such that a normalised qubit state can be represnted as $|\psi\rangle = \cos(\frac{\theta}{2})|0\rangle + e^{i\phi}\sin(\frac{\theta}{2})|1\rangle$. What are the values of θ and ϕ for the state $\begin{pmatrix} \frac{1}{\sqrt{2}} \\ \frac{1+i}{2} \end{pmatrix}$?

**Options**:
- θ = π/4, φ = 0
- θ = π/2, φ = π/8
- θ = π/4, φ = π/4
- θ = π/2, φ = π/4

**Solution**: The Bloch sphere representation of a qubit state is given by:

$|\psi\rangle = \cos(\frac{\theta}{2})|0\rangle + e^{i\phi}\sin(\frac{\theta}{2})|1\rangle$

Comparing this with the given state:

$(\frac{1}{\sqrt{2}}, \frac{1+i}{2})^T = (\cos(\frac{\theta}{2}), e^{i\phi}\sin(\frac{\theta}{2}))^T$

We can deduce:
$\cos(\frac{\theta}{2}) = \frac{1}{\sqrt{2}} \implies \theta = \frac{\pi}{2}$

$e^{i\phi}\sin(\frac{\theta}{2}) = \frac{1+i}{2} \implies \phi = \frac{\pi}{4}$

**Answer**: θ = π/2, φ = π/4

---

**Q2**: Which of the following pairs of two-qubit states are mutually orthogonal?

**Options**:
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), |00\rangle\}$
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)\}$
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), |01\rangle\}$
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)\}$

**Solution**: Two states are orthogonal if their inner product is zero. Let's check each pair:

1. $\langle 00|\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) = \frac{1}{\sqrt{2}} \neq 0$
2. $(\frac{1}{\sqrt{2}}(\langle 00| + \langle 11|))(\frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)) = 0$
3. $\langle 01|\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) = 0$
4. $(\frac{1}{\sqrt{2}}(\langle 00| + \langle 11|))(\frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)) = \frac{1}{2} - \frac{1}{2} = 0$

**Answer**:
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), \frac{1}{\sqrt{2}}(|01\rangle + |10\rangle)\}$
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), |01\rangle\}$
- $\{\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle), \frac{1}{\sqrt{2}}(|00\rangle - |11\rangle)\}$

---

**Q3**: Which of the following gate identities are correct?

**Options**:
- HXH = -Z
- HYH = -Y
- HTH = R_x(π/4)
- HZH = X

**Solution**: Let's verify each identity, taking $H = \begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix}$ and $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$:

HXH = $\begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} = Z \neq -Z$

Similarly we can verify the other identities and get the following results:

**Answer**:
- HYH = -Y
- HTH = $R_x(π/4)$
- HZH = X

---

**Q4**: Which of the following states are physically equivalent to $|\psi\rangle = \cos\frac{\pi}{6}|0\rangle + e^{i\pi}\sin\frac{\pi}{6}|1\rangle$?

**Options**:
- $e^{i\frac{\pi}{2}}\cos\frac{\pi}{6}|0\rangle + e^{i\frac{3\pi}{2}}\sin\frac{\pi}{6}|1\rangle$
- $\cos\frac{\pi}{6}|0\rangle + e^{i\frac{\pi}{2}}\sin\frac{\pi}{6}|1\rangle$
- $-\cos\frac{\pi}{6}|0\rangle - e^{i\pi}\sin\frac{\pi}{6}|1\rangle$
- $\cos\frac{\pi}{3}|0\rangle + e^{i\pi}\sin\frac{\pi}{3}|1\rangle$

**Solution**: Two quantum states are physically equivalent if they differ only by a global phase. The original state is:

$|\psi\rangle := \cos\frac{\pi}{6}|0\rangle + e^{i\pi}\sin\frac{\pi}{6}|1\rangle \Leftrightarrow \cos\frac{\pi}{6}|0\rangle - \sin\frac{\pi}{6}|1\rangle$

Comparing with the options:
1. This differs by a global phase of $e^{i\frac{\pi}{2}}$, so it's equivalent.
2. This has a different relative phase between |0⟩ and |1⟩, so it's not equivalent.
3. This differs by a global phase of -1, so it's equivalent.
4. This has different amplitudes, so it's not equivalent.

**Answer**:
- $e^{i\frac{\pi}{2}}\cos\frac{\pi}{6}|0\rangle + e^{i\frac{3\pi}{2}}\sin\frac{\pi}{6}|1\rangle$
- $-\cos\frac{\pi}{6}|0\rangle - e^{i\pi}\sin\frac{\pi}{6}|1\rangle$

---

**Q5**: What is the output of the following circuit when the input qubit is initialized to |0⟩?

$ H \rightarrow H \rightarrow X \rightarrow X \rightarrow
  H \rightarrow H \rightarrow X \rightarrow X \rightarrow X \rightarrow
  H \rightarrow X \rightarrow H \rightarrow X \rightarrow H$

**Options**:
- |1⟩
- |+⟩
- |0⟩
- |-⟩

**Solution**: We can simplify by cancelling out all pairs of H gates and X gates: $ H \rightarrow H = I$, $X \rightarrow X = I$. The circuit reduces to:

$ X \rightarrow H \rightarrow X \rightarrow H \rightarrow X \rightarrow H$

We can then apply the identities studied in the previous questions: $HXH = Z$, $HZH = X$. The circuit simplifies to:

$ X \rightarrow Z \rightarrow X \rightarrow H$

**Answer**: |+⟩

---

**Q6**: What is the tensor product expansion of the 3-qubit state |-1+⟩?

**Options**:
- $\frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 1 \\ 0 \\ -1 \\ 0 \\ 1 \\ 0 \\ -1 \end{pmatrix}$
- $\frac{1}{{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 1 \\ 0 \\ 0 \\ -1 \\ -1 \end{pmatrix}$
- $\frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 1 \\ 0 \\ 0 \\ -1 \\ -1 \end{pmatrix}$
- $\frac{1}{{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \\ 0 \\ 0 \\ 0 \\ -1 \end{pmatrix}$

**Solution**: The state |-1+⟩ can be expanded as:

$|-1+\rangle = |-\rangle \otimes |1\rangle \otimes |+\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}$

Expanding this tensor product gives:

**Answer**: $\frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 1 \\ 0 \\ 0 \\ -1 \\ -1 \end{pmatrix}$


---

**Q7**: Consider the following single-qubit rotation gates:

$R_x(\theta) = \begin{pmatrix} \cos(\theta/2) & -i\sin(\theta/2) \\ -i\sin(\theta/2) & \cos(\theta/2) \end{pmatrix}$,
$R_y(\theta) = \begin{pmatrix} \cos(\theta/2) & -\sin(\theta/2) \\ \sin(\theta/2) & \cos(\theta/2) \end{pmatrix}$,
$R_z(\theta) = \begin{pmatrix} e^{-i\theta/2} & 0 \\ 0 & e^{i\theta/2} \end{pmatrix}$.

The Hadamard gate can be realized as a sequence of gates of the form $e^{i\phi}R_z(\alpha)R_x(\theta)R_z(\beta)$. Identify the values of φ, α, θ, and β.

**Options**:
- φ = π/4, α = β = π, θ = π/2
- φ = 0, α = β = π/2, θ = π/4
- φ = π/4, α = β = π/2, θ = π/4
- φ = π/2, α = β = θ = π/2

**Solution**: The Hadamard gate is defined as:

$H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$

We need to find values such that:

$e^{i\phi}R_z(\alpha)R_x(\theta)R_z(\beta) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$

Expanding the right side:

$e^{i\phi}\begin{pmatrix} e^{-i\alpha/2} & 0 \\ 0 & e^{i\alpha/2} \end{pmatrix}\begin{pmatrix} \cos(\theta/2) & -i\sin(\theta/2) \\ -i\sin(\theta/2) & \cos(\theta/2) \end{pmatrix}\begin{pmatrix} e^{-i\beta/2} & 0 \\ 0 & e^{i\beta/2} \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$

Rather than solving the equation by multiplication and matching coefficients, it is much easier to see from trial and error that the Hadamard gate can be realized with the following values:

**Answer**: φ = π/2, α = β = θ = π/2

---

**Q8**: Which of the following gate sequences adds a relative phase of π/2 between |0⟩ and |1⟩?

**Options**:
- $H \rightarrow X \rightarrow S$
- $S \rightarrow S \rightarrow S \rightarrow S \rightarrow S$
- $X \rightarrow Y \rightarrow Z \rightarrow Z$
- $H \rightarrow X \rightarrow Y$

**Solution**: The matrix representation of the S gate is: $S = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}$. Let's analyze each sequence:

1. $H \rightarrow X \rightarrow S$: This sequence applies a Hadamard gate, followed by a Pauli-X gate, and then a S gate. The S gate adds a relative phase of π/2 between |0⟩ and |1⟩.
2. $S \rightarrow S \rightarrow S \rightarrow S \rightarrow S$: This sequence applies the S gate five times, which adds a relative phase of 5π/2 between |0⟩ and |1⟩.
3. $X \rightarrow Y \rightarrow Z \rightarrow Z$: This sequence applies a Pauli-X gate, followed by a Pauli-Y gate, and then two Pauli-Z gates. The Pauli-Z gate adds a relative phase of π between |0⟩ and |1⟩.

**Answer**: $H \rightarrow X \rightarrow S$, $S \rightarrow S \rightarrow S \rightarrow S \rightarrow S$ are both correct.

---

**Q9**: Which of the following circuits transforms the input state |00⟩ to the entangled state $\frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$?

**Options**:
- $H(0) → CNOT(0, 1)$
- $X(0) → CNOT(0, 1)$
- $H(1) → CNOT(1, 0)$
- $CNOT(0, 1) → H(0)$

**Answer**: Both a) and c) are correct. The Hadamard gate creates a superposition of |0⟩ and |1⟩ on the first qubit, and the CNOT gate entangles the two qubits.

---

**Q10**: Recall that the cnot gate is a two-qubit gate that flips the state of the second (target) qubit if and only if the state of the first (control) qubit is |1⟩. Which of the following statements about the cnot are correct?

**Options**:
- In tensor product notation, the cnot gate can be represented as I ⊗ X.
- In tensor product notation, the cnot gate can be represented as |0⟩⟨0|⊗I+|1⟩⟨1|⊗ X.
- Two successive applications of the cnot leads to an identity gate on two qubits.
- The cnot gate cannot be written as a tensor product of two single-qubit gates.

**Solution**: Let's analyze each statement:

1. Incorrect. I ⊗ X would apply X to the target qubit regardless of the control qubit's state.
2. Correct. This representation accurately describes the CNOT operation.
3. Correct. CNOT = CNOT dagger, the gate is its own inverse.
4. Correct. The CNOT gate is an entangling gate and cannot be decomposed into single-qubit operations.

**Answer**:
- In tensor product notation, the CNOT gate can be represented as |0⟩⟨0|⊗I + |1⟩⟨1|⊗ X.
- Two successive applications of the CNOT leads to an identity gate on two qubits.
- The CNOT gate cannot be written as a tensor product of two single-qubit gates.