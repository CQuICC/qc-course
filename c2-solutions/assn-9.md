## Assignment 9

**Q1**: Which among the following is not a concern for quantum machine learning although it is a general limitation of NISQ devices?

**Options**:

1. Less number of qubits  

2. Noise  

3. Interference time  

4. Qubit connectivity  

**Solution**:  

While noise is a general limitation of NISQ devices, it is not necessarily a direct concern specific to quantum machine learning (QML) in the same way other hardware issues are. QML algorithms are often designed to be robust to noise or to even exploit it in certain scenarios, such as variational quantum algorithms that can tolerate a degree of noise during training.

In contrast, Less number of qubits, qubit connectivity, and interference time are direct limitations that restrict the scalability and depth of QML models and circuits.

**Final Answer**: 

Noise.

---

**Q2**: Which of the following comes under quantum enhanced machine learning?

**Options**:

1. Quantum Support Vector Machine (QSVM)  

2. Variation Quantum Classifier (VQC)  

3. Tensor Networks  

4. Quantum Boltzmann Machine (QBM)  

**Solution**:  

Quantum-enhanced machine learning leverages quantum algorithms or quantum resources to potentially improve classical machine learning tasks. Here's how the options fit:

1. **Quantum Support Vector Machine (QSVM)**: Yes – it's a quantum-enhanced version of the classical SVM using quantum kernels or circuits.  

2. **Variation Quantum Classifier (VQC)**: Yes – it uses parameterized quantum circuits for classification tasks.  

3. **Tensor Networks**: No – although powerful in modeling quantum systems and useful in classical ML, they are not inherently quantum-enhanced unless specifically implemented on quantum hardware.  

4. **Quantum Boltzmann Machine (QBM)**: Yes – a quantum version of the Boltzmann machine that uses quantum properties to model probability distributions.

**Final Answer**: 

1, 2, 4.

---

**Q3**: Which among the following is one of the key requirements to gain practical advantage from Quantum Support Vector Machines?

**Options**:

1. Kernel is easy to compute classically  

2. Kernel is hard to compute classically  

3. Data is easily separable in higher dimensions  

4. Data is not easily separable in higher dimensions  

**Solution**:  

Quantum Support Vector Machines (QSVMs) aim to use a quantum computer to compute a kernel (quantum kernel) that captures complex data relationships not easily accessible by classical means. This provides a potential quantum advantage, but only if the quantum kernel cannot be efficiently approximated classically.

**Final Answer**: 

Kernel is hard to compute classically.

---

**Q4**: What is superdense coding?

**Options**:

1. A method to send quantum information via quantum information channels  

2. A method to send classical information via classical channels  

3. A method to send classical information via quantum information channels  

4. A method to send quantum information via classical channel  

**Solution**:  

Superdense coding is a quantum communication protocol that allows the transmission of two classical bits of information by sending only one qubit, using pre-shared entanglement between the sender and the receiver. This technique exploits the entanglement of quantum systems to enhance the capacity of quantum communication channels for classical information.

**Final Answer**: 

A method to send classical information via quantum information channels.

---

**Q5**: In what configuration should Bob apply CNOT gate and Hadamard gate in order to decode the information sent by Alice?

**Options**:

1. CNOT with control on Alice qubit and target on Bob qubit, Hadamard on Alice qubit  

2. CNOT with control on Bob qubit and target on Alice qubit, Hadamard on Alice qubit  

3. CNOT with control on Alice qubit and target on Bob qubit, Hadamard on Bob qubit  

4. CNOT with control on Bob qubit and target on Alice qubit, Hadamard on Bob qubit  

**Solution**:  

In the standard quantum dense coding, to decode the qubit, Bob typically needs to reverse the encoding operations done by Alice. Alice encodes information using Pauli operations, and Bob decodes it by applying a CNOT gate (control on Alice qubit, target on Bob qubit) followed by a Hadamard gate on the Alice qubit.

This disentangles the Bell state and allows measurement in the computational basis to retrieve the classical bits sent by Alice.

**Final Answer**:  

CNOT with control on Alice qubit and target on Bob qubit, Hadamard on Alice qubit.

---

**Q6**: Identify true statements among the following.

**Options**:

1. High variance leads to underfitting  

2. High variance leads to overfitting  

3. High bias leads to underfitting  

4. High bias leads to overfitting  

**Solution**:  

- High variance occurs when a model is too complex and fits the training data too closely, capturing noise. This leads to **overfitting** (Option 2 is true).
- High bias occurs when a model is too simple to capture the underlying pattern in the data. This leads to **underfitting** (Option 3 is true).


**Final Answer**:  

2. High variance leads to overfitting.

3. High bias leads to underfitting.

---

**Q7**: What purpose does cost function serve in machine learning model?

**Options**:

1. To calculate learning rate of model  

2. To divide the training data into batches  

3. To calculate the metrics of the model  

4. To optimize the parameters of the model  

**Solution**:  

The cost function in a machine learning model is used to measure how well the model's predictions match the actual values. It provides a quantitative measure of error or loss, which is minimized during training. Optimizers use the cost function's output to adjust the model parameters (e.g., weights) to improve performance. Thus, it helps optimize the parameters of the model.

Other options are incorrect:

- The learning rate is a hyperparameter, not derived from the cost function.
- Dividing data into batches is related to training strategy (e.g., mini-batch gradient descent).
- Model metrics (like accuracy, precision) are evaluation metrics, not the same as the cost function.

**Final Answer**:  

To optimize the parameters of the model.

---

**Q8**: What does kernel trick do in support vector machine?

**Options**:

1. Regularizes the model  

2. Optimizes the cost function  

3. Projects data into higher dimensions  

4. Optimizes for parameters of the model  

**Solution**: 

The kernel trick in Support Vector Machines (SVMs) is a technique that allows the algorithm to operate in a higher-dimensional space without explicitly computing the coordinates of the data in that space. This is useful for making non-linearly separable data linearly separable in the new space. The kernel function computes the inner products between data points in this higher-dimensional feature space efficiently.

**Final Answer**:  

Projects data into higher dimensions.

---

**Q9**: Define ansatz in variational quantum classifier.

**Options**:

1. A quantum circuit with trainable parameters  

2. A quantum circuit to apply measurement in desired bases  

3. A quantum circuit for error suppression  

4. A quantum circuit to encode classical data into quantum states  

**Solution**:  

In a variational quantum classifier (VQC), an **ansatz** refers to a parameterized quantum circuit that is used to represent the model. The parameters of the ansatz are adjusted (trained) using classical optimization techniques to minimize a cost function, much like weights in classical machine learning models.

Its main purpose is to act as the model's hypothesis space in the variational algorithm, enabling learning by tuning the parameters.

**Final Answer**:  

A quantum circuit with trainable parameters.

---

**Q10**: What is angle encoding?

**Options**:

1. Encode classical data to computational basis state  

2. Encode classical data in amplitudes of quantum state  

3. Encode classical data in angles of rotational gates  

4. Encode classical data in entangled circuit where angles of rotation gates depend on product of input feature spaces  

**Solution**:  

Angle encoding (also called parametric encoding or rotational encoding) is a method used in quantum machine learning where classical data is encoded into the quantum state by applying rotational gates (e.g., RX, RY, RZ) with angles proportional to the input data values. This approach is widely used because it is hardware-efficient and relatively simple to implement.

Other options:

- Option 1 refers to basis encoding.
- Option 2 refers to amplitude encoding.
- Option 4 is more aligned with feature map encoding used in quantum kernel methods.

**Final Answer**:  

Encode classical data in angles of rotational gates.

---
