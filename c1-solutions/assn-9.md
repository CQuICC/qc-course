## Assignment 9

**Q1** Which of these problems do we expect a quantum computer to solve exponentially faster than a classical computer?

**Options**:
- Given an oracle to a function $f$ which is guaranteed to be constant or balanced, figure out deterministically with probability 1 whether it is constant or balanced.
- Given an oracle to a function $f$ which is guaranteed to be of the form $f(x)=a \cdot x$ for some $a$, find that $a$.
- Prime factorization of a number which is a product of two primes.
- Given an oracle to a function $f$ which is guaranteed to have the property $f(x \oplus a)=f(x)$ for some $a$, find that $a$.

**Solution**:
Classical query complexity for DJ algorithm is $2^{n-1}+1$, whereas Quantum algorithm for DJ algorithm requires only one query to the oracle, hence giving an exponential speedup with respect to a corresponding classical algorithm.
Classically for prime factoring is an exponentially hard problem and takes $\mathcal{O}(e^{(\log N)^{1/3}})$ time, whereas the complexity for the Quantum factoring algorithm is of $Poly(\log N)$ order.
Simon's problem was the first evidence for a quantum algorithm (with query complexity of $\mathcal{O}(n)$) giving exponential speedup over its classical $(\mathcal{O}(n))$ counterpart.

**Answer**:v
1. Given an oracle to a function $f$ which is guaranteed to be constant or balanced, figure out deterministically with probability 1 whether it is constant or balanced.

2. Prime factorization of a number which is a product of two primes.

3. Given an oracle to a function $f$ which is guaranteed to have the property $f(x \oplus a)=f(x)$ for some $a$, find that $a$.


---



**Q2**: Consider the quantum circuit shown blow. What is the probability for at least one of the first three wires to output 1 when measured at the end of this circuit?

**Options**:
- $1/8$
- $1/4$
- $1$
- $0$

**Solution**: This is the quantum circuit for the DJ algorithm with the two CNOTs implementing the oracle $U_f$. Starting with $|\psi_1\rangle=|0001\rangle$, we get $|\psi_2\rangle=|+\rangle|+\rangle|+\rangle|-\rangle$ after the Hadamard operations. Because of the phase kickback, $|\psi_3\rangle=|-\rangle|+\rangle|+\rangle|-\rangle$ after the first CNOT. After the second CNOT $|\psi_4\rangle=|-\rangle|-\rangle|+\rangle|-\rangle$. After passing throught the final Hadamard, the state becomes $|\psi_5\rangle=|110\rangle|-\rangle$. Probability of observing 1 in atleast one of the three wires is 1 and the function $f$ is balanced.

**Answer**: 1


---



**Q3**: What state does the following circuit evaluate to?

**Options**:
- $|-1+-\rangle$
- $\frac{1}{\sqrt{2}}(|-10-\rangle+|+11-\rangle)$
- $-|+1+-\rangle$
- $|+1+-\rangle$


**Solution**:
$$
\begin{align*}
|\psi_1\rangle &= |0101\rangle \longrightarrow |\psi_2\rangle = |+1+-\rangle \longrightarrow |\psi_3\rangle = |-1+-\rangle \\
&\longrightarrow |\psi_4\rangle = |-1--\rangle \longrightarrow |\psi_5\rangle= |-1+-\rangle
\end{align*}
$$

**Answer:** $|-1+-\rangle$

---


**Q4**: Given a quantum oracle $U_f$ whose action is given by $U_f∣x\rangle∣y\rangle=∣x\rangle∣y \oplus f(x)\rangle$, for some Boolean function $f(x)$. Suppose, there exists a polynomial-sized quantum circuit that implements the oracle $U_f$, which of the following tasks can be performed more efficiently on a quantum processor in comparison with a classical computer?

**Options:**
- Identifying whether the function $f$ is one-to-one or many-to-one.
- Evaluating the period of the function $f$
- Evaluating $f(x_i)$ for different input strings $x_i$
- All of the above


**Solution**: The problem of determining whether $f$ is one-to-one or many-to-one is equivalent to that of Simon's problem where $f(x) = f(x \oplus a)$. Quantum algorithm for the problem gives an exponential speedup over classical algorithm.
Quantum period finding algorithm gives exponential speedup over classical period finding.
However, evaluating value of $f(x_i)$ takes only one query classically for each $x_i$ and quantum circuit does not give any better efficiency.

**Answers**:
1. Identifying whether the function $f$ is one-to-one or many-to-one
1. Evaluating the period of the function $f$


---


**Q5**: Given a quantum oracle that evaluates a t-bit Boolean function $f$ which is guaranteed to be of the form $f(x)=a\cdot x$ for some t-bit string a, what is the number of qubits required to find a?

**Options**:
- $t$ data qubits and $t$ ancilla qubits
- $2^t$ data qubits and 1 ancilla qubit
- The same number of qubits as required to determine whether the $t$-bit Boolean function is constant or balanced
- $t$ data qubits and 1 ancilla qubit

**Solution**: In Bernstein-Vazairani problem, we use the same quantum circuit as that of the DJ algorithm in which the number of ancilla qubit is 1. For $a$ being a t-bit string, $x$ is also of t-bits. Therefore, we need t-bit data qubits for the input $x$.


**Answer**:
1. The same number of qubits as required to determine whether the $t$-bit Boolean function is constant or balanced
2. $t$ data qubits and 1 ancilla qubit


---


**Q6**: Consider the quantum phase estimation algorithm to estimate the eigenvalue of a 2-qubit unitary U, corresponding to eigenstate $∣u\rangle$.  Suppose we wish to estimate the phase to an accuracy of 2 bits, so the algorithm requires exactly 2 data qubits and 2 ancilla qubits. Which of the following correctly describes the state of the 4 qubits before the inverse Quantum Fourier Transform is applied?

