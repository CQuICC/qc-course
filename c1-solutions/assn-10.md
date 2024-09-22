## Assignment 10

**Q1**. Consider an array having 4 elements. The Grover search algorithm is used to search for a single marked element, given access to an oracle. What is the probability of success if a measurement is directly performed on the initial state ?

**Options**:
- $\frac{1}{4}$
- $\frac{1}{2}$
- $\frac{1}{3}$
- $1$

**Solution**: E qually weigthed superposition state:$$|\Psi \rangle = \sqrt{\frac{N-M}{N}}|\alpha\rangle_{NS} + \sqrt{\frac{M}{N}}|\beta\rangle_{S}$$
Here N=4, M=1
$$|\Psi \rangle = \sqrt{\frac{3}{4}}|\alpha\rangle_{NS} + \sqrt{\frac{1}{4}}|\beta\rangle_{S} $$
$\therefore$ probability of succes = $|\text{coefficient of }|\beta\rangle |^2 = \frac{1}{4}$

**Answer** : $\frac{1}{4}$

---


**Q2**. What is the probability of success after applying the oracle and reflection operator once? (with reference to **Q1**)

**Options**:
- $\frac{1}{4}$
- $\frac{1}{2}$
- $\frac{1}{3}$
- $1$

**Solution**: After applying the grover oracle and reflection oeprator once, the state becomes:
$$
\hat{G} |\Psi\rangle = \cos\left(\frac{3}{2}\theta\right)|\alpha\rangle + \sin\left(\frac{3}{2}\theta\right)|\beta\rangle
$$
$\cos\frac{\theta}{2} = \sqrt{\frac{N-M}{N}} = \frac{\sqrt{3}}{2} \implies \frac{\theta}{2}=\frac{\pi}{6} \implies \theta = \frac{\pi}{3}$

$\therefore \cos\left(\frac{3\theta}{2}\right)=cos(\frac{\pi}{2})=0, \quad \sin(\frac{\pi}{2})=1$

Probability of success = $|\text{coefficient of }|\beta\rangle |^2 = 1$

**Answer** : $\frac{1}{4}$

---

**Q3**. What is the probability of success after applying oracle and reflection operator twice? (with reference to **Q1**)

**Options**:
- $\frac{1}{4}$
- $\frac{1}{2}$
- $\frac{1}{3}$
- $1$

**Solution**: After applying the grover oracle and reflection oeprator once, the state becomes
$$
\hat{G} |\Psi\rangle = \cos\left(\frac{5}{2}\theta\right)|\alpha\rangle + \sin\left(\frac{5}{2}\theta\right)|\beta\rangle
$$

$\theta = \frac{\pi}{3}$ (from previous soltn.)


$\cos\left(\frac{5\theta}{2}\right)=cos(\frac{5\pi}{6})=-\frac{\sqrt{3}}{2}, \quad \sin(\frac{5\pi}{6})=\frac{1}{2}$

Probability of success = $|\text{coefficient of }|\beta\rangle |^2 = \frac{1}{4}$

**Answer**: $\frac{1}{4}$

---

**Q4**. Suppose $|01\rangle$ is the solution state in a search space of $N=4$. How many Grover iterations are required to reach the solution state?

**Options**:
- 2
- 1
- 0.5
- Solution state cannot be reached

