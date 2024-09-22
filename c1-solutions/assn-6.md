## Assignment 6

**Q1**: Consider an algorithm which contains two nested for loops, each running over n iterations. As n is increased to infinity, what is the time complexity of this algorithm?

**Options**:
- $O(exp n)$
- $O(n^2)$
- $O(n!)$
- $O(\log n)$

**Solution**: The outer loop runs n times, and for each iteration of the outer loop, the inner loop also runs n times. This results in n * n = n^2 total iterations. As n approaches infinity, the dominant term is n^2.

$(x + n)^2 = x^2 + 2nx + n^2$ or for large n, $O(n^2)$

**Answer**: $O(n^2)$

---

**Q2**: Consider the following compare and swap algorithm.

```py
for j=1 to n - 1
  for k = j+1 to n
    compare-and-swap (j, k)
  end k
end j
```


What is the number of operations required by this algorithm?


**Options**:
- $O(n^2)$
- $O(\log n!)$
- $O(n \log n)$
- $O(2^n)$

**Solution**: $j, k$ traverse over one triangle of the matrix, and the number of operations is proportional to the number of elements in the triangle. The number of elements in the triangle is $n(n-1)/2$, which is $O(n^2)$. Therefore, the number of operations required by this algorithm is $O(n^2)$.

**Answer**: $O(n^2)$

---

**Q3**: A given problem can be verified efficiently on a classical computer. Which complexity class does this problem belong to?

**Options**:
- $NP$
- $P$
- $O(1)$
- $O(n)$

**Solution**: A problem that can be verified efficiently on a classical computer belongs to the complexity class $NP$, which therefore also implies $P$.

**NOTE:** while in practice algorithms which are $O(n), O(1)$ can be easily checked, the question is about the complexity class and not any measure of time complexity.

**Answer**: $NP$, $P$

---

**Q4**: How many queries to a quantum oracle are required to solve the Deutsch-Jozsa problem for a function that takes an input of size n qubits?

**Options**:
- logarithmic
- linear
- N
- 1

**Solution**: The Deutsch-Jozsa algorithm is a quantum algorithm that can determine whether a given function is constant or balanced using only one query to the quantum oracle, regardless of the input size n. This demonstrates quantum speedup over classical algorithms.

**Answer**: 1

---

**Q5**: Consider the two-qubit Hadamard gate $H^{\otimes 2} = H \otimes H$. Which of the following statements correctly describes the action of this gate?

**Options**:
- The output is always a uniform superposition of all four computational basis states, irrespective of the input state.
- If the input state is $|0\rangle|0\rangle$, the output state is a uniform superposition of all four computational basis states.
- If the input state is $|1\rangle|1\rangle$, the output state is a uniform superposition of all four computational basis states.
- The output is a uniform superposition of all four computational states iff the input state is $|0\rangle|0\rangle$.

**Solution**: The two-qubit Hadamard gate $H^{\otimes 2}$ applies a Hadamard transform to each qubit independently. When applied to $|0\rangle|0\rangle$, it produces a uniform superposition of all four computational basis states. Same for $|1\rangle|1\rangle$. If the input however is already $|+\rangle|+\rangle$ superposition, the output will be $|0\rangle|0\rangle$.

**Answer**:
- If the input state is $|0\rangle|0\rangle$, the output state is a uniform superposition of all four computational basis states.
- If the input state is $|1\rangle|1\rangle$, the output state is a uniform superposition of all four computational basis states.

---

**Q6**: A milk company delivers milk to a set of cities. They want to find the shortest possible route that visits all cities and returns to the starting point. To what complexity class does this problem belong?

**Options**:
- $P$
- $NP$
- $NP$-hard
- linear

**Solution**: This problem is known as the Traveling Salesman Problem (TSP). It is a well-known $NP$-hard problem. While it's easy to verify a given solution (making it part of $NP$), finding the optimal solution becomes exponentially more difficult as the number of cities increases. There is no known polynomial-time algorithm to solve it optimally for all cases.

**Answer**: $NP$-hard

---

**Q7**: Which part of a Turing Machine coordinates the operation of the machine?

**Options**:
- program
- finite state control
- tape
- read-write tape head

**Solution**: In a Turing Machine, the finite state control (also known as the control unit) coordinates the overall operation. It contains the set of states and transition rules that determine how the machine moves between states, reads and writes on the tape, and moves the tape head.

**Answer**: finite state control

---

**Q8**: A possible problem which can be solved on a Turing Machine might not be solvable on the best available computers today. What are the possible reasons for this?

**Options**:
- A Turing Machine has lesser number of parts than our classical computer.
- The Turing Machine can calculate functions which cannot be calculated using a classical computer.
- A Turing Machine is an idealized device and so will be more efficient than a classical computer.
- The class of functions computable by a Turing Machine is greater than the class of functions computable using a classical algorithm.?

**Solution**: A Turing Machine is a theoretical model of computation that can calculate functions that cannot be calculated using a classical computer. The turing machine has infinite memory.

**Answer**: A Turing Machine is an idealized device and so will be more efficient than a classical computer.

---

**Q9**: Consider the 4-qubit circuit shown below. What is the probability for at least one of the first 3 wires to output |0⟩ when measured at the end of this circuit?

(refer to assignment for the circuit diagram)

**Options**:
- 1/8
- 1/4
- 1
- None of the above

**Solution**: Probability of AT LEAST $|0\rangle$ on first 3 qubits = 1 - Probability of NONE of the first 3 qubits being $|0\rangle$ = 1 - Probability of all 3 qubits being $|1\rangle$

**Answer**: 1

---

**Q10**: Consider the Deutsch-Jozsa algorithm for an n-bit Boolean function. Which of the following statements describe the working of the algorithm correctly?

**Options**:
- The algorithm evaluates a **global** property of the function – one that is not specific to a given input string – via a single query to the oracle.
- The algorithm evaluates a **local** property of the function – one that is specific to a given input string – via a single query to the oracle.
- The number of Hadamard gates required to run the algorithm scales linearly with the input size.
- The number of ancillary qubits required to run the algorithm scales linearly with the input size

**Answer**:
- The algorithm evaluates a **global** property of the function – one that is not specific to a given input string – via a single query to the oracle.
- The number of Hadamard gates required to run the algorithm scales linearly with the input size.