**Options**:
- $\sum_{j=1,2} |j\rangle U^{2^j}|u\rangle$
- $\frac{1}{2}\sum_{j=0}^3 |j\rangle U^j |u\rangle$
- $\frac{1}{2}\sum_{j=0}^3 |j\rangle U^{2^j} |u\rangle$
- None of the above


**Solution**: Before applying the QFT, the data qubits will be in the state QFT $|\phi_1 \phi_2\rangle$ where $\phi = \phi_1 \phi_2$ is the phase that determines the eigenvalue of U. In phase estimation, the ancilla qubits are prepared in state $|u\rangle$. After applying the operator U, the state of ancilla does not change. Therefore, state of the all the qubits before applying QFT is
$$
\begin{align*}
&(\frac{|0\rangle +e^{4\pi i \phi}|1\rangle}{\sqrt{2}|1})\otimes (\frac{|0\rangle +e^{2\pi i \phi}|1\rangle}{\sqrt{2}})\otimes |u\rangle  \\
= &\frac{1}{2}(|00\rangle + e^{2\pi i\phi}|01\rangle + e^{2\pi (2i\phi)}|10\rangle + e^{2\pi i(3\phi)}|11\rangle ) \otimes |u\rangle \\
= & \frac{1}{2}(|00\rangle|u\rangle + |01\rangle U|u\rangle  + |10\rangle U^2|u\rangle + |11\rangle U^3|u\rangle ) \\
= & \frac{1}{2}(|0\rangle|u\rangle + |1\rangle U|u\rangle  + |2\rangle U^2|u\rangle + |3\rangle U^3|u\rangle ) \\
= & \frac{1}{2}\sum_{j=0}^3 |j\rangle U^j |u\rangle
\end{align*}
$$

**Answer**: $\frac{1}{2}\sum_{j=0}^3 |j\rangle U^j |u\rangle$

---


**Q7**: Consider the order-finding algorithm, for a pair of numbers $x<N$, where $N=2^n$. Let
U
U denote the unitary transformation that acts on the computational basis states of the n-qubit space, as, $U|y\rangle = |(xy)mod\, N\rangle$. Which of the following correctly describes the state of the t data qubits and the n acillary qubits, before the inverse quantum Fourier transform is applied?

**Options**:
- $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{2^{t}-1}|j\rangle U^j|1\rangle$
- $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{2^t-1}|j\rangle(U^j)^2|1\rangle$
- $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{2^t-1}|j\rangle\left|x^j \bmod N\right\rangle $
- $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{t-1}|j\rangle U^j|1\rangle $

**Solution**:
Order finding is essentially QPE algorithm for finding the eigenvalues of U. Since we do not know the eigenstates $|u\rangle$ is prior, we initialise the ancilla qubits in superposition of all the $|u\rangle$ states which is state $|1\rangle$.

**Answer**:
1. $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{2^{t}-1}|j\rangle U^j|1\rangle$
2. $|\psi\rangle=\frac{1}{\sqrt{N}} \sum_{j=0}^{2^t-1}|j\rangle\left|x^j \bmod N\right\rangle $

---


**Q8**: A sum of the form $S= 1+r+r^2+\cdots+r^{(n-1)}$ is called a geometric series. For any $r\neq 1$, the sum of n terms evaluates to $$S=\frac{1-r^n}{1-r}$$
Use this to evaluate the sum of the phases that occur in the quantum order-finding algorithm, and pick the correct answer(s):

**Options**:
- $\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}}=r$, for any integral value of $k$.
- $\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}}=r$, if $k=0$
- $\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}}=0$, for any $k \neq 0$
- $\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}}=0\ \forall\ k$

**Solution**:
For k=0,

$$
\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}} = \sum_{s=0}^{r-1}1 = r
$$

For $k\neq 0$,

$$
\begin{align*}
\sum_{s=0}^{r-1} e^{\frac{-2 \pi i s k}{r}} &=
1
+ e^{\frac{-2 \pi i k}{r}}
+ e^{\frac{-2 \pi i (2k)}{r}} + \cdots
+ e^{\frac{-2 \pi i (r-1)k}{r}}\\
&= \frac{1- e{\frac{-2 \pi i k}{r}}^r}{1- e^{-\frac{2 \pi i k}{r}}}\\
&= \frac{1- e^{-2 \pi i k}}{1- e{\frac{-2 \pi i k}{r}}}\\
&= 0    \qquad\qquad\qquad\qquad (\because k=1,2,\cdots r)
\end{align*}
$$

**Answer**:
1. $\sum_{s=0}^{r-1} e{\frac{-2 \pi i s k}{r}}=r$, if $k=0$
2. $\sum_{s=0}^{r-1} e{\frac{-2 \pi i s k}{r}}=0$, for any $k \neq 0$


---


**Q9**: Given a quantum oracle that evaluates a t-bit Boolean function $f$ which is guaranteed to be of the form $f(x)=f(a\oplus x)$ for some t-bit string $a$, what is the number of qubits required to find $a$?

**Options**:
- $t$ data qubits and $t$ ancilla qubits
- $2^t$ data qubits and 1 ancilla qubit
- The same number of qubits as required to determine whether the t-bit Boolean function is constant or balanced.
- $t$ data qubits and 1 ancilla qubit.

**Solution**:
In Simon's problem, the quantum circuit has same number of data and ancilla qubits which is equal to the length of the bit string used to represent the numbers $x$ and $a$. Therefore, we need $t$ data qubits and $t$ ancilla qubits to find $a$ using Simon's algorithm.

**Answer**:
1. $t$ data qubits and $t$ ancilla qubits