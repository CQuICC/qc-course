## Assignment 2

**Q1**: Choose the zero duration, zero error gate for a fixed frequency transmon qubit (qubits discussed in the qiskit demo uploaded on week 10)

**Options**:
1. RX Gate
2. RY Gate
3. RZ Gate
4. CNOT Gate


**Solution**:
In the context of fixed-frequency transmon qubits, the RZ gate can be implemented with effectively zero duration and zero error by simply adjusting the phase of the microwave control pulses, rather than physically manipulating the qubit. The other gates (RX, RY, and CNOT) involve physical manipulations and generally have finite durations and associated errors.

**Answer**:
RZ Gate

---

**Q2**: A user cannot send a signal from the classical control hardware to a qubit through which of the following channel?

**Options**:
1. Pulse Channel
2. Drive Channel
3. Measure Channel
4. Acquire Channel


**Solution**:
The Acquire Channel is not used to send signals to the qubit. Instead, it is used to acquire and process the measurement results from the qubit. Thus, a user cannot send a signal to a qubit via the Acquire Channel.

**Answer**:
Acquire Channel

---

**Q3**: Cross-resonance pulse is played on which channel?

**Options**:
1. Control Channel
2. Drive Channel
3. Measure Channel
4. Pulse Channel


**Solution**:
The Cross-Resonance (CR) pulse is used to implement two-qubit gates, such as the CNOT gate, in superconducting qubits. The CR pulse is applied to one qubit (the control qubit) to induce a conditional effect on a neighboring qubit (the target qubit). The Control Channel is specifically designed for operations that require interactions between multiple qubits, such as the cross-resonance interaction.

**Answer**:
Control Channel

---

**Q4**: While transforming an anharmonic oscillator to a qubit, we had ignored the higher energy levels. If we were to access the higher level through pulse control, you would have to optimise for which of the following parameter?

**Option**:

1. Frequency of the RF pulse
2. Resonance of the RF pulse
3. Beats of the RF pulse
4. None of the above


**Solution**:
When transforming an anharmonic oscillator (like a transmon) into a qubit, we typically focus on the two lowest energy levels ($|0\rangle$ and $|1\rangle$) and ignore higher levels ($|2\rangle$, $|3\rangle$, etc.). To access those higher energy levels, you need to apply a radio frequency (RF) pulse at a frequency that matches the transition between the desired energy levels.

The transitions are governed by the energy difference between the levels. In an anharmonic oscillator, these differences are not evenly spaced, meaning the frequency needed to excite $|0\rangle \rightarrow |1\rangle$ will differ from $|1\rangle \rightarrow |2\rangle$, and so on.

Frequency of the RF pulse must be tuned to match the specific transition you want to access (e.g., $f_{01}$ for $|0\rangle \rightarrow |1\rangle$, $f_{12}$ for $|1\rangle \rightarrow |2\rangle$).

**Answer**:
Frequency of the RF pulse

---

**Q5**: Which of the following gates can be implemented using pulse programming?

**Options**:
1. Any 1 qubit gate
2. Cross resonance entangling gate
3. Any 1 qubit gate and a cross resonance entangling gate
4. None of the above

**Solution**:
Pulse programming allows direct control over the microwave pulses that manipulate qubits and can be used to implement any one qubit gate as well as a cross resonance entangling gate.

**Answer**:
Any 1 qubit gate and a cross resonance entangling gate

---

**Q6**: Let us say that the frequency for a resonant qubit is $\omega_1$ and the associated resonator has a resonant frequency $\omega_2$. Which of the following operation depend on $\omega_2$?

**Options**:
1. X Gate
2. Y Gate
3. Measurement
4. RX Gate


**Solution**:
The resonant frequency of the resonator ($\omega_2$) is primarily involved in the measurement of the qubit state.

During measurement, the qubit state ($|0\rangle$ or $|1\rangle$) shifts the frequency of the resonator slightly due to the dispersive coupling between the qubit and the resonator. This shift in the resonator frequency is detected to infer the qubit state.

**Answer**:
Measurement

---

**Q7**: In a multi-pulse, multi-qubit circuit, the order of execution of the pulses should be:
**Options**:
1. The order of execution doesn’t matter as the operations are performed on different channels.
2. The control channel instructions have to be played before the drive channel instructions.
3. The drive channel instructions should be played before the control channel instructions.
4. None of the above

**Solution**:
1. "The order of execution doesn’t matter as the operations are performed on different channels": Incorrect, because timing coordination is important for proper circuit execution, even across independent channels.
2. "The control channel instructions have to be played before the drive channel instructions": Incorrect, as this is not always true—it depends on the circuit's design.
3. "The drive channel instructions should be played before the control channel instructions": Also incorrect, as the sequence depends on the specific gate or operation.

**Answer**:
None of the above

---

**Q8**: To universally control an n-qubit quantum computer, a complete set of gates can be made from (made from implies that any operation on this quantum computer can be decomposed as the combination of elements of this set):
i. Performing arbitrary one qubit gate

ii. Performing two-qubit X-OR gate

iii. Performing n-qubit X-OR gate

iv. Performing n-qubit CNOT gate

**Options**:
1. (i) only
2. (i), (iv) only
3. (ii), (iii) only
4. (i), (ii) only


**Solution**:
To universally control an n-qubit quantum computer, a universal gate set is required. A universal gate set must allow for any unitary operation to be decomposed as a combination of its elements. The minimal requirements are:
Arbitrary single-qubit gates (i): These allow for the manipulation of individual qubits to any desired state. They are essential for achieving universality.

Two-qubit entangling gates (ii): The two-qubit X-OR gate (or CNOT gate) is an entangling gate. When combined with single-qubit gates, it is sufficient to perform any operation on an n-qubit system.

**Answer**:
(i), (ii) only

---

**Q9**: The classical control hardware to generate the pulses and base frequency is kept at which stage of the golden chandelier ( $K$ = Kelvin):
**Options**:
1. 15 $mK$ along with the qubits
2. 1 $K$ with Liquid Helium bath
3. 40 $K$ with the copper tubes
4. Not kept inside the golden chandelier

**Solution**:
The classical control hardware responsible for generating pulses and base frequencies is typically not kept inside the golden chandelier (dilution refrigerator). This hardware includes microwave sources, and other control electronics that are typically kept at room temperature.

**Answer**:
Not kept inside the golden chandelier

---
**Q10**: Let us say, we have a 5 qubit quantum computer with the qubits lying in a linear fashion as shown in the image below. We have identified the pulse parameters to perform an X-gate operation on the qubit #2. Identify the correct option:
**Options**:
1. The same parameters can be applied to all the other qubits to perform X gate.
2. The X-gate calibration is layout sensitive and will only work on the nearest neighbor qubits, i.e. #1 and #3.
3. The pulse parameter for X-gate operation has to be calculated for each qubit individually.
4. None of the above


**Solution**:
In superconducting qubit systems (such as the one shown in the image), each qubit has its own specific resonant frequency due to slight variations in fabrication and design.

To perform an X-gate (or any other gate), the pulse must be carefully calibrated to match the resonant frequency of the target qubit. These parameters cannot be directly applied to other qubits because they will not respond correctly to pulses intended for a different frequency.

**Answer**:
The pulse parameter for X-gate operation has to be calculated for each qubit individually.
