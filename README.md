#  IBM Qiskit Hackathon — World of Quantum 2025  
📍Messe München, Germany  

This repository contains the code and methodology developed by team **Cycliq** for the Qiskit quantum computing Hackathon organized by IBM Quantum, at the [World of Quantum](https://world-of-quantum.com/en/) trade fair event (Messe München, June 24 to June 25, 2025).
The hackathon focussed on the development of custom [transpiler](https://docs.quantum.ibm.com/guides/transpile) pass routines that maps digital quantum circuits, to hardware specific physical circuits to be efficiently run on IBM hardware.
Team **Cycliq** was selected as a runner up in this event for our layout traspiler pass ACLM:

##  Project Title: Adaptive Cyclic Layout Map (ACLM)  
**A custom transpiler pass for hardware aware mapping of periodic [Two-Local Quantum circuits](https://docs.quantum.ibm.com/api/qiskit/qiskit.circuit.library.TwoLocal) to IBM Quantum computing backends**

##  Team Members  
- Quentin Ruiz  
- Rohan Srikumar  
- Kilian Teck  
- Dimitrios Diplaris  
- Kerem Yurtseven  
---

 ##  Code Organization
- `adaptive cyclic layout map.ipynb`: notebook introducing the algorithm and displaying its use case for general Two-Local periodic circuit, and a QAOA ansatz with a periodic Ising chain as the cost Hamiltonian.
- `benchmark.ipynb`: notebook compares the performance of ACLM (and approx ACLM) passes with respect to native transpiler passes, for different number of qubits and hardware backends.
- `find_best_cycle_with_error_minimization.ipynb`: notebook which take error mitigation of the backend, in case of the purpose algorithm find multiple cyclic sub-graph with the same length
- `SubmissionGroup4.ipynb`: combined notebook submitted for grading on 25/06/2025.
---
**Key Use Cases**

- Variational Quantum Eigensolver (VQE) with Circular Ansatz  
- Periodic Ising Model Simulations
- Quantum Approximate Optimization Algorithm (QAOA) implementations of:  
  - 1D periodic Ising chains  
  - Circular or nearest-neighbor graph structures  
  

**Computational Advantages**

- Utilizes available physical cycles when present  
- Optionally adds ancilla qubits to complete minimal-length cycles  
- Hardware-aware, reducing SWAP gate overhead and enhancing circuit fidelity  
- Generally outperforms default: 'trivial','dense' and 'sabre' layouts for such structured problems.

**Limitations**

- The ACLM algorithm does not outperform the state-of-the art VF2++ layout mapping algorithm. However, VF2++ is extremely costly for large circuits.
- The algorithm is only optimal for TwoLocal circuits and not optimal when multiqubit gates are introduced.


 