**Solution**: M=1, N=4
$\newcommand{\ceil}[1]{\lceil {#1} \rceil}$

$\cos(\theta /2)=\frac{\sqrt{3}}{2} \implies \theta = \frac{\pi}{3} $

Number of Grover iterations required: $$R=\lceil\frac{\cos^{-1}(\sqrt{\frac{M}{N}})}{\theta}\rceil = \lceil\frac{\cos^{-1}(\sqrt{\frac{1}{4}})}{\frac{\pi}{3}}\rceil = 1$$

**Answer**: 1

---

**Q5**. For a solution state $|01\rangle$ with search space N=4, We start the Grover algorithm with a uniform superposition state given by $$|\psi\rangle=\frac{1}{N^{1 / 2}} \sum_{x=0}^{N-1}|x\rangle$$

**Options**:
- $|\alpha\rangle=[|00\rangle+|10\rangle+|11\rangle], \beta=|01\rangle,|\psi\rangle=\frac{\sqrt{3}}{2}|\alpha\rangle+\frac{1}{2}|\beta\rangle $
- $\alpha\rangle=[|00\rangle+|10\rangle+|11\rangle], \beta=|01\rangle,|\psi\rangle=\frac{\sqrt{3}}{2}|\beta\rangle+\frac{1}{2}|\alpha\rangle $
- $|\alpha\rangle=\frac{1}{\sqrt{3}}[|00\rangle+|10\rangle+|11\rangle], \beta=|01\rangle,|\psi\rangle=\frac{\sqrt{3}}{2}|\alpha\rangle+\frac{1}{2}|\beta\rangle $
- $|\alpha\rangle=\frac{1}{\sqrt{3}}[|00\rangle+|10\rangle+|11\rangle], \beta=|01\rangle,|\psi\rangle=\frac{\sqrt{3}}{2}|\beta\rangle+\frac{1}{2}|\alpha\rangle $

Which of the following is the correct representation of the uniform superposition in terms of the solution state and the non- solution state?

**Solution**: $$|\psi \rangle = \sqrt{\frac{N-M}{N}}|\alpha\rangle + \sqrt{\frac{M}{N}}|\beta\rangle$$

Here, M=1, N=4. Solution $|\beta\rangle=|01\rangle$ and non-solution state $|\alpha\rangle = \frac{1}{\sqrt{3}}\left[|00\rangle + |10\rangle + |11\rangle\right]$, and
$$|\psi \rangle = \frac{\sqrt{3}}{2}|\alpha\rangle + \frac{1}{2}|\beta\rangle$$

**Answer**: $|\alpha\rangle=\frac{1}{\sqrt{3}}[|00\rangle+|10\rangle+|11\rangle], \beta=|01\rangle,|\psi\rangle=\frac{\sqrt{3}}{2}|\alpha\rangle+\frac{1}{2}|\beta\rangle $

---

**Q6**. The Grover iterate operation is given by the operator $G= (2|\psi\rangle\langle\psi| - I)O$ where $\psi$ is the equally weigthed superposition state and $O$ is the oracle. Consider again a solution state $|01\rangle$ with search space N=4. Which of the following is right?

**Options**:
- $G^2∣\psi⟩$ does a rotation by $30\degree$ towards the solution state but does not reach the solution.
- $G^2∣\psi⟩$ does a rotation by $60\degree$ towards the solution state and transforms $|\psi\rangle$ to the state $|01\rangle$
- $G∣\psi⟩$ does a rotation by $30\degree$ towards the solution state but does not reach the solution.
- $G∣\psi⟩$ does a rotation by $60\degree$ towards the solution state and transforms $|\psi\rangle$ to the state $|01\rangle$

**Solution**:
Application of $G$ on $|psi\rangle$, rotates the state by an angle $\theta$, where $|\psi \rangle = \sqrt{\frac{N-M}{N}}|\alpha\rangle + \sqrt{\frac{M}{N}}|\beta\rangle=\frac{\sqrt{3}}{2}|\alpha\rangle + \frac{1}{2}|\beta\rangle$ and $$\cos(\theta /2)=\frac{\sqrt{3}}{2} \implies \theta = \frac{\pi}{3} = 60\degree$$
$$\begin{align*}\hat{G} |\Psi\rangle &= \cos\left(\frac{3}{2}\theta\right)|\alpha\rangle + \sin\left(\frac{3}{2}\theta\right)|\beta\rangle\\
&= \cos\left(\frac{\pi}{2}\right)|\alpha\rangle + \sin\left(\frac{\pi}{2}\right)|\beta\rangle = |\beta\rangle
\end{align*}$$
$\therefore$ After applying $G$, the $|\psi\rangle$ transforms to the solution state $|01\rangle$.

**Answer**: $G∣\psi⟩$ does a rotation by $60\degree$ towards the solution state and transforms $|\psi\rangle$ to the state $|01\rangle$

---


**Q7**. Consider the Grover search algorithm over a database of $N$ elements with a single marked element $a$. What is the time complexity of Grover’s search?

**Options**:
- $O(\sqrt{N})$
- $O(N)$
- $O(\log{N})$
- $O(N^2)$

**Solution**: Grover's algorithm achieves a quadratic speedup, allowing it to search in $O(N)$ time, whereas the Classical search algorithms would require $O(N)$ queries to find the marked element.

**Answer**: $O(\sqrt{N})$

---


**Q8**. How many qubits are needed to implement Grover’s search on $N$ elements?

**Options**:
- $O(\sqrt{N})$
- $O(N)$
- $O(\log{N})$
- $O(N^2)$

**Solution**: n qubits can represent $2^n = N$ number of states. Therefore $n=\log_2N $ number of qubits are required to do grover search on a search space of size $N$.

**Answer**: $O(\log{N})$

---


**Q9**. Consider a Grover search with a single marked element. Suppose the initial state makes an angle of $\theta=15\degree$ with the non-solution axis ($|\alpha\rangle$-axis). Then what is the largest number of iterations that keeps the state in the first quadrant?

**Options**:
- 1
- 2
- 3
- 4


**Solution**:
Grover iteration rotates the state by $2\theta = 30\degree$.
$$\theta^\prime = 15\degree+30\degree = 45\degree$$
After second iteration rotation, angle with the $|\alpha\rangle$-axis:
$$\theta^{\prime\prime} = 45\degree + 30\degree = 75\degree$$

$\therefore$ maximum two iterations can be performed to keep the state in first quadrant.

**Answer**: 2

---


**Q10**. In Q9, what is the angle made after the above number of iterations?

**Options**:
- $30\degree$
- $45\degree$
- $60\degree$
- $75\degree$

**Solution**: After two iterations, $\theta^{\prime\prime}=75\degree$ as calculated in the previous solution

**Answer**: $75\degree$