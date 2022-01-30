# QuTech Challenges @ MIT iQuHACK 2022

<p align="left">
  <a href="https://qutech.nl" target="_blank"><img src="https://user-images.githubusercontent.com/10100490/151484481-7cedb7da-603e-43cc-890c-979fb66aeb60.png" width="25%" style="padding-right: 0%"/></a>
  <a href="https://iquhack.mit.edu/" target="_blank"><img src="https://user-images.githubusercontent.com/10100490/151647370-d161d5b5-119c-4db9-898e-cfb1745a8310.png" width="10%" style="padding-left: 0%"/> </a>
</p>


## Description 

For the 2022 edition of the iQuHack (interdisciplinary Quantum HACKathon), [QuTech](https://qutech.nl) has partnered with the team at MIT to propose 2 challenges, hosted in our own multi-hardware Quantum Technology platform, [Quantum Inspire](https://www.quantum-inspire.com). These aim to draw participants to the challenges at the heart of our mission: to develop scalable prototypes of a quantum computer and an inherently safe quantum internet, based on the fundamental laws of quantum mechanics.

To qualify for the QuTech Division Challenge, participants should submit a project that addresses either the proposed Quantum Error Correction (QEC) challenge or the Quantum Key Distribution (QKD) challenge. Detailed descriptions of these two challenges and their goals are available in the documents linked below (hosted in this repository):

- [Quantum Error Correction Challenge](https://github.com/iQuHACK/2022_qutech_challenge/blob/main/QuantumErrorCorrectionChallenge.pdf)


# Our Project

## Superdense Coding
Superdense Coding is a protocol that allows a messenger to send two classical bits of information by transferring only one qubit. 
This can be thought of as the flipside of quantum teleportation, which allows the sender to transfer the state of their qubit to the receiver by sending two classical bits of information. Superdense coding assumes that the sender and receiver share two qubits that are entangled with each other.

Let's say Alice wants to send two classical bits of information to Bob. There are four possible messages she can send: `00`, `01`, `10`, or `11`. Alice has one qubit, and Bob has another.

To start, the two of them meet up and entangle their qubits. This can be achieved by the following circuit:

![Entanglement Circuit](images/Entanglement.png)
                    
Next, Alice and Bob travel to different locations (their qubits are assumed to mainain an entangled state).

Alice can modify the Bell state by applying an X gate, a Z gate, or both. She can use these gates to encode the message she wants to send to Bob.

Once she does this, she sends her qubit to Bob. Bob performs a measurement in the Bell basis by executing the following circuit:

![Bell Basis Measurement](images/BellMeasurement.png)

The resulting output is the two-bit message that Alice was trying to send. Run the jupyter notebook to try it out!

### Error mitigation method
<div style="text-align: justify">We used a calibration method to reduce the effect of gate errors with the provided by the module Qiskit Ignis (deprecated). The method consists in getting the raw data in the form of a vector V and getting a calibration matrix A from it. essentially the solution to the problem:</div>

![image](https://user-images.githubusercontent.com/48070832/151705277-95e3b647-b8ad-47fe-acad-610fc9176d03.png)

 <div style="text-align: justify">We compute the calibration matrix on the device where we did the implementation and then use it to mitigate the measurement errors caused by the noisy nature of today's quantum hardware.</div>

- for details about the implementation refer to Superdense Coding.ipynb

## Summary of MIT IQuHack 2022
We learned a lot about error correction and had a lot of fun getting to know each other. However, we found that error correction is very difficult and were unable to develop a working error correction code. Overall, it was a good learning experience and we look forward to competing next year!

